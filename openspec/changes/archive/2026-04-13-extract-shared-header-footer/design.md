## Context

Hugo's template inheritance system (`baseof.html` + `{{ define "main" }}` blocks) is the idiomatic way to share layout chrome across pages. The project already uses this pattern: `layouts/_default/baseof.html` renders the shared `<header>` and `<footer>` via partials, and every page template defines only the `main` block.

Current file roles:
- `layouts/_default/baseof.html` — outer HTML shell; calls `header.html` and `footer.html` partials
- `layouts/partials/header.html` — site header with logo and navigation
- `layouts/partials/footer.html` — site footer with legal links and social media
- `layouts/partials/head.html` — `<head>` contents (meta, CSS)
- All templates under `layouts/` — define `{{ define "main" }}` only

## Goals / Non-Goals

**Goals:**
- Confirm that the centralized header/footer pattern is correctly implemented across all templates
- Ensure no page template redeclares header or footer markup directly
- Formalise the template structure so new pages follow the same pattern

**Non-Goals:**
- Changing the visual appearance of the header or footer
- Moving to a different templating mechanism
- Modifying the navigation items (covered by site-structure spec)

## Decisions

**Use Hugo's native `baseof.html` + partials pattern**
Hugo's block/partial system is the only correct mechanism for this in a pure Hugo project. No alternatives considered — the project already uses it.

**Partials are the single source of truth for header/footer markup**
`layouts/partials/header.html` and `layouts/partials/footer.html` are the only places where the respective markup lives. Page templates MUST NOT call these partials directly; `baseof.html` calls them implicitly for every page.

## Risks / Trade-offs

- No meaningful risks. The pattern is fully supported by Hugo and already in place.
- Risk of future regression: a developer adding a new page type might accidentally create a standalone template (one without `{{ define "main" }}`), causing it to render without the base layout. The spec scenario for this should catch such regressions during review.
