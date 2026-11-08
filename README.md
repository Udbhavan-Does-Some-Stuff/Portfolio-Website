# Portfolio

Personal site for Udbhavan Banerjee — systems engineering and machine learning.
Live at [TODO: add your URL once deployed].

## What this is

A single static HTML page. No build step, no dependencies to install, no framework.

```
index.html    the whole site — markup, styles, scripts, and inlined logo SVGs
resume.pdf    linked from the hero and the contact section
```

Open `index.html` in a browser and that is the site.

## Stack

- Hand-written HTML and CSS, no preprocessor
- [GSAP](https://gsap.com) + ScrollTrigger from cdnjs, for the reveals and the stacked project cards
- [Instrument Serif](https://fonts.google.com/specimen/Instrument+Serif) and [Archivo](https://fonts.google.com/specimen/Archivo) from Google Fonts
- Technology logos from [Simple Icons](https://simpleicons.org), inlined as SVG so they inherit `currentColor`

The prediction plot in the hero is drawn in SVG and resampled in JavaScript. It illustrates the
multimodal trajectory prediction project: three seconds of observed motion, then several weighted
six-second futures.

## Local development

No server required, but relative paths behave better over HTTP:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deployment

Served as static files from the repository root. GitHub Pages: **Settings → Pages →
Deploy from a branch → `main` / `(root)`**.

To attach a custom domain, add a `CNAME` file containing the bare domain and point
the DNS records at GitHub Pages.

## Accessibility and performance notes

- Every colour is a CSS custom property with light and dark values; the page follows the
  system theme and an explicit `data-theme` override.
- All motion is behind `prefers-reduced-motion: reduce`, which also disables the sticky
  card stacking and the custom cursor.
- No animation runs per scroll frame. The ScrollTriggers are one-shot, and the cursor
  loop sleeps when the pointer is still.
- The custom cursor and magnetic buttons are disabled on coarse pointers.
