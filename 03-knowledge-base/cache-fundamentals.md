# ⚡ Cache Fundamentals

> **Competência Core da Software Engineering Residency**

---

## 📌 Identificação
- **Nome da Skill**: `Cache Fundamentals`
- **Domínio / Categoria**: `Scaling & Performance`
- **Módulo Relacionado**: `Módulo 3 — Escalabilidade e Performance`
- **Nível de Complexidade**: `Fundamento / Intermediário`

---

## 🎯 Por que existe?
O Caching existe devido ao princípio de localidade de referência: a maioria das aplicações lê os mesmos dados repetidamente. Armazenar cópias desses dados em camadas de memória ultra-rápidas (RAM) evita acessos caros a banco de dados em disco ou chamadas de rede externas.

---

## 🛠️ Qual problema resolve?
- **Redução drástica de Latência**: Respostas em \(< 1-5ms\) (RAM) vs 50-500ms (Disco/Network).
- **Proteção do Banco de Dados**: Protege o banco primário contra exaustão de conexões e gargalos de CPU/Disco sob picos de tráfego.
- **Aumento de Throughput**: Permite responder dezenas de milhares de QPS com poucos servidores.

---

## ⚙️ Como funciona?
- **Estratégias de Cache**:
  - *Cache-Aside (Lazy Loading)*: A aplicação busca no Cache. Se Miss, busca na DB, escreve no Cache e retorna.
  - *Write-Through*: A aplicação escreve no Cache, e o Cache escreve imediatamente na DB.
  - *Write-Behind (Write-Back)*: A aplicação escreve no Cache, que responde imediatamente e atualiza a DB assincronamente em lote.
- **Políticas de Evicção (Quando o cache enche)**:
  - *LRU (Least Recently Used)*: Descarta o item menos acessado recentemente.
  - *LFU (Least Frequently Used)*: Descarta o item menos frequente.
  - *TTL (Time To Live)*: Expira itens após um tempo predeterminado.

---

## ✅ Quando usar?
- Sistemas com alto Read/Write ratio (ex: 90% leitura / 10% escrita).
- Consultas computacionalmente caras ou lentas.
- Sessões de usuário, dados de catálogo e configurações do sistema.

---

## ❌ Quando evitar?
- Dados que mudam a cada milissegundo com rigor absoluto de consistência estrita (ex: cotação de moedas em tempo real de alta frequência).
- Consultas que nunca se repetem (dados únicos por usuário sem reaproveitamento).

---

## 🔄 Alternativas

| Padrão | Exemplo | Uso Principal |
|---|---|---|
| **In-Memory Cache (Local)** | Guava / Caffeine / RAM do App | Menor latência possível, mas isolado em um único nó |
| **Distributed Cache (Remoto)** | Redis / Memcached | Cache compartilhado entre múltiplos nós de API |
| **CDN Cache** | Cloudflare / AWS CloudFront | Cache estático/dinâmico na borda (Edge) próximo ao cliente |

---

## ⚖️ Trade-offs
- **Ganha-se**: Performance absurda, redução de custos de banco de dados, alta escalabilidade.
- **Paga-se**: Complexidade de invalidação ("Existem apenas duas coisas difíceis na Ciência da Computação: invalidação de cache e nomear coisas"), risco de consistência eventual/dados desatualizados (stale data).

---

## 🏢 Exemplo Real
O Twitter/X armazena a Timeline de usuários populares inteiramente em instâncias Redis distribuídas. Quando você abre o app, a resposta vem do Redis em menos de 10ms sem encostar nos bancos de dados persistentes.

---

## ❓ Perguntas de Provocação do AI Mentor
1. *O que são Cache Stampede (Thundering Herd) e Cache Penetration, e como o uso de Mutex/Locking ou Bloom Filters resolve esses problemas?*
2. *Se você precisar escolher entre a estratégia Cache-Aside e Write-Through para uma aplicação de e-commerce, qual escolheria e por quê?*
3. *Como você garante que um usuário não veja dados desatualizados após atualizar o próprio perfil sem precisar zerar todo o cache da aplicação?*

---

## 🏆 Critério de Domínio (Pass / Fail)
O aluno demonstra domínio quando consegue:
- [ ] Explicar matematicamente a melhoria de latência agregada usando a fórmula de Hit Ratio.
- [ ] Implementar e defender estratégias adequadas de invalidação e expiração (TTL + Event-based).
- [ ] Diagnosticar e resolver cenários de falha catastrófica de cache (Cache Avalanche).
- [ ] Defender trade-offs de consistência eventual frente ao AI Mentor.
