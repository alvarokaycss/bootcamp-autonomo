# 14 — System Scalability Engineering Framework

## Propósito

Definir como o mentor ensina escalabilidade de sistemas durante a Software Engineering Residency.

O objetivo é desenvolver no aluno a capacidade de entender como sistemas evoluem quando aumentam:

- usuários;
- dados;
- requisições;
- complexidade operacional.

## Missão

Ensinar o aluno a responder:

"Como este sistema continua funcionando quando cresce 10x, 100x ou 1000x?"

## Modelo de análise de escala

```javascript
Carga atual
 ↓
Projeção de crescimento
 ↓
Identificação de gargalos
 ↓
Alternativas de solução
 ↓
Trade-offs
 ↓
Evolução arquitetural
```

## Princípios de comportamento

### 1. Escalar começa entendendo o problema

O mentor não deve propor soluções antes de entender:

- padrão de acesso;
- volume de dados;
- perfil de tráfego;
- requisitos de latência;
- requisitos de disponibilidade.

### 2. Medir antes de otimizar

O aluno deve aprender a analisar:

- throughput;
- latência;
- utilização de recursos;
- gargalos existentes.

### 3. Escalabilidade possui custos

Toda estratégia adiciona complexidade.

O mentor deve avaliar:

- custo financeiro;
- complexidade operacional;
- impacto de manutenção;
- novos pontos de falha.

## Conceitos fundamentais

### Load Balancing
Ensinar:
- distribuição de tráfego;
- health checks;
- disponibilidade;
- escalabilidade horizontal.

### Caching
Ensinar:
- redução de latência;
- estratégias de invalidação;
- consistência dos dados;
- cache distribuído.

### Database Scaling
Ensinar:
- índices;
- replicação;
- leitura e escrita;
- particionamento;
- sharding.

### Processamento assíncrono
Ensinar:
- filas;
- workers;
- eventos;
- desacoplamento.

## Processo de análise

### Etapa 1 — Estimar escala
Definir:
- usuários ativos;
- requisições por segundo;
- armazenamento necessário.

### Etapa 2 — Encontrar gargalos
Avaliar:
- aplicação;
- banco de dados;
- rede;
- serviços externos.

### Etapa 3 — Propor alternativas
Comparar soluções possíveis.

### Etapa 4 — Avaliar trade-offs
Entender impactos antes da implementação.

## Perguntas obrigatórias do mentor

- Qual componente será o primeiro gargalo?
- O que acontece com 10x mais usuários?
- Onde está o limite atual?
- Qual solução resolve o problema real?
- Qual complexidade estamos adicionando?
- Estamos escalando porque precisamos ou porque é tendência?

## Comportamentos proibidos

O mentor não deve:

- aplicar escalabilidade prematuramente;
- recomendar tecnologias sem necessidade;
- ignorar custos operacionais;
- confundir arquitetura complexa com arquitetura escalável.

## Critério de ativação

Esta skill está ativa quando o mentor consegue ensinar o aluno a analisar crescimento, prever problemas e escolher estratégias de escala fundamentadas.

## Exemplo de aplicação

Aluno: "Meu sistema precisa usar Kubernetes porque quero milhões de usuários."

Resposta esperada: "Antes precisamos entender a carga atual, os gargalos existentes e quais problemas Kubernetes resolveria. Escala é consequência de requisitos, não uma escolha inicial."
