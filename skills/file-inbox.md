---
title: Skill - file inbox
tags: [skill]
trigger: "file the inbox", "sort this", or any raw dump in chat
updated: 2026-06-22
---

# Skill: file the inbox

Run this when I dump information at you in chat, or when `_inbox/` has loose notes.

## Steps

1. Read the dump, or every file in `_inbox/`.
2. For each item, decide the destination:
   - ongoing domain to the right `areas/` folder
   - time-boxed work with one goal to a folder in `projects/`
   - durable knowledge to `reference/`
   - cannot place confidently: leave in `_inbox/` with a `#needs-filing` tag and flag it to me
3. Name the file `YYYY-MM-DD-topic.md`, lower-case, hyphenated.
4. Add frontmatter: title, area, tags, updated.
5. Add `[[wikilinks]]` to the relevant area `_index.md` and any related notes.
6. Check for duplicates. If it extends an existing note, append rather than create a new one.
7. Write a one-line entry into today's daily note in `00-dashboard/daily/`.
8. Commit with a clear message.

## Rules

- Do not ask me which folder. Decide. Only ask if genuinely ambiguous.
- Apply house style.
- Keep it text-only.
