---
name: propose-steps
description: Lay out the steps for a task without executing them.
---

# Propose Steps

Propose, don't execute. Lightweight, no artifacts on disk.

## Procedure

1. A numbered list in execution order. No prose preamble.
2. Each step:
   - **Action** + a one-line why
   - **Tool** (Bash, Edit, gh, etc.)
   - **Exact** command, message body, or file:line diff intent (real, not paraphrased)
   - **Reversible:** yes/no
3. End with: "Approve to execute, or tell me what to change."

## Rules

- No mutations. Read-only tools (Read, Glob, Grep, read-only MCP) are fine for grounding.
- Real text. `git commit -m 'fix: ...'`, not "I would commit".
- If a step depends on a prior step's output (e.g. a PR number from `gh pr create`), say so.
- Partial approval is fine ("do 1-3, skip 4"), re-confirm the rest, execute only the approved subset.

## When NOT to use

- User said "afk" / "just do it" → execute.
- A pure question with no action implied → just answer it.
- A trivial single action ("rename this var") → just do it.
- Real feature work spanning many files → use a planning skill that writes artifacts to disk.
