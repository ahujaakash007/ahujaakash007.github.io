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

## Design

Warm editorial paper. Tokens live in the `:root` block at the top of `index.html`:

| Token | Value | Role |
| --- | --- | --- |
| `--paper` | `#FBF7F0` | page background |
| `--paper-2` | `#F4EDE1` | tinted band (Fun facts) |
| `--ink` | `#221B16` | headings, primary text |
| `--muted` | `#7A6B5D` | labels, captions, notes |
| `--accent` | `#B4552F` | terracotta — used sparingly |

Type: **Fraunces** for display, **Newsreader** for body, **Courier Prime** for labels and
figures. Courier is deliberate — screenplays are set in it, which ties the data labels back
to the TVF writing credit.

The stats are set as a **credit roll** — label, dot leader, figure — rather than cards. That
device is the page's signature and is echoed in the section rules.

All text passes WCAG AA against the paper (body 9.7:1, muted 4.8:1, accent 4.6:1).

## Notes

- The link-preview image is referenced by absolute URL in the `og:image` meta tag. If the
  site ever moves to a custom domain, update `og:image`, `og:url` and `canonical` in `index.html`.
- Social platforms cache previews aggressively. After changing `og.png`, re-scrape via
  [LinkedIn Post Inspector](https://www.linkedin.com/post-inspector/).
