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
- **Redução drástica de Latência**: Respostas em < 1-5ms (RAM) vs 50-500ms (Disco/Network).
- **Proteção do Banco de Dados**: Protege o banco primário contra exaustão de conexões e gargalos de CPU/Disco sob picos de tráfego.
- **Aumento de Throughput**: Permite responder dezenas de milhares de QPS com poucos servidores.

---

## ⚙️ Como funciona?
- **Estratégias de Cache**:
  - *Cache-Aside (Lazy Loading)*: A aplicação busca no Cache. Se Miss, busca na DB, escreve no Cache e retorna.
  - *Write-Through*: A aplicação escreve no Cache, e o Cache escreve imediatamente na DB.
  - *Write-Behind (Write-Back)*: A aplicação escreve no Cache, que responde imediatamente e atualiza a DB assincronamente em lote.
- **Políticas de Evicção**: LRU (Least Recently Used), LFU (Least Frequently Used), TTL (Time To Live).
