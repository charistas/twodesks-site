# Copilot Repository Instructions

Read `AGENTS.md` first. This is a static GitHub Pages site for `https://twodesks.app`.

- On a fresh clone, run `npm ci` and `npm run install:browsers` before browser tests.
- Run `npm test` before handoff.
- Use `npm run verify` for static metadata/link/content checks.
- Use `npm run test:browser` for Playwright rendering screenshots and axe accessibility smoke tests.
- Keep the site plain HTML/CSS/JS. Do not add a framework or bundler.
- Do not add analytics claims or scripts unless the privacy policy is updated.
- Do not reintroduce old Bloomery or Mind Garden positioning.
