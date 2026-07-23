# 🔌 API Design

> **Competência Core da Software Engineering Residency**

---

## 📌 Identificação
- **Nome da Skill**: `API Design`
- **Domínio / Categoria**: `Backend Architecture & Interface Contracting`
- **Módulo Relacionado**: `Módulo 1 — Fundamentos de Engenharia de Sistemas`
- **Nível de Complexidade**: `Fundamento / Intermediário`

---

## 🎯 Por que existe?
APIs (Application Programming Interfaces) estabelecem os contratos de comunicação entre clientes e serviços ou entre microsserviços. Um bom design de API garante desacoplamento, facilidade de integração, previsibilidade, segurança e evolução sem breaking changes.

---

## 🛠️ Qual problema resolve?
- **Contratos Claros**: Evita ambiguidade sobre formatos de dados, parâmetros e respostas.
- **Idempotência e Segurança**: Garante que retentativas de chamadas não gerem efeitos colaterais duplicados indesejados.
- **Evolução de Versão**: Permite evoluir funcionalidades sem quebrar clientes legados.
- **Controle de Vazamento de Dados**: Expõe apenas os campos necessários do domínio.

---

## ⚙️ Como funciona?
- **Padrões de Estilo**:
  - *REST*: Baseado em recursos (URIs no plural), verbos HTTP e representações JSON.
  - *GraphQL*: Endpoint único onde o cliente especifica a query exata com os campos desejados (evita over-fetching/under-fetching).
  - *gRPC*: Chamadas de procedimento remoto com esquema sintático estrito em Protobuf.
- **Princípio da Idempotência**:
  - `GET`, `PUT`, `DELETE`: Idempotentes (múltiplas chamadas produzem o mesmo estado final).
  - `POST`: Não idempotente por padrão (exige uso de *Idempotency-Key* header para compras/pagamentos).
- **Paginação & Padrões de Filtro**:
  - Offset-based (`page=2&limit=20`) vs Cursor-based (`after_id=cursor_token`).

---

## ✅ Quando usar?
- REST: Para APIs públicas web/mobile de propósito geral com padrão RESTful consolidado.
- GraphQL: Para clientes com telas dinâmicas complexas e agregação de múltiplos serviços no BFF.
- gRPC: Para comunicação interna microserviço-para-microserviço de alta performance.

---

## ❌ Quando evitar?
- Evitar criar APIs RPC ad-hoc sobre HTTP GET/POST sem padrão ou documentação de contrato (ex: `GET /doSomethingDangerous`).
- Evitar GraphQL para APIs públicas de parceiros sem limitação estrita de profundidade de query (risco de ataques de negação de serviço via queries aninhadas).

---

## 🔄 Alternativas

| Estilo | Formato Payload | Melhor Caso de Uso |
|---|---|---|
| **RESTful** | JSON / XML | APIs públicas, integração web padrão, bom uso de cache HTTP |
| **GraphQL** | JSON (Query flexível) | Dashboards com requisitos de UI altamente dinâmicos |
| **gRPC** | Protobuf Binário | Microsserviços internos, alto throughput e forte checagem de tipos |

---

## ⚖️ Trade-offs
- **Ganha-se**: Desacoplamento entre times de Frontend e Backend, reusabilidade de serviços, capacidade de versionamento transparente.
- **Paga-se**: Necessidade de manutenção rigorosa de documentação (OpenAPI/Swagger), custo de governança e gerenciamento de breaking changes.

---

## 🏢 Exemplo Real
A Stripe possui uma das APIs REST mais elogiadas do mundo, utilizando o cabeçalho `Idempotency-Key` para garantir que retentativas de rede em cobranças de cartão de crédito jamais cobrem duas vezes o cliente final.

---

## ❓ Perguntas de Provocação do AI Mentor
1. *Qual a diferença fundamental entre paginação baseada em Offset (LIMIT/OFFSET) e paginação baseada em Cursor (Keyset Pagination) sob o ponto de vista de performance no banco de dados e consistência durante inserções simultâneas?*
2. *Como você projetaria um mecanismo de idempotência em uma API de pagamento usando Redis e banco de dados relacional?*
3. *Quando adicionar um novo campo a uma resposta de API é considerado uma mudança compatível (non-breaking) e quando isso pode se tornar uma breaking change em clientes fortemente tipados?*

---

## 🏆 Critério de Domínio (Pass / Fail)
O aluno demonstra domínio quando consegue:
- [ ] Desenhar a especificação OpenAPI (Swagger) completa de um recurso de API com tratamento de erros (RFC 7807).
- [ ] Demonstrar o funcionamento prático de um cabeçalho de Idempotência e taxa de limite (Rate Limiting).
- [ ] Justificar tecnicamente a escolha entre REST, GraphQL ou gRPC para um problema real.
- [ ] Defender estratégias de versionamento de API perante o AI Mentor.
