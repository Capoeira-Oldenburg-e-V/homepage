## Why

The site was built using "Capoeira Verein Oldenburg" as the organisation name, but the registered legal name is "Capoeira Oldenburg e. V." Using the wrong name creates inconsistency with the Impressum and any official communication.

## What Changes

- Replace every occurrence of "Capoeira Verein Oldenburg" with "Capoeira Oldenburg e. V." across all content, data files, and configuration
- Update `hugo.toml` site title
- Update `data/verein.yaml` name field
- Update all content markdown files where the old name appears in front matter or body text

## Capabilities

### New Capabilities

None. This is a pure rename with no new functionality.

### Modified Capabilities

None. No spec-level behavior changes — only the string value of the organisation name changes.

## Impact

- `hugo.toml`: `title` field
- `data/verein.yaml`: `name` field
- `content/_index.md`: title and description
- `content/ueber-uns.md`: body text
- `content/impressum.md`: body text
- `content/datenschutzerklaerung.md`: body text
- `layouts/index.html`: any hardcoded references
- `assets/css/main.css`: none expected
- All rendered pages that display `.Site.Title` will update automatically once `hugo.toml` is corrected
