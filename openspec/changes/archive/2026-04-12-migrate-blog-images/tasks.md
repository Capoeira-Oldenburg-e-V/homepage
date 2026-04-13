## 1. Download Images

- [x] 1.1 Create `static/images/blog/` directory
- [x] 1.2 Download `i8444528cfd6a9c09` → `static/images/blog/volta-por-cima-header.jpg` (URL: `https://image.jimcdn.com/app/cms/image/transf/dimension=664x10000:format=jpg/path/s3b1439775dda3467/image/i8444528cfd6a9c09/version/1717054519/image.jpg`)
- [x] 1.3 Download `i6bc973374f1eced7` → `static/images/blog/volta-por-cima-1.jpg` (URL: `https://image.jimcdn.com/app/cms/image/transf/dimension=664x1024:format=jpg/path/s3b1439775dda3467/image/i6bc973374f1eced7/version/1759219476/image.jpg`)
- [x] 1.4 Download `i82010b715b0c0f56` → `static/images/blog/volta-por-cima-2.jpg` (URL: `https://image.jimcdn.com/app/cms/image/transf/dimension=664x1024:format=jpg/path/s3b1439775dda3467/image/i82010b715b0c0f56/version/1759221324/image.jpg`)
- [x] 1.5 Download `idc5adc161ddfe4a0` → `static/images/blog/volta-por-cima-3.jpg` (URL: `https://image.jimcdn.com/app/cms/image/transf/dimension=664x10000:format=jpg/path/s3b1439775dda3467/image/idc5adc161ddfe4a0/version/1759221375/image.jpg`)
- [x] 1.6 Download `i9d0c945eb1c5dede` → `static/images/blog/duesseldorf-2025.jpg` (URL: `https://image.jimcdn.com/app/cms/image/transf/dimension=666x1024:format=jpg/path/s3b1439775dda3467/image/i9d0c945eb1c5dede/version/1717054377/image.jpg`)
- [x] 1.7 Download `iee3a22d469cab7db` → `static/images/blog/spaetsommerworkshop-2023.jpg` (URL: `https://image.jimcdn.com/app/cms/image/transf/dimension=664x10000:format=jpg/path/s3b1439775dda3467/image/iee3a22d469cab7db/version/1696500077/image.jpg`)
- [x] 1.8 Download `i73fbf38349884321` → `static/images/blog/workshop-aug-2023-1.jpg` (URL: `https://image.jimcdn.com/app/cms/image/transf/dimension=664x10000:format=jpg/path/s3b1439775dda3467/image/i73fbf38349884321/version/1692370537/image.jpg`)
- [x] 1.9 Download `i62dcfb2ee9a08fe0` → `static/images/blog/workshop-aug-2023-2.jpg` (URL: `https://image.jimcdn.com/app/cms/image/transf/dimension=664x10000:format=jpg/path/s3b1439775dda3467/image/i62dcfb2ee9a08fe0/version/1692370626/image.jpg`)
- [x] 1.10 Download `i06b6370fabfe18e0` → `static/images/blog/spendenaktion-2023.jpg` (URL: `https://image.jimcdn.com/app/cms/image/transf/dimension=454x1024:format=jpg/path/s3b1439775dda3467/image/i06b6370fabfe18e0/version/1686295741/image.jpg`)
- [x] 1.11 Download `ia21809f922bf0dc1` → `static/images/blog/training-2022.jpg` (URL: `https://image.jimcdn.com/app/cms/image/transf/dimension=664x1024:format=jpg/path/s3b1439775dda3467/image/ia21809f922bf0dc1/version/1485003161/image.jpg`)

## 2. Update Existing Blog Posts

- [x] 2.1 Add `![Volta por Cima Workshop](/images/blog/volta-por-cima-header.jpg)` to `content/blog/wirwunder-2025.md`, followed by a gallery of `volta-por-cima-1.jpg`, `volta-por-cima-2.jpg`, `volta-por-cima-3.jpg`
- [x] 2.2 Add `![Workshop in Düsseldorf](/images/blog/duesseldorf-2025.jpg)` to `content/blog/jahresrueckblick-2025.md`
- [x] 2.3 Add `![Capoeira Training](/images/blog/training-2022.jpg)` to `content/blog/willkommen.md`

## 3. Create Missing 2023 Blog Posts

- [x] 3.1 Create `content/blog/spaetsommerworkshop-2023.md` (date: 2023-10-05) with migrated text about the Spätsommerworkshop and inline image `spaetsommerworkshop-2023.jpg`
- [x] 3.2 Create `content/blog/workshop-aug-2023.md` (date: 2023-08-25) with migrated text about the August 2023 workshop and inline images `workshop-aug-2023-1.jpg` and `workshop-aug-2023-2.jpg`

## 4. Verify

- [x] 4.1 Run `hugo build` and confirm no errors
- [x] 4.2 Confirm `public/images/blog/` contains all 11 downloaded image files
- [x] 4.3 Open blog posts in `hugo server` and confirm images render correctly and are responsive at 320px
