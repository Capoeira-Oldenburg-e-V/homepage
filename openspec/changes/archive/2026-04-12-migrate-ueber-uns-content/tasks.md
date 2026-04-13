## 1. Download Image

- [x] 1.1 Download the Mestre Amapá portrait from `https://image.jimcdn.com/app/cms/image/transf/dimension=204x1024:format=jpg/path/s3b1439775dda3467/image/i5ff6fe9d9f00aab3/version/1555623833/image.jpg` and save to `static/images/mestre-amapa.jpg`

## 2. Migrate Content

- [x] 2.1 Replace `content/ueber-uns.md` with the full migrated content structured as four `##` sections: "Mestre Amapá", "Unser Verein", "Auftritte & Workshops", with the portrait photo embedded using `![Mestre Amapá](/images/mestre-amapa.jpg)`

## 3. Verify

- [x] 3.1 Run `hugo build` and confirm no errors
- [x] 3.2 Open `/ueber-uns/` in `hugo server` and confirm all four sections and the photo are visible
