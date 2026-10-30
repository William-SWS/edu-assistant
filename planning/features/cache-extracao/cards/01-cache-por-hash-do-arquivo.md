---
id: 01
title: Cachear o texto extraído por hash do arquivo
blocked_by: []
labels: []
---

# Cachear o texto extraído por hash do arquivo

## What to build

Ao clicar em "Extrair texto dos selecionados", arquivos já processados voltam do cache em vez de passarem de novo por OCR e refino com LLM. O professor vê que o arquivo veio do cache e pode forçar uma nova extração.

## Acceptance criteria

- [ ] Extrair duas vezes o mesmo arquivo, com o mesmo modelo, só roda OCR e refino na primeira.
- [ ] Trocar o modelo, ou alterar o conteúdo do arquivo, gera nova extração.
- [ ] A interface indica quais arquivos vieram do cache.
- [ ] Há uma forma de ignorar o cache para um arquivo ou para todos.
- [ ] O cache fica fora do controle de versão e não aparece na listagem de arquivos do professor.

## Notes

Arquivos prováveis: `utils/ocr.py` (`extract_text_from_file`), `app.py` (botão de extração) e `utils/file_utils.py` (`get_files_list` não deve listar o diretório de cache).
O ramo de PDF em `app.py` usa `process_pdf`, que duplica a lógica de `ocr.py`: confirmar por onde o cache entra antes de começar.
