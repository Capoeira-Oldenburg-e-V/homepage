## Why

The Trainingszeiten page uses an HTML table that overflows its container on narrow viewports, clipping the location column off-screen. This is the most important page for converting visitors into trial attendees, so it must be immediately readable on mobile.

## What Changes

- Replace or augment the schedule table with a mobile-first layout that displays all three columns (weekday, time, location) without horizontal overflow on viewports as narrow as 320px

## Capabilities

### New Capabilities

None.

### Modified Capabilities

- `trainingszeiten`: The training schedule display requirement gains an explicit mobile constraint — all schedule data SHALL be visible without horizontal scrolling on narrow viewports.

## Impact

- `assets/css/main.css`: update `.schedule-table` styles to reflow on small screens
- `layouts/_default/trainingszeiten.html`: may need structural changes if a card/stack layout replaces the table on mobile
