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
- **Relacionais (RDBMS / SQL)**: Baseados em tabelas, esquemas rígidos e SQL. Utilizam índices B-Tree/B+Tree e garantem ACID. Exemplo: PostgreSQL, MySQL.
- **Não-Relacionais (NoSQL)**:
  - *Documento*: Esquema flexível baseado em JSON/BSON. Ex: MongoDB.
  - *Key-Value*: Busca O(1) por chave primária. Ex: Redis, DynamoDB.
  - *Columnar / Wide-Column*: Otimizados para escritas massivas e analytics. Ex: Cassandra.

---

## ⚖️ Trade-offs
- **Ganha-se (SQL)**: Consistência forte, flexibilidade de queries ad-hoc (joins), integridade referencial.
- **Paga-se (SQL)**: Dificuldade de escalabilidade horizontal (sharding), custo computacional sob esquemas gigantes.
