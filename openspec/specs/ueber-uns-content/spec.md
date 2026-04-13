# Spec: ueber-uns-content

### Requirement: Mestre Amapá biography is present
The "Über uns" page SHALL include a biography section for Mestre Amapá covering his Capoeira history from 1977 through joining Menino Bom in 2021.

#### Scenario: Biography is rendered
- **WHEN** a visitor navigates to `/ueber-uns/`
- **THEN** the page displays content about Mestre Amapá including his start in 1977 and his move to Oldenburg in 2004

### Requirement: Verein history is present
The "Über uns" page SHALL describe the Verein's history including the founding year (2004), the partnership with Uni Oldenburg Hochschulsport, and current membership demographics.

#### Scenario: Verein history is rendered
- **WHEN** a visitor navigates to `/ueber-uns/`
- **THEN** the page displays the founding year, the Uni Oldenburg connection, and membership age range

### Requirement: Auftritte and Workshops section is present
The "Über uns" page SHALL describe the Verein's Auftritte and Workshop offerings, including the free-play performance format and how to book via email.

#### Scenario: Auftritte section is rendered
- **WHEN** a visitor navigates to `/ueber-uns/`
- **THEN** the page displays information about Auftritte and Workshops with a call to action to contact via email

### Requirement: Mestre Amapá portrait photo is displayed
The "Über uns" page SHALL display a photo of Mestre Amapá sourced from a locally saved image file.

#### Scenario: Portrait photo is rendered
- **WHEN** a visitor navigates to `/ueber-uns/`
- **THEN** a photo of Mestre Amapá is visible on the page with descriptive alt text
