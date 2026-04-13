## Context

The live page at capoeira-oldenburg.de/über-uns/ contains the following distinct sections:
1. **Mestre Amapá biography** — started Capoeira 1977 in Macapá, moved through Fortaleza, joined Cordão de Ouro 1990, moved to Oldenburg 2004, received fourth-grade Meisterkordel 2019, joined Menino Bom as Capoeira Oldenburg e.V. 2021.
2. **Verein history** — founded 2004 with Mestre Amapá, Hochschulsport Uni Oldenburg, current membership 7–50+ years, roughly equal gender split.
3. **Auftritte & Workshops** — public performances (intercultural events, Brasilien days, private events), school workshops, free-play format, percussion and song accompaniment, booking via email.
4. **Portrait photo** — Mestre Amapá headshot at `image.jimcdn.com/.../i5ff6fe9d9f00aab3/...`

The new site's `content/ueber-uns.md` uses the default `single.html` layout, which renders markdown body content directly. No layout changes are needed.

## Goals / Non-Goals

**Goals:**
- All four content sections from the live page are present in the new `ueber-uns.md`
- The Mestre Amapá photo is saved locally and referenced with a relative path in the markdown

**Non-Goals:**
- Translating or editing the content
- Adding interactive elements or a contact form
- Migrating the training schedule sidebar (already handled by `data/trainingszeiten.yaml`)

## Decisions

### D1: Inline image reference in markdown

The portrait is referenced directly in the markdown body with a standard `![alt](path)` tag pointing to `/images/mestre-amapa.jpg` in `static/`. Hugo copies `static/` files to `public/` as-is, so no Hugo Pipes processing is needed for this image.

### D2: Keep the four live-site sections as ## headings

The live page uses a clear section structure. Preserving it as `##` headings in markdown makes the content easy to read and edit.

## Risks / Trade-offs

- **Image alt text** — The original image has no descriptive alt text on the live site. A descriptive alt text will be added.
- **Legal content at bottom of live page** (Trainingszeiten, Kontakt) is footer/sidebar repetition — not page-specific content and already covered by dedicated pages; it will not be migrated here.
