# 🏛️ Software Engineering Bootcamp

> **Um Framework Open-Source de Engenharia de Prompts, Protocolos Pedagógicos & Sincronização Notion/Git para Mentoria de System Design via IA (~250h)**
> 
> *Desenvolvido como um experimento prático explorando recursos de MCP (Model Context Protocol), automações de repositório e o comportamento de diferentes modelos de Inteligência Artificial.*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![MCP Ready](https://img.shields.io/badge/MCP-Notion%20%26%20GitHub-purple.svg)](#-compatibilidade--modos-de-operação)
[![AI Mentor: Driver Mode](https://img.shields.io/badge/AI%20Mentor-Socratic%20Driver%20Mode-brightgreen.svg)](#-passo-a-passo-de-configuração-setup-guide)

---

## 🧪 Contexto & Propósito do Experimento

Este projeto nasceu de forma **intuitiva e experimental**, motivado pelo interesse de testar e validar na prática:

1. **Protocolo MCP (Model Context Protocol)**: Testar integrações de agentes de IA com o Notion (`notion-mcp-server`) e GitHub (`github-mcp-server`) para leitura de contexto, criação de tabelas e versionamento automático.
2. **Desenvolvimento de Skills em Markdown**: Avaliar como diretrizes comportamentais escritas em arquivos `.md` podem moldar o raciocínio de LLMs sem a necessidade de ajuste fino (fine-tuning).
3. **Comportamento Multimodelo**: Analisar o desempenho de diferentes plataformas e modelos de IA (Gemini, Claude 3.5, ChatGPT, Google Antigravity IDE, Cursor e CLI) ao interpretar contextos complexos.

Embora tenha surgido como um ambiente de testes de ferramentas, o resultado foi a estruturação de um **framework funcional e completo de mentoria em Arquitetura de Sistemas**, que está totalmente disponível para quem desejar testar, utilizar ou evoluir.

---

## 🎯 O que é o Framework? (Proposta Pedagógica)

A **Software Engineering Residency** é uma ementa e conjunto de diretrizes pedagógicas para transformar modelos de IA de "assistentes passivos que fornecem respostas prontas" em um **Mentor/Simulador Ativo de System Design (Driver Mode)**.

O framework aborda as lacunas comuns em graduações e bootcamps tradicionais, treinando a capacidade de tomada de decisão técnica a partir de quatro perguntas fundamentais:

1. *"Por que escolher essa arquitetura e não a alternativa X?"*
2. *"Quais são os trade-offs de latência, consistência e custo dessa decisão?"*
3. *"Quais estimativas de carga e volume justificam o uso desta ferramenta?"*
4. *"Em qual ponto de carga essa solução deixa de funcionar?"*

---

## ⚙️ Compatibilidade & Modos de Operação

O framework pode ser executado em três modalidades:

| Modo de Operação | Ambientes Suportados | Requisitos | Recursos Disponíveis |
|---|---|---|---|
| **1. Modo Autônomo MCP (Recomendado)** | **Google Antigravity IDE**, **Cursor**, **VSCode Agent** | Servidores MCP ativos (`notion-mcp-server` / `github-mcp-server`) | Auto-provisionamento de tabelas no Notion, leitura de arquivos locais e sincronização em tempo real. |
| **2. Modo Local Git / Agent CLI** | **Antigravity CLI**, **Aider**, **Claude Code** | Acesso ao sistema de arquivos local | Edição direta do arquivo `06-student-profile/STUDENT_JOURNEY.md` e commits automáticos. |
| **3. Modo Standalone Web (Manual)** | **ChatGPT Plus**, **Claude Web**, **Gemini Advanced** | Copiar e colar texto | Mentoria socrática ativa. O log da sessão é gerado em formato texto ao final para cópia manual. |

---

## 🚀 Passo a Passo de Configuração (Setup Guide)

Se você deseja testar o framework no seu ambiente, siga este tutorial:

### 1. Clonar o Repositório
```bash
git clone https://github.com/alvarokaycss/software-engineering-residency.git
cd software-engineering-residency
```

---

### 2. Configurar as Conexões MCP (Opcional — Para Automação Total)
Para habilitar o auto-provisionamento no Notion e commits automáticos:
- **Notion MCP**: Crie uma integração no Notion ([notion.so/my-integrations](https://www.notion.so/my-integrations)), compartilhe a página raiz do seu workspace com a integração e forneça a `NOTION_API_KEY` ao `notion-mcp-server`.
- **GitHub MCP**: Configurar o `github-mcp-server` com um Personal Access Token (PAT) com permissão de escrita em repositórios.

---

### 3. Carregar o System Prompt Mestre
- Copie o conteúdo de [`system-prompt/AI_MENTOR_SYSTEM_PROMPT.md`](system-prompt/AI_MENTOR_SYSTEM_PROMPT.md).
- Cole como **System Prompt** ou primeira mensagem de instrução no seu LLM/Agente.

---

### 4. Inicializar a Sessão de Mentoria (Bootstrapping)
Envie a mensagem no chat:
```text
Vamos iniciar.
```

O AI Mentor executará a seguinte sequência:
1. **Consulta de Memória**: Lê o histórico do aluno em `06-student-profile/STUDENT_JOURNEY.md` ou consulta a tabela `📝 Sessions` no Notion.
2. **Auto-Provisionamento** (se estiver via MCP no Notion): Invoca o [`NOTION_WORKSPACE_BLUEPRINT.md`](00-overview/NOTION_WORKSPACE_BLUEPRINT.md) para criar as tabelas ausentes automaticamente.
3. **Abertura da Aula em Driver Mode**: Apresenta o módulo ativo da ementa (ex: *Módulo 1.1 — HTTP & Como Sistemas Funcionam em Escala*), contextualiza a dor de engenharia e inicia as provocações socráticas.

---

## 📂 Estrutura Completa do Repositório

```text
software-engineering-residency/
├── README.md                            # Guia completo do projeto, setup e experimentos
├── LICENSE                              # Licença MIT
├── system-prompt/
│   └── AI_MENTOR_SYSTEM_PROMPT.md      # Prompt Mestre com Runbook determinístico de navegação
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
│   ├── CURRICULUM_ARCHITECTURE.md       # Visão geral da trilha de 250h
│   └── DETAILED_MODULE_BREAKDOWN.md     # Módulos 1 a 6 detalhados
├── 03-knowledge-base/
│   ├── TECHNICAL_SKILL_TEMPLATE.md      # Template oficial de skill técnica
│   ├── http-fundamentals.md             # Guia de estudo: HTTP & Networking
│   ├── database-fundamentals.md         # Guia de estudo: Bancos de Dados (SQL vs NoSQL)
│   ├── cache-fundamentals.md            # Guia de estudo: Caching & Invalidação
│   └── api-design.md                    # Guia de estudo: Design de APIs, Idempotência & Paginação
├── 04-case-studies/
│   └── url-shortener-tinyurl.md         # Estudo de caso guiado: TinyURL (Encurtador de URLs)
├── 05-competency-framework/
│   └── COMPETENCY_MATRIX.md             # Matriz de 7 competências core (Níveis 1 ao 4)
└── 06-student-profile/
    └── STUDENT_JOURNEY.md               # Template genérico do diário de classe e log de sessões
```

---

## 💬 Nota do Autor

Este projeto une **experimentação tecnológica** (testando o protocolo MCP e limites das LLMs) com uma **abordagem pragmática de aprendizado de System Design**. Sinta-se totalmente à vontade para clonar, testar no seu ambiente ou usar como inspiração para os seus próprios experimentos com Inteligência Artificial!

---

## 📜 Licença

Distribuído sob a licença [MIT](LICENSE).
