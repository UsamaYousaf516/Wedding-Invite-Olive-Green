# Aarav &amp; Meera — digital wedding invitation

A self-contained digital invitation: a sealed envelope you click to open, a
flat-lay stationery suite that doubles as the navigation, a live countdown, and
four full pages behind it — Save the Date, Our Story, Wedding Details and RSVP.

Everything is one `index.html` plus `assets/`. No build step, no framework, no
external requests: the fonts and the paper are served from this repo.

## Running it locally

Relative asset paths need a server — opening the file directly shows the paper
and the cover but not the cut-outs.

```bash
python -m http.server 5183
```

Then open <http://localhost:5183>.

## What's here

| Path | |
|---|---|
| `index.html` | the whole site — markup, styles and behaviour |
| `assets/` | 23 WebP cut-outs, the paper tile, the countdown painting, 7 fonts |
| `composition.ts` | the tablet layout as typed constants, generated from the markup |
| `composer-notes.txt` | **read this first** — the flow, the canvas rules, and what not to undo |

## Before sending it to anyone

- **The RSVP form is not connected.** `#rsvp-form` has an empty `data-endpoint`
  and refuses to submit until one is set. See `composer-notes.txt`.
- **`og:image` is a relative path.** Fine for WhatsApp, Slack and Twitter;
  Facebook's scraper wants an absolute URL once there is a domain.
- The date appears in several places and they are not wired together.

## Credits

Typefaces: Cormorant Garamond, Pinyon Script, Jost, Italiana, Italianno,
Cinzel, EB Garamond — all Open Font License, self-hosted.
