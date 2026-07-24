# 👨‍🎓 Student Profile & Journey — Álvaro Kayc

> **Registro Oficial do Residente, Diagnóstico Inicial e Histórico de Sessões da Software Engineering Residency**

---

## 👤 Perfil do Residente

- **Nome**: Álvaro Kayc (`@alvarokaycss`)
- **Curso**: Análise e Desenvolvimento de Sistemas (ADS — 5º Semestre)
- **Repositório Oficial GitHub**: [alvarokaycss/software-engineering-residency](https://github.com/alvarokaycss/software-engineering-residency)
- **Ritmo de Estudo**: ~1 hora por sessão

---

## 🛠️ Stack Tecnológica & Experiência

- **Linguagens / Frameworks**: Node.js, TypeScript, React, Python (FastAPI), JavaScript Vanilla, HTML/CSS.
- **Bancos de Dados**: PostgreSQL, MongoDB.
- **Infraestrutura & Ferramentas**: Docker, Git/GitHub.
- **Experiência Prática**: Prototipagem e modelagem de BD (PostgreSQL), validações com Regex, CORS, Helmet e segurança web básica.

---

## 🎯 Objetivos de Aprendizado

1. Desenvolver visão arquitetural sólida em **System Design**.
2. Evoluir da codificação de features isoladas para tomada de decisões de engenharia baseadas em requisitos de escala, latência, concorrência e disponibilidade.
3. Registrar progresso sincronizado entre o Notion e o repositório GitHub `software-engineering-residency`.

---

## 📍 Status Atual da Trilha (250h)

- **Fase**: 🏛️ Módulo 1 — Fundamentos de Engenharia de Sistemas (30h)
- **Tópico Ativo**: Concluído Módulo 1.1 — Como Sistemas Funcionam em Escala
- **Próximo Tópico**: Módulo 1.2 — Requisitos Funcionais vs Não-Funcionais em Detalhe & SLA/SLO/SLI
- **Diagnóstico Inicial**: Concluído (Fase 1 & 2 do Operating System).

---

## 🧭 Estado Atual da Matriz de Competências

| # | Competência Core | Nível Atual (1-4) | Status | Data da Última Avaliação | Evidências / Observações |
|---|---|---|---|---|---|
| 1 | **Análise de Requisitos** | Nível 2 (Aplicação) | 🟢 Consolidado | 2026-07-23 | Diferenciou requisitos funcionais vs não-funcionais sob tráfego de alta volumetria. |
| 2 | **Decisão Arquitetural** | Nível 2 (Aplicação) | 🟢 Consolidado | 2026-07-23 | Defendeu uso de Redis Atomic Counters em RAM para proteger o PostgreSQL contra 100.000 requisições simultâneas. |
| 3 | **Arquitetura de Dados** | Nível 2 (Aplicação) | 🟢 Consolidado | 2026-07-23 | Identificou a dor de Connection Pool Exhaustion e lock de linha sob alta concorrência. |
| 4 | **Escalabilidade** | Nível 1 (Fundamentos) | 🟡 Em Progresso | 2026-07-23 | Entende utilidade de in-memory cache; a aprofundar no Módulo 3. |
| 5 | **Sistemas Distribuídos** | Nível 1 (Fundamentos) | 🔴 Não Iniciado | - | A iniciar no Módulo 4. |
| 6 | **Segurança** | Nível 1 (Fundamentos) | 🟡 Em Progresso | 2026-07-23 | Prática prévia com Helmet, CORS e sanitização básica. |
| 7 | **Operação & SRE** | Nível 1 (Fundamentos) | 🔴 Não Iniciado | - | A iniciar no Módulo 5. |

---

## 📝 Diário de Sessões & Avaliações (`Sessions Log`)

### 📅 Sessão 01 (23/07/2026) — Módulo 1.1: Concorrência, Latência & Arquitetura Redis + PostgreSQL
- **Data**: 2026-07-23 | **Duração**: 60min
- **Módulo / Tópico**: Módulo 1.1 — Como Sistemas Funcionam em Escala
- **Competências Abordadas**: `Database Fundamentals`, `Cache Fundamentals`, `Architecture Decision Making`, `Trade-offs`
- **Conceitos Abordados**:
  - Transição de Localhost para Produção sob tráfego de alta volumetria.
  - Requisitos Funcionais vs Não-Funcionais.
  - Tabela de latência de hardware, memória RAM e disco.
  - Mecânica de Race Conditions e Esgotamento de Conexões (Connection Pool Exhaustion).
  - Padrão de Arquitetura: In-Memory Atomic Counters com Redis para proteção do banco relacional.
- **Desafios Práticos**:
  1. Análise de 5.000 requisições simultâneas em sistema de cupons.
  2. Arquitetura de venda de 5.000 ingressos sob tráfego de 100.000 requisições simultâneas.
- **Avaliação do AI Mentor**: **Nota 10/10 na Análise Arquitetural!**
  - Identificou que o lock de linha no PostgreSQL sob 100.000 requisições transformaria o banco em uma "bomba relógio" consumindo CPU excessiva.
  - Defendeu corretamente o uso do Redis como camada de decisão rápida em memória RAM, filtrando requisições excedentes antes que toquem no banco principal.
- **Status do Módulo 1.1**: **CONCLUÍDO COM EXCELÊNCIA** 🎯
- **Próximo Passo**: Módulo 1.2 — Requisitos Funcionais vs Não-Funcionais em Detalhe & SLA/SLO/SLI.
