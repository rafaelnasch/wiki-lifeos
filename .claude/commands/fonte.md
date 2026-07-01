---
description: Ingere uma fonte externa (url/arquivo/texto) → salva cru em 10-sources + conceitos atômicos em 20-wiki
argument-hint: <url, caminho de arquivo, ou cole o texto>
allowed-tools: WebFetch, Read, Write, Edit, Glob, Grep, Bash
---

Ingira a fonte seguindo o AGENTS.md: $ARGUMENTS

> **Motor de promoção, não porta de entrada do humano.** O raw da fonte vive em
> `10-sources/` (read-only) — isso é esperado. Mas **ingerir SEM extrair conceitos
> atômicos + `[[wikilinks]]` é bug**: nunca deixe uma fonte grande na camada canônica
> sem atomizar. Se não der pra colher agora, não marque como processada.

1. Se for URL, busque com WebFetch. Se arquivo, leia. Se texto, use direto.
2. Salve o **cru** em `10-sources/<tipo>/<slug>.md` (tipo = articles/books/courses/
   papers/podcasts/videos). **Read-only / append-only** — nunca modificar depois.
   Frontmatter: title, url/origem, data de hoje (`date +%F`).
3. Extraia os 3-8 **conceitos atômicos**. Antes de criar, `grep` em `20-wiki/`
   pra achar notas existentes relacionadas (inclusive sinônimos).
4. Crie/atualize notas em `20-wiki/concepts/` (e `entities/` pra pessoas/empresas/
   ferramentas) com `[[wikilinks]]` bidirecionais. Crie links-fantasma livremente.
5. Atualize a MOC do tema (`20-wiki/maps/`) se houver 5+ notas no tema.
6. Relate: fonte salva, conceitos criados/atualizados, novos links.
