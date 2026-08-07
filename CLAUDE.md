# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with
code in this repository.

## Project overview

Material for the workshop "Maak een game voor de Fri3d badge met GB Studio",
given by Lars & Wannes De Richter at Fri3d Camp 2024 and 2026. The repo holds
two separate things:

- **The game** — `gb-asteroids.gbsproj` plus `assets/`, a
  [GB Studio](https://www.gbstudio.dev/) 4.x project that compiles to a Game Boy
  ROM. Authored in the GB Studio desktop app, not by hand. `downloads/` holds
  sprites and backgrounds for workshop attendees.
- **The slides** — `slides/`, a [Slidev](https://sli.dev/) deck deployed to
  <https://lars-derichter.github.io/gb-asteroids/>.

Slide content is in Dutch (Flemish); GB Studio UI terms stay in English
(`Add Event`, `On Init`, `Launch Projectile`, `Collision Group`).

The version milestones in the deck (v0.0.0 … v0.4.0) map to
[releases](https://github.com/lars-derichter/gb-asteroids/releases), so
attendees can download the state being built at any point.

## Commands

Run from `slides/`:

- `npm run dev` — dev server with live preview (opens browser)
- `npm run build` — static site to `slides/dist/`
- `npm run export` — export to PDF (needs `npm i -D playwright-chromium` first)

## Architecture

Standard Slidev project inside `slides/`:

- `slides.md` — the spine: headmatter, cover, agenda, `src:` includes, colophon
- `pages/*.md` — one file per section, each opening with a `layout: section`
  divider carrying `number: "0N"` and an `eyebrow:`
- `public/` — the ten GB Studio screenshots, served at the root path

There is no deck-level CSS or components directory: everything visual comes
from the theme.

## Theme

The deck uses `slidev-theme-ldr` (`theme: ldr`), installed as a **Git
dependency** pinned to `github:lars-derichter/ldr-slidev-theme#v1.2.0`. Git deps
do not auto-update; bump the pinned tag to pull new theme commits.

Layouts: `cover`, `section` (`number`/`eyebrow`), `default` (bare `---`),
`two-cols-ldr` (`::left::`/`::right::`), `quote` (`author`), `image-side` and
`image-full` (`image`, `eyebrow`, `caption`, `credit`, `fit`), `end`
(`contact`).

House idioms used throughout:

- Aphorisms and warnings are `<hr class="ldr-rule-maple" />` followed by an
  italic line — **not** `>` blockquotes, which the theme only styles inside
  `layout: quote`.
- Problem/solution pairs use MDC labels on their own line:
  `Probleem {.eyebrow.maple}` / `Oplossing {.eyebrow.sage}`.
- Colour utilities: `forest`, `sage`, `maple`, `ochre`, `ink`, `ink-soft`,
  `ink-faint`.

### Images — two different mechanisms

- **Layout images** (`image:` frontmatter) are root-relative: `/navigator.png`.
  The layout prepends `BASE_URL` itself, because a frontmatter string handed to
  CSS `url()` is opaque to Slidev's asset rewriting.
- **Markdown images** must be **relative**: `../public/sprite-sheet.png` from a
  file in `pages/`. A root-relative `![](/x.png)` works in `npm run dev` but
  fails `npm run build` with `resolves outside of Vite server.fs.allow`.

The GB Studio screenshots all use `fit: contain` — the default `cover` crops,
which is fine for photography and wrong for a UI capture.

Size things inside a slide in `rem`/`px`, never `vh`: the slide is a fixed
980×552 canvas that gets transform-scaled, so viewport units measure the browser
window instead.

## Conventions

- Section pages use `transition: slide-left` in their frontmatter.
- Headings are `#` on cover/section/end slides, `##` on content slides, `###`
  inside columns and on `image-full`. Sentence case, never Title Case.
- No `<v-click>` reveals: this is a follow-along workshop, so every bullet is
  visible at once.
- Prettier is configured with `prettier-plugin-slidev` to parse `slides.md` and
  `pages/*.md` with the Slidev parser (see `slides/.prettierrc`). The default
  Markdown parser reflows the per-slide frontmatter blocks into headings and
  breaks the deck.

## Deployment

`.github/workflows/static.yml` builds and deploys to GitHub Pages on every push
to `master`. The build runs with `working-directory: ./slides` and
`--base /gb-asteroids/`, and uploads `slides/dist`.
