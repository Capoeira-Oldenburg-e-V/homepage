## ADDED Requirements

### Requirement: Blog images stored locally
All images migrated from the original site's blog/news entries SHALL be stored in `static/images/blog/`. No blog post SHALL reference an external `image.jimcdn.com` URL.

#### Scenario: Images are in static directory
- **WHEN** the site is built
- **THEN** the `public/images/blog/` directory contains the migrated image files

### Requirement: Blog posts include inline images
Each blog post that has a corresponding image on the original site SHALL contain at least one inline image rendered from a locally stored file.

#### Scenario: Post renders its image
- **WHEN** a visitor navigates to a blog post that has an associated image
- **THEN** the image is visible in the post body

#### Scenario: Images are responsive
- **WHEN** a blog post with an image is viewed at 320px viewport width
- **THEN** the image does not overflow its container (inherits `max-width: 100%` from global img reset)

### Requirement: Two additional 2023 blog posts with images
Two 2023 news entries that exist on the live site and have images SHALL be added as blog posts: the Spätsommerworkshop 2023 (October 2023) and the August 2023 workshop (August 2023).

#### Scenario: 2023 posts are in the blog index
- **WHEN** a visitor navigates to `/blog/`
- **THEN** the Spätsommerworkshop 2023 and August 2023 workshop posts appear in the listing in correct reverse-chronological order
