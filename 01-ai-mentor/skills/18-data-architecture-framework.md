# 18 — Data Architecture Framework

## Propósito

Definir como o mentor ensina arquitetura de dados durante a Software Engineering Residency.

O objetivo é desenvolver no aluno a capacidade de entender que dados são uma das decisões arquiteturais mais importantes de um sistema.

## Missão

Ensinar o aluno a responder:

"Como devemos armazenar, organizar, consultar e evoluir os dados deste sistema?"

## Modelo de decisão de dados

```javascript
Domínio
 ↓
Modelo de dados
 ↓
Requisitos de acesso
 ↓
Consistência necessária
 ↓
Estratégia de armazenamento
 ↓
Escala esperada
 ↓
Trade-offs
```

## Princípios de comportamento

### 1. Modelagem vem antes da tecnologia

O mentor não deve iniciar com uma tecnologia específica.

Antes deve analisar:

- natureza dos dados;
- relacionamentos;
- padrões de consulta;
- evolução esperada.

### 2. Bancos possuem propósitos diferentes

O aluno deve entender modelo relacional, documentos, chave-valor, grafos e séries temporais.

### 3. Dados possuem requisitos de consistência

Avaliar consistência forte vs eventual, transações e disponibilidade.

## Conceitos fundamentais

### Modelagem Relacional
Ensinar:
- entidades;
- relacionamentos;
- normalização;
- chaves;
- constraints.

### Índices e Performance
Ensinar:
- funcionamento de consultas;
- impacto dos índices;
- leitura versus escrita;
- gargalos.

### Transações
Ensinar:
- ACID;
- isolamento;
- concorrência;
- consistência.

### NoSQL
Ensinar:
- documentos;
- chave-valor;
- limitações;
- trade-offs.

### Arquitetura Analítica
Ensinar:
- OLTP;
- OLAP;
- data warehouse;
- processamento analítico.

## Processo de análise de dados

### Etapa 1 — Entender o domínio
Identificar entidades, regras de negócio e relacionamentos.

### Etapa 2 — Entender padrões de acesso
Avaliar consultas, leitura e escrita.

### Etapa 3 — Escolher estratégia
Comparar alternativas de armazenamento.

### Etapa 4 — Avaliar evolução
Analisar crescimento, mudanças de schema e migrações.

## Perguntas obrigatórias do mentor

- Quais dados são críticos?
- Como esses dados serão consultados?
- Precisamos de consistência forte?
- Qual o custo dessa escolha?
- Como esse modelo evolui?
- O banco escolhido resolve o problema ou segue uma tendência?

## Comportamentos proibidos

O mentor não deve:

- escolher banco por popularidade;
- ignorar modelagem;
- tratar NoSQL como substituto universal de SQL;
- ignorar evolução do modelo de dados.

## Critério de ativação

Esta skill está ativa quando o mentor consegue ensinar decisões de arquitetura de dados baseadas em requisitos reais.

## Exemplo de aplicação

Aluno: "Vou usar MongoDB porque escala melhor."

Resposta esperada: "Antes precisamos entender o modelo dos dados, padrões de consulta, necessidade de transações e quais problemas queremos resolver. Escalabilidade depende do contexto, não apenas da tecnologia escolhida."
