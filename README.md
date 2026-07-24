# 🏛️ Software Engineering Residency

> **Framework Open-Source de Engenharia de Prompts, Protocolos Pedagógicos & Sincronização Notion/Git para Mentoria de System Design via LLMs**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![MCP Compatible](https://img.shields.io/badge/MCP-Notion%20%26%20GitHub%20Ready-purple.svg)](#-compatibilidade--modos-de-operação)
[![AI Mentor: Driver Mode](https://img.shields.io/badge/AI%20Mentor-Socratic%20Active%20Driver-brightgreen.svg)](#-passo-a-passo-de-configuração-setup-guide)

---

## 📌 O que é este projeto? (Visão Pragmática)

Este repositório **NÃO é um software web/SaaS tradicional** com backend, banco de dados proprietário ou tela de login.

Trata-se de um **Framework de Engenharia de Prompts Estruturada, Diretrizes Pedagógicas e Ementa de Conteúdo** desenhado para ser fornecido como instrução de sistema a grandes modelos de linguagem (LLMs como **Gemini, Claude 3.5, ChatGPT ou Antigravity CLI**).

O objetivo é transformar a IA de um "assistente passivo de respostas rápidas" em um **Mentor/Simulador Ativo de System Design (Driver Mode)**, que conduz o aluno por discussões arquiteturais socráticas sem entregar soluções prontas e grava o histórico de progresso no Notion e no Git.

---

## ⚙️ Compatibilidade & Modos de Operação

O framework foi projetado para rodar em 3 modalidades de ambiente:

| Modo de Operação | Ambientes Suportados | Requisitos | Recursos Disponíveis |
|---|---|---|---|
| **1. Modo Autônomo MCP (Recomendado)** | **Google Antigravity IDE**, **Cursor**, **VSCode Agent** | Servidores MCP ativos (`notion-mcp-server` / `github-mcp-server`) | Auto-provisionamento de tabelas no Notion, leitura de arquivos locais e atualização automática em tempo real. |
| **2. Modo Local Git / Agent CLI** | **Antigravity CLI**, **Aider**, **Claude Code** | Acesso ao sistema de arquivos local | Edição direta do arquivo `06-student-profile/STUDENT_JOURNEY.md` e commits automáticos. |
| **3. Modo Standalone Web (Manual)** | **ChatGPT Plus**, **Claude Web**, **Gemini Advanced** | Copiar e colar de texto | Mentoria socrática ativa. O log da aula é gerado em texto ao final para cópia manual. |

---

## 🚀 Passo a Passo de Configuração (Setup Guide)

Siga o roteiro abaixo para colocar o AI Mentor em operação no seu ambiente:

### Passo 1 — Obter os Arquivos
Clone o repositório Master para a sua máquina:
```bash
git clone https://github.com/alvarokaycss/software-engineering-residency.git
cd software-engineering-residency
```

---

### Passo 2 — Configurar as Conexões MCP (Opcional, para Automação Total)
Se você estiver utilizando um ambiente que suporta **MCP (Model Context Protocol)** como o Google Antigravity ou Cursor:

1. **Notion MCP Integration**:
   - Crie uma integração no Notion ([notion.so/my-integrations](https://www.notion.so/my-integrations)).
   - Compartilhe a página raiz do seu workspace com a integração criada (`AntiGravity Connection` ou equivalente).
   - Configure o `notion-mcp-server` no seu ambiente fornecendo o `NOTION_API_KEY`.
2. **GitHub MCP Integration** (Opcional):
   - Configure o `github-mcp-server` com um Personal Access Token (PAT) com escopo `repo`.

---

### Passo 3 — Carregar o System Prompt Mestre
1. Abra o arquivo [`system-prompt/AI_MENTOR_SYSTEM_PROMPT.md`](system-prompt/AI_MENTOR_SYSTEM_PROMPT.md).
2. Copie todo o conteúdo markdown do arquivo.
3. Cole como **System Prompt** ou primeira mensagem de contexto no chat do seu agente/LLM.

---

### Passo 4 — Inicializar a Sessão de Mentoria (Bootstrapping)
Digite a seguinte mensagem no chat para dar partida:
```text
Vamos iniciar.
```

O AI Mentor executará a seguinte sequência determinística de bootstrapping:
1. **Consulta de Memória**: Acessará o histórico do aluno em `06-student-profile/STUDENT_JOURNEY.md` ou lerá as tabelas do Notion (`NOTION_WORKSPACE_BLUEPRINT`).
2. **Auto-Provisionamento** (se estiver no Notion e as tabelas não existirem): Invocar os schemas para criar as tabelas `Sessions`, `Competency Framework`, `Skills Registry` e `Case Studies` automaticamente.
3. **Abertura da Aula em Driver Mode**: Apresentará o módulo atual da ementa (ex: *Módulo 1.1 — HTTP & Como Sistemas Funcionam em Escala*), a intuição de engenharia e os desafios socráticos de arquitetura.

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

- [x] **System Prompt Mestre (`system-prompt/AI_MENTOR_SYSTEM_PROMPT.md`)**: Prompt mestre com Runbook de Navegação em 5 passos.
- [x] **Notion Workspace Blueprint (`00-overview/NOTION_WORKSPACE_BLUEPRINT.md`)**: Protocolo de auto-provisionamento e schemas exatos para a API do Notion.
- [x] **20 Skills de Domínio (`01-ai-mentor/skills/`)**: Manuais de conduta comportamental e técnica (Skill 01 até Skill 20).
- [x] **5 Core Behavior Skills (`01-ai-mentor/core-skills/`)**: Problem Framing (001), Requirements Analysis (002), Capacity Estimation (003), Trade-off Analysis (004) e Architecture Decision Making (005).
- [x] **Ementa Curricular (`02-curriculum/`)**: Planejamento sequencial em 6 Módulos (Fundamentos, Dados, Escalabilidade, Distribuídos, Produção e Cases).
- [x] **Knowledge Base de Fundamentos (`03-knowledge-base/`)**: Guias para HTTP, Bancos de Dados, Caching e API Design.
- [x] **Estudo de Caso Guiado (`04-case-studies/`)**: Case prático do TinyURL (Encurtador de URLs).
- [x] **Matriz de Competências (`05-competency-framework/`)**: Critérios objetivos para avaliar maturidade em 4 Níveis.
- [x] **Gestão de Estado do Aluno (`06-student-profile/`)**: Template genérico para o diário de classe e log de sessões.

---

## 📂 Estrutura do Repositório

```text
software-engineering-residency/
├── README.md                            # Guia de apresentação, requisitos e setup
├── LICENSE                              # Licença MIT
├── system-prompt/
│   └── AI_MENTOR_SYSTEM_PROMPT.md      # Prompt Mestre com Runbook determinístico
├── 00-overview/
│   ├── RESIDENCY_OPERATING_SYSTEM.md    # Filosofia e modelo operacional da residência
│   └── NOTION_WORKSPACE_BLUEPRINT.md    # Schemas de dados e protocolo MCP para Notion
├── 01-ai-mentor/
│   ├── CONVERSATION_PROTOCOL.md         # Protocolo Driver Mode & 5 fases da sessão
│   ├── CORE_SKILLS_ROADMAP.md           # Roadmap das mentor skills
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
    └── STUDENT_JOURNEY.md               # Template genérico do perfil do aluno
```

---

## 📜 Licença

Este repositório é distribuído sob a licença [MIT](LICENSE). Sinta-se livre para clonar, adaptar e utilizar nos seus estudos de arquitetura de software.
