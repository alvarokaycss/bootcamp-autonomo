# 🏛️ Software Engineering Residency

> **Framework Open-Source de Engenharia de Prompts & Protocolos Pedagógicos para Mentoria de System Design via LLMs**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![MVP Status: Functional](https://img.shields.io/badge/MVP-Functional%20Prompt%20Engine-brightgreen.svg)](#-o-que-está-disponível-hoje-no-mvp)

---

## 📌 O que é este projeto? (Visão Pragmática)

Este repositório **NÃO é um software web/SaaS tradicional** com backend, banco de dados próprio ou telas de login.

Trata-se de um **Framework de Engenharia de Prompts Estruturada, Diretrizes Pedagógicas e Ementa de Conteúdo** desenhado para ser fornecido como instrução de sistema a grandes modelos de linguagem (LLMs como **Gemini, Claude 3.5, ChatGPT ou Antigravity CLI**).

O objetivo é transformar a IA de um "assistente passivo de respostas rápidas" em um **Mentor/Simulador Ativo de System Design (Driver Mode)**, que conduz o aluno por discussões arquiteturais socráticas sem entregar soluções prontas.

---

## 🎯 Qual problema ele resolve?

A maioria dos cursos, bootcamps e graduações de TI (como ADS ou Ciência da Computação) ensina a escrever sintaxe de código e usar frameworks do momento, mas **não ensina a pensar como um Arquiteto de Software**.

O AI Mentor simula sessões de mentoria e entrevistas técnicas focando em quatro perguntas:

1. *"Por que escolher essa arquitetura e não a alternativa X?"*
2. *"Quais são os trade-offs de latência, consistência e custo dessa decisão?"*
3. *"Quais estimativas de carga e volume justificam o uso desta ferramenta?"*
4. *"Em qual ponto de carga essa solução deixa de funcionar?"*

---

## ✅ O que está DISPONÍVEL HOJE no MVP?

Atualmente, o repositório entrega a estrutura completa de conduta e conteúdo:

- [x] **System Prompt Mestre (`system-prompt/AI_MENTOR_SYSTEM_PROMPT.md`)**: Prompt de instrução de sistema pronto para colar no seu LLM de preferência.
- [x] **20 Skills de Domínio (`01-ai-mentor/skills/`)**: Manuais de conduta comportamental e técnica (da Skill 01 — Mentor Identity até a Skill 20 — Observability & SRE).
- [x] **5 Core Behavior Skills (`01-ai-mentor/core-skills/`)**: Diretrizes para Problem Framing (001), Requirements Analysis (002), Capacity Estimation (003), Trade-off Analysis (004) e Architecture Decision Making (005).
- [x] **Ementa Curricular (`02-curriculum/`)**: Planejamento sequencial em 6 Módulos (Fundamentos, Dados, Escalabilidade, Distribuídos, Produção e Cases).
- [x] **Knowledge Base de Fundamentos (`03-knowledge-base/`)**: Guias de estudo para HTTP, Bancos de Dados (SQL vs NoSQL), Caching e API Design.
- [x] **Estudo de Caso Guiado (`04-case-studies/`)**: Case prático completo do TinyURL (Encurtador de URLs em Escala).
- [x] **Matriz de Competências (`05-competency-framework/`)**: Critérios objetivos para avaliar a maturidade técnica em 4 Níveis.
- [x] **Gestão de Estado do Aluno (`06-student-profile/`)**: Template para registrar o diário de classe, histórico de sessões e avanço no currículo.

---

## ⚠️ O que este repositório NÃO é (Limitações do MVP)

- **Não possui código executável em backend**: Toda a lógica de interação depende do motor de uma LLM externa.
- **Não grava vídeos ou aulas teóricas estáticas**: A dinâmica é 100% baseada em diálogo socrático e modelagem guiada.
- **Não valida compilação de código**: O foco é **arquitetura de sistemas, estimativas e trade-offs**, não sintaxe de linguagens.

---

## 📂 Estrutura do Repositório

```text
software-engineering-residency/
├── README.md                            # Este guia de apresentação e uso do MVP
├── LICENSE                              # Licença MIT
├── system-prompt/
│   └── AI_MENTOR_SYSTEM_PROMPT.md      # Prompt Mestre para configurar a LLM
├── 00-overview/
│   └── RESIDENCY_OPERATING_SYSTEM.md    # Filosofia e modelo operacional da residência
├── 01-ai-mentor/
│   ├── CONVERSATION_PROTOCOL.md         # Protocolo Driver Mode & 5 fases da sessão
│   ├── CORE_SKILLS_ROADMAP.md           # Roadmap de especificações das mentor skills
│   ├── EVALUATION_AND_PROGRESSION_SYSTEM.md # Sistema de avaliação por evidências
│   ├── OPERATING_SYSTEM_CORE_PRINCIPLES.md # Princípios fundamentais de mentoria
│   ├── core-skills/                     # Skills Comportamentais (001 a 005)
│   └── skills/                          # Skills de Domínio (01 a 20)
├── 02-curriculum/
│   ├── CURRICULUM_ARCHITECTURE.md       # Visão geral da trilha
│   └── DETAILED_MODULE_BREAKDOWN.md     # Módulos 1 a 6 detalhados
├── 03-knowledge-base/
│   ├── TECHNICAL_SKILL_TEMPLATE.md      # Template oficial de skill técnica
│   ├── http-fundamentals.md             # Fundamentos de HTTP & Networking
│   ├── database-fundamentals.md         # Fundamentos de Bancos de Dados
│   ├── cache-fundamentals.md            # Fundamentos de Caching & Invalidação
│   └── api-design.md                    # Design de APIs, Idempotência & Paginação
├── 04-case-studies/
│   └── url-shortener-tinyurl.md         # Case 1: Encurtador de URLs (TinyURL)
├── 05-competency-framework/
│   └── COMPETENCY_MATRIX.md             # Matriz de 7 competências core
└── 06-student-profile/
    └── STUDENT_JOURNEY.md               # Diário de classe e log de sessões do aluno
```

---

## 🚀 Como usar o MVP na prática

1. Abra o seu LLM de preferência (**Gemini Advanced, Claude 3.5 Sonnet, ChatGPT Plus ou Antigravity CLI**).
2. Copie o texto de [`system-prompt/AI_MENTOR_SYSTEM_PROMPT.md`](system-prompt/AI_MENTOR_SYSTEM_PROMPT.md).
3. Cole como **System Prompt** ou primeira mensagem no chat.
4. (Opcional) Cole o conteúdo de [`06-student-profile/STUDENT_JOURNEY.md`](06-student-profile/STUDENT_JOURNEY.md) para restaurar seu histórico de estudos.
5. Digite:
   ```text
   Vamos iniciar.
   ```
6. A IA assumirá a condução socrática, apresentando a aula do módulo atual e provocando decisões de engenharia.

---

## 📜 Licença

Este repositório é distribuído sob a licença [MIT](LICENSE). Sinta-se livre para clonar, adaptar e utilizar nos seus estudos de arquitetura de software.
