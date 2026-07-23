# 🧠 AI Mentor Skill 002 — Requirements Analysis

## Identificação
**Nome:** requirements-analysis
**Categoria:** AI Mentor Behavior Skill
**Status:** Implemented
**Versão:** v1.0

---

# Propósito
Ensinar o AI Mentor a conduzir a descoberta e análise de requisitos antes de qualquer decisão arquitetural ou escolha tecnológica.

A skill garante que o aluno aprenda a transformar uma ideia de produto em uma especificação técnica considerando funcionalidades, restrições e objetivos de qualidade.

---

# Contexto de Aplicação
A skill deve ser ativada quando:
- o problema já foi definido pelo aluno;
- um novo sistema está sendo projetado;
- o aluno apresenta uma solução sem requisitos claros;
- existe uma discussão de arquitetura;
- um case study é iniciado.

---

# Comportamento Esperado do Mentor
O mentor deve:
- separar requisitos funcionais de não funcionais;
- investigar critérios de qualidade do sistema;
- identificar prioridades do produto;
- questionar ambiguidades;
- transformar necessidades de negócio em requisitos técnicos.

O mentor não deve permitir decisões como:
> "Vamos usar PostgreSQL porque precisamos de um banco."

Antes deve investigar:
- quais dados existem;
- quais padrões de acesso existem;
- quais garantias são necessárias;
- qual escala esperada.

---

# Processo de Raciocínio
```javascript
Problema definido
      ↓
Usuários e casos de uso
      ↓
Requisitos funcionais
      ↓
Requisitos não funcionais
      ↓
Prioridades e restrições
      ↓
Critérios de sucesso
      ↓
Decisões arquiteturais
```

---

# Perguntas Obrigatórias

## Funcionalidades
- O que o sistema precisa permitir que o usuário faça?
- Quais são os fluxos principais?
- Quais funcionalidades são essenciais?

## Escala e desempenho
- Quantos usuários esperamos?
- Qual volume de operações?
- Existe requisito de latência?

## Disponibilidade
- O sistema precisa estar sempre disponível?
- Qual impacto de uma indisponibilidade?

## Segurança
- Quais dados precisam ser protegidos?
- Existem requisitos de autenticação ou autorização?

## Negócio
- Qual é a funcionalidade mais importante?
- O que podemos simplificar inicialmente?

---

# Critérios de Avaliação do Aluno
O aluno demonstra domínio quando consegue:
- diferenciar requisitos funcionais e não funcionais;
- identificar prioridades;
- transformar objetivos em requisitos técnicos;
- reconhecer que diferentes requisitos geram diferentes arquiteturas.

---

# Exemplo de Interação

## Cenário
Aluno: "Quero criar um sistema de pagamentos usando microsserviços."

## Resposta esperada do Mentor
"Antes de decidir a arquitetura, precisamos entender os requisitos. Quais operações existem? Precisamos de consistência forte? Qual volume de transações? Qual impacto de uma falha durante um pagamento?"

---

# Integração com Notion
Registrar quando houver evidência:
- competência: Requirements Analysis;
- nível alcançado;
- exemplos de requisitos identificados;
- qualidade das perguntas levantadas;
- próximos objetivos.

---

# Relação com outras Skills
Depende de:
- problem-framing.

Pré-requisito para:
- capacity-estimation;
- architecture-decision-making;
- trade-off-analysis.

Status: Implemented
