# Decisions: Gabarito separado (versão aluno e versão professor)

Todas as entradas abaixo são **propostas** feitas na fase de brainstorm. Ainda não passaram por grilling com o usuário.

## 2026-10-30

1. **Feature escolhida (confirmada pelo usuário)**: exportar a lista de exercícios sem respostas e o gabarito à parte.
2. **Proposta: separar por pós-processamento do texto gerado**, sem mudar o prompt, apoiado em `format_alternatives` e no formato atual (alternativas a) a d) mais gabarito).
3. **Proposta: dois botões de download** (versão aluno, versão professor), nos mesmos formatos TXT, DOCX e PDF.
4. **Proposta: se o texto não tiver um gabarito reconhecível**, a versão aluno sai igual ao texto original e o app avisa o professor.
5. **Depende de verificar** como o LLM marca o gabarito hoje. Se for inconsistente, a feature precisa de uma saída estruturada (isso mudaria o escopo e merece grilling).
6. **ADR-worthy?** Não.
