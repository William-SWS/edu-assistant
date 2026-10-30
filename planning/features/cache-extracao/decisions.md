# Decisions: Cache da extração de texto

Todas as entradas abaixo são **propostas** feitas na fase de brainstorm. Ainda não passaram por grilling com o usuário.

## 2026-10-30

1. **Feature escolhida (confirmada pelo usuário)**: cache do texto extraído, por arquivo.
2. **Proposta: chave do cache** = hash (SHA-256) do conteúdo do arquivo mais o modelo usado no refino, já que o texto muda com o modelo.
3. **Proposta: armazenar** em um diretório de cache dentro da pasta de dados (por exemplo `docs/.cache/`), um arquivo de texto por chave. Sem banco de dados.
4. **Proposta: botão "Reextrair"** (ou checkbox) para ignorar o cache quando o professor quiser.
5. **Aberto:** o cache deve cobrir também o refino por LLM (`refine_text_with_llm`)? A proposta é que sim, porque é a parte lenta e cara.
6. **ADR-worthy?** Possivelmente: o formato e o local do cache viram contrato com dados do usuário. Registrar um ADR se a feature avançar.
