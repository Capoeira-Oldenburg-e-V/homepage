## Why

Every rendered page must share the same site header (with navigation) and footer (with legal links), with the markup defined in exactly one place. Duplication across page templates causes inconsistency and makes global changes to navigation or footer require edits in multiple files.

## What Changes

- A single base layout (`layouts/_default/baseof.html`) wraps every page and renders the shared `<header>` and `<footer>` via Hugo partials
- The site header markup lives exclusively in `layouts/partials/header.html`
- The site footer markup lives exclusively in `layouts/partials/footer.html`
- All page-specific templates define only the `main` block — they do not redeclare the header or footer

**Status note:** The project already implements this structure correctly. `baseof.html` exists and references both partials; all page templates use `{{ define "main" }}`. This change formalises the requirement and verifies the implementation is complete.

## Capabilities

### New Capabilities
- None. This change formalises an existing implementation.

### Modified Capabilities
- `site-structure`: No requirement change — the existing "Base layout with consistent page structure" requirement already covers this. Implementation verification only.

## Impact

- `layouts/_default/baseof.html` — base template (already correct)
- `layouts/partials/header.html` — shared header partial (already correct)
- `layouts/partials/footer.html` — shared footer partial (already correct)
- All files under `layouts/` — must each use `{{ define "main" }}` without redeclaring header or footer markup
