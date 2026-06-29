# AGENTS.md

Vanilla JS PacMan. No build, no bundler, no tests, no lint, no package manager.

## Run

Open `src/index.html` directly in a browser (file://). No dev server required.

## Architecture

Scripts are plain `<script>` tags loaded in fixed order from `src/index.html`:
`maze.js -> game.js -> render.js -> main.js`. They share globals (`MAZE`, `createGame`,
`update`, `draw`) — there are no ES modules. Break that load order or move a
function across files and the game breaks silently.

- `maze.js` — maze definition (`MAZE_STR`, parsed `MAZE`).
- `game.js` — state (`createGame`), loop step (`update`).
- `render.js` — canvas drawing (`draw`, `TILE = 20`).
- `main.js` — loop, keyboard, overlay/UI wiring. Entry point.

## Spec-driven workflow

This repo exists to practice spec-driven dev via the `/spec` and `/spec-impl` skills
(see `.agents/skills/`). Specs are written into `specs/`. `/spec` only designs and
asks questions — it does not write code. `/spec-impl` branches off an approved spec.
When using those skills, reply in the same language as the user's prompt.

## Conventions

UI text and `README.md` are in Spanish — match that language for user-facing strings
and specs unless asked otherwise. Code identifiers and comments are English.
