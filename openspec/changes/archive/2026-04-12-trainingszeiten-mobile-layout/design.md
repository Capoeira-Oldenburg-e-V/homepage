## Context

The Trainingszeiten page renders a three-column HTML table (Wochentag / Uhrzeit / Ort). On narrow viewports the table's minimum content width exceeds the viewport, causing horizontal overflow and clipping the location column. The existing CSS has no mobile override for `.schedule-table`.

## Goals / Non-Goals

**Goals:**
- All three schedule columns are fully visible and readable without horizontal scrolling on viewports ≥ 320px
- No change to the desktop (≥ 641px) table layout

**Non-Goals:**
- Redesigning the page structure beyond the schedule table
- Adding interactivity or filtering

## Decisions

### D1: CSS-only stacked card layout below 640px

**Choice:** At `max-width: 640px`, hide the `<thead>` and reflow each `<tr>` into a block, with each `<td>` displaying its column header via a `data-label` attribute and CSS `::before` pseudo-element.

**Alternatives considered:**
- Horizontal scroll wrapper (`overflow-x: auto`): Keeps the table intact but still requires horizontal scrolling — violates the mobile-usability requirement.
- Replace table with `<dl>` / card markup in the template: Works, but requires both a template change and CSS. The CSS-only approach avoids touching the template.
- Reduced font size: Hacky; degrades readability without solving the overflow.

**Rationale:** The "responsive table via data-label" pattern requires only CSS changes and minimal HTML attribute additions (`data-label` on each `<td>`). No JavaScript. No layout restructuring. Minimal diff.

### D2: Add `data-label` attributes to `<td>` elements in the template

The `::before` pseudo-element needs `content` sourced from `data-label` on each cell. This requires a one-line change per `<td>` in `layouts/_default/trainingszeiten.html`.

## Risks / Trade-offs

- **No risk of regression on desktop** — the new CSS is entirely inside a `max-width: 640px` media query, which is the same breakpoint already used for the nav toggle.
- **`data-label` values are hardcoded in German** in the template — acceptable since the site is German-only (design decision D1 in the original website-redesign change).
