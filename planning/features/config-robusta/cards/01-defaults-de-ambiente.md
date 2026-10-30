---
id: 01
title: Dar defaults às variáveis de ambiente e repassá-las no compose
blocked_by: []
labels: []
---

# Dar defaults às variáveis de ambiente e repassá-las no compose

## What to build

Quem sobe o app sem `MAX_CONTEXT_CHARS`, `CHUNK_SIZE` ou `SUMMARIZE_TIMEOUT` no `.env` hoje vê o app quebrar na importação (`int(None)` gera `TypeError`). Depois desta mudança o app sobe com os mesmos valores de `.env.example` e o `docker-compose.yml` passa as três variáveis ao container.

## Acceptance criteria

- [ ] Com as três variáveis ausentes, `uv run streamlit run app.py` abre sem erro e usa 50000, 5000 e 180.
- [ ] Valores definidos no `.env` continuam valendo.
- [ ] `docker-compose.yml` repassa `MAX_CONTEXT_CHARS`, `CHUNK_SIZE` e `SUMMARIZE_TIMEOUT` com os mesmos defaults.
- [ ] `OLLAMA_HOST` tem um default razoável (ou erro claro) em `utils/llm.py`.

## Notes

Arquivos prováveis: `app.py` (linhas 16 a 18), `utils/llm.py`, `docker-compose.yml`, `.env.example`.
`SUMMARIZE_TIMEOUT` é lido mas não é usado: decidir se passa a valer em `summarize_chunk` ou se sai.
