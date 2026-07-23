# 🔗 Case Study — URL Shortener (TinyURL)

> **Estudo de Caso Prático Guiado da Software Engineering Residency**

---

## 🎯 1. Visão Geral do Caso
- **Nome do Sistema**: Encurtador de URLs em Escala Planetária (TinyURL / bit.ly)
- **Nível de Dificuldade**: `Iniciante / Intermediário`
- **Competências Requeridas**: `HTTP Fundamentals`, `Database Fundamentals`, `Cache Fundamentals`, `API Design`
- **Carga Horária Estimada**: `15h de estudo, projeto e defesa socrática com o AI Mentor`

---

## 📋 2. Requisitos do Sistema

### Requisitos Funcionais (FR)
- [x] **FR-1**: Dado uma URL original longa (ex: `https://example.com/very/long/path/123`), o sistema gera um alias encurtado exclusivo e curto (ex: `https://tiny.url/abc123X`).
- [x] **FR-2**: Quando o usuário acessa o link encurtado, o sistema o redireciona para a URL original com a menor latência possível.
- [x] **FR-3**: Opcionalmente, o usuário pode definir um alias customizado (ex: `https://tiny.url/minha-promo`).
- [x] **FR-4**: Os links encurtados possuem um tempo de expiração padrão configurável.

### Requisitos Não-Funcionais (NFR)
- [x] **NFR-1 (Alta Disponibilidade)**: 99.99% de uptime para a operação de redirecionamento (leitura).
- [x] **NFR-2 (Baixa Latência)**: Redirecionamento com latência \(p99 < 20ms\).
- [x] **NFR-3 (Escala de Leitura vs Escrita)**: O sistema é fortemente orientado a leitura (Read-Heavy), na proporção de 100 leituras para 1 escrita (\(100:1\)).
- [x] **NFR-4 (Segurança)**: Impedir brute-force / enumeração sequencial de URLs e prevenir abusos via Rate Limiting.

---

## 🧮 3. Estimativas de Capacidade (Back-of-the-envelope)

### Tráfego e RPS
- **Novas URLs criadas (Escritas)**: 100 milhões de URLs por mês.
- **Escritas por segundo (WPS)**:
  \[\frac{100.000.000}{30 \text{ dias} \times 86.400 \text{ seg}} \approx 40 \text{ URLs/seg (Média)}\]
  *Pico de Escrita (2x)*: \(\approx 80 \text{ WPS}\).
- **Redirecionamentos (Leituras - Ratio 100:1)**:
  \[40 \times 100 = 4.000 \text{ requisições/seg (RPS Médio)}\]
  *Pico de Leitura (2x)*: \(\approx 8.000 \text{ RPS}\).

### Armazenamento de Dados
- **Tamanho de cada registro no Banco de Dados**:
  - `short_hash` (Base62 - 7 chars): 7 bytes
  - `original_url`: 512 bytes (média)
  - `created_at` & `expires_at`: 16 bytes
  - **Total por registro**: \(\approx 535 \text{ bytes}\).
- **Armazenamento por mês**:
  \[100.000.000 \times 535 \text{ bytes} \approx 53,5 \text{ GB / mês}\]
- **Armazenamento em 5 anos**:
  \[53,5 \text{ GB} \times 12 \times 5 \approx 3,2 \text{ TB}\]

### Memória de Cache (Regra dos 80/20)
- 20% das URLs geram 80% do tráfego de leitura diário.
- **Leituras por day**: \(4.000 \text{ RPS} \times 86.400 \text{ seg} \approx 345 \text{ milhões de acessos/dia}\).
- **Cache para 20% das URLs acessadas no dia**:
  \[0,20 \times 345 \text{ milhões} \times 535 \text{ bytes} \approx 37 \text{ GB de RAM em Cache (Redis)}\]

---

## 🏗️ 4. Design Arquitetural (Evolutivo)

### Fase 1: API REST & Algoritmo de Hashing (Base62)
- **Verbo & Status Code de Redirecionamento**:
  - `HTTP 301 (Moved Permanently)`: O navegador faz cache agressivo do redirecionamento. Reduz carga nos nossos servidores, mas dificulta coleta de métricas de analytics.
  - `HTTP 302 (Found / Temporary)`: O navegador sempre consulta o encurtador antes de ir para o destino. Permite analytics em tempo real.
