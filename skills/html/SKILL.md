---
name: html
description: Render a non-trivial answer as a self-contained HTML page and open it in the browser.
---

# HTML

When the output is non-trivial, a single `.html` you open in the browser beats a wall of markdown. (Idea popularized by Thariq Shihipar's html-effectiveness.)

See [`examples/`](https://github.com/Pawel-Kica/skills-that-ship/tree/main/skills/html/examples) for ready-to-crib pages in this exact style: a decision tree, a comparison matrix, an annotated code review, a report dashboard, and an inline-SVG diagram. Open `examples/index.html` for the gallery.

Explicit trigger only. When invoked: read the context, pick a category, ship. Don't ask what they want.

## Categories

| Category | Use for |
|---|---|
| Exploration / Planning | Decision trees, option matrices |
| Code Review | Diff annotations, risk callouts |
| Design | Visual comparisons |
| Prototyping | Throwaway UI |
| Diagrams | Architecture, flows, state machines |
| Decks | Slide-style sections |
| Research | Multi-source synthesis, comparisons |
| Reports | Summaries, metrics, dashboards |
| Custom editors | One-off data tools |

Out of scope: production app UI and page redesigns, route those to a dedicated design skill.

## Rules

Self-contained `.html`. Inline CSS/JS, no build. CDN libs only when earned (Chart.js, D3, Mermaid). Mock data inline as a JS const. An eye-readable layout beats clever source. Throwaway by default.

## Style

Minimal: cream `#F6F2EA`, near-black text, serif headlines, sans body, accent `#C8553D` used sparingly, max-width 720-900px for prose. No shadows, gradients, or emoji. "Make it pop" → go bolder and commit.

Stuck for a layout: crib from the [`examples/`](https://github.com/Pawel-Kica/skills-that-ship/tree/main/skills/html/examples) folder, one per category.

## Output

Write to `/tmp/claude-html/<slug>.html` (or your project's artifacts folder if you keep one).

After: print the path, run `open <path>` (`open -a "Google Chrome" <path>` to force the browser), and give a one-sentence summary. The file is the answer.
