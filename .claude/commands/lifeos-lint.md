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

Entregue relatório priorizado (impacto primeiro). Pergunte antes de corrigir.
