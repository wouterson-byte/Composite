# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Stack & Conventions

- **Single-file project.** The entire project must live in one `index.html` file. All CSS goes in `<style>` tags and all JavaScript in `<script>` tags, both inlined directly in `index.html` — never in separate `.css` or `.js` files. No additional HTML pages. Linking external images, CSS libraries, and JavaScript libraries (e.g. via `<link>`/`<script src>` to a CDN) is allowed. This constraint exists so the finished project can be copy-pasted as a single file for sharing in class and on single-file code platforms.
- **Vanilla only.** Use plain HTML, CSS, and JavaScript only — no frameworks (React, Vue, Tailwind build, etc.) and no build step. If a library is needed, link it from a CDN in `index.html` rather than installing it via a package manager.

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
