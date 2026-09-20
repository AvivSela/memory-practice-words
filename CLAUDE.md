# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A single-page, static Hebrew (RTL) web app: a word-set generator for "חמש מילים" (Five Words), a memory-training game. There is no build system, package manager, or server — it's just `docs/index.html` and `docs/words.js`, served from `docs/` (GitHub Pages source), opened directly in a browser.

## Running / testing

There is no build or test tooling. To develop, open `docs/index.html` directly in a browser (or serve the `docs/` directory with any static file server) and reload after edits.

## Architecture

- **`docs/words.js`** — defines the word bank (`bank`), a plain object keyed by semantic category (animals, objects, nature, places, food, people_life, household, misc). Each word is `{w: "<hebrew word>", j: 0|1}`, where `j:1` marks a "juicy" (vivid/concrete/imageable) word and `j:0` a neutral one. Add/edit/remove words only in this file. Before adding words, read `WORD_SELECTION_GUIDE.md`, which documents the clinical/psycholinguistic rationale (concreteness, frequency, word length, semantic clustering, phonological/visual letter similarity, unpointed-Hebrew ambiguity, etc.) behind what makes a word a good or bad fit, and gives a concrete checklist to apply per candidate.
- **`docs/index.html`** — everything else: styles, markup, and all app logic in one inline `<script>` at the bottom. It has two tabs/screens toggled via `switchTab()`:
  - **Practice screen** — generate one set at a time, click words you remembered, track score, and persist a scoring history to `localStorage` (key `fiveWordsHistory`).
  - **Worksheets screen** (דפי תרגול) — generate a batch of N sets at once for printing (via `window.print()`), with dedicated CSS under `@media print`.

### Set generation algorithm (`buildSet` in docs/index.html)

Word sets are generated deterministically from an integer seed via a seeded PRNG (`mulberry32`), so the same `(seed, count, level)` always reproduces the same words — this is what makes a set reproducible/shareable from a single number. The pipeline, in order:

1. Shuffle categories with the seeded RNG and pick one word per category (repeating categories if `count` exceeds the category count).
2. `balanceJuiciness()` — nudge the mix of juicy vs. neutral words toward a target ratio that depends on difficulty (`easy` skews juicy/vivid, `hard` skews neutral).
3. `fixDuplicateLetters()` — the final, authoritative pass: guarantees no two words share a first letter and no word repeats, swapping in same-category alternatives (same juiciness where possible). This runs last because it's a hard constraint that must win over the juiciness balance.

When modifying set-generation logic, preserve this ordering — juiciness balancing before the letter-uniqueness fix, not after — since the letter fix is meant to have final say.

### History / persistence

Practice-mode results are stored in `localStorage` under `fiveWordsHistory` (capped at 200 entries, oldest dropped first). Each history entry is keyed by a generated `historyId` and updated in place as the user clicks words (rather than only written once at save time). A code comment in `docs/index.html` notes this is expected to eventually map 1:1 to rows in a `generated_sets` Supabase table if/when the app gets accounts/sync — keep that shape in mind if implementing persistence changes.

## Conventions

- All UI text and comments are in Hebrew; the document is `dir="rtl"`.
- No frameworks or dependencies beyond a Google Fonts stylesheet — keep it that way unless asked to introduce tooling.
- Theming is done via CSS custom properties on `:root`, with a dark variant under `prefers-color-scheme: dark` (overridable via `data-theme="dark"`/`"light"`).
