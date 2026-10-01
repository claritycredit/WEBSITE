# Clarity Credit & Co. — Website

A single self-contained HTML file for the Clarity Credit & Co. marketing site. No build step, no dependencies to install — everything (styles, images, scripts) lives inside `index.html`.

## Publishing (GitHub Pages)

1. In your GitHub repo, upload/replace `index.html` at the root (or inside `/docs` if that's how Pages is configured).
2. Commit the change.
3. GitHub Pages rebuilds automatically — give it 1–2 minutes, then hard-refresh (Ctrl/Cmd+Shift+R) to clear cached CSS/JS.

That's the whole deploy process. There's nothing else to install or configure.

## What's in the file

- **One file, four parts:** `<style>` (all CSS), the page markup (`<body>`), the two popup modals (booking call + hidden leftover styling), and a `<script>` block at the bottom handling the booking popup and smooth interactions.
- **Images are embedded**, not linked — the logo, hero photo, and headshot are all base64-encoded directly into the HTML (`data:image/...;base64,...`). This means the site has zero broken-image risk, but it also means the file itself is large (a few MB). To swap an image, you need to re-encode a new one to base64 and replace the relevant `src="data:image/..."` string — ask Claude to do this any time you have a new photo.

## Key sections (in page order)

| Section | What it is |
|---|---|
| Nav | Logo + menu + "Book a Call" button (sticky at top) |
| Hero | Headline, subhead, hero photo, CTA |
| The Method | Dispute → Rebuild → Thrive sequence |
| Who We Serve | Audience section |
| Services | Service cards (Full Service Repair, Audit, Consultation, etc.) |
| Results | Proof/results strip |
| About Su | Founder bio + headshot |
| Join Our Email List | Embedded signup form (LeadConnector) |
| Final CTA | Book Your Audit / Instagram |
| Footer | Nav links, Connect links, social |

## Interactive elements

- **"Book a Call" buttons** (nav, hero, footer, final CTA) open a popup modal containing an embedded LeadConnector booking calendar. The popup only loads the calendar the first time it's opened, so the page stays fast.
- **Email signup form** is embedded directly inline on the page (not a popup) in the "Join Our Email List" section, so visitors see and can fill it out without any extra click.
- Both embeds point to LeadConnector/GoHighLevel widget URLs. If those links ever change, search the file for `leadconnectorhq.com` and swap in the new widget URL(s).

## Brand reference

| Color | Hex | Use |
|---|---|---|
| Deep Navy | `#0D1B2A` | Primary background |
| Navy Mid | `#1E3352` | Secondary surfaces |
| Champagne Gold | `#C9A84C` | Primary accent |
| Gold Light | `#E2C97E` | Hover states |
| Cream | `#FAF7F2` | Body text / light backgrounds |
| Muted Blue-Grey | `#8A9BB0` | Supporting text |

Fonts: **Playfair Display** (headlines), **Montserrat** (body/UI) — loaded from Google Fonts.

## Making common edits

- **Change text:** find the text in the file (Ctrl/Cmd+F) and edit it directly — it's plain HTML.
- **Change a link/button destination:** look for the matching `<a href="...">` tag.
- **Swap a photo or the logo:** send Claude the new image and ask it to update the relevant section — it'll handle resizing and re-embedding.
- **Update the booking or email widget:** replace the LeadConnector URL in the iframe's `src` (or `data-src` for the booking popup).

## Notes

- The site is fully responsive (mobile, tablet, desktop) and has been tested at common breakpoints.
- Because everything is one file, always keep a backup of the last known-good version before making manual edits — a single broken tag can affect the whole layout.
