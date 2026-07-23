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
- Servir arquivos estáticos, aplicações web e dados JSON.

---

## ❌ Quando evitar?
- Comunicação de ultra-baixa latência bidirecional contínua (ex: jogos multiplayer em tempo real) \(\rightarrow\) usar WebSockets ou UDP nativo.
- Comunicação assíncrona entre microsserviços de alto throughput onde filas de mensagem (ex: RabbitMQ, Kafka) são mais adequadas.

---

## 🔄 Alternativas

| Alternativa | Comparativo Principal | Diferencial |
|---|---|---|
| **WebSockets** | Conexão full-duplex persistente sobre TCP | Ideal para tempo real bidirecional sem overhead de headers a cada mensagem |
| **gRPC (Protobuf)** | Protocolo binário forte sobre HTTP/2 | Muito mais rápido e eficiente em termos de payload para comunicação inter-serviços |
| **UDP Raw** | Transporte sem garantia de entrega ou ordenação | Máxima velocidade e menor latência possível para streaming/jogos |

---

## ⚖️ Trade-offs
- **Ganha-se**: Simplicidade de navegação, ecossistema gigante, facilidade de inspeção/debug, interoperabilidade universal e suporte nativo em todos os proxies e CDNs.
- **Paga-se**: Overhead de cabeçalhos ASCII (no HTTP/1.1), latência de RTT no handshake TCP/TLS e características de protocolo stateless (exige envio explícito de tokens de sessão/auth).

---

## 🏢 Exemplo Real
Toda chamada de API na Web (ex: busca no Google, login no GitHub) trafega via HTTP/HTTPS. A Netflix utiliza HTTP/2 para troca de metadados entre apps cliente e servidores de controle, enquanto o streaming de vídeo usa blocos HTTP carregados de CDNs (HLS/DASH).

---

## ❓ Perguntas de Provocação do AI Mentor
1. *Por que dizemos que o HTTP é um protocolo stateless, e como mantemos o estado do usuário sem violar esse princípio na arquitetura?*
2. *Qual a diferença prática entre o código HTTP 301 (Moved Permanently) e 302 (Found/Temporary) do ponto de vista de Caching no cliente e na CDN?*
3. *Como o Head-of-Line Blocking afeta o HTTP/1.1 e de que forma o HTTP/2 e o HTTP/3 (QUIC) resolveram esse problema em camadas diferentes?*

---

## 🏆 Critério de Domínio (Pass / Fail)
O aluno demonstra domínio quando consegue:
- [ ] Explicar o ciclo completo de uma requisição HTTP desde a resolução DNS até o fechamento/reuse da conexão TCP.
- [ ] Diferenciar semanticamente o uso adequado de verbos (GET vs POST vs PUT vs PATCH) e status codes (ex: 401 vs 403, 409 vs 422).
- [ ] Justificar quando migrar de HTTP REST para gRPC ou WebSockets baseado em requisitos não-funcionais.
- [ ] Defender decisões de caching e headers (`Cache-Control`, `ETag`, `Authorization`) frente ao AI Mentor.
