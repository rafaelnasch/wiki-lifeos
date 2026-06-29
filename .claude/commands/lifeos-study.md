---
description: Nota de estudo (INPUT — entender teoria/livro/curso) → 25-studies; rascunho WIP até finalizar
argument-hint: [tema/fonte do estudo — ou vazio pra processar 00-capture/studies]
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

Nota de estudo (natureza = **estudo / INPUT, entender**): $ARGUMENTS

Régua: estudo = INPUT (entender). Se for algo que você CONSTRUIU, use `/lifeos-worklog`.

1. Se vazio, processe rascunhos em `00-capture/studies/`.
2. Crie/atualize a nota em `25-studies/<slug>.md` com frontmatter
   `type: study`, `status: wip|done`, `sources`, `created`, `updated`.
   Estudos são **WIP** — construa incrementalmente; só marque `done` quando fechar.
3. Ao finalizar (`done`): **extraia os conceitos atômicos** pra `20-wiki/concepts/`
   com `[[wikilinks]]` bidirecionais (grep antes pra não duplicar).
4. Se a fonte for externa (artigo/livro/curso), salve o cru em `10-sources/` (read-only).
5. Relate: nota criada/atualizada, status, conceitos extraídos.