- **Geração do Hash de 7 Caracteres**:
  - Utilização do conjunto Base62 (`[a-z, A-Z, 0-9]`).
  - Capacidade total com 7 caracteres:
    \[62^7 \approx 3,5 \text{ trilhões de combinações únicas}\]
  - *Estratégia de Geração*:
    - **Opção A (MD5 / SHA-256 + Truncate)**: Risco de colisão. Exige checar no banco e resolver colisões.
    - **Opção B (KGS - Key Generation Service)**: Serviço separado que pré-gera chaves de 7 caracteres aleatórias e não repetidas em memória/banco. Desempenho \(O(1)\) sem colisões na inserção!

### Fase 2: Modelagem do Banco de Dados & Cache (Redis)
- **Tabela `urls` (PostgreSQL / DynamoDB)**:
```sql
CREATE TABLE urls (
    short_key VARCHAR(7) PRIMARY KEY,
    original_url TEXT NOT NULL,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP,
    expires_at TIMESTAMP WITH TIME ZONE
);
```
- **Camada de Cache (Redis Cluster - Cache-Aside Strategy)**:
  - Chave no Redis: `url:{short_key}` \(\rightarrow\) Valor: `original_url`.
  - Política de Evicção: `Volatile-LRU` com TTL padrão de 30 dias.

### Fase 3: Diagrama de Fluxo do Sistema
```javascript
[Cliente / Browser]
        │
        ▼ (HTTP GET /abc123X)
[Load Balancer (NGINX / ALB)]
        │
        ▼
[API Cluster (Stateless Nodes)]
        │
        ├──► 1. Busca no Redis Cache ──(HIT - <2ms)──► Retorna HTTP 302
        │
        └──► 2. (MISS) Busca no PostgreSQL/NoSQL
                   │
                   ├──► Salva no Redis
                   └──► Retorna HTTP 302
```

---

## 💥 5. Failure Modes & Resiliência
- **O que acontece se o Redis reiniciar?**: As APIs falharão temporariamente para o banco de dados primário (Cache Miss). Para evitar exaustão do banco, utiliza-se a técnica de *Singleflight / Mutex* na API para consolidar requisições concorrentes da mesma chave em uma única query ao banco.
- **Como prevenir abuso e varredura de URLs por robôs?**: Aplicação de *Rate Limiting* no API Gateway baseado no IP do cliente ou Token de API (ex: no máximo 10 encurtamentos por minuto por IP).

---

## 🛡️ 6. Defesa Arquitetural & Trade-offs Aceitos
- **Decisão**: Escolha do status `HTTP 302` ao invés de `HTTP 301`.
  - *Trade-off*: Aceitamos um custo ligeiramente maior de banda e CPU nos nossos servidores para garantir capacidade total de rastreamento de métricas e expiração imediata de links desativados.
- **Decisão**: Adoção do KGS (Key Generation Service) pré-gerando chaves em lote.
  - *Trade-off*: Adicionamos um componente na infraestrutura, mas eliminamos totalmente qualquer trava de concorrência ou cálculo de colisão no momento da escrita.

---

## 🤖 7. Protocolo de Arguição do AI Mentor
### 🎯 Como conduzir a sessão socrática com o aluno:
1. **Fase 1 (Estimativas)**: Peça para o aluno recalcular a memória de Cache se a razão de leitura passar de 100:1 para 1000:1.
2. **Fase 2 (Colisão & Hashing)**: Pergunte: *"Se gerarmos o hash truncando os primeiros 7 caracteres do MD5 da URL original, o que acontece se dois usuários encurtarem a mesma URL no mesmo segundo?"*
3. **Fase 3 (Redirecionamento)**: Questionar: *"Se o cliente reportar que mudou a URL de destino de um encurtamento, mas os usuários continuam sendo enviados para o destino antigo, qual cabeçalho HTTP foi usado e onde está o erro?"*
4. **Fase 4 (Escala de Banco)**: Desafiar o aluno a projetar o sharding do banco de dados quando o volume passar de 3 TB para 300 TB.
