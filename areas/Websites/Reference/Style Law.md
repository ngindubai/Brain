---
title: Style Law
tags: [websites, style, content-rules, reference]
updated: 2026-07-22
---

# Style Law

The writing law shared by every site, enforced by the humanising worker and the style gate. Site CLAUDE.md files carry site specific additions (personas, English variant); this is the common core. It exists because the sites win by producing genuine information gain and natural prose at the same time, not by tricking a detector.

## Absolute bans

- **No em dashes, ever, anywhere.** Not in headings, tables, JSON, schema, code comments or chat. No double hyphen or en dash substitutes. Restructure with commas, colons, full stops or brackets.
- **Banned words** (single canonical list; site check scripts must match it): delve, meticulous, comprehensive, tailored, navigate, leverage, seamless, robust, vital, crucial, utilize, intricate, paramount, pivotal, embark, foster, elevate, unleash, unlock, harness, streamline, holistic, realm, landscape (figurative; literal terrain is allowed), testament, tapestry, vibrant, bustling, nestled, cornerstone, myriad, plethora, multifaceted, underscore, moreover, furthermore, additionally, notably, essentially, ultimately, nuanced, boasts, empower, unpack, beacon, facilitate, ever evolving, cutting edge, game changer, fast paced.
- **Banned frames**: "Not only X but also Y", "It's not just X, it's Y", "Whether you're X or Y", "From X to Y", "In the world of", "In the realm of", "Let's dive in", "dive into", "embark on", "it is worth noting", "it is important to note", "when it comes to", "in conclusion", "at the end of the day", "in today's fast paced world", "navigate the complexities", "a testament to", "plays a crucial role", "rest assured", "look no further". Never close on a summary or reflective wrap up; end on a concrete point.
- **Never invent**: statistics, rates, prices, ratings, reviews, testimonials, certifications, credentials, first person anecdotes, company histories. On content sites every figure is a sourced dated claim in claims.json; on programmatic sites every fact comes from the entity data record. A vendor sourced number is labelled as a vendor estimate, never laundered.

## The human signals

- **Burstiness is the strongest signal.** Follow a 25 word sentence with a 4 word one. Use the odd fragment. Never three same shaped sentences in a row. Vary paragraph length hard: one line paragraphs allowed.
- **Contractions** in body prose, never in schema JSON or table cells.
- **Concrete over abstract**: digits for figures, real place names, real prices in the correct currency, named regulations with codes, actual timeframes.
- **Cut hedging**: one hedge per few hundred words at most; never stack generally, typically, in most cases.
- **Sentence case headings.** The occasional genuine question, answered, sparingly.

## Information gain (the ship test)

Before drafting, name the one specific fact, figure, rule, cost, process step or comparison this page has that competitor pages do not. No gain, no ship. A page with nothing new is scaled content spam, humanised or not.

## Template footprint (the scale penalty defence)

- Never open sibling pages with the same sentence frame; open on this page's own number, authority, scenario or question.
- Rotate section order and count where the subject allows. Vary FAQ heading wording, closing section labels and meta description structure across siblings.
- Never repeat a boilerplate sentence verbatim across pages (over 8 words duplicated fails the gate); paraphrase per page.
- Multi pass self critique on every page: draft, hunt for repeated sentence shapes, banned words, uniform paragraphs, a template identical opening, missing gain, unsupported claims; revise; re check.

## YMYL guard (always on for regulated and health adjacent niches)

Accuracy outranks every stylistic rule: if a humanisation technique risks a wrong statement, drop the technique. Personas are editorial bylines, not a licence for fabricated experience. Every figure matches the site's canonical facts and data files and carries a named dated source.

## Per site variables (set in the site CLAUDE.md, never assumed)

- English variant: British for UK and UAE, American absolutely for US sites (banned British spellings listed by word in the pest-control-usa CLAUDE.md).
- Author model: named persona pool, real founder byline, or Organization desk. Never Gareth's name on the programmatic sites.
- Tone brief for the audience (anxious pet owner, stressed homeowner, expat borrower).
- Contact surface (WhatsApp and form only on pet-transport; no email stated).
