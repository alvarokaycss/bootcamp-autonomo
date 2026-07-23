# 🏛️ Software Engineering Residency

> **Um Framework Open-Source de Formação Técnica em Arquitetura de Sistemas & System Design Guiado por IA (~250 Horas)**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![AI Mentor: Ready](https://img.shields.io/badge/AI%20Mentor-Socratic%20Active%20Driver-brightgreen.svg)](#-como-usar-o-ai-mentor)

---

## 🎯 Sobre o Projeto

A **Software Engineering Residency** é uma formação avançada orientada a competências e tomada de decisão arquitetural. 

Diferente de cursos tradicionais, bootcamps ou faculdades de TI (como ADS ou Ciência da Computação) que focam em ensinar sintaxe de linguagens e frameworks passageiros, a residência foi desenhada para responder às quatro perguntas fundamentais de um Arquiteto de Software:

1. *"Por que essa arquitetura?"*
2. *"Quais alternativas existem e por que foram descartadas?"*
3. *"Quais são os custos e trade-offs dessa decisão?"*
4. *"Em qual ponto de carga essa solução deixa de funcionar?"*

Um **AI Mentor** (configurável em qualquer LLM como ChatGPT, Claude ou Gemini) atua como um professor catedrático ativo, guiando o aluno pela trilha de 250h através do método socrático, sem entregar respostas prontas.

---

## 📂 Estrutura do Repositório

```text
software-engineering-residency/
├── README.md                            # Apresentação do projeto e guia de uso
├── LICENSE                              # Licença Open-Source MIT
├── system-prompt/
│   └── AI_MENTOR_SYSTEM_PROMPT.md      # Prompt Mestre para inicializar a IA em modo ativo
├── 00-overview/
│   └── RESIDENCY_OPERATING_SYSTEM.md    # Sistema operacional e filosofia da residência
├── 01-ai-mentor/
│   ├── CONVERSATION_PROTOCOL.md         # Protocolo de condução ativa do mentor
│   ├── EVALUATION_SYSTEM.md             # Sistema de avaliação por evidências
│   └── SKILL_SPECIFICATION_TEMPLATE.md  # Template de especificação de novas mentor skills
├── 02-curriculum/
│   ├── DETAILED_MODULE_BREAKDOWN.md     # Trilha modular de 250 horas
│   └── LEARNING_DEPENDENCY_MAP.md       # Grafo de dependências pedagógicas
├── 03-knowledge-base/
│   ├── TEMPLATE_TECHNICAL_SKILL.md      # Template oficial de competência técnica
│   ├── http-fundamentals.md             # Competência: HTTP & Networking
│   ├── database-fundamentals.md         # Competência: Bancos SQL vs NoSQL
│   ├── cache-fundamentals.md            # Competência: Estratégias de Caching & Invalidação
│   └── api-design.md                    # Competência: Design REST, Idempotência & Paginação
├── 04-case-studies/
│   ├── TEMPLATE_CASE_STUDY.md           # Template oficial de estudo de caso
│   ├── CASE_STUDY_FRAMEWORK.md          # Metodologia de condução de cases
│   └── url-shortener-tinyurl.md         # Case 1: Encurtador de URLs (TinyURL) em Escala
├── 05-competency-framework/
│   └── COMPETENCY_MATRIX.md             # Matriz de competências (Níveis 1 ao 4)
└── 06-student-journey/
    └── STUDENT_PROGRESS_TRACKER_TEMPLATE.md # Template para o aluno acompanhar seu progresso
```

---

## 🤖 Como Usar o AI Mentor

1. Abra o seu LLM de preferência (ChatGPT Plus/Claude 3.5 Sonnet/Gemini Advanced).
2. Copie todo o conteúdo do arquivo [`system-prompt/AI_MENTOR_SYSTEM_PROMPT.md`](system-prompt/AI_MENTOR_SYSTEM_PROMPT.md).
3. Cole como **System Prompt** ou como a primeira mensagem no chat.
4. Envie o comando de inicialização:
   ```text
   Vamos iniciar.
   ```
5. O Mentor assumirá ativamente o controle da sessão, apresentando o módulo atual, a intuição de engenharia e os desafios socráticos de arquitetura.

---

## 📜 Licença

Este repositório é distribuído sob a licença [MIT](LICENSE). Sinta-se livre para usar, clonar, modificar e compartilhar.
