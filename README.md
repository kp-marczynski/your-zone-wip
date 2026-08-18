# your-zone-wip

The **YOUR ZONE** holding page ("Strona w budowie"), served from GitHub Pages.

`index.html` is a self-contained export of the `/w-budowie/` page from the
`your-zone` WordPress project: one file, every asset (fonts, icons, photos, the
"AI generated" mark) embedded as a `data:` URI, no external requests.

## Updating it

Rebuild the export from the running site and copy it over `index.html`:

```sh
cd ~/code/your-zone
make up                       # site must be running and provisioned
make static-snapshot PAGES=/w-budowie/ PHOTOS=real \
  OUT=../your-zone-wip/index.html
```

`PAGES=` captures exactly that route (a single page ships without the preview
router, so the file *is* the page); `PHOTOS=real` embeds the real pictures
instead of the placeholder boxes.
