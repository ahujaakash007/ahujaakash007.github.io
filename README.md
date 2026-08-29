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
| `Aakash-Ahuja-CV.pdf` | Linked by the "Download CV" button |
| `aakash.jpg` | Portrait in the contact section (640px wide, watermark cropped) |

## Palette

Defined once in the `:root` block at the top of `index.html` — change these six values and
the whole site follows:

| Token | Value | Role |
| --- | --- | --- |
| `--ink` | `#15100B` | warm espresso background |
| `--ink-2` | `#1D160E` | tinted band (Fun facts) |
| `--bone` | `#F5EDE0` | body text |
| `--mute` | `#9C8B78` | labels, captions |
| `--hot` | `#FF8A3D` | tangerine accent |

Contrast on the background: body 16.3:1, muted 5.7:1, tangerine 8.1:1 — all WCAG AA.

## Notes

- The link-preview image is referenced by absolute URL in the `og:image` meta tag. If the
  site ever moves to a custom domain, update `og:image`, `og:url` and `canonical` in `index.html`.
- Social platforms cache previews aggressively. After changing `og.png`, re-scrape via
  [LinkedIn Post Inspector](https://www.linkedin.com/post-inspector/).
