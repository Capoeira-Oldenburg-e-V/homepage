## ADDED Requirements

### Requirement: Hugo project with valid configuration
The project SHALL be a valid Hugo site with a `hugo.toml` configuration file that defines the site title, base URL (`https://capoeira-oldenburg.de/`), language (`de`), and menu structure.

#### Scenario: Hugo builds successfully
- **WHEN** `hugo build` is run in the project root
- **THEN** the site builds without errors and produces output in the `public/` directory

#### Scenario: Site language is German
- **WHEN** the site is built
- **THEN** the HTML `lang` attribute is set to `de`

### Requirement: Base layout with consistent page structure
Every page SHALL use a base layout that includes: an HTML `<head>` with charset, viewport meta tag, page-specific `<title>`, and CSS link; a site header with navigation; a main content area; and a footer.

#### Scenario: Page has required head elements
- **WHEN** any page is rendered
- **THEN** it contains a `<meta charset>`, a `<meta name="viewport">` tag, a `<title>` element, and a `<link>` to the stylesheet

#### Scenario: Page has header and footer
- **WHEN** any page is rendered
- **THEN** it contains a `<header>` element with navigation and a `<footer>` element

### Requirement: Navigation menu with all pages
The site header SHALL contain a navigation element linking to: Home, Trainingszeiten, Was ist Capoeira?, Ueber uns, Events, Blog, and Kontakt. Impressum and Datenschutzerklaerung are excluded from the main navigation.

#### Scenario: Main navigation links are present
- **WHEN** any page is rendered
- **THEN** the `<nav>` element contains links to all seven main pages

#### Scenario: Legal pages are not in main navigation
- **WHEN** any page is rendered
- **THEN** the `<nav>` element does not contain links to Impressum or Datenschutzerklaerung

### Requirement: Footer with legal page links
The footer on every page SHALL contain links to Impressum and Datenschutzerklaerung.

#### Scenario: Footer links to legal pages
- **WHEN** any page is rendered
- **THEN** the `<footer>` contains a link to `/impressum/` and a link to `/datenschutzerklaerung/`

### Requirement: Mobile-first responsive layout
The site layout SHALL be designed mobile-first. The navigation SHALL be usable on small screens (e.g., collapsible menu or equivalent pattern). Content SHALL be readable without horizontal scrolling on viewports as narrow as 320px.

#### Scenario: Content is readable on mobile
- **WHEN** a page is viewed at 320px viewport width
- **THEN** no horizontal scrollbar appears and all text is readable without zooming

#### Scenario: Navigation is usable on mobile
- **WHEN** the site is viewed on a mobile viewport
- **THEN** all navigation links are accessible (via a hamburger menu, collapsible nav, or equivalent)

### Requirement: CSS via Hugo Pipes
Stylesheets SHALL be placed in `assets/css/` and processed through Hugo Pipes for minification and fingerprinting in production builds.

#### Scenario: CSS is minified in production
- **WHEN** the site is built with `hugo --minify`
- **THEN** the CSS output is minified and the `<link>` tag references a fingerprinted filename
