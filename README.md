# skills that ship

Claude Code skills I actually use to ship faster. Not prompts you paste, skills you install: each one becomes a `/command` your agent runs on demand.

Six of them, the ones that earn their place.

## Install

Clone the repo, then point Claude Code at the skills you want. A symlink keeps them live (edit the file here, it updates everywhere). Use `cp` instead if you'd rather have a frozen copy.

```bash
git clone https://github.com/Pawel-Kica/skills-that-ship.git
cd skills-that-ship

# Live link (edit once, updates everywhere):
for s in skills/*/; do
  name="$(basename "$s")"
  mkdir -p ~/.claude/skills/"$name"
  ln -sf "$PWD/${s}SKILL.md" ~/.claude/skills/"$name"/SKILL.md
done

# Or copy, no live link:
# cp -r skills/* ~/.claude/skills/
```

Reload Claude Code and type `/` to see them. The clipboard and browser bits use `pbcopy` and `open`, so those are macOS; the rest is portable.

## How to write a skill that ships

No framework, just what works.

1. **Terse beats prose.** A skill is instructions for a model, not an essay for a human. Cut every word the model doesn't need.
2. **One job per skill.** A variation is a new skill, not a bigger one.
3. **A sharp trigger and description.** That's how the agent (and you) find it. Say what it does and when to fire it.
4. **Procedure, not philosophy.** Numbered steps, exact commands, real paths. "Run X, then Y" beats "consider doing X".
5. **Say when NOT to use it.** The best skills name their own edges, so the agent doesn't reach for them wrong.

## The skills

### handoff

Compacts the conversation into a doc a fresh agent can resume from. For when context is full or you're switching machines and you want the next session to start where this one ended.

### implement-handoff

The other half. Describe a handoff loosely ("the reminder one"), it finds the file, summarises the status, and picks the work back up.

### html

Renders a non-trivial answer as a self-contained HTML page and opens it. Decision trees, diffs, dashboards, diagrams: anything that's worse as a wall of markdown.

### pcopy

Pulls one piece out of the last reply to your clipboard: the curl command, the JSON, the second code block. No mouse, no reselecting. (macOS.)

### propose-steps

Plan before execute. Lays out the exact steps, tools, and commands, then waits for your OK. No disk artifacts, no surprises.

### afk-mode

Hand it the wheel. Takes the task end to end with no clarifying questions, notes the defaults it picked, and leaves a report when it's done.

## License

MIT
