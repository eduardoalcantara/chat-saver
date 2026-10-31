# flow.md — fluxo operacional do agente

## Leitura condicional

Não ler a raiz inteira em todo prompt.

| Situação | Ler |
|---|---|
| Sempre | `AGENTS.md` (índice já injetado). Abrir os outros documentos só na linha que couber |
| Implementar / documentar | `spec-root.md`, `rules.md`, e trechos necessários de `flow.md` |
| Repo/entrega de software/sistemas | `software-development-rules.md` (SOLID, DI, padrões); **ignorar** se o domínio não for software |
| Scripts | `rules-scripts.md` |
| Entrega material | `status.md`, `timeline.md` |
| Spec ativa em `specs/to-do/` | A spec ativa (escopo mandatório) |

## Modos de tarefa

Um prompt → um modo: `explorar` | `implementar` | `corrigir` | `documentar` | `commit+push`.

## Fluxo de execução

1. Identificar modo e escopo.
2. Ler só o necessário (tabela acima).
3. Executar só o escopo confirmado (sem refactor espontâneo).
4. Validar ou declarar limitação.
5. Atualizar `status.md` / `timeline.md` se material.
6. Responder com dados mínimos + DoD.

`.prompt-status` está desativado. Não criar nem atualizar.

## Checklist (DoD)

- [ ] Modo e escopo claros
- [ ] Leitura condicional feita
- [ ] Sem refactor fora do pedido
- [ ] Validação ou limitação declarada
- [ ] Docs atualizados se material
- [ ] Próximo passo explícito

## Limite de exploração

Sem progresso após ~8 buscas/leituras → pause com opções numeradas.
