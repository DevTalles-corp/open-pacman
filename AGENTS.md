# AGENTS.md

Pac-Man-like game built to learn **spec-driven development**. No code yet — every feature is delivered through the spec workflow, not by ad-hoc code edits.

## Stack

- Vanilla JS, HTML, CSS. No bundler, no framework, no package manager.
- Run by opening `index.html` directly in a browser. No build step, no npm scripts — do not invent them.

## Workflow (the important part)

This repo's whole point is the spec-driven method. Features are not coded directly.

1. `/spec "<feature>"` — design a spec in `specs/`, section by section, ending in `Draft`. This skill never writes code.
2. Human reviews and flips `Status:` to `Approved` (or `Aprobado`).
3. `/spec-impl NN-slug` — validates the state means Approved, creates/switches to branch `spec-NN-slug`, then implements the plan one step at a time, pausing for diff review after each step.

Specs live in `specs/`, named `NN-slug.md`. Valid states: `Draft`, `In review`, `Approved`, `Implemented`, `Obsolete` (Spanish equivalents: `Borrador`, `En revisión`, `Aprobado`, `Implementado`, `Obsoleto`). `spec-impl` refuses anything that doesn't mean Approved.

## Language

README and user are Spanish. Reply to the user in Spanish; spec content follows the user's language too.

## Don't

- Don't write feature code without an Approved spec — that defeats the project's purpose.
- Don't reinstall the `/spec` / `/spec-impl` skills — they're locked in `skills-lock.json` and live in `.agents/skills/`.
- Don't add build tooling, `package.json`, or test runners unless a spec calls for it.
