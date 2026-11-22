# Casebook download page

`index.html` is a fully self-contained static page — no build step, no
dependencies, no trackers. Deploy it anywhere that serves files.

## Before deploying

Edit the `EDIT THESE` block at the top of `index.html`:

- `RELEASES` — where the built installers live. GitHub Releases pattern is
  `https://github.com/<owner>/<repo>/releases/latest/download` — the
  `/latest/` alias always serves the newest release, so the page never needs
  updating for new versions.
- `FILES` — filenames must match what you upload. Current dist output is
  `Casebook Setup 0.1.0.exe` / `Casebook 0.1.0.exe`; either rename uploads to
  the names in FILES or update FILES to match.
- `CHECKOUT` — the payment page/link once a provider is chosen.
- `PRICE_MO` / `PRICE_YR` — display prices.

## Easiest hosting options (all free)

**GitHub Pages** — everything lives in the repo:

1. Push the repo to GitHub (`git init`, `git remote add origin …`, push).
2. Settings → Pages → source = `main` branch, folder = `/site` (rename `site/`
   to `docs/` if you prefer — GitHub offers `/docs` as a source).
3. Page goes live at `https://<owner>.github.io/<repo>/`.
4. Upload builds: `npm run dist`, then on the repo page → Releases → new
   release → attach the files from `dist/`.

**Netlify / Cloudflare Pages** — drag `site/` onto the dashboard; done. Point a
custom domain at it later from their DNS settings.

**Any web host** — it's one file; `scp` it up.

## What the page does

- "Computer / Phone" pickers, auto-selected from the user agent, with a
  "probably you" hint on the detected desktop OS.
- iOS is shown as *coming soon* — no fake button.
- Trial copy matches the app: download IS the 14-day trial; expiry degrades to
  open/verify/export, never locks the user's own records.
