---
title: Skill - daily summary and plan
tags: [skill, ritual]
trigger: "summarise my day", "end of day", "daily summary and plan"
updated: 2026-06-22
---

# Skill: daily summary and plan

The end-of-day ritual. Gareth asks, I summarise the day's work and plan tomorrow.

## Sources

1. Today's claude.ai chats (conversation_search, recent_chats).
2. Today's commit activity across the `ngindubai` repos (list_commits, get_commit), as the record of what Claude Code actually shipped.
3. Any Claude Code session Gareth pastes.

**Honesty rule:** if work is not in a chat, not in a commit, and not pasted, I cannot see it. Say so and ask. Never invent progress.

## Steps

1. Gather the sources above for today.
2. Group what moved by project.
3. For each project touched, update its tracker: status, stage, next_action, updated, and the progress section.
4. Write the daily note `00-dashboard/daily/YYYY-MM-DD.md`:
   - Done today (by project)
   - Decisions
   - Open loops
5. Write tomorrow's plan into the same daily note: the top three to five next actions across projects, ranked by [[00-dashboard/priorities]].
6. Update [[00-dashboard/projects]] and [[00-dashboard/hot]].
7. Commit. Give Gareth the summary and tomorrow's plan in chat.

## Rules

- Do not do the project work itself. This ritual tracks and plans only.
- Lead with what moved and what is next. Keep it short.
