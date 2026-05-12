# Two Desks Website

Landing page for [twodesks.app](https://twodesks.app) — a small studio making thoughtful mobile apps.

## Local Development

```bash
npx serve .
```

Or:

```bash
python3 -m http.server 8000
```

## Deployment

Deployed via GitHub Pages with custom domain (twodesks.app) through Cloudflare.

## Launch QA Notes

- Pages: `index.html`, `privacy.html`
- Metadata: canonical URLs, Open Graph, Twitter preview cards, theme color, SVG favicon, and social preview image are defined.
- Accessibility: semantic headings, skip link, visible keyboard focus, and 44px minimum link targets are included.
- Privacy: policy is plain-language and matches the studio landing page's data collection claims.
- Verified on May 12, 2026 with `python3 -m http.server` at desktop `1440x900` and mobile `390x844` widths.
