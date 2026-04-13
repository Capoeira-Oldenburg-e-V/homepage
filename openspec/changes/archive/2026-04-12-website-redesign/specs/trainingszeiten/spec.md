## ADDED Requirements

### Requirement: Training schedule display
The Trainingszeiten page SHALL display the current training schedule sourced from `data/trainingszeiten.yaml`. Each entry SHALL show the weekday, time, and location.

#### Scenario: Schedule entries are displayed
- **WHEN** a visitor navigates to `/trainingszeiten/`
- **THEN** all training entries from the data file are displayed with weekday, time, and location

#### Scenario: Schedule is scannable within seconds
- **WHEN** a visitor lands on the Trainingszeiten page
- **THEN** the training times and locations are immediately visible without scrolling past unrelated content

### Requirement: Probetraining information
The Trainingszeiten page SHALL prominently display a note that newcomers can attend trial sessions (Probetraining) without Verein membership.

#### Scenario: Probetraining note is visible
- **WHEN** a visitor views the Trainingszeiten page
- **THEN** a clearly visible note about Probetraining is present on the page

### Requirement: Training data in YAML
The training schedule SHALL be defined in `data/trainingszeiten.yaml` as a list of entries. Each entry SHALL have fields for weekday, time, and location. Additional fields (e.g., notes, age group) are optional.

#### Scenario: YAML data file structure
- **WHEN** the `data/trainingszeiten.yaml` file is read
- **THEN** it contains a list of entries each with `weekday`, `time`, and `location` fields
