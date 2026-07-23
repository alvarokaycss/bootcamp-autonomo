# 🧩 System Design Residency — Detailed Module Breakdown (250h)

## Objetivo

Transformar a arquitetura curricular da residência em módulos, aulas, práticas e avaliações, criando uma formação equivalente a uma disciplina avançada de System Design.

A organização deve garantir progressão gradual, aplicação prática e desenvolvimento de capacidade arquitetural.

---

# Módulo 1 — Fundamentos de Engenharia de Sistemas (30h)

## Objetivo
Ensinar o aluno a analisar problemas antes de escolher tecnologias.

## Conteúdos

### 1.1 Como sistemas funcionam
- cliente-servidor;
- HTTP;
- APIs;
- comunicação entre componentes.

### 1.2 Requisitos de sistemas
- requisitos funcionais;
- requisitos não funcionais;
- disponibilidade;
- latência;
- escala.

### 1.3 Estimativas de capacidade
- usuários;
- requisições por segundo;
- armazenamento;
- crescimento.

### Avaliação
Mini system design: projetar uma API escalável considerando requisitos.

---

# Módulo 2 — Arquitetura de Dados (40h)

## Objetivo
Ensinar decisões relacionadas ao armazenamento e acesso aos dados.

## Conteúdos

### 2.1 Modelagem de dados
- entidades;
- relacionamentos;
- normalização.

### 2.2 Bancos relacionais
- PostgreSQL;
- índices;
- queries;
- transações.

### 2.3 Cache e armazenamento rápido
- Redis;
- estratégias de cache;
- invalidação.

### 2.4 NoSQL
- MongoDB;
- documentos;
- trade-offs.

### Avaliação
Escolher arquitetura de dados para um sistema real e defender decisão.

---

# Módulo 3 — Escalabilidade e Performance (45h)

## Objetivo
Ensinar evolução de sistemas sob crescimento.

## Conteúdos
- caching;
- load balancing;
- filas;
- processamento assíncrono;
- particionamento;
- otimização.

## Avaliação
Evoluir uma arquitetura de milhares para milhões de usuários.

---

# Módulo 4 — Sistemas Distribuídos (50h)

## Objetivo
Ensinar comportamento de sistemas com múltiplos componentes.

## Conteúdos
- CAP theorem;
- replicação;
- consistência;
- eventos;
- comunicação distribuída;
- microsserviços.

## Avaliação
Projetar sistema distribuído e justificar decisões.

---

# Módulo 5 — Sistemas de Produção (45h)

## Objetivo
Ensinar engenharia de sistemas operados em escala.

## Conteúdos
- cloud architecture;
- segurança;
- observabilidade;
- SRE;
- incident response.

## Avaliação
Análise de arquitetura em produção e plano de operação.

---

# Módulo 6 — System Design Case Studies (40h)

## Objetivo
Aplicar conhecimento em problemas próximos da realidade.

## Casos
- construir WhatsApp;
- construir Netflix;
- construir Uber;
- construir YouTube;
- sistemas financeiros;
- marketplaces.

## Método
Cada caso seguirá:

```javascript
Requisitos
 ↓
Estimativas
 ↓
Arquitetura inicial
 ↓
Escala
 ↓
Falhas
 ↓
Trade-offs
 ↓
Defesa final
```

---

# Distribuição Total

| Módulo | Horas |
|---|---|
| Fundamentos | 30h |
| Dados | 40h |
| Escalabilidade | 45h |
| Distribuídos | 50h |
| Produção | 45h |
| Cases | 40h |
| **Total** | **250h** |

---

# Regra Pedagógica

Nenhum módulo deve ser tratado como coleção de ferramentas.
O foco sempre será:
Problema → Contexto → Alternativas → Decisão → Trade-offs → Evolução.

Status: Estrutura inicial criada.
