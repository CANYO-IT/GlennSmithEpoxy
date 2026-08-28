# Glenn Smith Epoxy — Website

Single-file static site (`index.html`). No build step, no dependencies — just hand-coded
HTML/CSS/JS with Google Fonts loaded from CDN. Deploy anywhere (GitHub Pages, Netlify,
cPanel, S3) by uploading `index.html`.

## Wire up the quote form (Formspree) — 2 steps

1. Create a free form at https://formspree.io and copy your form ID (looks like `xabcdwyz`).
2. In `index.html`, find `YOUR_FORMSPREE_ID` (in the `<form>` tag, inside the "quote" section)
   and replace it with your ID:
   `<form id="quoteForm" action="https://formspree.io/f/xabcdwyz" method="POST">`

Done. Submissions email you automatically, and the page shows an inline success
message (no redirect, no page reload). A honeypot field (`_gotcha`) is already in place
for spam.

Until you wire it, submitting shows a toast reminder instead of losing the lead —
and the click-to-call buttons always work.

## Nice extras already built in

- **Finish Lab → form pre-fill**: when a visitor builds a flake blend and clicks
  "Request this finish", the Finish Style dropdown and the message box are pre-filled
  with their exact selection (base coat + blend + broadcast density). Look for
  `data-lab` attributes if you want to customize.
- **WebGL liquid-resin hero**: animated molten epoxy shader that reacts to the mouse.
  Degrades gracefully — static gradient fallback if WebGL is unavailable, and all
  motion is disabled for `prefers-reduced-motion` users.
- **Before/After slider**: draggable (touch + mouse + arrow keys), auto-sways until
  first interaction.
- **SEO**: LocalBusiness JSON-LD schema, meta/OG tags, semantic headings — edit the
  `<head>` to adjust.
- **Zero tracking**: no analytics, no cookies. Add your own if you want them.

## Local preview

    cd ~/Sites/GlennSmithEpoxy && python3 -m http.server 8080
    # then open http://localhost:8080

(Or just double-click `index.html` — everything works from `file://` too.)
