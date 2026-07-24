# 🏛️ Notion Workspace Blueprint & Provisioning Protocol

> **Manual de Arquitetura de Dados, Schemas de Tabelas e Algoritmo de Auto-Provisionamento do Notion para o AI Mentor**

---

## 🎯 Propósito

Este documento estabelece o **contrato exato de arquitetura de dados no Notion** utilizado pela Software Engineering Residency.

Ele serve de guia tanto para a IA (auto-provisionamento e sincronização contínua) quanto para o aluno (organização visual do workspace), garantindo que o AI Mentor saiba exatamente **quais tabelas existem, quais propriedades atualizar e como ler/gravar o histórico do aluno sem erros de esquema**.

---

## 🗄️ Estrutura das 4 Bases de Dados Essenciais

### 1. 📝 Base de Dados: `Sessions`
Guarda o histórico detalhado de todas as sessões de mentoria socrática.

| Propriedade | Tipo no Notion | Descrição / Valores Aceitos |
|---|---|---|
| **Sessão** | `title` | Título da aula (ex: *"001 — Fundamentos de HTTP & Stateless"*). |
| **Módulo** | `rich_text` | Código e nome do módulo (ex: *"Módulo 1.1"*). |
| **Data** | `date` | Data e hora da realização da sessão. |
| **Duração** | `number` | Tempo em minutos (ex: `60`). |
| **Competências** | `multi_select` | Competências abordadas (ex: `[HTTP, REST, Caching, Trade-offs]`). |
| **Resumo** | `rich_text` | Síntese do que foi ensinado e modelado na aula. |
| **Dúvidas / Gaps** | `rich_text` | Lacunas técnicas identificadas durante a arguição. |
| **Próximo Passo** | `rich_text` | Tema e objetivo da próxima sessão agendada. |

---

### 2. 📊 Base de Dados: `Competency Framework`
Mapeia o estado atual de maturidade técnica do aluno em cada competência core.

| Propriedade | Tipo no Notion | Descrição / Valores Aceitos |
|---|---|---|
| **Competência** | `title` | Nome da competência (ex: *"Database Fundamentals"*). |
| **Nível Atual** | `select` | `Nível 1 — Fundamentos` \| `Nível 2 — Aplicação` \| `Nível 3 — Decisão` \| `Nível 4 — Arquitetura`. |
| **Status** | `select` | `🔴 Não Iniciado` \| `🟡 Em Desenvolvimento` \| `🟢 Consolidado` \| `🏆 Dominado`. |
| **Última Evidência** | `rich_text` | Trecho/citação do aluno comprovando defesa técnica. |
| **Módulo Relacionado** | `rich_text` | Módulo associado da ementa (ex: *"Módulo 2 — Arquitetura de Dados"*). |
| **Data Atualização** | `date` | Data da última alteração de nível. |

---

### 3. 🧠 Base de Dados: `AI Mentor Skills Registry`
Cadastra todas as 20 skills comportamentais e pedagógicas do mentor.

| Propriedade | Tipo no Notion | Descrição / Valores Aceitos |
|---|---|---|
| **Skill** | `title` | Nome da skill (ex: *"01 — Mentor Identity"*). |
| **Categoria** | `select` | `Core Mentor` \| `Pedagógica` \| `Técnica`. |
| **Status** | `select` | `Planejada` \| `Em Desenvolvimento` \| `Implementada`. |
| **Objetivo** | `rich_text` | Síntese do propósito da skill. |
| **Responsabilidade** | `rich_text` | Atribuição pedagógica da IA sob essa skill. |
| **Critérios de Avaliação** | `rich_text` | Como a IA sabe que a skill foi aplicada com sucesso. |

---

### 4. 🎯 Base de Dados: `Case Studies`
Histórico de projetos práticos e defesa de arquiteturas de sistemas reais.

| Propriedade | Tipo no Notion | Descrição / Valores Aceitos |
|---|---|---|
| **Caso** | `title` | Nome do sistema (ex: *"TinyURL / Encurtador de URLs"*). |
| **Dificuldade** | `select` | `Iniciante` \| `Intermediário` \| `Avançado`. |
| **Competências Requeridas** | `multi_select` | Ex: `[HTTP, Database, Cache, API Design]`. |
| **Status Aluno** | `select` | `🔴 Não Iniciado` \| `🟡 Em Projeto` \| `🟢 Defendido`. |
| **Decisões Aceitas** | `rich_text` | Principais escolhas técnicas e ADRs registradas. |

---

## 🤖 Algoritmo de Auto-Provisionamento do AI Mentor

Quando o AI Mentor é inicializado em um workspace do Notion, ele segue o algoritmo abaixo:

```javascript
Fase 1: Diagnóstico de Infraestrutura
    │
    ├──► 1.1 Executa chamada de busca no Notion (API-post-search)
    │
    ├──► 1.2 As 4 bases (Sessions, Competencies, Skills, Cases) existem?
    │       ├── SIM ──► Armazena os IDs e carrega o histórico do aluno.
    │       └── NÃO ──► Transiciona para a Fase 2 (Auto-Provisionamento).

Fase 2: Auto-Provisionamento (Criação de Tabelas)
    │
    ├──► 2.1 Invoca `API-create-a-database` para cada tabela ausente usando os schemas deste Blueprint.
    ├──► 2.2 Cria a página "🏠 Dashboard" e vincula os bancos criados.
    └──► 2.3 Notifica o aluno: "Workspace do Notion provisionado com sucesso!".

Fase 3: Operação Contínua
    │
    └──► A cada fim de aula, atualiza `Sessions` e `Competency Framework` via API.
```

---

## 📝 Payloads da API do Notion para Sincronização

### Exemplo de Payload para Criar Registro na Tabela `Sessions`:

```json
{
  "parent": { "database_id": "<SESSIONS_DATABASE_ID>" },
  "properties": {
    "Sessão": {
      "title": [{ "text": { "content": "001 — Fundamentos de HTTP & Stateless" } }]
    },
    "Módulo": {
      "rich_text": [{ "text": { "content": "Módulo 1.1" } }]
    },
    "Data": {
      "date": { "start": "2026-07-23" }
    },
    "Duração": {
      "number": 60
    },
    "Competências": {
      "multi_select": [{ "name": "HTTP" }, { "name": "APIs" }]
    },
    "Resumo": {
      "rich_text": [{ "text": { "content": "Modelagem da camada HTTP, discussão sobre idempotência e status codes." } }]
    },
    "Dúvidas / Gaps": {
      "rich_text": [{ "text": { "content": "Dificuldade inicial em diferenciar HTTP 301 (Cache de Browser) de 302." } }]
    },
    "Próximo Passo": {
      "rich_text": [{ "text": { "content": "Módulo 1.2 — Estimativas de Capacidade (Back-of-the-envelope)." } }]
    }
  }
}
```

---

## 📌 Garantia de Consistência

Este Blueprint garante que **qualquer LLM conectada ao Notion (ou operando via arquivos locais)** saiba exatamente a estrutura de dados a ser lida e gravada, mantendo o histórico de progresso do aluno 100% preservado e rastreável.
