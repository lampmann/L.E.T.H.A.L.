# L.E.T.H.A.L.

Source for the **L.E.T.H.A.L.** tabletop roleplaying game wiki — a living
rulebook built with [MkDocs](https://www.mkdocs.org/) and
[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/), skinned to
read like an encyclopedia rather than a software manual.

The game is in early development. Most pages are deliberate placeholders.

## Local preview

Requires Python 3.9+.

```bash
pip install -r requirements.txt
mkdocs serve
```

Then open <http://127.0.0.1:8000>. The page reloads as you save.

To reproduce exactly what CI does:

```bash
mkdocs build --strict
```

## Layout

```
docs/                   Wiki content — one Markdown file per page
  index.md              Home
  rules/                Core rules and character creation
  gm/                   Referee-facing material
  glossary.md           Terms of art
  contributing.md       House style and page furniture
  stylesheets/wiki.css  The Wikipedia-style skin
includes/
  abbreviations.md      Abbreviations expanded on hover site-wide
mkdocs.yml              Site config and navigation
```

Adding a page means creating the file under `docs/` and listing it in the `nav:`
block of `mkdocs.yml`. See `docs/contributing.md` for house conventions —
infoboxes, hatnotes, stub notices, roll tables and red links.

## Publishing

Pushes to `main` build the wiki and publish it to GitHub Pages via
`.github/workflows/deploy.yml`. Pull requests run the same strict build without
deploying.

**One-time setup:** in the repository's *Settings → Pages*, set **Source** to
**GitHub Actions**. The site then appears at
<https://lampmann.github.io/L.E.T.H.A.L./>.

If the published URL ends up differing — repository names containing dots can
be served from an unexpected path — update `site_url` in `mkdocs.yml` to match,
since search and canonical links are generated from it.

## Licensing

**Undecided.** The site footer currently asserts copyright without granting a
licence, which keeps both paths open.

- To make the wiki freely reusable, add a `LICENSE` file (Creative Commons
  BY-SA 4.0 is the usual choice for wiki text) and update `copyright:` in
  `mkdocs.yml`.
- To keep it proprietary ahead of a commercial release, leave it as is and say
  so explicitly in the footer.

Worth settling before the wiki has an audience — relicensing is easy while
you are the only contributor and awkward afterwards.
