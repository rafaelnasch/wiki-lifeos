---
description: Processa o inbox cru (00-capture/quick) — classifica pela natureza, promove pra casa e zera o slot
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

Processe o inbox seguindo o AGENTS.md. Objetivo: **inbox-zero**.

1. Liste `00-capture/quick/` (ignore `.gitkeep`). **Stub vazio** (0 byte — nota que
   o Obsidian criou ao clicar num link-fantasma) → mande direto pro `_trash/` espelhando
   o caminho, sem promover; o `[[link]]` volta a ser fantasma (estado desejável).
2. Pra cada item, classifique pela **natureza** (não pelo assunto):
   - vida/interior/família → `40-journal/daily/` (estilo `/diario`)
   - estudo / quero entender (INPUT) → `00-capture/studies/` ou `25-studies/`
   - trabalho executado (OUTPUT) → `00-capture/worklogs/` ou `35-worklogs/`
   - conhecimento maduro / link / fonte → `/fonte` (10-sources + 20-wiki)
3. **Promova (não é só mover — é PROCESSAR):** leve o valor pra casa certa com
   frontmatter e **quebre em conceitos atômicos** pra `20-wiki/concepts/` com
   `[[wikilinks]]` bidirecionais (faça `grep` em `20-wiki/` antes pra não duplicar).
   Estudo/worklog só vai como `done` **depois** de atomizado; crie MOC se o tema
   tiver 5+ notas. **Nunca deposite um monólito bruto numa camada canônica** — se o
   conteúdo é grande, quebre; se não der pra quebrar agora, deixe `wip`.
4. **Esvazie o slot** processado movendo o raw pra `_trash/` **espelhando o caminho
   de origem** (`00-capture/quick/x.md` → `_trash/00-capture/quick/x.md`; use `git mv`).
   Nunca achate o caminho nem use `rm`. O valor já vive na camada de destino + git.
5. Relate: o que foi pra onde, e confirme se o inbox ficou zerado.
