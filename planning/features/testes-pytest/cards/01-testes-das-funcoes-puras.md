---
id: 01
title: Criar a primeira suíte pytest para as funções puras
blocked_by: []
labels: []
---

# Criar a primeira suíte pytest para as funções puras

## What to build

O repositório passa a ter `tests/` e um comando (`uv run pytest`) que roda testes sobre as funções sem dependência de Streamlit, rede ou LLM.

## Acceptance criteria

- [ ] `pytest` entra como dependência de desenvolvimento em `pyproject.toml`.
- [ ] Há testes para `split_into_chunks`, `filter_context_by_keywords`, `extract_urls_from_text`, `format_alternatives` e `create_download_link` (TXT).
- [ ] Cada teste verifica comportamento observável (entrada e saída), incluindo ao menos um caso de borda por função.
- [ ] `uv run pytest` passa em uma máquina limpa.
- [ ] O README tem uma linha explicando como rodar os testes.

## Notes

Algumas dessas funções vivem em `app.py`, que executa código Streamlit e lê `os.getenv` na importação. Se isso impedir a importação nos testes, extrair as funções puras para um módulo em `utils/` faz parte deste card.
Esta card ajuda os cards de `gabarito-separado` e `parametros-estruturados`, que precisam testar funções que montam texto.
