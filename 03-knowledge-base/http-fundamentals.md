# 🌐 HTTP Fundamentals

> **Competência Core da Software Engineering Residency**

---

## 📌 Identificação
- **Nome da Skill**: `HTTP Fundamentals`
- **Domínio / Categoria**: `Networking & Web Architecture`
- **Módulo Relacionado**: `Módulo 1 — Fundamentos de Engenharia de Sistemas`
- **Nível de Complexidade**: `Fundamento`

---

## 🎯 Por que existe?
O HTTP (Hypertext Transfer Protocol) foi criado para permitir a comunicação padronizada, sem estado (stateless), entre clientes (navegadores/aplicativos) e servidores na Web, fornecendo uma camada de aplicação universal sob a pilha TCP/IP.

---

## 🛠️ Qual problema resolve?
- **Padronização Universal**: Permite que clientes e servidores construídos em linguagens e plataformas totalmente heterogêneas se comuniquem.
- **Formatação Semântica**: Define estruturas claras para requisições, respostas, cabeçalhos (headers), status codes e verbos.
- **Desacoplamento Stateless**: Garante que cada requisição isolada contenha o contexto necessário, facilitando o balanceamento de carga e escalabilidade horizontal.

---

## ⚙️ Como funciona?
- **Modelo Request/Response**: O cliente estabelece uma conexão TCP (porta 80/443), envia uma mensagem de requisição com verbo (GET, POST, PUT, DELETE, etc.), URI, Headers e Body. O servidor processa e retorna um Status Code (1xx, 2xx, 3xx, 4xx, 5xx), Headers e Body.
- **HTTP/1.1 vs HTTP/2 vs HTTP/3**:
  - *HTTP/1.1*: Keep-Alive, multiplexação limitada (head-of-line blocking).
  - *HTTP/2*: Multiplexação completa sobre uma única conexão TCP, compressão HPACK e Server Push.
  - *HTTP/3*: Utiliza QUIC sobre UDP para eliminar Head-of-Line Blocking no nível de transporte.

---

## ✅ Quando usar?
- Comunicação cliente-servidor síncrona ou request-driven.
- APIs Web RESTful, GraphQL ou gRPC (HTTP/2).

---

## ❌ Quando evitar?
- Comunicação de ultra-baixa latência bidirecional contínua (ex: jogos multiplayer em tempo real) $\rightarrow$ usar WebSockets ou UDP nativo.

---

## ⚖️ Trade-offs
- **Ganha-se**: Simplicidade de navegação, ecossistema gigante, facilidade de inspeção/debug, suporte nativo em proxies e CDNs.
- **Paga-se**: Overhead de cabeçalhos ASCII (no HTTP/1.1), latência de RTT no handshake TCP/TLS e características de protocolo stateless.
