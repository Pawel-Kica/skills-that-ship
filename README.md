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

No framework, just what works. Same idea as a [prompt that ships](https://github.com/Pawel-Kica/prompts-that-ship), with one flip.

### 1. Write the steps, not the goal

A prompt sets a goal and lets the agent find the path. A skill is the opposite: a path you have already walked and want to repeat. So write the steps, the exact commands, real paths, in order.

### 2. Keep it short

A skill loads every time it fires, so every word costs you. Cut the words the model does not need. Short and plain beats long and polished.

### 3. A clear description, or it gets ignored

The trigger and description are all the agent sees when it decides whether to use the skill. Vague, and it just sits there. Say what it does and exactly when to use it.

## The skills

### 1. 📤 handoff

Compacts the conversation into a doc a fresh agent can resume from. For when context is full or you're switching machines and you want the next session to start where this one ended.

### 2. 📥 implement-handoff

The other half. Describe a handoff loosely ("the reminder one"), it finds the file, summarises the status, and picks the work back up.

### 3. 🌐 html

Renders a non-trivial answer as a self-contained HTML page and opens it. Decision trees, diffs, dashboards, diagrams: anything that's worse as a wall of markdown.

### 4. 📋 pcopy

Pulls one piece out of the last reply to your clipboard: the curl command, the JSON, the second code block. No mouse, no reselecting. (macOS.)

### 5. 🗺️ propose-steps

Plan before execute. Lays out the exact steps, tools, and commands, then waits for your OK. No disk artifacts, no surprises.

### 6. 🤖 afk-mode

Hand it the wheel. Takes the task end to end with no clarifying questions, notes the defaults it picked, and leaves a report when it's done.

## License

MIT
