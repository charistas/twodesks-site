# Two Desks Site Guidance

## Project Snapshot

- Static GitHub Pages site for `https://twodesks.app`.
- Purpose: studio website for Two Desks, with Tendi as the first public product.
- Pages: `index.html`, `privacy.html`, `.well-known/security.txt`, `llms.txt`, `robots.txt`, `sitemap.xml`.
- Runtime code is plain HTML, CSS, and a small `assets/site.js` helper for email-link generation, current year text, and reveal animations.
- Deployment is GitHub Pages behind Cloudflare with custom domain `twodesks.app`.

## Product And Privacy Constraints

- Two Desks is a small studio making thoughtful, privacy-first mobile apps.
- Tendi is the first public product and links to `https://tendijournal.app`.
- The site has no accounts, no forms, no newsletter signup, and no separate analytics script in this repository.
- The support link goes to `https://buymeacoffee.com/twodesks`; payments happen there, not on `twodesks.app`.
- Do not claim Cloudflare Web Analytics unless it is intentionally enabled and the privacy policy is updated.
- Do not reintroduce old Bloomery or Mind Garden positioning into public site copy.

## Development

Use port `8001` for local preview:

```bash
python3 -m http.server 8001
```

Open `http://localhost:8001`.

## Verification

Install dependencies with `npm ci` after cloning or when `package-lock.json` changes.
Install Playwright's Chromium browser with `npm run install:browsers` before the first browser test run on a fresh machine.

Run the full local gate before handoff:

```bash
npm test
```

Useful focused checks:

```bash
npm run verify
npm run test:browser
```

The browser check starts a local static server, runs desktop `1280x900` and mobile `390x844` rendering checks, writes screenshots under `test-results/screenshots/`, and runs axe accessibility smoke tests. Review screenshots when layout, copy length, imagery, or CSS changes.

## Editing Rules

- Keep the site static; do not add React, Vite, Tailwind, or a bundler.
- Keep page metadata aligned across canonical URL, Open Graph, Twitter tags, `sitemap.xml`, `robots.txt`, and `llms.txt`.
- If public copy changes, check `privacy.html` and `llms.txt` for matching claims.
- Keep `_config.yml` excluding agent, test, and tooling files from GitHub Pages while including `.well-known`; do not re-add `.nojekyll` unless Pages deployment moves off repository-root publishing.
- Keep `social-card.png` at `1200x630` when regenerating it.
- Keep Cloudflare notes in `cloudflare-security.md` current if DNS, headers, CSP, or Cloudflare injection behavior changes.

## Cloudflare Gotchas

- The live site may include Cloudflare-injected bot/security markup that is not present locally.
- Do not add a strict CSP while Cloudflare is injecting or rewriting live HTML.
- After deploy, fetch the live domain and verify headers, injected scripts, support/contact links, and privacy wording.
