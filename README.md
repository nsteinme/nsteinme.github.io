# www.nicksteinmetz.com

Static site, served by GitHub Pages from the root of this repository at the domain in
`CNAME`. There is no Jekyll any more: `index.html` and `publications.html` are complete,
self-contained pages, and `.nojekyll` tells GitHub Pages to serve them as-is.

## Do not edit the HTML here

Both pages are **generated**. Their sources live in the
[SteinmetzLab/website-v2](https://github.com/SteinmetzLab/website-v2) repository, which
they share with the lab site so that the two keep the same design:

| Page here | Source there |
|---|---|
| `index.html` | `mockups/src/ns-index.html` |
| `publications.html` | `mockups/src/ns-publications.html` |
| the publication list | `mockups/data/pubs.json` (the same file the lab site uses) |
| header and footer | `mockups/src/partials/ns-nav.html`, `ns-foot.html` |
| styling | `mockups/src/partials/a-base.css`, `a-page.css`, `palettes.css` |

To update:

```
cd path/to/website-v2/mockups
python build.py --personal      # writes out-personal/
```

then copy `out-personal/*` over the files here and commit. Adding a paper means editing
`data/pubs.json` in that repo, which updates this site and the lab site together.

## What is kept

- `CNAME` — the custom domain. Removing it breaks the domain.
- `assets/` — images and paper PDFs from the previous version of the site, kept so that
  existing links to them keep working. Nothing on the current pages uses this folder.
- `publications/` and `cv/` — one-line redirect pages, so the old `/publications/` and
  `/cv/` URLs still land somewhere sensible.
- `Steinmetz_CV_2026-08-11.pdf` — the current CV, linked from both pages.
