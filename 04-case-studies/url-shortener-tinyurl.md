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
- [x] **FR-1**: Dado uma URL original longa, o sistema gera um alias encurtado exclusivo e curto (ex: `https://tiny.url/abc123X`).
- [x] **FR-2**: Quando o usuário acessa o link encurtado, o sistema o redireciona para a URL original com a menor latência possível.
- [x] **FR-3**: Opcionalmente, o usuário pode definir um alias customizado (ex: `https://tiny.url/minha-promo`).
- [x] **FR-4**: Os links encurtados possuem um tempo de expiração padrão configurável.

### Requisitos Não-Funcionais (NFR)
- [x] **NFR-1 (Alta Disponibilidade)**: 99.99% de uptime para a operação de redirecionamento (leitura).
- [x] **NFR-2 (Baixa Latência)**: Redirecionamento com latência $p99 < 20ms$.
- [x] **NFR-3 (Escala de Leitura vs Escrita)**: O sistema é fortemente orientado a leitura (Read-Heavy - $100:1$).
- [x] **NFR-4 (Segurança)**: Impedir brute-force / enumeração sequencial de URLs e aplicar Rate Limiting.

---

## 🧮 3. Estimativas de Capacidade (Back-of-the-envelope)
- **Novas URLs criadas**: 100 milhões por mês $\rightarrow \approx 40$ WPS (escritas por segundo). Pico: 80 WPS.
- **Redirecionamentos**: $4.000$ RPS (leituras por segundo). Pico: 8.000 RPS.
- **Armazenamento**: $\approx 535$ bytes por URL $\rightarrow 53,5$ GB/mês $\rightarrow 3,2$ TB em 5 anos.
- **Cache (Redis)**: Regra 80/20 $\rightarrow 37$ GB de RAM em Redis para cobrir 20% do tráfego diário.

---

## 🏗️ 4. Design Arquitetural & Decisões
- **HTTP Status**: Uso de `302 Found` para permitir rastreamento de métricas em tempo real por requisição.
- **Algoritmo de Hash**: Base62 ($62^7 \approx 3,5$ trilhões de combinações) + **KGS (Key Generation Service)** pré-gerando chaves em lote sem colisões.
- **Camada de Dados**: PostgreSQL / DynamoDB + Redis Cluster em estratégia *Cache-Aside*.
