# AGENTS.md

Asteroids clone. HTML5 Canvas, vanilla ES6+ JavaScript. No framework, no bundler, no package.json, no tests, no linter.

## Run

Open `index.html` directly in browser, or:

```bash
npx serve .   # http://localhost:3000
```

No build step. Edit `game.js`, reload page.

## Architecture

- Entire game in one file: `game.js` (~420 lines), loaded via `<script>` from `index.html`.
- Canvas fixed 800×600 (`W`/`H` constants in `game.js`).
- Entities: `Ship`, `Bullet`, `Asteroid`, `Particle` classes, each with `update(dt)` + `draw()`.
- Game state machine in module-level vars: `state` ∈ `'playing' | 'dead' | 'gameover'`.
- Toroidal space: positions wrapped with `wrap(v, max)`; don't remove wrap or objects vanish at edges.
- Input: `keys` (held) + `justPressed` (edge). `pressed(code)` consumes the flag — call at most once per frame per code.
- Main loop: `requestAnimationFrame`, dt clamped to 0.05s.

## Conventions

- Comments, UI strings, and README in Spanish. Keep new ones in Spanish.
- README features list is aspirational: power-ups and "estrella fugaz" mentioned but NOT implemented. Don't trust README for behavior; `game.js` is source of truth.
