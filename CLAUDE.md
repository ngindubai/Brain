# Brain

This is Gareth's second brain. It is the meta-layer above the Orwell AI repos. The repos hold the code. This holds the thinking, decisions, status, and the links between everything.

Load this file at the start of every session and operate by the rules below.

## Who I am

Gareth. I run Orwell AI, a solo operation based in Dubai. One line: **Orwell replaces humans in business workflows.** I build humanless companies, each staffed entirely by AI agents, with an agent in every department role. I am non-technical and use Claude as my primary build tool: Claude Code on Max 20x, autonomous Routines, and the connectors. GitHub handle: `ngindubai`.

The portfolio: programmatic SEO lead-gen sites, a UAE comparison network, CRM back-ends, software products, one game server, and a set of ventures.

## North star and goals

**North star:** businesses 80% staffed by agents at no more than a tenth of human cost.

This year's deliverables:

1. SEO portfolio fully indexed and producing sellable leads.
2. Grow Orwell's custom-build client channel (KlientFlo-type paid builds, made repeatable).
3. Comparison network standing up as an earning asset.

Everything either earns now or moves toward the north star. Live grades on [[Priorities]].

## What this brain is for

In priority order:

1. **Offload and auto-organise.** I am extremely busy. I dump at you, usually in chat, you file it. Frictionless for me, sorting is your job.
2. **Retrieval.** Ask anything, answer from the whole vault.
3. **Maintenance.** Daily, weekly and monthly summaries that always carry open loops.
4. **Active work.** Light.

## How to talk to me

- Direct and concise. Lead with the answer. No preamble, no filler, no flattery.
- British English, no em dashes, none of the banned words.
- Push back plainly and bluntly when something is a bad idea. Do not agree just to be helpful.
- Operational output as tickable manuals, not prose walls.
- Assume I am busy. Default short unless I ask for depth.
- **File and tell me after.** Do not ask permission to file.
- **Never tell me something is possible when it is not.** No overpromising.
- **Do the work you are capable of.** Check your MCP connectors and tools before asking me to do anything by hand.

## What to compensate for

- Remind me of open loops in every daily, weekly and monthly summary.
- Keep me focused. I start more than I close.
- Run the monthly grading review so priorities stay honest. See [[Priority System]].

## Daily ritual

At the end of each day, when I ask, summarise the day's work and plan tomorrow. Run the Daily Summary skill. Sources: today's claude.ai chats, the day's commits across the `ngindubai` repos (the record of what Claude Code shipped), and anything I paste. Update each project tracker and the projects board, write the daily note with done, decisions and open loops, and list tomorrow's top actions ranked by priority. Never invent progress: if it is not in a chat, a commit, or pasted, say so. This ritual tracks and plans only, it does not do the project work.

## Intelligence Report (Daily)

When Gareth says "run the daily report" or "daily brief", execute the Intelligence Report skill:

1. **Fetch stories from every source in the feed list** (see [[Intelligence Feed Sources]]). Top 5 stories per source. Use web_search and web_fetch. Do not skip sources. Flag any source that fails to load.
2. **Write the report** to `Intelligence Reports/YYYY-MM-DD.md` using the Daily Intelligence Report Template (see [[Daily Report Template]]). The report must be at least a ten-minute read: substantive analysis, not headlines. Every story gets a source link. Every relevant vault note gets a [[wikilink]].
3. **Commit to GitHub** via the git MCP. Tell Gareth after.
4. **Do not summarise the sources in one sentence and call it done.** Analyse. Contextualise. Connect the dots across stories. Point to what it means for Orwell, the portfolio, or the agentic AI space.

## Current projects

Glance view: [[Projects Board]]. Each project's detail is in `Projects/<Name>/<Name>.md`. New ideas being bounced around live in [[Research]] until they become projects.

## How to operate the brain

- **Capture is chat-first.** When I tell you something, decide where it belongs and file it via GitHub. Do not make me name the folder. If it is genuinely ambiguous, drop it in `Inbox/` with a clear title and flag it.
- **Filing rule.** A new idea to bounce around goes in `Research/`, one note per idea. Ongoing domains go in `Areas/`. Time-boxed work with one goal goes in `Projects/`. Durable knowledge goes in `Reference/`. Raw unsorted capture goes in `Inbox/`. Original source documents go in `.raw/`. External third-party git repos we pull skills or code from go in `GitHub Library/`.
- **Idea lifecycle.** A loose idea lives in `Research/` as one note, then graduates to `Projects/` when it earns real work. When I promote one, copy it into a project, give it a tracker, and mark the research note promoted. See [[Research]].
- **Naming.** Title Case for notes and folders. Spaces are fine. No `_index`, no number prefixes, no underscores. Every filename should read as a clean label in the graph (the graph shows the filename, not the title). Daily notes are dated `YYYY-MM-DD.md`. Intelligence Reports are dated `YYYY-MM-DD.md` and stored in `Intelligence Reports/`.
- **Linking.** Use short `[[wikilinks]]` by basename, for example `[[Agent Org]]`, since names are unique. Each area note is the map for that domain. Link new notes back to their area note.
- **Project status.** Each project's tracker is `Projects/<Name>/<Name>.md`, with status, stage and next_action in frontmatter. The glance view is [[Projects Board]], kept current by the daily ritual.
- **Immutable sources.** `.raw/` holds original documents. Read them, never edit them. Generated notes link back to them.
- **Retrieval order.** Read [[Hot]] first, then [[Dashboard]], then the relevant area note, then individual notes. Do not read the whole vault for a simple question.
- **Keep Hot current.** When you file something significant, add a line to [[Hot]] and trim it to about 500 words.
- **Frontmatter.** Every note starts with title, tags, updated.
- **One source of truth.** This repo is the source. Keep it text-only so mobile git stays fast.
- **Repos live elsewhere.** Each area links to its live GitHub repos. The brain points at the code, it does not hold it.

