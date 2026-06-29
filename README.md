<div align="center">
  <h1 align="center">Second Brain — Life OS</h1>

  <p align="center">
    Um <strong>Wiki LLM</strong> pessoal — Zettelkasten operado por agente.
    <br />
    Você captura, pergunta e decide. A IA escreve, linka e mantém.
  </p>
</div>

---

## Sobre o Projeto

Second Brain é um sistema de conhecimento pessoal no formato **Wiki LLM**: um
vault Obsidian feito só de Markdown com frontmatter YAML, operado por um agente
(Claude Code) que aplica regras, templates e conexões Zettelkasten
automaticamente.

> **Capture rápido, pergunte bastante, e deixe a IA fazer a curadoria.**

Você tem dois papéis: **capturar** (jogar coisas pra dentro) e **perguntar**. O
agente faz o resto — classifica, extrai conceitos atômicos, linka, atualiza áreas
de vida, detecta padrões e mantém o wiki saudável.

A constituição completa do agente vive em **[AGENTS.md](AGENTS.md)**.

---

## As Camadas

Cada pensamento tem uma casa **pela natureza** — não pelo assunto. O eixo central
separa três coisas que costumam ser confundidas:

| Natureza | O que é | Casa | Comando |
|---|---|---|---|
| **Vida** | interior, humor, família, oração, filosofia | `40-journal/daily/` | `/lifeos-journal` |
| **Estudo** (INPUT) | algo que você quer **entender** — teoria, livro, curso | `25-studies/` | `/lifeos-study` |
| **Trabalho** (OUTPUT) | algo que você **executou/construiu** — código, debug, deploy | `35-worklogs/` | `/lifeos-worklog` |
| **Conhecimento** | maduro, atômico, linkado, reutilizável | `20-wiki/` | `/lifeos-ingest` |

Régua rápida: **estudo = INPUT (entender)** · **worklog = OUTPUT (construir)**.

### Maturidade: captura → processar → promover

`00-capture/` é **inbox transiente**. Processar não apaga conhecimento —
**promove** o conteúdo pra sua casa permanente e **esvazia** o slot do inbox. O
raw nunca se perde (vive na camada de destino + git guarda o original).
**Inbox-zero é o estado saudável.**

```
00-capture/  →  [processar / promover]  →  casa permanente
  quick/     →  classifica → qualquer camada
  diary/     →  40-journal/daily/        (/lifeos-journal)
  studies/   →  25-studies/              (/lifeos-study)
  worklogs/  →  35-worklogs/ + harvest/  (/lifeos-worklog — colheita)
```

`studies/` e `worklogs/` são **rascunhos WIP** que você constrói
incrementalmente; só são promovidos quando finalizados.

---

## Estrutura do Vault

```
Second Brain/
├── 00-capture/          # INBOX — input cru; processa → promove → esvazia
│   ├── quick/           #   anotei e joguei, não sei o que é → classificar
│   ├── diary/           #   vida, pensamento, filosofia → journal
│   ├── studies/         #   nota de estudo (rascunho WIP) → 25-studies
│   └── worklogs/        #   nota de trabalho (rascunho WIP) → 35-worklogs
│
├── 10-sources/          # RAW MATERIAL externo — read-only, NUNCA modificar
│   └── articles/ books/ courses/ papers/ podcasts/ videos/ assets/
│
├── 20-wiki/             # KNOWLEDGE — o agente é dono (read/write)
│   ├── concepts/        #   ideias atômicas (uma por arquivo)
│   ├── entities/        #   pessoas, empresas, ferramentas
│   ├── areas/           #   domínios de vida (work, health, family, …)
│   ├── decisions/       #   decisões com contexto e outcome
│   ├── patterns/        #   padrões recorrentes detectados
│   ├── syntheses/       #   análises salvas, respostas de query
│   └── maps/            #   Maps of Content (índices temáticos)
│
├── 25-studies/          # estudos finalizados (promovidos de capture/studies)
├── 35-worklogs/         # trabalhos executados (+ harvest/ pra colher conceitos)
└── 40-journal/daily/    # diário, uma entrada por dia
```

---

## Os Comandos

Operados como slash commands do Claude Code (vivem em `.claude/commands/`, então
**viajam junto com o vault** — ao abrir o Claude Code dentro da pasta, já estão
ativos):

