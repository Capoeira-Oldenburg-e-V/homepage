## Context

The Hugo site was scaffolded with "Capoeira Verein Oldenburg" as the site title. The correct registered name is "Capoeira Oldenburg e. V." The name surfaces in several places: the Hugo config, a data file, and inline in markdown content. All rendered pages that use `.Site.Title` will be fixed automatically once `hugo.toml` is corrected; content files that contain the old name verbatim must be updated individually.

## Goals / Non-Goals

**Goals:**
- Replace every occurrence of "Capoeira Verein Oldenburg" with "Capoeira Oldenburg e. V." across config, data, and content
- Verify the built output contains no remaining instances of the old name

**Non-Goals:**
- Changing any other copy or content
- Redesigning layouts or templates
- Updating the `static/images/logo.png` (logo is an image, not text)

## Decisions

### D1: Use grep to find all occurrences before editing

A targeted grep across the project (excluding `public/`, `.git/`, and `openspec/`) gives a definitive list of files to update. This avoids missing any file or editing files unnecessarily.

### D2: Update `hugo.toml` title first

`hugo.toml` is the canonical source for `.Site.Title`, which is rendered into every page's `<title>` and header. Updating it first means the build immediately reflects the correct name everywhere templates use it.

### D3: No template changes needed

All layout templates reference `.Site.Title` or `.Site.Data.verein.name` — they do not hardcode the name. Only the data sources need updating.

## Risks / Trade-offs

- **Inconsistent spacing around "e. V."** — German convention uses spaces: "e. V." (not "e.V." or "eV"). The canonical form to use is "Capoeira Oldenburg e. V." with a non-breaking space before "V." is not required at this stage.
- **`openspec/` directory contains the old name** in proposal and design text — these are documentation artifacts, not the live site, and should not be rewritten.
