---
name: afk-mode
description: Take a task end to end, autonomously, with no clarifying questions.
---

# AFK Mode

A modifier on the current task, not a session state. "afk, research X" means: research X deeply, autonomously, end to end. Don't reply "AFK on, ready when you are." Don't wait. Don't ask. Acknowledge in one line max, then plan and execute in the same turn.

A bare "afk" with nothing in flight → ask what to do. Otherwise apply it to whatever is in flight.

## Procedure

1. No preamble. One short line is fine ("Going deep, plan first."), then step 2 in the same turn.
2. Plan with a todo list. Concrete, ordered, verifiable steps.
3. Execute. Mark in_progress → completed.
4. Self-review the diff: stray logs, half-applied refactors, unused imports, broken tests, missed edges. Fix them.
5. Final report:

```
## AFK report
**Task:** <one-line restatement>
**Status:** Done / Done with caveats / Blocked
**What changed:** <file: one-line why>
**Verified by:** <test/manual check + result>
**Assumptions made:** <decisions taken without asking>
**Open questions:** <only if blocking>
**Suggested next:** <if applicable>
```

A pure-research task → swap "What changed" for "What I found", "Verified by" for "Sources".

## Rules

- Ambiguity → reasonable judgment, note the assumption, continue. Surface it in the final report.
- Think hard on every non-trivial decision.
- Use subagents (a read-only explorer for codebase research, a planner for architecture, parallel agents for independent investigations).
- Verify your own work: tests, types, lint, build, a manual click-through if it's UI. No "code looks right". Can't verify → say so.
- Stay in scope. AFK = "do it thoroughly", not "rewrite the codebase".

## Safety (still applies)

- No destructive git without prior authorization (force-push, reset --hard, branch -D, rm -rf on tracked paths).
- No push, PRs, or messages on the user's behalf unless the task says so.
- No committing secrets. No `--no-verify`.
- Hit something irreversible and unauthorized → STOP, note it in the report.

## When NOT to use

- The path forward genuinely needs user input → one question beats an hour of spinning.
- Irreversible external actions (prod deploys, paid APIs at scale) without prior authorization.
