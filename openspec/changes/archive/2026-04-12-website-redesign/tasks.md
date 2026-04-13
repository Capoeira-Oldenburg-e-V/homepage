## 1. Hugo Project Scaffolding

- [x] 1.1 Initialize Hugo project: run `hugo new site` and configure `hugo.toml` with site title, baseURL (`https://capoeira-oldenburg.de/`), language (`de`), and permalink structure
- [x] 1.2 Create the directory structure: `content/`, `content/blog/`, `content/events/`, `data/`, `layouts/_default/`, `layouts/partials/`, `layouts/blog/`, `layouts/events/`, `assets/css/`, `static/images/`
- [x] 1.3 Add `static/CNAME` file containing `capoeira-oldenburg.de`

## 2. Base Layout and CSS

- [x] 2.1 Create `layouts/_default/baseof.html` with HTML5 doctype, `<html lang="de">`, head partial, header partial, `<main>` block, and footer partial
- [x] 2.2 Create `layouts/partials/head.html` with charset, viewport meta, `<title>` (page title + site title), `<meta name="description">`, `<link rel="canonical">`, and CSS link via Hugo Pipes
- [x] 2.3 Create `layouts/partials/header.html` with site logo, site name, and `<nav>` linking to: Home, Trainingszeiten, Was ist Capoeira?, Ueber uns, Events, Blog, Kontakt
- [x] 2.4 Create `layouts/partials/footer.html` with links to Impressum and Datenschutzerklaerung, plus social media links from `data/social.yaml`
- [x] 2.5 Create `assets/css/main.css` with CSS custom properties for design tokens (colors, spacing, typography), mobile-first base styles, responsive navigation (hamburger/collapsible for mobile), and `min-width` media queries for larger screens
- [x] 2.6 Verify: all pages render with header, nav, main content area, and footer; no horizontal scroll at 320px viewport

## 3. SEO and Structured Data

- [x] 3.1 Create `layouts/partials/jsonld.html` with LocalBusiness JSON-LD containing organization name, address, business type, and URL sourced from `data/verein.yaml`
- [x] 3.2 Include the JSON-LD partial in `head.html`
- [x] 3.3 Create `data/verein.yaml` with Verein name, address (Oldenburg), email, and business type
- [x] 3.4 Verify: every rendered page has a unique `<title>`, `<meta name="description">`, `<link rel="canonical">`, and LocalBusiness JSON-LD block

## 4. Content Pages

- [x] 4.1 Create `content/_index.md` (Home) with front matter (`title`, `description`) and welcome content with prominent link to Trainingszeiten
- [x] 4.2 Create `layouts/index.html` (Home layout) rendering the home page with logo and navigation callouts
- [x] 4.3 Create `content/was-ist-capoeira.md` with front matter and placeholder or migrated content
- [x] 4.4 Create `content/ueber-uns.md` with front matter and placeholder or migrated content
- [x] 4.5 Create `content/kontakt.md` with front matter; template renders email and social links from `data/social.yaml`
- [x] 4.6 Create `data/social.yaml` with social media links migrated from the existing site
- [x] 4.7 Create `content/impressum.md` with front matter and legal notice content (DDG SS5)
- [x] 4.8 Create `content/datenschutzerklaerung.md` with front matter and privacy policy content (DSGVO Art. 13/14)
- [x] 4.9 Create `layouts/_default/single.html` as the default single-page template
- [x] 4.10 Verify: all six content pages render at their expected URLs with correct titles and meta descriptions

## 5. Trainingszeiten Page

- [x] 5.1 Create `data/trainingszeiten.yaml` with training schedule entries (weekday, time, location) migrated from existing site
- [x] 5.2 Create `content/trainingszeiten.md` with front matter and Probetraining note in the body
- [x] 5.3 Create a layout or template logic for the Trainingszeiten page that iterates over `data/trainingszeiten.yaml` and renders each entry with weekday, time, and location in a clear, scannable format
- [x] 5.4 Verify: schedule entries and Probetraining note are visible immediately upon page load without scrolling past unrelated content

## 6. Blog

- [x] 6.1 Create `content/blog/_index.md` with front matter for the blog index page
- [x] 6.2 Create `layouts/blog/list.html` listing posts in reverse-chronological order with title, date, and summary/excerpt
- [x] 6.3 Create `layouts/blog/single.html` rendering a single post with title, date, and full content inside an `<article>` element
- [x] 6.4 Create at least one sample blog post in `content/blog/` with `title`, `date`, and `description` front matter (migrate existing post if available)
- [x] 6.5 Verify: blog index shows posts newest-first; individual post pages render correctly; empty blog index does not error

## 7. Events

- [x] 7.1 Create `content/events/_index.md` with front matter for the events index page
- [x] 7.2 Create `layouts/events/list.html` that splits events into upcoming (date >= now) and past (date < now) sections, with upcoming shown first chronologically and past in a visually distinct archive section
- [x] 7.3 Create `layouts/events/single.html` rendering a single event with title, date, location, and description
- [x] 7.4 Create at least one sample event in `content/events/` with `title`, `date`, `location` front matter (migrate existing events if available)
- [x] 7.5 Verify: events page shows upcoming and past sections correctly; event detail pages render; page handles zero upcoming events without error

## 8. Content Migration

- [x] 8.1 Download and save the Verein logo from the existing site to `static/images/`
- [x] 8.2 Migrate text content from capoeira-oldenburg.de into the respective markdown files (Was ist Capoeira, Ueber uns, Kontakt info, Impressum, Datenschutz)
- [x] 8.3 Migrate training schedule data into `data/trainingszeiten.yaml`
- [x] 8.4 Migrate existing blog posts into `content/blog/` as markdown files with correct front matter
- [x] 8.5 Migrate event data into `content/events/` as markdown files
- [x] 8.6 Migrate social media links into `data/social.yaml`
- [x] 8.7 Migrate any reusable images to `static/images/`
- [x] 8.8 Review all migrated content against the live site for completeness and formatting

## 9. Deployment

- [x] 9.1 Create `.github/workflows/deploy.yml` GitHub Actions workflow: trigger on push to main, install Hugo, run `hugo build --minify`, deploy to GitHub Pages
- [ ] 9.2 Verify: workflow runs successfully and site is accessible at the GitHub Pages URL
- [ ] 9.3 Configure custom domain DNS (A records / CNAME pointing to GitHub Pages) and verify HTTPS works at `https://capoeira-oldenburg.de/`

## 10. Final Verification

- [x] 10.1 All nine pages are reachable via navigation or footer links
- [x] 10.2 Site is fully responsive and usable on mobile (test at 320px, 768px, 1024px+)
- [x] 10.3 Impressum and Datenschutzerklaerung are linked from every page via footer
- [x] 10.4 Trainingszeiten displays schedule, locations, and Probetraining note
- [x] 10.5 Blog index shows posts in reverse-chronological order
- [x] 10.6 Events page shows upcoming events and past events archive
- [x] 10.7 All pages have proper `<title>`, meta description, canonical URL, and semantic HTML
- [x] 10.8 LocalBusiness JSON-LD is present on all pages
- [x] 10.9 Site loads noticeably faster than the current capoeira-oldenburg.de
