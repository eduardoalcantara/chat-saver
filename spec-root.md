# spec-root.md — autoridade arquitetural

## Propósito do projeto

chat-saver existe para expandir os prompts e as respostas de um chat de IA aberto numa aba do navegador e salvar a conversa.

## Visão geral

- O projeto é governado pelos documentos da raiz.
- O agente opera segundo `flow.md`, `rules.md` e `AGENTS.md`.
- O essencial do produto/sistema vive em `/core` (código e scripts necessários para manter, compilar, rodar e instalar).
- O progresso deste repositório é rastreado em `status.md` e `timeline.md`.
- A entrega ativa é uma extensão Manifest V3 carregada no Vivaldi: site Gemini, exportação Markdown. Spec: `specs/to-do/extensao-gemini-markdown.md`.

## Princípios fundacionais

1. **Repositório nasce documentado** — contexto mínimo antes de código solto.
2. **A raiz orienta** — cada arquivo da raiz tem função operacional.
3. **Contexto explícito para o agente** — regras, fluxo, estado e histórico visíveis.
4. **Formato universal, conteúdo adaptável** — espinha dorsal fixa; interior muda por domínio.
5. **`/core` é o essencial do produto** — o que bastaria copiar sozinho para continuar a manutenção (alterar, compilar, rodar, gerar instalador), inclusive scripts de produto em `core/scripts/`; e o que se salvaria “no incêndio” se não desse tempo de salvar tudo. Script de repositório fica em `scripts/` na raiz e **não** entra em `/core`.
6. **Nomenclatura com hífen** — arquivos Markdown de governança na raiz usam `-`, nunca `_`.

## Escopo

- Extensão de navegador compatível com Chrome, para uso no Vivaldi, atuando na aba já aberta.
- Primeira entrega: conversa do Gemini, com prompts e respostas expandidos, gravada em Markdown.
- Essencial do produto em `/core`.
- Manter a estrutura documental e operacional da raiz.
- Garantir que o Cursor consiga operar sem ambiguidade sobre regras, validação e documentação.

## Fora de escopo

- Implementação de domínio específico antes de specs em `specs/to-do/`.
- Ferramentas, serviços ou integrações não documentadas.
- Alterações que violem a hierarquia normativa sem atualização explícita de `spec-root.md` e `rules.md`.

## Arquitetura de alto nível

```text
raiz documental (governança)
├── fluxo e regras do agente
├── estado e histórico
├── specs / docs / prompts
├── scripts / reports / resources
└── core/  ← essencial do produto (cópia mínima / “incêndio”)
```

## Contratos centrais

| Contrato | Documento |
|---|---|
| O que o projeto é | `spec-root.md`, `readme.md` |
| Como o agente age | `flow.md`, `AGENTS.md` |
| O que é permitido | `rules.md` |
| Como scripts funcionam | `rules-scripts.md` |
| Onde está o essencial do produto | `/core` (`core/readme.md`) |
| Árvore mínima | `scripts/validation/min-tree.txt` |

## Regras permanentes

- Não implementar fora do escopo confirmado.
- Não usar `.prompt-status` (desativado).
- Não colocar o essencial do produto fora de `/core` sem justificativa normativa; scripts essenciais de build/run/installer do produto ficam em `/core`, não em `scripts/` da raiz.
- `/core` ≠ pasta genérica de “código”: é o mínimo operacional do produto (critérios em `core/readme.md`).
- Não renomear arquivos de governança da raiz para underscore; manter hífen.
- Mudanças relevantes atualizam `status.md` e `timeline.md`.

## Critérios de sucesso

O repositório está pronto quando o Cursor responde sem ambiguidade:

- o que o projeto é;
- quais são as regras;
- como operar e validar;
- como documentar progresso;
- onde fica o essencial do produto em `/core` (cópia mínima / critério do “incêndio”);
- como o agente se comporta;
- como distinguir script de repositório (`scripts/`) de script de produto (`core/scripts/`).

## Conclusão normativa

Este arquivo é a autoridade arquitetural máxima. Specs em `specs/` detalham entregas; se houver conflito, `spec-root.md` prevalece até ser atualizado formalmente.
