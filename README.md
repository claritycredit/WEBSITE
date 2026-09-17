# Clarity Credit & Co. — Website

Marketing site for **Clarity Credit & Co.** — strategic credit repair, built around the
brand's core sequence: **Dispute. Rebuild. Thrive.**

🔗 **Live site:** https://claude.ai/artifact/3WMZzgetY3N4AEXn9RYvMF

---

## Overview

This is a **single-file, static HTML website** — no build step, no dependencies, no
backend. Everything (styles, fonts, icons, and images) is bundled into one
self-contained `.html` file so it can be hosted anywhere that serves static files.

- **Framework:** none — plain HTML5 + CSS3
- **Fonts:** Cormorant Garamond (display) + Montserrat (body/UI), loaded from Google Fonts
- **Images:** embedded directly in the file as base64 data URIs (hero photo, founder
  photo, logo lockup) — there are no separate image assets to keep track of
- **Icons:** hand-drawn inline SVG, no icon library

## File Structure

```
.
├── clarity-credit-co.html   # the entire site — one file
└── README.md                # this file
```

## Running Locally

No install required. Either:

```bash
# Option 1: just open it
open clarity-credit-co.html      # macOS
start clarity-credit-co.html     # Windows

# Option 2: serve it (recommended, avoids any local file:// quirks)
python3 -m http.server 8000
# then visit http://localhost:8000/clarity-credit-co.html
```

## Deploying

Because it's a single static file, it can be deployed anywhere with zero config:

| Host | Steps |
|---|---|
| **GitHub Pages** | Rename the file to `index.html`, push to a repo, enable Pages on the `main` branch (root or `/docs`) in **Settings → Pages**. |
| **Netlify / Vercel** | Drag-and-drop the file (or connect the repo) — no build command needed. |
| **Any static host** (S3, Cloudflare Pages, etc.) | Upload the file as `index.html`. |

## Editing the Site

Everything lives in one `<style>` block and one `<body>` in `clarity-credit-co.html`.

**Brand tokens** are defined as CSS custom properties at the top of the `<style>` block:

```css
--navy:        #0D1B2A   /* primary background */
--navy-mid:    #1E3352   /* secondary surfaces */
--gold:        #C9A84C   /* primary accent */
--gold-light:  #E2C97E   /* hover states */
--cream:       #FAF7F2   /* light text */
--slate:       #8A9BB0   /* muted/supporting text */
```

Change a value once here and it updates everywhere on the page.

**Sections** (in order): Hero → Promise strip → The Method (sequence) → Who We Serve →
Services → Results/Proof → About → Final CTA → Footer. Each has its own commented
block in the HTML (`<!-- HERO -->`, `<!-- SERVICES -->`, etc.) for quick navigation.

**Key links to update if they ever change:**
- Call booking (nav, hero, footer, several CTAs): Stan Store booking link
- MyFreeScoreNow affiliate enrollment (Services card)
- General Stan Store / sales hub link
- Instagram: `@flickmeupsu`

## Notes

- All images are inlined as base64 — editing/replacing them requires re-encoding a new
  image and swapping the `data:image/...;base64,...` string in the relevant `<img>` tag.
- The page has no JavaScript and no external API calls beyond Google Fonts, so it has
  no runtime dependencies to keep updated.
- Respects `prefers-reduced-motion` — animated effects (button shimmer, etc.) are
  disabled for users who request reduced motion.

## License

Private brand asset for Clarity Credit & Co. Not licensed for reuse.
