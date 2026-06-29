---
description: Processa o inbox cru (00-capture/quick) — classifica pela natureza, promove pra casa e zera o slot
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

Processe o inbox seguindo o AGENTS.md. Objetivo: **inbox-zero**.

1. Liste `00-capture/quick/` (ignore `.gitkeep`).
2. Pra cada item, classifique pela **natureza** (não pelo assunto):
   - vida/interior/família → `40-journal/daily/` (estilo `/lifeos-journal`)
   - estudo / quero entender (INPUT) → `00-capture/studies/` ou `25-studies/`
   - trabalho executado (OUTPUT) → `00-capture/worklogs/` ou `35-worklogs/`
   - conhecimento maduro / link / fonte → `/lifeos-ingest` (10-sources + 20-wiki)
3. **Promova**: mova o valor pra casa certa, com frontmatter e `[[wikilinks]]`
   (faça `grep` em `20-wiki/` antes pra não duplicar conceito existente).
4. **Esvazie o slot** processado (o raw fica versionado no git + na camada de destino).
5. Relate: o que foi pra onde, e confirme se o inbox ficou zerado.
