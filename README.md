# chispot_web

The public marketing site for **chispots.com** — a static, no-build site
(plain HTML + CSS). Design tokens mirror the mobile app theme
(`chispot_mobile/src/theme`) so the web presence reads as the same product.

Current state: **coming-soon landing** + **privacy policy**. The store slot in
`index.html` (marked with a comment) is where the App Store / Google Play badges
and links drop in at launch.

## Files

- `index.html` — coming-soon landing + contact/support (Apple Support URL = `chispots.com`).
- `privacy.html` — Privacy Policy (Apple submission requires a reachable Privacy Policy URL: `chispots.com/privacy.html`).
- `styles.css` — shared tokens + layout (light/dark via `prefers-color-scheme`).
- `favicon.svg` — location-pin mark in the app accent.

## Deploy — Cloudflare Pages

Hosting is **Cloudflare Pages** (free static hosting on a global CDN, HTTPS
auto-provisioned). Every project gets a live `*.pages.dev` URL immediately, even
before DNS is attached.

1. Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** →
   **Upload assets** (direct upload) → drag this `chispot_web` folder.
   (Later, switch to a Git-connected project so pushes auto-deploy.)
2. Confirm the page loads at the generated `*.pages.dev` URL.
3. **Custom domain** → add `chispots.com` and `www.chispots.com`.

### Pointing the domain (DNS stays at Network Solutions for now)

DNS currently lives at Network Solutions. To go live **without touching the Zoho
mail records**, add records-only in the NetSol panel (do **not** change
nameservers yet):

- `www` → `CNAME` → the `*.pages.dev` target Cloudflare shows.
- apex (`@`) → the `A`/`AAAA` targets Cloudflare provides for the custom domain,
  replacing the parking-page `A` record (`208.91.197.27`).

Leave the Zoho `MX`, merged `SPF`, both `DKIM` keys, and `_dmarc` untouched.
