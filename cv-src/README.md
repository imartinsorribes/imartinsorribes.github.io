# CV source (editable)

These HTML files are the **editable source** for the PDF CVs at
`imartinsorribes.github.io/assets/cv-es.pdf` and `cv-en.pdf`.
Until now there was no source — the PDFs had been produced ad-hoc — so any
edit meant rebuilding from scratch. Edit the HTML here instead and re-render.

- `cv-es.html` — Spanish CV
- `cv-en.html` — English CV
- `avatar.png` — photo used by both (keep next to the HTML)

Font: **Source Sans 3** (Google Fonts), the same family the original PDFs used.
Layout is tuned to fit exactly **one A4 page**; if you add content, keep an eye
on overflow.

## Regenerate the PDFs

Headless Chrome (Windows path shown; adjust if needed):

```bash
CHROME="/c/Program Files/Google/Chrome/Application/chrome.exe"
"$CHROME" --headless=new --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="cv-es.pdf" "file:///<abs-path>/cv-src/cv-es.html"
"$CHROME" --headless=new --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="cv-en.pdf" "file:///<abs-path>/cv-src/cv-en.html"
```

Then copy `cv-es.pdf` / `cv-en.pdf` into the site repo's `assets/` folder.

### Check it still fits one page

Open the HTML in a browser and confirm `document.body.scrollHeight` stays
under ~1123px (A4 height at 96dpi), or just print-preview to A4 and confirm
it's a single page.
