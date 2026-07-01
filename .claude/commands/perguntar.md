---
description: Pergunta ao wiki — responde só com o conteúdo do vault, citando [[notas]]; salva síntese se valiosa
argument-hint: <sua pergunta>
allowed-tools: Read, Write, Glob, Grep
---

Responda usando SOMENTE o conteúdo do vault (`20-wiki/`, `25-studies/`,
`35-worklogs/`, `40-journal/`, `10-sources/`): $ARGUMENTS

1. Use `grep`/`glob` pra achar as notas relevantes em todas as camadas.
2. Sintetize uma resposta clara, citando as `[[notas]]` que usou.
3. Se o vault não cobre, diga exatamente o que falta capturar/ingerir.
4. Se a análise for valiosa/reutilizável, salve em `20-wiki/syntheses/<slug>.md`
   (frontmatter `type: synthesis`, `created`) com os `[[wikilinks]]` das fontes.
