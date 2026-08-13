# fshbet.github.io

Personal project index, served at **<https://fshbet.github.io>**.

A single static page summarising eight projects — AI agents, automation frameworks, data
platforms and trading infrastructure — with token-level codebase measurements and an honest
statement of what each project does and does not yet do.

## Contents

| File | Purpose |
|---|---|
| `index.html` | The entire site. Self-contained: no build step, no dependencies, no external requests. |

Styling is inline, fonts come from the system stack, and the page adapts to light and dark
themes via `prefers-color-scheme` with an explicit `data-theme` override.

## Editing

Edit `index.html` and push to `main`. GitHub Pages redeploys automatically.

## Measurement methodology

Token counts are produced with tiktoken `cl100k_base` across source, test, documentation and
configuration files. Dependencies, virtual environments, lockfiles, generated API schemas,
minified bundles and build output are excluded from every figure.