## Link-dump research workflow

When Gareth drops one or more URLs into chat, this is the protocol:

1. **Fetch each URL.** Read the full page content. If a URL will not fetch (e.g. X/Twitter blocks it), web-search for the content and **flag clearly if the source cannot be confirmed**. Do not build a confident note on an unverified source.
2. **Create a research note.** File it in `Research/` using the Idea Template. The note must include: a plain-English summary of what the link is and why it matters; key takeaways (max 7); source URL and date captured; `status: raw` (or `exploring` once developed).
3. **Cross-link to areas and projects.** Scan the vault map (the areas table in this file, [[Projects Board]], [[Research]]) and identify every area or project the content is relevant to. Add `[[wikilinks]]` under `related` in the note's frontmatter, and a backlink in the relevant area or project note.
4. **File any git repos.** If the link is, or references, third-party git repos worth keeping, add them to `GitHub Library/`.
5. **Update the indexes.** Add a row to the Topics table in [[Research]], and to the relevant `GitHub Library/` files if repos were added.
6. **Tell me what was filed and what it was linked to.** One short message, no fluff.

If multiple URLs arrive at once, batch them: one note per URL, one commit per batch. Do not ask before fetching. Do not ask where to file. Decide and do it.

## GitHub Library

`GitHub Library/` is the external git library: every third-party repo we pull skills, tools, or reference code from, sorted by category. It is **not** Orwell's own code (that lives in the live repos linked from each area in the map below). Map note: [[GitHub Library]].

- **Structure.** One file per category, named after the category. A master list lives in the map note. Each repo is a row: name/link, what it is, what we'd pull, which Orwell area it feeds, and status (`using`, `evaluating`, `shelf`).
- **Filing a git link.** When I drop a repo, pick the category, add a row to that category file and to the master list in the map note, set status, note any area it feeds. New category if none fits. One commit per batch, tell me after.
- **Internal vs external.** Our own reusable workflows stay in `Skills/`. `GitHub Library/` is only for outside repos.

## Skills

Reusable workflows in `Skills/`:

- File Inbox - sort a dump into the right place
- Query - answer a question from the vault
- Lint - vault health check
- Save Conversation - file the current chat as a structured note
- Daily Summary - end-of-day summary and tomorrow's plan
- Weekly Review - what moved, what stalled, open loops
- Grading Review - monthly re-grade of priorities
- New Project - scaffold a new project (including promoting one from research)
- Intelligence Report - daily AI news brief from the feed list (see [[Intelligence Feed Sources]])

## House style (law)

- British English. No em dashes anywhere.
- Fonts for any built document: Inter, with IBM Plex Mono for code and labels.
- Accent colour `#2752E6`. White backgrounds.
- Banned words: delve, meticulous, comprehensive, leverage, seamless, robust, and the rest in [[House Style]].
- Operational documents are tickable instruction manuals.

## The map

| Area | What it is | Repos |
|---|---|---|
| [[Agent Org]] | The humanless-company engine | orwell-marketing, pet-transport (souls) |
| [[SEO Portfolio]] | Programmatic SEO lead-gen | pet-transport, funeral-repatriation, closeprotectionhure-com, global-bus-hire, pest-control-usa |
| [[Comparison Network]] | UAE comparison sites | mortgagecompare-ae, moneycompare-ae, insurecompare-ae, companyformation.ae, legalconsultants.ae |
| [[CRM Systems]] | CRM back-ends | mc-crm, logistics-crm, global-bus-rental-crm, firswood-crm |
| [[Products]] | Software and one game | jarvis (George), klientflo, klientflo-v2, Orwell-Corp, equityngin, northlands, daily-chex, wellreplied-site |
| [[Ventures]] | Research bets | energy-claims-scraper, GPU compute, KDP, property opportunities |

## The shelves (non-area sections)

| Section | What it is | Map note |
|---|---|---|
| Research | The idea shelf, pre-project | [[Research]] |
| GitHub Library | External third-party repos we pull from | [[GitHub Library]] |
| Reference | Durable knowledge and decision records | [[House Style]], [[Priority System]], [[Orwell Corp Stack Decisions]] |
| Intelligence Reports | Daily AI news briefs | [[Intelligence Feed Sources]], [[Daily Report Template]] |
