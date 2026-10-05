# Wave Casting for Hybrid-Scene Interactive Holography — project page

Source for the WaveCast project page (SIGGRAPH Asia 2026 Conference Papers).
Built on the [Nerfies](https://github.com/nerfies/nerfies.github.io) template.

## Deploying

This is a plain static site — no build step.

1. Create the repository `<name>.github.io` under the account or organization
   named `<name>`, and push this directory to its default branch.
2. Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.

`.nojekyll` is present so Pages serves the files as-is instead of running them
through Jekyll.

## Before the first deploy

- **`og:image` in `index.html`** is an absolute URL and still points at
  `rongduo.github.io`. Open Graph does not accept relative paths, so this has to
  be updated by hand once the final domain is known.
- **`index.css?v=4`** — the query string is a cache-buster. Bump it whenever
  `static/css/index.css` changes, otherwise browsers and the Pages CDN may keep
  serving the old stylesheet.
- **Link buttons are coloured by position** — `.link-block:nth-child(1|2|3)` in
  `static/css/index.css`. Adding a fourth button (e.g. the ACM DOI, live from
  December 2026) needs a matching `nth-child(4)` rule, or it falls back to
  Bulma's plain black.

## Layout

```
index.html
static/
  css/    bulma.min.css, index.css
  js/     tabs.js (card switchers), nav.js (scroll-spy side rail)
  images/ teaser, pipeline and ablation figures, compare/ grids, favicon
  videos/ captured focal stacks, interactive GUI recording
  pdfs/   wavecast.pdf (paper), supplementary_material.pdf
```

This copy is self-contained: every reference resolves inside the directory, so
it can be served from a repository root or from any subdirectory.
