# NeuroRush

**Neural Reflex Protocol** — a rapid-fire arcade test of reflex, precision, cognition, and perception.

Four escalating modules. One life pool. Every level gets faster, tighter, and more deceptive.

▶ **[Play the latest build](https://htmlpreview.github.io/?https://raw.githubusercontent.com/Buggydemon/neurorush/main/neurorush.code.html)**

> `raw.githubusercontent.com` serves the file as plain text, so use the preview link above to actually play.

---

## Modules

| Module | Tests | How it works |
| --- | --- | --- |
| **SIGNAL** | Reflex | Wait for the orb to go live, then tap — too early or too late costs a life. |
| **ALIGN** | Precision | Stop a sweeping marker inside the shrinking target window. |
| **STROOP** | Cognition | Answer the on-screen rule (match the word, the arrow, or invert it) under a short timer. |
| **SCAN** | Perception | Tap the one tile whose shade differs from the grid. |

Modules are drawn without repeating the same type twice in a row, and the difficulty curve tightens every level:

- Reflex waits get shorter and the reaction window narrows.
- Precision markers speed up while target zones shrink.
- Cognition adds a rule-inversion variant from level 6 and shortens the timer.
- Scan grids grow from 3×3 to 5×5 as the color delta shrinks.

## Gameplay

- **5 lives (INTEGRITY)** — a failed module costs one.
- **Streaks** — every 10 consecutive clears grants **+1 life** (capped at 5).
- **Best score** — highest level cleared is saved locally and shown on the menu.
- **Instant restart** — the next level begins automatically after each result.

## Controls

| Action | Input |
| --- | --- |
| Start / retry | `Space`, `Enter`, or click |
| SIGNAL / SCAN | Click or tap the orb / tile |
| ALIGN | Click, tap, or `Space` |
| STROOP | `←` `→`, or tap either half of the screen |
| Mute | Mute button (top right) |

Touch and mouse are treated identically, and keyboard input never leaks between levels.

## Run locally

No build step, no dependencies, no server required:

```bash
# Download neurorush.code.html and open it in any modern browser
start neurorush.code.html
```

Or serve the folder:

```bash
python -m http.server 8000
# http://localhost:8000/neurorush.code.html
```

## Tech

- Vanilla HTML, CSS, and JavaScript in a **single file** — no frameworks, no build tooling.
- One clamped `requestAnimationFrame` loop drives the timer and all mini-games.
- Web Audio API for synthesized sound effects (lazy-init, respects mute).
- `localStorage` for best score and mute preference.
- Responsive from 320 px up, including landscape phones, safe-area insets, and `prefers-reduced-motion`.
- Accessible focus states, semantic buttons, and a live region for status messages.

## Repository layout

```
neurorush.code.html   # the entire game (HTML + CSS + JS)
README.md
```

To serve it as a site, enable **Settings → Pages → Deploy from branch → `main` / root** and rename the file to `index.html`, or visit `/neurorush.code.html` directly.

## License

No license specified — all rights reserved by the author.
