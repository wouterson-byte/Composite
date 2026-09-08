# CLAUDE.md

This file provides guidance to Claude Code when working within
`fibre-composites-course/`. It is a standalone mini-course site, built
once from a fixed set of slides, and is **not** part of the tool portal
at the repo root (not linked from the root `index.html` tool grid, not
subject to its "one file per tool" rule — this project has its own
single-file rule below).

## Stack & Conventions

- **Single-file project.** The entire site lives in one `index.html`
  in this folder. All CSS in `<style>` tags, all JavaScript in
  `<script>` tags, both inlined in `index.html`. No separate `.css`/
  `.js` files, no other HTML pages — every section is a div shown/
  hidden by JS, not a separate URL.
- **Vanilla only.** Plain HTML, CSS, and JavaScript — no frameworks,
  no build step. Tailwind CSS via CDN for styling. Any other library
  must be linked from a CDN, never installed via a package manager.
- **No backend, no database.** Fully static.
- **Light/dark theme toggle**, choice remembered across visits via
  `localStorage`.
- **One-time content build, not a tool.** The 5 lessons are transcribed
  once from slide images shared directly in conversation and hardcoded
  into the page's content data. There is no upload feature and no
  visitor-facing way to change the content.
- **Lesson voice.** Each section is written as normal course prose for
  polytechnic students meeting the topic for the first time — not a
  slide-by-slide transcript. Text only, no embedded images/diagrams.
- **Navigation.** A nav element lists all 5 section titles (jump to
  any section directly) plus Prev/Next controls at the bottom of each
  section. Free browsing — no progress tracking, no "read" state.

## Feature Plan

Status legend: not started / in progress / done. Prune completed
phases' detail over time — keep this section skimmable.

### Phase 1 — Skeleton + navigation shell (not started)
- Data model: a JS array of 5 section objects —
  `{ id, title, body, recap }`, where `body` is the lesson prose
  (HTML string or array of paragraph strings) and `recap` is an array
  of short "Key Takeaways" bullet strings.
- Key flow: page renders the nav (title list + Prev/Next) from this
  array, one section visible at a time, toggled via JS (no page
  reload, no routing). Theme toggle wired to the shared `localStorage`
  pattern.
- Content in this phase is placeholder text — structure only.

### Phase 2 — Populate lesson content (not started)
- Fill in `body` and `recap` for each of the 5 sections, one per slide,
  as slides are shared in conversation.
- Goal: every section reads as a finished lesson with a Key Takeaways
  recap at the end — no leftover placeholder text.

### Phase 3 — Polish (not started)
- Responsive check (mobile nav collapse), keyboard/focus handling for
  Prev/Next and nav links, visual pass on both themes.
