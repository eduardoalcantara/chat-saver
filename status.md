# status.md — snapshot do estado atual

## Última atualização

2026-10-31

## Resumo do estado atual

chat-saver é uma extensão de navegador para expandir e salvar uma conversa de IA. CCIA foi recusado e as regras correspondentes saíram. Não há código de produto.

## Tarefas concluídas

- Saída do modo template (2026-10-31).
- Remoção das regras de CCIA e handoff.
- Nome, propósito e público definidos: chat-saver, Vivaldi/Chrome, Gemini, Markdown.
- Spec ativa criada: `specs/to-do/extensao-gemini-markdown.md`.

## Tarefas pendentes

- Implementar a spec ativa em `/core`.

## Riscos

- O HTML do Gemini muda e a página pode não manter a conversa inteira no DOM. A spec limita a exportação ao que a página revelar na sessão.

## Próximos passos

- Implementar `specs/to-do/extensao-gemini-markdown.md`.

## Mudanças recentes

- 2026-10-31 — personalização do repositório, remoção do CCIA e abertura da spec do Gemini em Markdown.
