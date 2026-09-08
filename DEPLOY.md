# CMA Part 1 Prep Studio — Deploy as an installable app (PWA)

Your app is now **PWA-ready**. Once you host these files on any HTTPS web host, it becomes installable on Android, iPhone and desktop, and works offline after the first load.

## Files in this folder
- `cma-part1-prep.html`  → **rename to `index.html`** before hosting
- `manifest.webmanifest` → app name, colours, icons
- `sw.js` → service worker (offline caching)
- `icon-192.png`, `icon-512.png` → app icons

## Step 1 — Rename
Rename `cma-part1-prep.html` to **`index.html`** so the app opens at the site root. Keep all 5 files together in one folder.

## Step 2 — Host it (pick one, all free, all give HTTPS)
A service worker + "Add to Home Screen" only work over HTTPS, so you must host — opening the raw file will not install as an app.

**Option A — Netlify Drop (easiest, no account needed to try):**
1. Go to https://app.netlify.com/drop
2. Drag the whole folder in. You get a live HTTPS link in seconds.

**Option B — GitHub Pages:**
1. Create a public repo, upload the 5 files.
2. Settings → Pages → deploy from the `main` branch, root folder.
3. Your app is at `https://<username>.github.io/<repo>/`.

**Option C — Vercel / Cloudflare Pages:** create a project, upload the folder, deploy. Same result.

## Step 3 — Install on your phone
- **Android (Chrome):** open the link → menu (⋮) → **Install app** / **Add to Home screen**.
- **iPhone (Safari):** open the link → Share → **Add to Home Screen**.
- **Desktop (Chrome/Edge):** an **Install** icon appears in the address bar.

After the first visit, the app opens full-screen and works **offline** (all notes, questions, essays and mock exams are built in).

## What still needs a backend (next layer — optional)
The static PWA above covers everything except two things that cannot be done from the browser alone:

1. **AI features everywhere** (AI Tutor, AI-generated questions/podcasts).
   The browser cannot safely hold your Anthropic API key. You need a tiny **proxy** (e.g. a Cloudflare Worker or Vercel serverless function) that holds the key and forwards requests. Ask and I'll write that Worker for you. The offline tutor, notes, question generator, essays and mocks already work without it.

2. **Sync across devices** (same progress + your uploaded PDFs on phone *and* laptop).
   Local storage lives in one browser only. Cross-device sync needs a backend + login (e.g. **Supabase** or **Firebase**: Auth + a database/storage bucket). Ask and I'll scaffold it.

## Notes
- "CMA", "IMA", "IFRS", "IAS" are trademarks of their respective owners. This app is an independent study aid, not affiliated with or endorsed by them.
- Always confirm exam scope against the official IMA Content Specification Outlines and Learning Outcome Statements.
