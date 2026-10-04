# fshbet.github.io

Personal engineering code archive, served at **<https://fshbet.github.io>**.

A single static page indexing thirteen projects — AI agents, orchestration, automation
frameworks, knowledge and data platforms, trading infrastructure and a parametric CAD
enclosure — with token-level measurements and an honest statement of what each project does
and does not yet do.

## Contents

| File | Purpose |
|---|---|
| `index.html` | The entire site. No build step, no dependencies, no framework. |

The page is self-contained apart from two webfonts (IBM Plex Sans and JetBrains Mono) loaded
asynchronously from Google Fonts, with a system-font fallback so first paint never blocks.
Roughly 24 KB over the wire, gzipped.

## Design

Dark-first, with a light theme available from the header toggle and a system-preference
default. Colour, type, spacing and radius are defined as CSS custom properties at the top of
the file; change a token there and the whole page follows.

- **Type** — IBM Plex Sans for narrative prose, JetBrains Mono for every machine-readable
  figure: repository names, token counts, file counts, status labels and section markers.
  The split is deliberate: prose reads as writing, metadata reads as measurement.
- **Colour** — graphite surfaces, one cyan accent reserved for links, active state and data
  emphasis. Status uses its own restrained green / amber / neutral set and is never carried
  by colour alone — every status chip pairs its colour with an icon and a word.
- **Structure** — hairline grids, section numbers, no decorative illustration. Each project
  carries a small inline SVG glyph drawn from what it actually is (a board, a node graph, a
  camera, a wireframe enclosure).

## Behaviour

Vanilla JavaScript, no libraries, degrading cleanly when it fails:

- Theme toggle, persisted in `localStorage` and resolved before first paint.
- Status, domain and free-text filtering over the project index; the technology landscape
  doubles as a filter.
- Per-project detail in native `<details>` panels, opened automatically when a project is
  deep-linked.
- Section reveal, bar growth and metric count-up, all suppressed under
  `prefers-reduced-motion` and all guaranteed to settle on the real figure.

Accessibility targets WCAG 2.2 AA: skip link, visible focus, semantic headings, 44px touch
targets, a text-table alternative to the token chart, and no horizontal overflow down to
375px.

## Editing

Edit `index.html` and push to `main`. GitHub Pages redeploys automatically.

Project facts live in the markup, not in a data file. When a project changes, update its
card, its row in the token-weight chart and the table beneath it, and the archive totals in
the hero and the `§01` grid.

## Measurement methodology

Token counts are produced with tiktoken `cl100k_base` across source, test, documentation and
configuration files. Dependencies, virtual environments, lockfiles, generated API schemas,
minified bundles and build output are excluded from every figure — including the exported
STL meshes of the CAD project, which are build output of its OpenSCAD source.

Per-repository documentation share is derived from those same counts: a repository's
documentation tokens as a percentage of its own total.
