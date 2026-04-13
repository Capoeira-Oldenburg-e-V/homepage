## ADDED Requirements

### Requirement: Unique title and meta description per page
Every page SHALL have a unique, descriptive `<title>` element and a `<meta name="description">` tag. The title SHALL follow the pattern: `<Page Title> | Capoeira Verein Oldenburg` (or similar consistent format).

#### Scenario: Page has unique title
- **WHEN** any page is rendered
- **THEN** the `<title>` element contains a descriptive, page-specific title

#### Scenario: Page has meta description
- **WHEN** any page is rendered
- **THEN** a `<meta name="description">` tag is present with content derived from the page's front matter `description` field

### Requirement: Semantic HTML
All pages SHALL use semantic HTML elements: `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>` as appropriate for the content structure.

#### Scenario: Semantic elements present
- **WHEN** any page is rendered
- **THEN** it uses `<header>`, `<nav>`, `<main>`, and `<footer>` elements

#### Scenario: Blog posts use article element
- **WHEN** a blog post page is rendered
- **THEN** the post content is wrapped in an `<article>` element

### Requirement: LocalBusiness structured data
The site SHALL include LocalBusiness JSON-LD structured data on every page. The data SHALL include the organization name, address (Oldenburg), type of business, and URL.

#### Scenario: JSON-LD is present
- **WHEN** any page is rendered
- **THEN** a `<script type="application/ld+json">` block is present containing a LocalBusiness schema with `name`, `address`, `@type`, and `url` fields

### Requirement: Canonical URLs
Every page SHALL include a `<link rel="canonical">` tag pointing to its canonical URL.

#### Scenario: Canonical link present
- **WHEN** any page is rendered
- **THEN** a `<link rel="canonical" href="...">` tag is present with the page's full URL
