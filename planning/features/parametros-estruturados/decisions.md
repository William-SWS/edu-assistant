# Decisions: Parâmetros estruturados de plano e exercícios

Todas as entradas abaixo são **propostas** feitas na fase de brainstorm. Ainda não passaram por grilling com o usuário.

## 2026-10-30

1. **Feature escolhida (confirmada pelo usuário)**: campos estruturados para gerar plano de aula e exercícios.
2. **Proposta: campos de plano**: série/ano, duração da aula (min) e tema livre (já existe).
3. **Proposta: campos de exercícios**: série/ano, nível de dificuldade (fácil, médio, difícil), número de questões e instrução livre (já existe).
4. **Proposta: os campos entram no prompt por texto**, sem mudar a assinatura pública além de parâmetros opcionais com default, para manter `generate_plan` e `generate_exercises` compatíveis.
5. **Proposta: o texto livre continua existindo** e tem prioridade quando conflitar com os campos.
6. **ADR-worthy?** Não.
