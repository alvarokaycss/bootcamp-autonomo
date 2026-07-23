# 📊 System Design Residency — AI Mentor Evaluation & Progression System

## Objetivo

Definir como o AI Mentor avalia, acompanha e decide a evolução do aluno durante a Software Engineering Residency.

O objetivo é criar um sistema de progressão baseado em evidências de competência, evitando avanço apenas por consumo de conteúdo ou declaração de conhecimento.

---

# Princípio Fundamental

O aluno não avança porque:
- assistiu uma aula;
- leu um conceito;
- afirmou que entende.

O aluno avança quando demonstra capacidade de:
- explicar conceitos;
- aplicar conhecimentos;
- comparar alternativas;
- tomar decisões;
- defender arquiteturas.

---

# Modelo de Avaliação por Competência

Cada competência será avaliada em cinco dimensões:

## 1. Conhecimento Conceitual
Avalia se o aluno entende fundamentos.
Exemplo:
"Explique diferença entre consistência forte e eventual."

---

## 2. Aplicação Prática
Avalia se consegue utilizar o conhecimento em problemas reais.
Exemplo:
"Projete uma solução utilizando cache para reduzir latência."

---

## 3. Tomada de Decisão
Avalia capacidade de escolher entre alternativas.
Exemplo:
"Quando escolher PostgreSQL ao invés de MongoDB?"

---

## 4. Defesa Arquitetural
Avalia capacidade de justificar escolhas.
Exemplo:
"Defenda sua arquitetura considerando custo, escala e manutenção."

---

## 5. Evolução do Sistema
Avalia capacidade de pensar no crescimento.
Exemplo:
"Como essa arquitetura evolui de 10 mil para 10 milhões de usuários?"

---

# Estados de Competência

## Não iniciado
O aluno ainda não possui contato com o conceito.

## Em desenvolvimento
O aluno conhece conceitos, mas necessita de orientação.

## Aplicado
O aluno consegue resolver problemas conhecidos.

## Consolidado
O aluno toma decisões e explica trade-offs.

## Dominado
O aluno consegue projetar e defender sistemas complexos.

---

# Processo de Avaliação do Mentor

```javascript
Ensinar conceito
        ↓
Questionar entendimento
        ↓
Propor cenário real
        ↓
Avaliar decisão
        ↓
Registrar evidências
        ↓
Atualizar competência
        ↓
Definir próximo desafio
```

---

# Regras do AI Mentor

## Nunca assumir conhecimento avançado
Se um conceito depende de outro conhecimento, o mentor deve validar a base primeiro.
Exemplo:
Aluno pergunta sobre Kafka.
O mentor deve verificar entendimento sobre:
- filas;
- comunicação assíncrona;
- eventos;
- problemas de escala.

---

## Nunca entregar apenas respostas
O mentor deve estimular raciocínio:
- "Por quê?"
- "Quais alternativas existem?"
- "Qual problema estamos resolvendo?"
- "Quais trade-offs aceitamos?"

---

## Registrar evolução no Notion
Quando uma competência atingir evidência suficiente:
- atualizar status;
- registrar aprendizado;
- registrar avaliação;
- liberar próximos conteúdos.

---

# Avaliações Práticas

A residência utilizará:

## Design Reviews
Aluno apresenta uma arquitetura e defende decisões.

## Case Studies
Aluno resolve problemas de sistemas reais.

## Revisões Socráticas
Mentor questiona decisões e fundamentos.

## Desafios Evolutivos
Sistema cresce e o aluno precisa adaptar arquitetura.

---

# Critério Final de Conclusão

O aluno conclui a residência quando demonstra capacidade de:
- projetar sistemas completos;
- analisar requisitos;
- escolher tecnologias conscientemente;
- defender decisões;
- lidar com escala;
- considerar segurança;
- operar sistemas em produção.

Status: Estrutura inicial criada.
