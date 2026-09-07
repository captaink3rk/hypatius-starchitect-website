# STARCHITECT — Website · deploy package 2026-09-07 (rev 3)

Static multi-page site. No build step. `index.html` is the entry point.

## What changed in this package
- VOSB / Veteran-Owned / VetCert language removed site-wide. Stamp now reads `UEI UKELB3UV76V6 · CAGE 19S89`.
- Intro sting replaced with the corrected cut and renamed `assets/intro-sting-v2.mp4` so every visitor gets the new file immediately (the old name would have been served from browser cache). `intro.html` and `intro-preview.html` point at the new name.
- All corporate links → **https://hypati.us** (was main.hypati.us): footers, About CTAs, Company page.
- ALIDADE platform cards (Company page, brief home variant) now link to **https://alidade.us**.
- `vercel.json`: clean URLs (`/platform` not `/platform.html`) and long-cache headers on `/assets`.
- Not in the package: the standalone bundle and `intro-live.html` (review-only files).

## Deploy to Vercel (project: hypatius / starchitect-website → starchitect.us)

**Option A — one-time push (fastest)**
1. Unzip. In a terminal inside the folder: `npx vercel --prod` and pick the existing `starchitect-website` project (team: hypatius).
   — or — drag the unzipped folder onto https://vercel.com/new (team hypatius) and select the existing project instead of creating a new one.
2. Domains (`starchitect.us`, `www.starchitect.us`) are already attached; they pick up the new deployment automatically.

**Option B — Git-linked (auto-deploys on every push)**
1. Create an empty GitHub repo, e.g. `uwgamer/starchitect-website`, and push the contents of this folder to `main`.
2. Vercel → starchitect-website → Settings → Git → Connect Git Repository → pick the repo. Framework preset: **Other**. Build command: none. Output directory: `.` (root).
3. Every push to `main` then goes live at starchitect.us; every branch gets a preview URL.

## Notes
- The briefing form (`<form id="briefingForm">`) is still a front-end mock — wire it to your CRM/email endpoint before relying on it.
- `intro.html` plays the sting once per session and redirects to `index.html`; the domain root currently points at `index.html`, so the intro is opt-in.
- Fonts (Bebas Neue, Rajdhani, IBM Plex Mono) load from Google Fonts.
- © 2026 HYPATIUS LLC. STARCHITECT is a HYPATIUS platform.
