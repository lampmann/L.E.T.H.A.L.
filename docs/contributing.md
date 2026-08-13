# Editing This Wiki

How pages are written, previewed and published.

## Previewing locally

You need Python 3.9 or newer. From the repository root:

```bash
pip install -r requirements.txt
mkdocs serve
```

That serves the wiki at <http://127.0.0.1:8000> and reloads the page every time
you save a file. `mkdocs build --strict` does a one-off build and fails on
broken internal links, which is the same check CI runs.

## Adding a page

1. Create a Markdown file under `docs/`.
2. Add it to the `nav:` block in `mkdocs.yml`. Pages outside the nav still
   build, but nothing links to them.
3. Start the file with a single `#` heading. That heading becomes the page
   title in the sidebar and in search results.

Links between pages point at the Markdown file, not the built URL:

```markdown
See [Character Creation](rules/character-creation.md).
```

MkDocs rewrites those to real URLs at build time and warns you if the target
does not exist.

## Page furniture

The skin in `docs/stylesheets/wiki.css` provides the pieces a wiki usually
wants. All of them need `markdown` on the opening tag — without it the contents
are treated as raw HTML and stop being Markdown.

### Infobox

The summary panel that floats at the top right of a page.

```markdown
<div class="infobox" markdown>

### Name of the thing

|  |  |
|---|---|
| **Type** | Sidearm |
| **Range** | Short |

</div>
```

Put it directly under the page's `#` heading. On phones it drops below the text
instead of squeezing it.

### Hatnote

The italic "see also" line under a heading:

```markdown
<p class="hatnote">For the referee's side, see <a href="../gm/">Running the Game</a>.</p>
```

Hatnotes use plain HTML links because they sit outside Markdown processing —
mind the relative path, and remember built URLs end in `/`.

### Stub notice

Marks a page or section as an unwritten placeholder:

```markdown
<div class="stub" markdown>
Placeholder. Say what still needs deciding.
</div>
```

Searching the repository for `class="stub"` gives you a to-do list of every
unfinished section in the wiki.

### Roll tables

Wrapping a table centres and narrows its first column, which is what you want
for a die-range column:

```markdown
<div class="roll-table" markdown>

| d6 | Result |
|---|---|
| 1–2 | Something |

</div>
```

### Red links

For a page you intend to write but haven't yet, mark the link so it shows in
red rather than blue:

```markdown
<span class="new">[Bestiary](#)</span>
```

## Abbreviations

Terms listed in `includes/abbreviations.md` are expanded on hover anywhere they
appear in the wiki, automatically, on every page. The format is:

```markdown
*[GM]: Game Master
```

Use it for short forms that recur. Longer terms belong in the
[Glossary](glossary.md) instead.

## Admonitions

Standard MkDocs Material admonitions work and are styled flat to match the skin:

```markdown
!!! note "Optional rule"
    Text of the note.
```

`!!! example`, `!!! warning` and `??? note` (collapsible) are also available.

## Publishing

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the
wiki and publishes it to GitHub Pages. Nothing else is needed — no generated
files are committed, and `site/` is ignored by git.

Every page has a pencil icon at the top right that opens the source file in the
GitHub editor, which is the quickest way to fix a typo from a phone.
