## Why

The migrated blog posts on the new site are text-only. The original site's news feed includes images alongside each entry. Without these images the blog posts look sparse compared to the live site, and some entries (particularly workshops and events) are primarily communicated through photos.

## What Changes

- Download all unique blog/news images from the live site (Jimdo CDN) to `static/images/blog/`
- Embed the images inline in their corresponding blog posts using standard markdown image syntax
- Create two additional blog posts for 2023 news entries that have images but were not yet migrated: the Spätsommerworkshop 2023 and the August 2023 workshop
- Add a `static/images/blog/` subdirectory to keep blog images separate from general site images

## Capabilities

### New Capabilities

None.

### Modified Capabilities

- `blog-images`: Blog posts SHALL include images migrated from the original site where images exist. Each image SHALL be stored locally in `static/images/blog/` and referenced via a relative path.

## Impact

- `static/images/blog/`: new directory with ~9 image files
- `content/blog/jahresrueckblick-2025.md`: add 1 inline image (Volta por Cima)
- `content/blog/wirwunder-2025.md`: add 3 inline images (Volta por Cima gallery)
- `content/blog/sportsommer-2024.md`: no images found for this entry on the live site
- `content/blog/plaene-2024.md`: no images found for this entry
- `content/blog/spaetsommerworkshop-2023.md`: new post with 1 image
- `content/blog/workshop-aug-2023.md`: new post with 2 images
- No template or CSS changes required; `<img>` tags rendered from markdown body are already styled by `.post-body` rules
