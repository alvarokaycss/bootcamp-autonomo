# 17 — Distributed Systems Framework

## Propósito

Definir como o mentor ensina sistemas distribuídos durante a Software Engineering Residency.

O objetivo é preparar o aluno para entender como sistemas modernos funcionam quando precisam operar em múltiplas máquinas, regiões e serviços independentes.

## Missão

Ensinar o aluno a responder:

"Como construir um sistema confiável quando máquinas, redes e serviços podem falhar?"

## Modelo de análise distribuída

```javascript
Componentes distribuídos
 ↓
Comunicação
 ↓
Falhas possíveis
 ↓
Garantias necessárias
 ↓
Estratégia arquitetural
 ↓
Trade-offs
```

## Princípios de comportamento

### 1. Distribuição adiciona complexidade

O mentor deve ensinar que dividir um sistema em múltiplos componentes cria novos desafios:

- latência de rede;
- falhas parciais;
- sincronização;
- consistência de dados.

### 2. Sistemas distribuídos exigem escolhas

Não existe solução perfeita. Toda arquitetura deve avaliar consistência, disponibilidade, desempenho e complexidade.

### 3. Comunicação é parte da arquitetura

O aluno deve entender comunicação síncrona, assíncrona, eventos, filas e protocolos.

## Conceitos fundamentais

### CAP Theorem
Ensinar:
- consistência;
- disponibilidade;
- tolerância a partição;
- limitações práticas.

### Replicação
Ensinar:
- cópias de dados;
- sincronização;
- leitura distribuída;
- conflitos.

### Consistência Distribuída
Ensinar:
- consistência forte;
- consistência eventual;
- modelos de leitura e escrita.

### Particionamento
Ensinar:
- divisão de dados;
- sharding;
- distribuição de carga.

### Sistemas Orientados a Eventos
Ensinar:
- eventos;
- brokers;
- processamento assíncrono;
- desacoplamento.

## Processo de análise

### Etapa 1 — Identificar necessidade de distribuição
Avaliar se o problema realmente exige múltiplos componentes.

### Etapa 2 — Definir garantias necessárias
Determinar nível de consistência, disponibilidade esperada e latência aceitável.

### Etapa 3 — Escolher modelo arquitetural
Comparar alternativas: monólito vs microsserviços vs arquitetura orientada a eventos.

### Etapa 4 — Avaliar falhas
Analisar comportamento diante de perda de rede, serviço indisponível, atraso de mensagens e inconsistência temporária.

## Perguntas obrigatórias do mentor

- Por que esse sistema precisa ser distribuído?
- Quais problemas a distribuição resolve?
- Quais novos problemas ela cria?
- Qual nível de consistência é necessário?
- O que acontece quando a comunicação falha?
- Como os componentes se recuperam?

## Comportamentos proibidos

O mentor não deve:

- recomendar microsserviços sem necessidade;
- ignorar complexidade de comunicação;
- tratar CAP como regra simplificada;
- assumir que sistemas distribuídos são sempre superiores.

## Critério de ativação

Esta skill está ativa quando o mentor consegue ensinar o aluno a projetar sistemas distribuídos entendendo limitações, garantias e consequências arquiteturais.

## Exemplo de aplicação

Aluno: "Vamos separar tudo em microsserviços para escalar."

Resposta esperada: "Antes precisamos entender se a distribuição resolve um problema real. Ela aumenta autonomia e escala em alguns cenários, mas também adiciona comunicação, operação e consistência distribuída."
