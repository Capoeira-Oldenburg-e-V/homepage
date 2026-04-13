## ADDED Requirements

### Requirement: GitHub Actions build workflow
A GitHub Actions workflow SHALL build the Hugo site on every push to the main branch. The workflow SHALL use a recent Hugo version and produce the static output.

#### Scenario: Site builds on push
- **WHEN** code is pushed to the main branch
- **THEN** the GitHub Actions workflow triggers and runs `hugo build` successfully

### Requirement: GitHub Pages deployment
The workflow SHALL deploy the built site to GitHub Pages. The site SHALL be accessible via HTTPS at `https://capoeira-oldenburg.de/`.

#### Scenario: Site is deployed and accessible
- **WHEN** the build workflow completes successfully
- **THEN** the built site is deployed to GitHub Pages and accessible at the custom domain

### Requirement: Custom domain configuration
The repository SHALL include a `CNAME` file in `static/` containing `capoeira-oldenburg.de` so that GitHub Pages serves the site on the custom domain.

#### Scenario: CNAME file present
- **WHEN** the site is built
- **THEN** the `public/` output contains a `CNAME` file with `capoeira-oldenburg.de`

### Requirement: HTTPS enforcement
The site SHALL be served over HTTPS. GitHub Pages provides this automatically for custom domains with correct DNS configuration.

#### Scenario: Site served over HTTPS
- **WHEN** a visitor navigates to `http://capoeira-oldenburg.de/`
- **THEN** they are redirected to `https://capoeira-oldenburg.de/`
