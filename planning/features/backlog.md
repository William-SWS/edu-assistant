# Backlog de features

Ideias avaliadas em 2026-10-30 que ainda não viraram cards. Uma linha por ideia.

- **Histórico de gerações**: salvar planos e exercícios em JSON e reabrir depois do reload (esforço M, reaproveita o bloco de saída de `app.py`).
- **Exportar o chat**: baixar a conversa em MD/DOCX/PDF via `create_download_link` (esforço P).
- **Citação de fonte nas respostas**: o chat indica o arquivo de origem, apoiado nos blocos `--- arquivo ---` (esforço M, risco de qualidade do LLM).
- **Links como contexto**: colar URLs e incluí-las no contexto, reaproveitando `fetch_url_content` e `extract_urls_from_text`, hoje sem uso (esforço P).
- **Upload seguro**: sanitizar `uploaded_file.name` e não sobrescrever arquivo de mesmo nome em `save_uploaded_file` (esforço P).
