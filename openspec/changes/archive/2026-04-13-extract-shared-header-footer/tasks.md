## 1. Verify Base Layout

- [x] 1.1 Confirm `layouts/_default/baseof.html` calls `{{ partial "header.html" . }}` and `{{ partial "footer.html" . }}` and is the sole place that does so
- [x] 1.2 Confirm `layouts/partials/header.html` contains the site header markup (logo + nav) with no duplication elsewhere
- [x] 1.3 Confirm `layouts/partials/footer.html` contains the site footer markup (legal links + social) with no duplication elsewhere

## 2. Verify Page Templates

- [x] 2.1 Confirm every template under `layouts/` (excluding `partials/` and `_default/baseof.html`) uses `{{ define "main" }}` and contains no direct call to `header.html` or `footer.html` partials
- [x] 2.2 Confirm no template contains a standalone HTML document structure (`<!DOCTYPE>`, `<html>`, or `<body>` tags)

## 3. Build Verification

- [x] 3.1 Run `hugo build` and confirm it succeeds with no errors
- [x] 3.2 Inspect a rendered page in `public/` and confirm exactly one `<header>` (site-level) and one `<footer>` are present per page
