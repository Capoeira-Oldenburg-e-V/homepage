## Context

The Trainingszeiten page is the most important conversion page on the site (FR-2). It currently shows only a schedule table from `data/trainingszeiten.yaml` and a one-line Probetraining note from the markdown content. The old Jimdo site has several additional sections that provide important context for first-time visitors.

Current file roles:
- `content/trainingszeiten.md` — page frontmatter and a single prose line
- `layouts/_default/trainingszeiten.html` — renders the schedule table from data, then `.Content`
- `data/trainingszeiten.yaml` — three schedule entries (Montag, Mittwoch, Freitag)

Content extracted from old site to integrate:
- **Training location text**: trains Mon/Wed at Heiligengeisttorschule; Fri Oct–Apr at Herbartgymnasium
- **Location directions**: entrance next to Schulmensa, ring bell if door is closed
- **Training structure**: warm-up → movements → Roda; beginner guidance; additional disciplines
- **Training photo**: `https://image.jimcdn.com/app/cms/image/transf/none/path/s3b1439775dda3467/image/i4cbb9f38a246e117/version/1484938006/image.jpg` (400×300 jpg)
- **Probetraining details**: Mon or Wed, watching permitted
- **Clothing tip**: barefoot or long pants; indoor shoes if footwear needed

## Goals / Non-Goals

**Goals:**
- Rename page and URL from `/trainingszeiten/` to `/training/`
- Add all migrated text content to the page
- Add the training photo stored locally
- Add seasonal note (Wintersaison) to Freitag schedule entry
- Update all internal links pointing to `/trainingszeiten/`

**Non-Goals:**
- Embedding a Google Map (not used in the new site, addresses are sufficient)
- Adding the Capoeira quote from the old site (out of place on this page)
- Changing the schedule data format or adding new data fields beyond `notes`

## Decisions

**Content in markdown, structure in template**
The rich text (training description, Probetraining section, tips) goes into the markdown content file, rendered as `.Content` by the template. The schedule table remains data-driven and template-rendered above `.Content`. This keeps domain content editable without touching templates.

**Image in `static/images/`, referenced via markdown**
The training photo is stored in `static/images/training-ablauf.jpg` and referenced with a standard markdown image tag inside the content file. Hugo serves it verbatim with no processing needed. (`assets/images/` is used only for CSS/fingerprinted resources.)

**Rename content file and template, keep data file name**
`content/trainingszeiten.md` → `content/training.md` (changes URL to `/training/`).
`layouts/_default/trainingszeiten.html` → `layouts/_default/training.html` (update `layout:` frontmatter accordingly).
`data/trainingszeiten.yaml` keeps its name — it is an internal reference only used by the template.

**Freitag seasonal note via existing `notes` field**
The `data/trainingszeiten.yaml` already has a `notes` field (currently empty). Set it to `"Wintersaison (Oktober–April)"` for the Freitag entry. The template already renders `notes` inline.

**Update two internal links**
`content/was-ist-capoeira.md` and `content/blog/willkommen.md` each link to `/trainingszeiten/`. Both must be updated to `/training/`.

## Risks / Trade-offs

- URL change from `/trainingszeiten/` to `/training/` → **BREAKING** for any external links or bookmarks. Acceptable — the site is not yet live on the new domain.
- `static/images/capoeira-training.jpg` already exists; the new image uses a distinct filename (`training-ablauf.jpg`) to avoid collision.
