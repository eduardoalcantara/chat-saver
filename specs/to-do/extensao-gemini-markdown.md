# Extensão Gemini — exportar Markdown

## Objetivo

Entregar uma extensão de navegador que, na aba do Gemini já aberta no Vivaldi, expande os prompts e as respostas e grava a conversa em um arquivo Markdown.

## Dependências

- Relação com `spec-root.md`: primeira entrega do chat-saver. O produto vive em `/core`.
- Specs anteriores: nenhuma
- Pré-requisitos técnicos: Vivaldi com suporte a extensão descompactada no formato do Chrome (Manifest V3). Conta e conversa do Gemini já abertas pelo usuário.

## Escopo

- Extensão Manifest V3, carregada descompactada no Vivaldi.
- Atua só na aba já aberta de `gemini.google.com`.
- Uma ação do usuário expande prompts e respostas recolhidos que a página exibir.
- Se a página mantiver só parte da conversa no DOM, a extensão percorre a conversa e acumula os turnos que a página revelar nessa sessão.
- Grava um arquivo `.md` na máquina do usuário, com os turnos na ordem da página.
- Código do produto em `/core`.

## Fora de escopo

- ChatGPT, Perplexity e qualquer outro site.
- Exportação HTML.
- Modo debug, DevTools Protocol ou navegador lançado à parte.
- Chrome Web Store, Edge e Firefox como alvos.
- Login, backend, conta do chat-saver ou envio da conversa a outro serviço.
- Leitura da API interna do Gemini. A leitura é a página aberta.

## Requisitos

1. A extensão carrega no Vivaldi como extensão descompactada, sem publicação em loja.
2. Com uma conversa do Gemini aberta, uma ação do usuário dispara expandir e exportar.
3. O Markdown inclui cada turno na ordem da página, com cabeçalho `Prompt` ou `Resposta` e o texto daquele turno depois de expandido.
4. Turnos que só aparecem depois de expandir ou de percorrer a página entram no arquivo.
5. A extensão não envia o texto da conversa para fora do navegador. O arquivo fica na máquina do usuário.
6. O código necessário para carregar e manter a extensão fica em `/core`.

## Resultado esperado

No Vivaldi, com uma conversa do Gemini aberta, o usuário aciona a extensão e recebe um arquivo Markdown da conversa, com prompts e respostas expandidos, na ordem em que a página os mostrou.

## Critérios de aceite

- [ ] A extensão descompactada carrega no Vivaldi.
- [ ] Numa conversa do Gemini com trechos recolhidos, o Markdown contém o texto expandido desses trechos.
- [ ] Numa conversa em que a página não mostra todos os turnos de uma vez, o Markdown acumula os turnos que a página revelar ao ser percorrida.
- [ ] Cada turno está identificado como `Prompt` ou `Resposta`, na ordem da página.
- [ ] O arquivo é gerado localmente, sem envio da conversa a outro serviço.
- [ ] Código do produto em `/core`.
- [ ] Documentação atualizada (`status.md`, `timeline.md` quando aplicável)

## Impacto

- Usuários / operadores: uma ação na aba do Gemini produz o Markdown da conversa.
- Arquitetura: o produto passa a existir em `/core` como extensão Manifest V3.
- Documentação: esta spec é a entrega ativa; `spec-root.md` e `readme.md` apontam para ela.

## Arquivos afetados

- `core/` — extensão (a criar na implementação)
- `status.md`
- `timeline.md`

## Validações

- [ ] Carregar a extensão descompactada no Vivaldi e confirmar que ela aparece habilitada.
- [ ] Numa conversa real do Gemini, acionar a exportação e conferir o Markdown: ordem, rótulos `Prompt` e `Resposta`, e texto que estava recolhido.
- [ ] Repetir numa conversa longa o bastante para a página não manter todos os turnos no DOM ao mesmo tempo.

## Riscos

- O HTML do Gemini muda sem aviso. O adaptador da página quebra e a exportação passa a sair incompleta ou vazia. Mitigação: validar numa conversa real antes de dar a entrega por pronta; não fixar seletores nesta spec.
- Parte da conversa pode não ser revelada pela página mesmo depois de percorrer e expandir. O arquivo só pode conter o que a página mostrar nessa sessão.

## Próxima spec

- a definir
