# Two Desks Website

Static website for [twodesks.app](https://twodesks.app), the studio site for Two Desks.

## Local Development

Use port `8001` so it does not collide with the Bloomery site preview on `8000`.

```bash
python3 -m http.server 8001
```

Open [http://localhost:8001](http://localhost:8001).

## Deployment

Deployed via GitHub Pages with custom domain `twodesks.app` through Cloudflare.

Do not assume Cloudflare-injected behavior from local preview. After deploy, re-fetch the live domain and verify the injected Cloudflare scripts, contact links, and privacy wording still match.

## Launch QA Notes

- Pages: `index.html`, `privacy.html`
- Cloudflare security hardening: follow `cloudflare-security.md` before launch or after DNS/security changes.
- Metadata: canonical URLs, Open Graph, Twitter preview cards, theme color, SVG favicon, and social preview image are defined.
- Accessibility: semantic headings, skip link, visible keyboard focus, and 44px minimum link targets are included.
- Privacy: policy is scoped to the studio website, contact email, the outbound Buy Me a Coffee support link, GitHub Pages hosting, and Cloudflare-provided site services. It does not claim Cloudflare Web Analytics unless separately confirmed.
- Visual QA should cover desktop `1280x900` and mobile `390x844` with a CSS-viewport-accurate browser check.
- Last local QA update: July 2, 2026.

## Asset Provenance

Assets copied from the sibling Bloomery website in `../bloomery-site/`:

- `assets/fonts/Fraunces-opsz-wght-latin.woff2`
- `assets/fonts/OFL.txt`
- `assets/app-icon.png`
- `assets/screenshot-home.png`

Fraunces is licensed under the SIL Open Font License. The subset was already produced for the Bloomery site from the Google Fonts upstream source:

```bash
curl -L 'https://raw.githubusercontent.com/google/fonts/main/ofl/fraunces/Fraunces%5BSOFT%2CWONK%2Copsz%2Cwght%5D.ttf' -o /private/tmp/Fraunces-variable.ttf

pyftsubset /private/tmp/Fraunces-variable.ttf \
  --output-file=assets/fonts/Fraunces-opsz-wght-latin.woff2 \
  --flavor=woff2 \
  --layout-features='*' \
  --unicodes='U+000D,U+0020-007E,U+00A0,U+00A9,U+2019,U+2026'
```

WebP screenshot generated locally:

```bash
cwebp -quiet -q 82 assets/screenshot-home.png -o assets/screenshot-home.webp
```

The social preview PNG is generated from `social-card.svg` with a browser renderer and must be visually inspected after regeneration to confirm the referenced app icon and screenshot rendered.
