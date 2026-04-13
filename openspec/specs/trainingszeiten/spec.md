### Requirement: Training schedule display
The Training page SHALL display the current training schedule sourced from `data/trainingszeiten.yaml`. Each entry SHALL show the weekday, time, and location. On viewports narrower than 641px, all three fields SHALL be visible without horizontal scrolling. Schedule entries MAY include an optional `notes` field displayed inline with the location (e.g., seasonal restrictions).

#### Scenario: Schedule entries are displayed
- **WHEN** a visitor navigates to `/training/`
- **THEN** all training entries from the data file are displayed with weekday, time, and location

#### Scenario: Schedule is scannable within seconds
- **WHEN** a visitor lands on the Training page
- **THEN** the training times and locations are immediately visible without scrolling past unrelated content

#### Scenario: Schedule is fully visible on mobile
- **WHEN** a visitor views the Training page at 320px viewport width
- **THEN** all three columns (weekday, time, location) are visible without horizontal scrolling and without content being clipped

### Requirement: Probetraining information
The Training page SHALL prominently display a note that newcomers can attend trial sessions (Probetraining) without Verein membership, and SHALL specify that both watching and participating are welcome.

#### Scenario: Probetraining note is visible
- **WHEN** a visitor views the Training page
- **THEN** a clearly visible note about Probetraining is present on the page

#### Scenario: Probetraining details are present
- **WHEN** a visitor reads the Probetraining section
- **THEN** it states that Probetraining is free, available on Montag and Mittwoch, and that watching is permitted

### Requirement: Training data in YAML
The training schedule SHALL be defined in `data/trainingszeiten.yaml` as a list of entries. Each entry SHALL have fields for `weekday`, `time`, and `location`. An optional `notes` field MAY be used for supplementary information such as seasonal restrictions.

#### Scenario: YAML data file structure
- **WHEN** the `data/trainingszeiten.yaml` file is read
- **THEN** it contains a list of entries each with `weekday`, `time`, and `location` fields

#### Scenario: Freitag entry includes seasonal note
- **WHEN** the `data/trainingszeiten.yaml` file is read
- **THEN** the Freitag entry has a `notes` value indicating it is Wintersaison only (Oktober–April)

### Requirement: Training description content
The Training page SHALL include a section describing the structure of a training session: warm-up, Capoeira movements, and closing Roda. It SHALL mention that beginners are guided by trainers and experienced members, and that additional disciplines trained include Maculelê, Miudinho, Samba, Berimbau, Pandeiro, and Atabaque.

#### Scenario: Training description is present
- **WHEN** a visitor reads the Training page
- **THEN** it contains a description of the training flow including warm-up, exercises, and Roda

### Requirement: Training photo
The Training page SHALL display a photo of the training. The image SHALL be stored locally in `static/images/` and referenced with an appropriate alt text.

#### Scenario: Training photo is displayed
- **WHEN** a visitor views the Training page
- **THEN** a training photo is visible on the page

### Requirement: Clothing and footwear tip
The Training page SHALL include a note that Capoeira is trained barefoot or with long training pants, and that indoor shoes are required if footwear is worn.

#### Scenario: Clothing tip is present
- **WHEN** a visitor reads the Training page
- **THEN** a tip about appropriate clothing and footwear is visible
