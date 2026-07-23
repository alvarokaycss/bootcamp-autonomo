# 🏛️ Software Engineering Residency

> **Um Framework Open-Source de Formação Técnica em Arquitetura de Sistemas & System Design Guiado por IA (~250 Horas)**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![AI Mentor: Driver Mode](https://img.shields.io/badge/AI%20Mentor-Socratic%20Active%20Driver-brightgreen.svg)](#-como-usar-o-ai-mentor)
[![Skills Core: 25 Implemented](https://img.shields.io/badge/Skills-25%20Implemented-purple.svg)](#-estrutura-do-repositório)

---

## 🎯 Sobre o Projeto

A **Software Engineering Residency** é uma formação avançada orientada a competências, tomada de decisão arquitetural e defesa técnica de engenharia.

Diferente de cursos tradicionais, bootcamps ou faculdades de TI (como ADS ou Ciência da Computação) que focam em ensinar apenas sintaxe de linguagens e frameworks passageiros, a residência foi desenhada para desenvolver capacidade de engenharia de nível pleno/sênior, respondendo a quatro perguntas fundamentais:

1. *"Por que essa arquitetura?"*
2. *"Quais alternativas existem e por que foram descartadas?"*
3. *"Quais são os custos e trade-offs dessa decisão?"*
4. *"Em qual ponto de carga essa solução deixa de funcionar?"*

Um **AI Mentor** (configurável em qualquer LLM avançado como Gemini, Claude ou ChatGPT) atua como um professor catedrático ativo (Driver Mode), guiando o aluno pela trilha de ~250h através do método socrático, sem entregar respostas prontas e registrando evidências contínuas de evolução.

---

## 📂 Estrutura Completa do Repositório

```text
software-engineering-residency/
├── README.md                            # Apresentação do projeto e guia de inicialização
├── LICENSE                              # Licença Open-Source MIT
├── system-prompt/
│   └── AI_MENTOR_SYSTEM_PROMPT.md      # Prompt Mestre para inicializar a IA em Driver Mode
├── 00-overview/
│   └── RESIDENCY_OPERATING_SYSTEM.md    # Sistema operacional, jornada de 5 fases e regras
├── 01-ai-mentor/
│   ├── CONVERSATION_PROTOCOL.md         # Protocolo Driver Mode & 5 fases da sessão
│   ├── CORE_SKILLS_ROADMAP.md           # Roadmap de especificações das mentor skills
│   ├── EVALUATION_AND_PROGRESSION_SYSTEM.md # Sistema de avaliação em 5 dimensões
│   ├── OPERATING_SYSTEM_CORE_PRINCIPLES.md # Princípios fundamentais de mentoria
│   ├── core-skills/                     # Skills Comportamentais do Mentor
│   │   ├── 001-problem-framing.md
│   │   ├── 002-requirements-analysis.md
│   │   ├── 003-capacity-estimation.md
│   │   ├── 004-trade-off-analysis.md
│   │   └── 005-architecture-decision-making.md
│   └── skills/                          # Skills de Domínio do Mentor (01 a 20)
│       ├── 01-mentor-identity.md
│       ├── 02-student-assessment.md
│       ├── 03-socratic-engineering-dialogue.md
│       ├── 04-knowledge-gap-detection.md
│       ├── 05-learning-path-management.md
│       ├── 06-competency-evaluation.md
│       ├── 07-evidence-based-progress-tracker.md
│       ├── 08-notion-knowledge-synchronization.md
│       ├── 09-technical-review-system.md
│       ├── 10-residency-feedback-loop.md
│       ├── 11-system-design-curriculum-engine.md
│       ├── 12-system-design-case-study-framework.md
│       ├── 13-architecture-decision-making.md
│       ├── 14-system-scalability-engineering-framework.md
│       ├── 15-reliability-fault-tolerance-framework.md
│       ├── 16-security-engineering-framework.md
│       ├── 17-distributed-systems-framework.md
│       ├── 18-data-architecture-framework.md
│       ├── 19-cloud-architecture-framework.md
│       └── 20-observability-sre-framework.md
├── 02-curriculum/
│   ├── CURRICULUM_ARCHITECTURE.md       # Estrutura modular da formação de 250h
│   └── DETAILED_MODULE_BREAKDOWN.md     # Módulos 1 a 6 detalhados hora por hora
├── 03-knowledge-base/
│   ├── TECHNICAL_SKILL_TEMPLATE.md      # Template oficial de competência técnica
│   ├── http-fundamentals.md             # Competência: HTTP & Networking
│   ├── database-fundamentals.md         # Competência: Bancos SQL vs NoSQL
│   ├── cache-fundamentals.md            # Competência: Estratégias de Caching & Invalidação
│   └── api-design.md                    # Competência: Design REST, Idempotência & Paginação
├── 04-case-studies/
│   └── url-shortener-tinyurl.md         # Case 1: Encurtador de URLs em Escala Planetária
├── 05-competency-framework/
│   └── COMPETENCY_MATRIX.md             # Matriz de 7 competências core (Níveis 1 ao 4)
└── 06-student-profile/
    └── STUDENT_JOURNEY.md               # Diário de classe, estado do aluno e log de sessões
```

---

## 🤖 Como Usar o AI Mentor

1. Copie o conteúdo do arquivo [`system-prompt/AI_MENTOR_SYSTEM_PROMPT.md`](system-prompt/AI_MENTOR_SYSTEM_PROMPT.md).
2. Cole como **System Prompt** ou primeira mensagem no seu LLM (ChatGPT / Claude / Gemini / Antigravity CLI / APIs).
3. (Opcional) Copie ou forneça o arquivo [`06-student-profile/STUDENT_JOURNEY.md`](06-student-profile/STUDENT_JOURNEY.md) para restaurar o estado das aulas anteriores.
4. Envie a mensagem inicial:
   ```text
   Vamos iniciar.
   ```
5. O Mentor assumirá **100% a liderança pedagógica (Driver Mode)**, informando o módulo atual, contextualizando a dor de engenharia, construindo a solução guiada e aplicando provocações socráticas.

---

## 🔄 Integração com o Notion

O repositório foi construído para operar de forma integrada com o Notion:
- A skill `08 — Notion Knowledge Synchronization` permite que o AI Mentor registre automaticamente eventos relevantes (gaps corrigidos, novas competências atingidas, ADRs produzidas e logs de sessões) no seu Dashboard do Notion via API.

---

## 📜 Licença

Este projeto é distribuído sob a licença [MIT](LICENSE). Sinta-se livre para utilizar, clonar, evoluir e compartilhar com a comunidade de engenharia de software.
