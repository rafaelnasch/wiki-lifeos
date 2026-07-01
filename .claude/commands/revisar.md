---
description: Saúde do vault — links quebrados, notas órfãs, inbox não-zero, WIP parado, MOCs desatualizadas
allowed-tools: Read, Glob, Grep, Bash
---

Health check do vault. **Somente leitura + relatório.** Não corrija sem confirmar.

1. **Inbox-zero?** Conte itens em `00-capture/quick|diary|studies|worklogs/` (fora `.gitkeep`).
   Liste o que está parado esperando processamento.
2. **WIP parado:** notas em `25-studies/`/`35-worklogs/` com `status: wip` e `updated` antigo.
3. **Links-fantasma:** `[[slugs]]` citados sem nota correspondente (candidatos a preencher).
4. **Órfãs:** notas em `20-wiki/` que ninguém linka.
5. **MOCs:** temas com 5+ notas sem MOC em `20-wiki/maps/`.
6. **10-sources:** confirme que nada foi modificado (deve ser read-only).
7. **`_trash/` consistente:** todo arquivo em `_trash/` deve **espelhar o caminho de
   origem** (`_trash/00-capture/quick/…`, não `_trash/00-capture-quick/…`). Sinalize
   pastas achatadas ou fora do espelho pra normalizar.
8. **Monólitos não-processados (CRÍTICO):** notas em `20-wiki/`, `25-studies/` ou
   `35-worklogs/` que são **grandes e não-atomizadas** — sintoma de conteúdo que
   entrou sem passar pelo Passo 2. Regra prática: arquivo com **~500+ linhas** OU
   **muitos headings** mas **poucos `[[wikilinks]]`** (heurística: menos de 1 link a
   cada ~150 palavras), ou um estudo/worklog `status: done` sem conceitos atômicos
   correspondentes em `20-wiki/concepts/`. Liste cada um com nº de linhas/palavras e
   contagem de `[[links]]`, e proponha a colheita (quebrar em conceitos + linkar + MOC).

Entregue relatório priorizado (impacto primeiro). Pergunte antes de corrigir.
