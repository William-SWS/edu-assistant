# Decisions: Primeira suíte de testes (pytest)

Todas as entradas abaixo são **propostas** feitas na fase de brainstorm. Ainda não passaram por grilling com o usuário.

## 2026-10-30

1. **Feature escolhida (confirmada pelo usuário)**: primeira suíte pytest sobre funções puras.
2. **Proposta: pytest como dev dependency** em `pyproject.toml`, rodando com `uv run pytest`.
3. **Proposta: começar só pelo que já é puro**: `split_into_chunks`, `filter_context_by_keywords`, `extract_urls_from_text`, `format_alternatives` e `create_download_link` (formato TXT).
4. **Proposta: sem mocks de LLM nesta etapa.** Funções que dependem de `st.*` ou de variáveis lidas na importação ficam para depois.
5. **Aberto:** CI no GitHub Actions entra junto ou em card separado? A proposta é um card separado, para não bloquear os testes.
6. **ADR-worthy?** Não.
