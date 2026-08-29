# ahujaakash007.github.io

Personal portfolio — **https://ahujaakash007.github.io**

Single static page, no build step. `index.html` contains the markup, CSS and JS inline.

## Editing

Edit `index.html`, then:

```bash
git add -A && git commit -m "Update copy" && git push
```

GitHub Pages redeploys automatically in ~1 minute.

## Local preview

```bash
python3 -m http.server 4173
```

Then open http://localhost:4173

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The entire site |
| `og.png` | 1200×630 link-preview image (LinkedIn / WhatsApp / X) |
| `Aakash-Ahuja-CV.pdf` | Linked by the "Download CV" button — **not yet added** |

## Notes

- The link-preview image is referenced by absolute URL in the `og:image` meta tag. If the
  site ever moves to a custom domain, update `og:image`, `og:url` and `canonical` in `index.html`.
- Social platforms cache previews aggressively. After changing `og.png`, re-scrape via
  [LinkedIn Post Inspector](https://www.linkedin.com/post-inspector/).
