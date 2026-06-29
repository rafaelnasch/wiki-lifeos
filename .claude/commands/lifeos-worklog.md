---
description: Log de trabalho (OUTPUT — implementação/debug/deploy) → 35-worklogs; colhe conceitos pro wiki
argument-hint: [o que você construiu/fez — ou vazio pra processar 00-capture/worklogs]
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

Worklog (natureza = **trabalho / OUTPUT, construir**): $ARGUMENTS

Régua: worklog = OUTPUT (construir). Se for algo que você quer ENTENDER, use `/lifeos-study`.

1. Se vazio, processe rascunhos em `00-capture/worklogs/`.
2. Crie/atualize `35-worklogs/<slug>.md` com frontmatter `type: worklog`,
   `status: wip|done`, `area`, `created`, `updated`. WIP até finalizar.
3. **Colheita (harvest):** ao finalizar, identifique os conceitos/lições
   reutilizáveis. Coloque-os em `35-worklogs/harvest/` e promova pra
   `20-wiki/concepts/` (ou `20-wiki/patterns/` se for padrão) com `[[wikilinks]]`.
4. Se o trabalho gerou uma decisão, registre em `20-wiki/decisions/` (contexto + outcome).
5. Relate: worklog salvo, conceitos colhidos, decisões registradas.