| Comando | Natureza | Destino |
|---|---|---|
| `/lifeos-capture` | processa o inbox cru | classifica → qualquer camada |
| `/lifeos-journal` | vida | `40-journal/daily/` |
| `/lifeos-study` | estudo (input) | `25-studies/` |
| `/lifeos-worklog` | trabalho (output) | `35-worklogs/` + `harvest/` |
| `/lifeos-ingest` | fonte externa | `10-sources/` + `20-wiki/concepts/` |
| `/lifeos-ask` | pergunta | resposta + `20-wiki/syntheses/` |
| `/lifeos-lint` | saúde do vault | relatório |

---

## Como usar no dia a dia

Você não precisa decorar comando: o `AGENTS.md` está carregado e **traduz
linguagem natural** pro comando certo. Fale como pensa.

**Capturar (durante o dia)** — jogue a ideia crua, sem parar pra organizar:

> *Anota: e se o cliente X tivesse um wiki interno por processo?*
> *Loga essa sessão: ~6h colocando o servidor pra rodar…*
> *Nota de estudo sobre LoRA training…*

**Processar / promover** — quando quiser, esvazie o inbox:

> *O que tem pendente no inbox?*
> *Processa o inbox* &nbsp;→ `/lifeos-capture`
> *Colhe o log de hoje* &nbsp;→ `/lifeos-worklog` (worklog → harvest)

**Integrar fonte e perguntar:**

> *Integra o artigo em 10-sources/articles/nome.md* &nbsp;→ `/lifeos-ingest`
> *O que eu sei sobre produtividade e sono?* &nbsp;→ `/lifeos-ask`
> *Salva isso no wiki* &nbsp;→ resposta vira `20-wiki/syntheses/`

**Vida (fim do dia) e manutenção:**

> *Processa o journal de hoje* &nbsp;→ `/lifeos-journal` (daily → sinais → áreas)
> *Faz um health check no wiki* &nbsp;→ `/lifeos-lint`

---

## Convenções

- **Nomes de arquivo:** kebab-case em pt-BR · **conteúdo:** pt-BR.
- **Datas absolutas** (AAAA-MM-DD), sempre no frontmatter — nunca no nome.
- **Conceitos atômicos:** uma ideia por arquivo; notas curtas. Se crescer, divida.
- **Wikilinks** `[[slug]]` bare (nunca em backticks). Linke liberalmente,
  inclusive **links-fantasma** (conceitos que ainda não têm nota — desejável).
- **MOC** (`20-wiki/maps/`) quando um tema acumula 5+ notas.
- Toda nota tem **frontmatter YAML**; `status: wip | done` em studies/worklogs.

---

## Anti-Patterns (o que o agente nunca faz)

- ❌ Cria nota pra toda menção marginal — **linka** em vez de duplicar.
- ❌ Resume fontes — **extrai conceitos atômicos**.
- ❌ Modifica `10-sources/` — é **read-only, sagrado** (append-only).
- ❌ Deleta com `rm` — **move pra `_trash/` antes**.
- ❌ Deixa o inbox acumular — **inbox-zero** é o estado saudável.
- ❌ Promove rascunho imaturo pro `20-wiki/` canônico.
- ❌ Mistura naturezas (estudo / trabalho / vida) na camada errada.
- ❌ Ignora contradições entre notas — **sinaliza**.

---

## Como instalar (pra quem recebeu)

Você recebeu este Second Brain como repositório (ou `.zip`). Para usar o seu:

```bash
# 1. Coloque a pasta onde quiser
#    ex.: ~/meu-second-brain

# 2. Inicie seu próprio versionamento (se veio como zip)
cd meu-second-brain
git init && git add -A && git commit -m "meu second brain"

# 3. Abra o Claude Code dentro da pasta
claude
```

Pronto: o **`AGENTS.md`** e os **7 comandos `/lifeos-*`** já estão ativos.

**Comece capturando** — rode `/lifeos-capture` ou jogue um `.md` em
`00-capture/quick/`. Depois `/lifeos-ask "..."` pra perguntar ao seu cérebro.

> **Obsidian (opcional):** abra a mesma pasta como vault pra ver o grafo de
> conexões e os backlinks. O Obsidian é só a camada visual — o cérebro é o agente.

---

<div align="center">
  <sub>Vault pessoal de conhecimento — privado. Sem licença pública.</sub>
</div>
