# 🧪 Software Engineering Residency (Experimento Prático)

> **Um projeto pessoal de testes para explorar integrações MCP, desenvolvimento de Skills em Markdown, automações Notion/GitHub e o comportamento de diferentes modelos de IA.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status: Experimental](https://img.shields.io/badge/Status-Experimental%20%2F%20Testes-orange.svg)](#-sobre-o-projeto)

---

## 📌 Sobre o Projeto

Este repositório é **apenas um projeto experimental e de aprendizado prático**. 

O objetivo **não** é criar um produto comercial ou um "framework revolucionário", mas sim **testar ferramentas e entender o funcionamento de novas tecnologias na prática**, explorando:

1. **Recursos de MCP (Model Context Protocol)**: Testes de servidores MCP do Notion (`notion-mcp-server`) e GitHub (`github-mcp-server`) para leitura e escrita automática via IA.
2. **Desenvolvimento de Skills**: Criação de manuais de conduta e instruções em arquivos Markdown para guiar o comportamento de LLMs.
3. **Comportamento em Diferentes Chats/Agentes**: Avaliação de como diferentes modelos (Gemini, Claude 3.5, ChatGPT, Antigravity CLI, Cursor) interpretam contextos e instruções complexas.
4. **Construção Intuitiva com IA**: Todo o conteúdo foi gerado e estruturado de forma intuitiva durante conversas e experimentações com agentes de Inteligência Artificial.

---

## 🛠️ O que foi testado neste repositório

- **Engenharia de Prompts (`system-prompt/`)**: Experimento com prompts mestres para forçar a IA a adotar uma postura ativa de mentoria socrática (*Driver Mode*).
- **Skills Comportamentais e Técnicas (`01-ai-mentor/`)**: Testes de escrita de especificações de comportamento em Markdown (Skills 01 a 20 e Core Skills 001 a 005).
- **Automação de Tabelas no Notion (`00-overview/NOTION_WORKSPACE_BLUEPRINT.md`)**: Blueprint de schemas para criação e atualização automática de tabelas via chamadas de API/MCP.
- **Ementa e Casos de Uso (`02-curriculum/` e `04-case-studies/`)**: Roteiros teóricos e o estudo de caso do TinyURL usados para testar a retenção de contexto da IA durante simulações de entrevista.

---

## ⚙️ Como os testes foram executados

### 1. Com Conexão MCP (Google Antigravity IDE / Cursor)
- Servidores MCP do Notion e GitHub conectados.
- A IA lê a estrutura local dos arquivos `.md`, realiza chamadas para criar tabelas no Notion e atualiza logs de teste em tempo real.

### 2. Standalone (ChatGPT / Claude Web / Gemini)
- Cópia do prompt mestre em `system-prompt/AI_MENTOR_SYSTEM_PROMPT.md` para testar a postura do modelo sem ferramentas externas ativas.

---

## 📂 Estrutura de Arquivos

```text
software-engineering-residency/
├── README.md                            # Registro sincero de experimentos
├── LICENSE                              # Licença MIT
├── system-prompt/
│   └── AI_MENTOR_SYSTEM_PROMPT.md      # Experimento de prompt mestre
├── 00-overview/
│   ├── RESIDENCY_OPERATING_SYSTEM.md    # Conceito operacional da residência
│   └── NOTION_WORKSPACE_BLUEPRINT.md    # Schemas de teste para API do Notion
├── 01-ai-mentor/
│   ├── CONVERSATION_PROTOCOL.md         # Experimento de protocolo de conversação
│   ├── core-skills/                     # Testes de skills comportamentais (001 a 005)
│   └── skills/                          # Testes de skills de domínio (01 a 20)
├── 02-curriculum/
│   ├── CURRICULUM_ARCHITECTURE.md       # Roteiro de tópicos de estudo
│   └── DETAILED_MODULE_BREAKDOWN.md     # Detalhamento de módulos de teste
├── 03-knowledge-base/
│   ├── http-fundamentals.md             # Guia de estudo: HTTP
│   ├── database-fundamentals.md         # Guia de estudo: Bancos de Dados
│   ├── cache-fundamentals.md            # Guia de estudo: Caching
│   └── api-design.md                    # Guia de estudo: API Design
├── 04-case-studies/
│   └── url-shortener-tinyurl.md         # Estudo de caso de teste: TinyURL
├── 05-competency-framework/
│   └── COMPETENCY_MATRIX.md             # Matriz de teste de níveis
└── 06-student-profile/
    └── STUDENT_JOURNEY.md               # Template de histórico de progresso
```

---

## 💬 Nota Sincera

Se você chegou até este repositório, sinta-se à vontade para explorar, clonar ou utilizar as ideias de MCP e Prompts nos seus próprios testes de IA!

---

## 📜 Licença

Distribuído sob a licença [MIT](LICENSE).
