## 1. Template

- [x] 1.1 In `layouts/_default/trainingszeiten.html`, add `data-label="Wochentag"` to the weekday `<td>`, `data-label="Uhrzeit"` to the time `<td>`, and `data-label="Ort"` to the location `<td>`

## 2. CSS

- [x] 2.1 In `assets/css/main.css`, inside the existing `@media (max-width: 640px)` block, add rules for `.schedule-table` to reflow into a stacked card layout: hide `<thead>`, make each `<tr>` a block with bottom margin, make each `<td>` a block with a `::before` pseudo-element that displays `attr(data-label)` as a muted label above the value

## 3. Verify

- [x] 3.1 Run `hugo server` and confirm the Trainingszeiten page at 320px viewport shows all schedule data without horizontal overflow
- [x] 3.2 Confirm the desktop table layout (≥ 641px) is unchanged
