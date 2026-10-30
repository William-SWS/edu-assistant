---
id: 02
title: Tratar 429 e falhas de conexão do LLM com retry e mensagem clara
blocked_by: []
labels: []
---

# Tratar 429 e falhas de conexão do LLM com retry e mensagem clara

## What to build

Quando a API da NVIDIA devolver 429 (limite de taxa) ou o Ollama estiver fora do ar, o professor vê uma mensagem em português dizendo o que aconteceu e o que fazer, em vez de "Erro ao obter resposta". O app tenta de novo algumas vezes, com espera curta, antes de desistir. Se a chave do Ollama estiver vazia, a requisição não envia `Authorization: Bearer None`.

## Acceptance criteria

- [ ] Resposta 429 dispara até 3 tentativas com espera crescente, e a mensagem final cita o limite de taxa.
- [ ] Erro de conexão mostra mensagem distinta de erro de autenticação (401/403).
- [ ] O mesmo comportamento vale para `call_ollama` e `call_ollama_stream`, nos dois providers.
- [ ] Sem `OLLAMA_API_KEY`, o header `Authorization` não é enviado.
- [ ] Os `except:` nus de `utils/llm.py` (parse do stream) passam a capturar exceções específicas.

## Notes

Arquivos prováveis: `utils/llm.py` (`_call_nvidia`, `_call_nvidia_stream` e as chamadas Ollama), `utils/ocr.py` (linha 322, mesmo header).
Hoje os erros viram `st.error` mais string vazia, e o chamador em `app.py` mostra uma mensagem genérica.
