## Why

The current "Trainingszeiten" page shows only a schedule table and a one-line Probetraining note. The old website (capoeira-oldenburg.de/training/) has substantially richer content — training structure, beginner guidance, location directions, a training photo, and clothing tips — that helps first-time visitors understand what to expect and decide to show up. This change migrates that content and renames the page to "Training" (matching the old URL slug).

## What Changes

- **BREAKING** Rename page from "Trainingszeiten" to "Training": URL changes from `/trainingszeiten/` to `/training/`
- Navigation menu label updated from "Trainingszeiten" to "Training"
- Add "Ablauf des Trainings" section: training structure description (warm-up → exercises → Roda), beginner guidance, additional disciplines (Maculelê, Miudinho, Samba, instruments)
- Add training photo (from old site) alongside the training description
- Add Freitag seasonal note (Wintersaison: Oktober bis April only) to schedule data
- Add location directions for Heiligengeisttorschule (entrance next to Mensa)
- Expand Probetraining section with: specific days (Montag or Mittwoch), watching permitted
- Add clothing tip: barefoot or long pants; indoor shoes if footwear required
- Download and store training image locally in `static/images/`

## Capabilities

### New Capabilities
- None

### Modified Capabilities
- `trainingszeiten`: URL changes to `/training/`; new content sections added (training description, location directions, clothing tip); schedule entries gain optional seasonal notes
- `site-structure`: Navigation label for the training page changes from "Trainingszeiten" to "Training"

## Impact

- `content/trainingszeiten.md` → renamed to `content/training.md`
- `layouts/_default/trainingszeiten.html` → renamed to `layouts/_default/training.html`
- `hugo.toml` → menu entry name and URL updated
- `data/trainingszeiten.yaml` → Freitag entry gains seasonal note
- `static/images/` → new training image added
- Any internal links to `/trainingszeiten/` → updated to `/training/`
