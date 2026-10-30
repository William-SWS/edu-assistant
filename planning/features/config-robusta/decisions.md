# Decisions: Config robusta e erros de LLM claros

Todas as entradas abaixo são **propostas** feitas na fase de brainstorm. Ainda não passaram por grilling com o usuário.

## 2026-10-30

1. **Feature escolhida (confirmada pelo usuário)**: config robusta + erros de LLM claros, entre as 10 ideias levantadas. Alternativas que ficaram no backlog ou em outras features: ver `../backlog.md`.
2. **Proposta: defaults no código**: `MAX_CONTEXT_CHARS=50000`, `CHUNK_SIZE=5000`, `SUMMARIZE_TIMEOUT=180`, os mesmos valores de `.env.example`, para o app não quebrar com `int(None)`.
3. **Proposta: repassar as variáveis no `docker-compose.yml`** para não depender só do `.env` montado.
4. **Proposta: retry com backoff curto só para HTTP 429 e erros de conexão**, e mensagem clara para o professor quando o limite da NVIDIA estourar.
5. **Proposta: não enviar o header `Authorization` quando a chave Ollama estiver vazia** (hoje vai `Bearer None`).
6. **ADR-worthy?** Não. Nenhuma decisão aqui é difícil de reverter.
