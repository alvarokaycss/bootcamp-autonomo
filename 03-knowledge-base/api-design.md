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
- **Idempotência e Segurança**: Garante que retentativas de chamadas não gerem efeitos colaterais duplicados indesejados (`Idempotency-Key`).
- **Evolução de Versão**: Permite evoluir funcionalidades sem quebrar clientes legados.
- **Paginação**: Cursor-based vs Offset-based pagination para alta performance.
