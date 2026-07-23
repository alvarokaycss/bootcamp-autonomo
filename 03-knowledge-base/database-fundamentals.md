# 🗄️ Database Fundamentals

> **Competência Core da Software Engineering Residency**

---

## 📌 Identificação
- **Nome da Skill**: `Database Fundamentals`
- **Domínio / Categoria**: `Database & Data Storage Architecture`
- **Módulo Relacionado**: `Módulo 2 — Arquitetura de Dados`
- **Nível de Complexidade**: `Fundamento`

---

## 🎯 Por que existe?
Os bancos de dados surgiram da necessidade de persistir dados de forma confiável e estruturada além do tempo de vida dos processos em memória, provendo garantias de integridade, busca rápida e consistência transacional.

---

## 🛠️ Qual problema resolve?
- **Persistência Confiável**: Evita perda de estado durante falhas no servidor ou reinicialização de sistemas.
- **Estruturação e Modelagem**: Organiza entidades e relacionamentos de negócio.
- **Indexação e Busca**: Permite consultar milhões de registros em milissegundos utilizando estruturas de dados otimizadas no disco/RAM (B-Trees, LSM-Trees).
- **Garantias ACID vs BASE**: Oferece isolamento de concorrência e consistência multi-usuário.

---

## ⚙️ Como funciona?
- **Relacionais (RDBMS / SQL)**: Baseados em tabelas, esquemas rígidos e SQL. Utilizam índices B-Tree/B+Tree e garantem ACID (Atomicity, Consistency, Isolation, Durability). Exemplo: PostgreSQL, MySQL.
- **Não-Relacionais (NoSQL)**:
  - *Documento*: Esquema flexível baseado em JSON/BSON. Ex: MongoDB.
  - *Key-Value*: Busca O(1) por chave primária. Ex: Redis, DynamoDB.
  - *Columnar / Wide-Column*: Otimizados para escritas massivas e analytics. Ex: Cassandra.
  - *Grafo*: Focados em relacionamentos complexos. Ex: Neo4j.

---

## ✅ Quando usar?
- **Bancos Relacionais**: Dados estruturados, necessidade de transações financeiras/complexas, consistência forte e relacionamentos N:N.
- **Bancos NoSQL**: Dados não-estruturados ou com esquemas mutáveis, throughput massivo de escrita e necessidade de sharding automático simples.

---

## ❌ Quando evitar?
- Não usar um banco relacional com joins complexos para dados sem nenhum relacionamento ou para chaves/valores de cache temporário.
- Não usar bancos NoSQL sem suporte ACID nativo para sistemas de saldo bancário e movimentação contábil rigorosa.

---

## 🔄 Alternativas

| Categoria | Exemplo | Melhor Caso de Uso |
|---|---|---|
| **SQL (Relacional)** | PostgreSQL | Dados de negócio ricos, relatórios complexos, consistência estrita |
| **NoSQL Documento** | MongoDB | Catálogo de produtos, perfis de usuários com campos dinâmicos |
| **NoSQL Key-Value** | Redis | Caching, sessão de usuário, contadores de alta velocidade |

---

## ⚖️ Trade-offs
- **Ganha-se (SQL)**: Consistência forte, flexibilidade de queries ad-hoc (joins), integridade referencial.
- **Paga-se (SQL)**: Dificuldade de escalabilidade horizontal (sharding), custo computacional sob esquemas gigantes.

---

## 🏢 Exemplo Real
O Uber utiliza PostgreSQL para gerenciar dados relacionais de viagens e contas, enquanto usa Redis para armazenamento rápido em memória de localizações de motoristas ativos, e Cassandra para persistir o histórico massivo de posições GPS.

---

## ❓ Perguntas de Provocação do AI Mentor
1. *O que é o teorema CAP e por que um banco de dados não pode oferecer Consistência e Disponibilidade perfeitas simultaneamente durante uma partição de rede?*
2. *Como um índice B-Tree acelera consultas de leitura no PostgreSQL e qual o custo que ele adiciona às operações de escrita (INSERT/UPDATE)?*
3. *Em qual cenário você recomendaria MongoDB em vez de PostgreSQL para uma aplicação e quais trade-offs de consistência você aceitaria nessa decisão?*

---

## 🏆 Critério de Domínio (Pass / Fail)
O aluno demonstra domínio quando consegue:
- [ ] Modelar um domínio de entidade de negócio relacional e não-relacional comparando os esquemas.
- [ ] Explicar a diferença entre isolamento Read Committed, Repeatable Read e Serializable.
- [ ] Escolher a tecnologia de banco de dados correta baseada no Read/Write ratio e perfil dos dados.
- [ ] Responder a testes socráticos de degradação e indexação com o AI Mentor.
