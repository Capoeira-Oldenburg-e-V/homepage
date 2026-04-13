## Why

The current capoeira-oldenburg.de website is a single long-scrolling page that loads slowly and is difficult to navigate on mobile. It fails at its primary job: helping people curious about Capoeira in Oldenburg find the training schedule and show up to a trial session. The site needs a complete replacement with a fast, mobile-first, multi-page static site.

## What Changes

- Replace the entire existing website with a new Hugo-based static site
- Introduce nine distinct pages: Home, Trainingszeiten, Was ist Capoeira?, Ueber uns, Events/Kalender, Blog, Kontakt, Impressum, Datenschutzerklaerung
- Implement mobile-first responsive design with proper multi-page navigation
- Add SEO optimization: semantic HTML, meta tags, LocalBusiness structured data
- Set up deployment via GitHub Pages on the custom domain capoeira-oldenburg.de
- Migrate all existing content: text, images, blog posts, training schedule, social links, logo

## Capabilities

### New Capabilities
- `site-structure`: Base Hugo project setup, configuration, layout system (base template, header/nav, footer with legal links), and CSS architecture
- `content-pages`: Static content pages -- Home, Was ist Capoeira?, Ueber uns, Kontakt, Impressum, Datenschutzerklaerung
- `trainingszeiten`: Training schedule page displaying times, locations, and Probetraining information from a structured data file
- `blog`: Blog section with markdown-authored posts displayed in reverse-chronological order on an index page
- `events`: Events page with chronological event listing and automatic past/upcoming separation with archive section
- `seo`: SEO optimization including per-page titles and meta descriptions, semantic HTML, and LocalBusiness JSON-LD structured data
- `deployment`: GitHub Actions workflow for building Hugo and deploying to GitHub Pages with custom domain and HTTPS

### Modified Capabilities

None. This is a greenfield project with no existing specs.

## Impact

- New Hugo project with full directory structure (content, layouts, data, assets, static)
- New GitHub Actions CI/CD pipeline
- DNS configuration required for custom domain on GitHub Pages
- All existing content from capoeira-oldenburg.de must be manually migrated into markdown and data files
