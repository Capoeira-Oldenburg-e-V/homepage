## Context

The live site serves images through Jimdo's CDN at `image.jimcdn.com` at multiple responsive dimensions. By analysing document order (image IDs relative to date stamps in the HTML), the following mapping was established:

| Image ID | Filename | Blog post |
|---|---|---|
| `i8444528cfd6a9c09` | `volta-por-cima-header.jpg` | `wirwunder-2025.md` (Volta por Cima section) |
| `i6bc973374f1eced7` | `volta-por-cima-1.jpg` | `wirwunder-2025.md` |
| `i82010b715b0c0f56` | `volta-por-cima-2.jpg` | `wirwunder-2025.md` |
| `idc5adc161ddfe4a0` | `volta-por-cima-3.jpg` | `wirwunder-2025.md` |
| `i9d0c945eb1c5dede` | `duesseldorf-2025.jpg` | `jahresrueckblick-2025.md` |
| `iee3a22d469cab7db` | `spaetsommerworkshop-2023.jpg` | `spaetsommerworkshop-2023.md` (new) |
| `i73fbf38349884321` | `workshop-aug-2023-1.jpg` | `workshop-aug-2023.md` (new) |
| `i62dcfb2ee9a08fe0` | `workshop-aug-2023-2.jpg` | `workshop-aug-2023.md` (new) |
| `i06b6370fabfe18e0` | `spendenaktion-2023.jpg` | standalone — added to a new `spendenaktion-2023.md` post |
| `ia21809f922bf0dc1` | `training-2022.jpg` | `willkommen.md` as a general training photo |

Already downloaded (excluded from this change): logo (`ifb3c4dd6b673b014`), training shot (`i7c44c01cc82f4bf7`).

## Goals / Non-Goals

**Goals:**
- All blog-associated images saved locally under `static/images/blog/`
- Each image referenced via inline markdown in its corresponding post
- Two missing 2023 posts created with their images

**Non-Goals:**
- CSS changes for image layout (existing `.post-body img { max-width: 100% }` inherits from the global `img` reset)
- Caption styling or lightbox
- Downloading full-resolution originals beyond 664px wide (sufficient for web display)

## Decisions

### D1: `static/images/blog/` subdirectory

Keeps blog images separate from general site images (`logo.png`, `capoeira-training.jpg`). No Hugo Pipes needed — static images are copied as-is.

### D2: Download at 664px wide dimension

The 664px variants are the largest that fit the `--max-width: 900px` content column with padding. The originals are not always available without authentication. Use the `dimension=664x10000` URL form.

### D3: Inline markdown images, not front matter `featured_image`

Inline `![alt text](/images/blog/name.jpg)` requires no template changes and gives the post author control over placement. A `featured_image` field would require a template update and is over-engineering for the current scope.

## Risks / Trade-offs

- **Image–post attribution** — The Jimdo page is a single-scroll news feed, not individual post pages. Attribution was inferred from document order. There is a small risk one or two images are misattributed by one post. Visual review after implementation is recommended.
- **Jimdo CDN availability** — These are external CDN URLs. They should remain accessible since the old site is still live, but they could be taken down after the DNS cutover. Downloading now mitigates this.
