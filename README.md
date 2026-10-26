# chispot-web

The public site for **chispots.com** — a static, no-build page (plain HTML + CSS).
Design tokens mirror the Chispot mobile app theme so the web presence reads as
the same product.

## Files

- `index.html` — homepage
- `privacy.html` — privacy policy
- `styles.css` — layout + design tokens (light/dark via `prefers-color-scheme`)
- `logo.png` / `favicon.svg` — brand mark
- `badges/` — official App Store / Google Play badge art (never redrawn or recoloured)
- `screens/` — app screenshots shown on the homepage
- `CNAME` — custom domain for GitHub Pages

## Run locally

```
npx serve .
```

Then open http://localhost:3000. Serve it rather than opening the file directly —
root-relative links (`href="/"`) break under `file://`.

## Deploy

Served by **GitHub Pages** from the `main` branch (root). Pushing to `main`
publishes the site — there is no build step.
