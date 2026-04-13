## MODIFIED Requirements

### Requirement: Training schedule display
The Trainingszeiten page SHALL display the current training schedule sourced from `data/trainingszeiten.yaml`. Each entry SHALL show the weekday, time, and location. On viewports narrower than 641px, all three fields SHALL be visible without horizontal scrolling.

#### Scenario: Schedule entries are displayed
- **WHEN** a visitor navigates to `/trainingszeiten/`
- **THEN** all training entries from the data file are displayed with weekday, time, and location

#### Scenario: Schedule is scannable within seconds
- **WHEN** a visitor lands on the Trainingszeiten page
- **THEN** the training times and locations are immediately visible without scrolling past unrelated content

#### Scenario: Schedule is fully visible on mobile
- **WHEN** a visitor views the Trainingszeiten page at 320px viewport width
- **THEN** all three columns (weekday, time, location) are visible without horizontal scrolling and without content being clipped
