# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build

```bash
hugo build          # production build → public/
hugo server         # dev server with live reload at localhost:1313
```

Always delete `public/` before a build when renaming or removing pages — Hugo does not clean stale output directories automatically.

## Architecture

Hugo static site. No themes in use — all layouts are in `layouts/`.

### Template inheritance

Every page template defines `{{ define "main" }}` and relies on `layouts/_default/baseof.html` for the outer shell (doctype, `<html>`, `<head>`, site `<header>`, `<footer>`). Templates must never call the header or footer partials directly, and must never include a full HTML document structure.

### Layout resolution

Hugo picks a template in this order of specificity:

| Content file | Template used |
|---|---|
| `content/blog/*.md` | `layouts/blog/single.html` |
| `content/events/*.md` | `layouts/events/single.html` |
| `content/training.md` | `layouts/_default/training.html` (via `layout: "training"` frontmatter) |
| All other `*.md` | `layouts/_default/single.html` |
| `content/_index.md` | `layouts/index.html` |
| `content/blog/_index.md` | `layouts/blog/list.html` |
| `content/events/_index.md` | `layouts/events/list.html` |

### Data files (`data/`)

Site-wide structured data used in templates:

- `data/verein.yaml` — club name, contact, address, type (drives JSON-LD schema)
- `data/trainingszeiten.yaml` — training schedule (used only in `layouts/_default/training.html`)

### Partials (`layouts/partials/`)

- `head.html` — `<head>` contents: meta, canonical, CSS (Hugo Pipes), favicon, JSON-LD
- `header.html` — site logo + navigation from `menus.main` in `hugo.toml`
- `footer.html` — legal links and copyright
- `jsonld.html` — LocalBusiness structured data from `data/verein.yaml`

### CSS

Single file: `assets/css/main.css`, processed through Hugo Pipes (minified + fingerprinted). Design tokens are CSS custom properties at the top of the file. Dark theme with gold (`#c8a84b`) as the primary accent color.

### Images

Two locations with different roles:

- `assets/images/` — processed by Hugo Pipes (currently only `logo.png`, referenced in `header.html` via `resources.Get`)
- `static/images/` — served verbatim at `/images/*`; used for content images (blog photos, training photos, etc.)

### Navigation

Menu items are defined in `hugo.toml` under `[[menus.main]]`. When renaming a page, update: the content filename, the `layout:` frontmatter if it uses a custom layout, the menu entry in `hugo.toml`, and any internal links in other content files and layout templates.

### Adding a blog post

Create `content/blog/<slug>.md` with frontmatter `title`, `date`, and optionally `description`. It will automatically appear in the blog list in reverse-chronological order.

### Adding an event

Create `content/events/<slug>.md` with frontmatter `title`, `date`, and optionally `location` and `description`. Past events (date < now) are automatically moved to the archive section on the events list page.
