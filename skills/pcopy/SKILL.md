---
name: pcopy
description: Copy a piece of the last response to the clipboard (macOS).
argument-hint: [what to copy — e.g. "curl command", "the JSON", "second code block". Empty = whole last code block]
---

# pcopy

Copy something from the previous assistant message to the clipboard via `pbcopy` (macOS).

**What:** `$ARGUMENTS` non-empty → extract the matching piece. Empty → the last fenced code block; no block → the main answer stripped of filler. Raw content only, no fences or preamble.

**How:** heredoc into `pbcopy`. Use the sentinel `PCOPY_EOF`; change it if the payload contains that string.

**After:** one line, `Copied <what> (<N> chars).` Nothing else. Can't find a match → say so, do nothing.
