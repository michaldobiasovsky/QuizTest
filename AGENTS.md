# QuizTest – AGENTS.md

## Project

Single-page HTML/CSS/JS vocabulary quiz app (CZ UI, EN↔CZ vocab). No build system, no framework, no package manager.

## Dev server

```bash
python3 -m http.server 8080
# or: npx serve .
```

Opening `index.html` via `file://` breaks PDF.js (CORS). Always serve via HTTP.

## Architecture

- **`index.html`** — the entire app: markup, styles (embedded `<style>`), logic (embedded `<script>`)
- State persisted in `localStorage` key `study_db_v62`
- PDF import via `pdfjsLib` from CDN

## Important conventions

- UI strings and comments are in **Czech** (do not translate them)
- Data model: `{ term, def, asked, correct }` — `term` = EN, `def` = CZ
- No tests, no linting, no typechecking, no CI
- Git history uses Czech commit messages
