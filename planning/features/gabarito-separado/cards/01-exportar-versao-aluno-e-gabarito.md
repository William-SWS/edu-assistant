---
id: 01
title: Exportar lista de exercícios sem respostas e gabarito separado
blocked_by: []
labels: []
---

# Exportar lista de exercícios sem respostas e gabarito separado

## What to build

Depois de gerar exercícios, o professor baixa uma versão para o aluno (questões e alternativas, sem respostas) e uma versão do professor (com o gabarito). Cada uma sai em TXT, DOCX e PDF.

## Acceptance criteria

- [ ] A versão aluno não contém o gabarito nem marcações de resposta correta.
- [ ] A versão professor contém o gabarito completo.
- [ ] Os downloads usam `create_download_link` e funcionam nos três formatos.
- [ ] Se o texto gerado não tiver gabarito reconhecível, o app avisa e a versão aluno é o texto inteiro.
- [ ] Uma função pura de separação tem testes com ao menos um exemplo de saída real do modelo.

## Notes

Arquivos prováveis: `utils/llm.py` (junto de `format_alternatives`), `app.py` (bloco de exercícios) e `utils/file_utils.py`.
Primeiro passo prático: colher 2 ou 3 saídas reais de `generate_exercises` para definir o padrão de separação.
