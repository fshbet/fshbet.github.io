# fshbet.github.io

Personal project index, served at **<https://fshbet.github.io>**.

A single static page summarising eleven projects — AI agents, orchestration, automation
frameworks, data platforms, trading infrastructure and a parametric CAD enclosure — with token-level
measurements and an honest statement of what each project does and does not yet do.

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
minified bundles and build output are excluded from every figure — including the exported
STL meshes of the CAD project, which are build output of its OpenSCAD source.
