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
| `work/bddb-*.mp4` | Self-hosted films in "Made with the pipeline" (720×720, faststart) |
| `work/bddb-*.jpg` | Poster frames for those films |

## Palette

Sampled from [sarvam.ai](https://www.sarvam.ai/). Defined once in the `:root` block at the top
of `index.html` — change these and the whole site follows:

| Token | Value | Role |
| --- | --- | --- |
| `--paper` | `#FFFFFF` | page background |
| `--surface` | `#F5F5F5` | tinted band, card wells, secondary pills |
| `--ink` | `#1F1F1F` | headings |
| `--ink-2` | `#3D3D3D` | body text |
| `--muted` | `#666666` | labels, captions |
| `--accent` | `#212191` | Sarvam indigo |
| `--peri-2` | `#D5E0FE` | periwinkle highlight behind bold text |
| `--btn` | `#2A2C33` | primary pill button |

The hero bloom (`body::before`) is a radial gradient stepping peach `#EFAF80` through
periwinkle `#C1CCF6` to white, matching Sarvam's hero.

Type is **Inter Tight** (headings) and **Inter** (body). Sarvam itself uses Matter and
Season Mix, both commercial licences — Inter is the closest freely available match.

Contrast on white: headings 16.5:1, body 10.9:1, muted 5.7:1, indigo 12.4:1. The indigo
holds 7.9:1 against the periwinkle band, so the eyebrow stays legible over the gradient.

## Video

Films in "Made with the pipeline" are self-hosted from `work/`. Two rules when adding more:

- Remux with `ffmpeg -i in.mp4 -c copy -movflags +faststart out.mp4`. Without `faststart`
  the `moov` atom sits at the end of the file and the browser must download the whole thing
  before it will play.
- Always give the `<video>` a `poster` and `preload="metadata"`, so the page costs a few KB
  until someone actually presses play.
- In CSS the video needs `height:auto`. The `height` HTML attribute is a presentational hint
  that otherwise beats `aspect-ratio` and leaves the box at its intrinsic height.

## Notes

- The link-preview image is referenced by absolute URL in the `og:image` meta tag. If the
  site ever moves to a custom domain, update `og:image`, `og:url` and `canonical` in `index.html`.
- Social platforms cache previews aggressively. After changing `og.png`, re-scrape via
  [LinkedIn Post Inspector](https://www.linkedin.com/post-inspector/).
