## 1. Audit

- [x] 1.1 Run `grep -r "Capoeira Verein Oldenburg"` across the project (excluding `public/`, `.git/`, `openspec/`) to confirm the exact list of files containing the old name

## 2. Update Configuration and Data

- [x] 2.1 Update `hugo.toml`: change `title` from `'Capoeira Verein Oldenburg'` to `'Capoeira Oldenburg e. V.'`
- [x] 2.2 Update `data/verein.yaml`: change `name` field to `"Capoeira Oldenburg e. V."`

## 3. Update Content Pages

- [x] 3.1 Update `content/_index.md`: replace old name in `title`, `description`, and body
- [x] 3.2 Update `content/ueber-uns.md`: replace old name in body text
- [x] 3.3 Update `content/impressum.md`: replace old name in body text
- [x] 3.4 Update `content/datenschutzerklaerung.md`: replace old name in body text

## 4. Verify

- [x] 4.1 Run `hugo build` and confirm no build errors
- [x] 4.2 Confirm `grep -r "Capoeira Verein Oldenburg" public/` returns zero matches
