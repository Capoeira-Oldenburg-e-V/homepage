## MODIFIED Requirements

### Requirement: Navigation menu with all pages
The site header SHALL contain a navigation element linking to: Home, Training, Was ist Capoeira?, Ueber uns, Events, Blog, and Kontakt. Impressum and Datenschutzerklaerung are excluded from the main navigation.

#### Scenario: Main navigation links are present
- **WHEN** any page is rendered
- **THEN** the `<nav>` element contains links to all seven main pages

#### Scenario: Legal pages are not in main navigation
- **WHEN** any page is rendered
- **THEN** the `<nav>` element does not contain links to Impressum or Datenschutzerklaerung
