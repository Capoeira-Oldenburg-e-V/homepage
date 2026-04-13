## ADDED Requirements

### Requirement: Page templates define only the main content block
Every Hugo page template under `layouts/` SHALL use `{{ define "main" }}` to inject page-specific content into the base layout. Templates SHALL NOT call `{{ partial "header.html" }}` or `{{ partial "footer.html" }}` directly, and SHALL NOT include a full HTML document structure (`<!DOCTYPE>`, `<html>`, `<body>`).

#### Scenario: Template uses define block
- **WHEN** any file under `layouts/` is inspected (excluding `partials/` and `_default/baseof.html`)
- **THEN** it contains `{{ define "main" }}` and does not contain a call to the header or footer partial
