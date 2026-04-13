### Requirement: Blog index page
The blog index page at `/blog/` SHALL display all blog posts in reverse-chronological order (newest first). Each entry SHALL show the post title, date, and a summary or excerpt.

#### Scenario: Posts displayed in reverse-chronological order
- **WHEN** a visitor navigates to `/blog/`
- **THEN** blog posts are listed with the most recent post first, each showing title, date, and summary

#### Scenario: Blog index with no posts
- **WHEN** no blog posts exist
- **THEN** the blog index page renders without errors

### Requirement: Blog posts as markdown files
Blog posts SHALL be authored as markdown files in `content/blog/`. Each post SHALL have front matter with at least `title`, `date`, and `description` fields.

#### Scenario: Blog post renders from markdown
- **WHEN** a blog post markdown file exists in `content/blog/` with valid front matter
- **THEN** it is accessible at `/blog/<slug>/` and renders the markdown content as HTML

### Requirement: Blog post single page
Each blog post SHALL have its own page displaying the full post content, title, and publication date.

#### Scenario: Single blog post page
- **WHEN** a visitor navigates to a blog post URL
- **THEN** the page displays the post title, publication date, and full content
