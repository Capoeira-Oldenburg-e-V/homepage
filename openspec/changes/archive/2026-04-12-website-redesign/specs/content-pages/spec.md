## ADDED Requirements

### Requirement: Home page
The Home page SHALL serve as the landing page at the site root (`/`). It SHALL provide clear navigation paths to key sections, particularly Trainingszeiten. It SHALL include a brief welcome text and the Verein logo.

#### Scenario: Home page is accessible at root
- **WHEN** a visitor navigates to `/`
- **THEN** the Home page is displayed with welcome content, the Verein logo, and prominent links to Trainingszeiten and other key sections

### Requirement: Was ist Capoeira page
The "Was ist Capoeira?" page SHALL provide an introduction to Capoeira for newcomers. Content is authored as a markdown file at `content/was-ist-capoeira.md`.

#### Scenario: Was ist Capoeira page renders content
- **WHEN** a visitor navigates to `/was-ist-capoeira/`
- **THEN** the page displays the introduction content from the markdown file

### Requirement: Ueber uns page
The "Ueber uns" page SHALL describe the Verein, its history, and its mestres. Content is authored as a markdown file at `content/ueber-uns.md`.

#### Scenario: Ueber uns page renders content
- **WHEN** a visitor navigates to `/ueber-uns/`
- **THEN** the page displays the Verein description, history, and mestre information

### Requirement: Kontakt page
The Kontakt page SHALL display the Verein email address and social media links. Social media links SHALL be sourced from `data/social.yaml`.

#### Scenario: Kontakt page shows email and social links
- **WHEN** a visitor navigates to `/kontakt/`
- **THEN** the page displays the email address and all social media links defined in the data file

### Requirement: Impressum page
The Impressum page SHALL contain the legal notice as required by DDG SS5. It SHALL be accessible at `/impressum/`.

#### Scenario: Impressum page is accessible
- **WHEN** a visitor navigates to `/impressum/`
- **THEN** the legal notice content is displayed

### Requirement: Datenschutzerklaerung page
The Datenschutzerklaerung page SHALL contain the privacy policy as required by DSGVO Art. 13/14. It SHALL be accessible at `/datenschutzerklaerung/`.

#### Scenario: Datenschutzerklaerung page is accessible
- **WHEN** a visitor navigates to `/datenschutzerklaerung/`
- **THEN** the privacy policy content is displayed

### Requirement: Content authored in markdown
All content pages SHALL be authored as markdown files in the `content/` directory. Each markdown file SHALL include front matter with at least `title` and `description` fields.

#### Scenario: Markdown file has required front matter
- **WHEN** a content page markdown file is created
- **THEN** it includes `title` and `description` in its front matter
