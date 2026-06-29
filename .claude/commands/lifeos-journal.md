---
description: Registra/processa o diário do dia (vida, humor, família, filosofia) em 40-journal/daily
argument-hint: [o que aconteceu / cole a nota — ou vazio pra processar 00-capture/diary]
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

Entrada de diário (natureza = **vida**): $ARGUMENTS

1. Se houver argumento, é a entrada de hoje. Se vazio, processe tudo em `00-capture/diary/`.
2. Escreva/atualize `40-journal/daily/AAAA-MM-DD.md` (use a data de hoje via `date +%F`),
   frontmatter `type: journal`, `created`, `tags`, `area` se aplicável.
3. Linke pessoas/temas com `[[wikilinks]]`. Se um tema recorrente aparecer (humor,
   família, fé, trabalho), considere atualizar a área em `20-wiki/areas/`.
4. Se detectar um padrão recorrente (ex: mesma tensão repetindo), registre/atualize
   em `20-wiki/patterns/`.
5. Esvazie o slot de `00-capture/diary/` que processou. Relate brevemente.
