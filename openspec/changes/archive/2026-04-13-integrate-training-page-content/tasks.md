## 1. Download and store the training image

- [x] 1.1 Download `https://image.jimcdn.com/app/cms/image/transf/none/path/s3b1439775dda3467/image/i4cbb9f38a246e117/version/1484938006/image.jpg` using curl with browser headers and save as `static/images/training-ablauf.jpg`

## 2. Rename the page files

- [x] 2.1 Rename `content/trainingszeiten.md` to `content/training.md`
- [x] 2.2 Rename `layouts/_default/trainingszeiten.html` to `layouts/_default/training.html`
- [x] 2.3 Update the `layout:` value in `content/training.md` frontmatter from `"trainingszeiten"` to `"training"`
- [x] 2.4 Update the page `title` in `content/training.md` frontmatter from `"Trainingszeiten"` to `"Training"`

## 3. Update the schedule data

- [x] 3.1 Add `notes: "Wintersaison (Oktober–April)"` to the Freitag entry in `data/trainingszeiten.yaml`

## 4. Integrate the content

- [x] 4.1 Replace the content body of `content/training.md` with the migrated sections: training locations intro, "Ablauf des Trainings" heading + image + description, Probetraining heading + details, clothing tip

## 5. Update navigation and internal links

- [x] 5.1 Update `hugo.toml` menu entry: change `name` from `'Trainingszeiten'` to `'Training'` and `url` from `'/trainingszeiten/'` to `'/training/'`
- [x] 5.2 Update link in `content/was-ist-capoeira.md` from `/trainingszeiten/` to `/training/`
- [x] 5.3 Update link in `content/blog/willkommen.md` from `/trainingszeiten/` to `/training/`
- [x] 5.4 Update link in `layouts/index.html` home card (if it references `/trainingszeiten/`) to `/training/`

## 6. Build and verify

- [x] 6.1 Run `hugo build` and confirm it succeeds with no errors
- [x] 6.2 Confirm `public/training/index.html` exists and contains the schedule table, training description, photo, Probetraining section, and clothing tip
- [x] 6.3 Confirm `public/trainingszeiten/` does NOT exist (old URL gone)
- [x] 6.4 Confirm the nav in any rendered page links to `/training/` with label "Training"
