# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Stack & Conventions

- **Single-file project.** The entire project must live in one `index.html` file. All CSS goes in `<style>` tags and all JavaScript in `<script>` tags, both inlined directly in `index.html` — never in separate `.css` or `.js` files. No additional HTML pages. Linking external images, CSS libraries, and JavaScript libraries (e.g. via `<link>`/`<script src>` to a CDN) is allowed. This constraint exists so the finished project can be copy-pasted as a single file for sharing in class and on single-file code platforms.
- **Vanilla only.** Use plain HTML, CSS, and JavaScript only — no frameworks (React, Vue, Tailwind build, etc.) and no build step. If a library is needed, link it from a CDN in `index.html` rather than installing it via a package manager.
- **Portal exception.** This project is a portal of many small tools, so the single-file rule applies per *tool*, not per *project*: `index.html` is the portal and links out to tool pages rather than inlining every tool. Each tool is its own self-contained, kebab-case `.html` file at the repo root (e.g. `pomodoro-timer.html`), so it stays independently copy-paste-able and shareable on its own.

## Tech stack (hard constraints — do not deviate)
- Vanilla HTML, CSS, and JavaScript only. No React, Vue, or any JS framework.
- Tailwind CSS for all styling (via CDN only).
- No backend, no database. Fully static site.
- A toggle for light and dark theme, with the choice remembered
  across visits.

## Working conventions
- Before implementing any non-trivial feature, ask clarifying
  questions about scope, edge cases, and constraints first —
  don't propose a plan until you've asked.

## Feature Plan

Status legend: not started / in progress / done. Prune completed phases'
detail over time — keep this section skimmable.

### Phase 1 — Portal + first 2 tools (done)
- Proved the browse-and-link pattern: portal renders a tool-array-driven
  card grid, each card links to a standalone tool page, theme persists
  across navigation via a shared `localStorage` key, every tool page
  links back to the portal.
- Files: `index.html`, `pomodoro-timer.html`, `unit-converter.html`.

### Phase 2 — Add tools beyond the first two (not started)
- Goal: grow the collection without changing the portal's structure.
- Flow: adding a tool = one new kebab-case `<tool-name>.html` file + one
  new entry in the portal's tool array. Nothing else changes.

### Phase 3 — Organize the collection (not started, as needed)
- Goal: once the list is long enough that a flat card grid stops being
  browsable, add lightweight organization (e.g. categories and/or a
  client-side search/filter box) on top of the same data array — no
  backend, no build step.
