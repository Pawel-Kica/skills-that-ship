---
name: handoff
description: Compact the current conversation into a handoff doc a fresh agent can resume from.
argument-hint: "What will the next session focus on?"
---

# Handoff

Summarise the conversation so a fresh agent can continue. Save to `~/.claude/handoffs/` (the global `.claude`, not the workspace). Create the dir if it's missing.

A "Suggested skills" section is required. Don't duplicate PRD / plan / ADR / issue / commit / diff content, reference it by path or URL. Redact secrets and PII.

The user's args are the next session's focus. After saving, copy the path to the clipboard (`printf '%s' <path> | pbcopy` on macOS), then confirm the path.
