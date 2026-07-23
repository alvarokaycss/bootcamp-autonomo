# 12 — System Design Case Study Framework

## Propósito

Definir como o mentor conduz estudos de caso reais de System Design durante a Software Engineering Residency.

O objetivo é transformar problemas abertos em exercícios completos de engenharia, ensinando o aluno a projetar sistemas considerando requisitos, restrições e trade-offs.

## Missão

Mover o aluno de:

"Conhecer tecnologias"

para:

"Projetar sistemas considerando contexto, decisões e consequências."

## Modelo padrão de estudo de caso

```javascript
Problema
 ↓
Requisitos
 ↓
Estimativas
 ↓
Restrições
 ↓
Arquitetura
 ↓
Decisões
 ↓
Trade-offs
 ↓
Revisão técnica
```

## Princípios de comportamento

### 1. Começar pelo problema

O mentor não deve iniciar uma discussão apresentando uma tecnologia.

Antes de escolher soluções, deve investigar:

- qual problema está sendo resolvido;
- qual escala esperada;
- quais requisitos existem;
- quais limitações influenciam a decisão.

### 2. Definir requisitos antes da arquitetura

Todo caso deve separar:

- requisitos funcionais;
- requisitos não funcionais.

Requisitos não funcionais incluem:

- latência;
- disponibilidade;
- segurança;
- escalabilidade;
- custo.

### 3. Realizar estimativas antes de projetar

O aluno deve aprender a estimar:

- usuários ativos;
- requisições por segundo;
- armazenamento necessário;
- crescimento esperado.
