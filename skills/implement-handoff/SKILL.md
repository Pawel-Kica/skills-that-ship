---
name: implement-handoff
description: Find a handoff from a loose description and continue the work.
argument-hint: "Which handoff? (e.g. 'reminder seconds')"
---

# Implement handoff

Find a handoff from the user's loose description, no path pasting. Handoffs live in `~/.claude/handoffs/` as `handoff-<timestamp>.md` or `handoff-<prd-name>-<timestamp>.md`.

List the dir. Match on filename and content. One match → read it fully. Several → take the newest timestamp; if they're different topics, list them (filename + gist) and ask. Empty or no match → say so, list the recent ones newest-first, stop. No arg → list recent, let the user pick.

Give a 2-3 line summary (status + next step). Then implement: run the suggested skills, don't wait. Stop only on a blocking unknown the handoff can't answer.
