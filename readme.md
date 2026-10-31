# chat-saver

## Resumo

Extensão de navegador para expandir os prompts e as respostas de uma conversa do Gemini aberta numa aba e salvar o resultado em Markdown. O uso prioritário é no Vivaldi, com extensão compatível com Chrome.

## Público e objetivo

- **Público:** quem usa o Gemini no Vivaldi, ou em outro navegador que carregue extensão do Chrome, e quer guardar a conversa.
- **Objetivo:** expandir prompts e respostas e salvar a conversa em Markdown.

## Estrutura de alto nível

| Caminho | Função |
|---|---|
| `AGENTS.md` | Índice único do agente (não repete as regras) |
| `CLAUDE.md` | Claude Code: importa `AGENTS.md` |
| `.gemini/settings.json` | Gemini CLI: contexto = `AGENTS.md` |
| `spec-root.md` | Autoridade arquitetural do projeto |
| `rules.md` | Governança permanente, inclusive fronteira script de repo vs script de produto |
| `software-development-rules.md` | SOLID, DI e padrões (só se o repo for software/sistemas) |
| `flow.md` | Ordem de leitura e execução |
| `status.md` / `timeline.md` | Estado e histórico deste repositório |
| `setup.md` / `tools-*.md` | Ambiente e ferramentas |
| `specs/` | Especificações formais (`to-do/`, `done/`, `optional/`) |
| `scripts/validation/min-tree.txt` | Única lista da árvore mínima |
| `core/` | Essencial do produto, inclusive scripts de produto em `core/scripts/` |
| `scripts/` | Scripts do **repositório** (não entram em `/core`) |
| `docs/`, `ideas/`, `references/`, `reports/`, `prompts/`, `resources/` | Apoio documental e operacional |

## Agentes

`AGENTS.md` é o único texto de instrução. Cursor, OpenCode e Codex leem esse arquivo. Claude Code lê `CLAUDE.md`, que só importa `AGENTS.md`. Gemini CLI usa `.gemini/settings.json` para procurar `AGENTS.md` em vez de `GEMINI.md`.

## Como iniciar

1. Clone este repositório e abra a pasta no Cursor.
2. Leia: `spec-root.md` → `rules.md` → `flow.md` → a spec em `specs/to-do/`.
3. O produto fica em `/core` (`core/scripts/` para scripts de produto). Scripts que só servem ao repositório ficam em `scripts/`.
4. Atualize `status.md` e `timeline.md` a cada entrega relevante.

Detalhes de ambiente: ver `setup.md`, `tools-linux.md` e `tools-windows.md`.

## Documentação relacionada

- Fluxo do agente: `flow.md`
- Regras permanentes: `rules.md`
- Regras de scripts: `rules-scripts.md`
- Molde de specs: `spec-template.md`

## Estado atual

Spec ativa: `specs/to-do/extensao-gemini-markdown.md`. Sem código de produto ainda. Detalhe em `status.md`.
