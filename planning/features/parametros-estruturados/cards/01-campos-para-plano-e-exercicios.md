---
id: 01
title: Adicionar campos estruturados à geração de plano e de exercícios
blocked_by: []
labels: []
---

# Adicionar campos estruturados à geração de plano e de exercícios

## What to build

Nas "Ferramentas rápidas", o professor escolhe série/ano, duração da aula (plano) e dificuldade e número de questões (exercícios) em campos próprios, em vez de escrever tudo no texto livre. Os valores entram no prompt e o resultado respeita o número de questões e o nível pedidos.

## Acceptance criteria

- [ ] O plano tem os campos série/ano e duração (min), com defaults que não alteram o comportamento atual.
- [ ] Os exercícios têm série/ano, dificuldade (fácil, médio, difícil) e número de questões.
- [ ] Os valores aparecem no prompt enviado ao LLM (verificável por teste da função que monta o prompt).
- [ ] Gerar sem mexer nos campos produz o mesmo tipo de saída de hoje.
- [ ] O texto livre continua funcionando e prevalece em caso de conflito.

## Notes

Arquivos prováveis: `utils/llm.py` (`generate_plan` e `generate_exercises`, com parâmetros opcionais) e a seção de ferramentas rápidas em `app.py`.
Se o LLM devolver número de questões diferente do pedido, não tratar nesta card (fica como risco conhecido).
