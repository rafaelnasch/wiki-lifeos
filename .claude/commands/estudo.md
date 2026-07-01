---
description: Nota de estudo (INPUT — entender teoria/livro/curso) → 25-studies; rascunho WIP até finalizar
argument-hint: [tema/fonte do estudo — ou vazio pra processar 00-capture/studies]
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

Nota de estudo (natureza = **estudo / INPUT, entender**): $ARGUMENTS

Régua: estudo = INPUT (entender). Se for algo que você CONSTRUIU, use `/trabalho`.

> **Este comando é o MOTOR de promoção, não uma porta de entrada.** Conteúdo cru
> entra pelo capture (fale com o agente ou largue um `.md` em `00-capture/quick/`).
> Não jogue um texto pronto direto
> em `25-studies/` pulando o inbox.
> **GATE INVIOLÁVEL:** um estudo **NUNCA** fica `status: done` sem colheita. Texto
> grande e ainda não atomizado → ou fica `wip`, ou você atomiza AGORA. **Nunca deixe
> um monólito `done`** (um estudo gigante entrando sem ser quebrado é o anti-padrão que este gate previne).

1. Se vazio, processe rascunhos em `00-capture/studies/`.
2. Crie/atualize a nota em `25-studies/<slug>.md` com frontmatter
   `type: study`, `status: wip|done`, `sources`, `created`, `updated`.
   Estudos são **WIP** — construa incrementalmente; só marque `done` quando fechar.
3. **Ao finalizar (`done`) — obrigatório, sem exceção:** quebre o estudo em
   **conceitos atômicos** (um por arquivo em `20-wiki/concepts/`) com `[[wikilinks]]`
   bidirecionais estudo↔conceito (grep antes pra não duplicar); crie o **MOC** em
   `20-wiki/maps/` se o tema tiver 5+ conceitos; preencha `## Conexões` no estudo.
   **Sem isso, o estudo continua `wip`** — não existe estudo `done` sem rede.
4. Se a fonte for externa (artigo/livro/curso), salve o cru em `10-sources/` (read-only).
5. Relate: nota criada/atualizada, status, conceitos extraídos.
