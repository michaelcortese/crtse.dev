# crtse.dev (Retro Portfolio)

Retro-styled personal portfolio using the BOOTSTRA.386 theme (Bootstrap 4.4.1 variant) with an ASCII boot intro and dynamic GitHub projects loader.

## Features
- 1980s DOS aesthetic (BOOTSTRA.386 / Bootstrap 4.4.1 themed local assets)
- ASCII boot splash with typewriter sequence (skip / disable via localStorage)
- Dynamic GitHub repo list (cached 10 min; manual refresh button)
- Simple static deployment (no build step)

## Local Development
Just open `index.html` in a browser. No build process required.

## Dynamic Projects Caching
Cached in `localStorage` under key `gh_projects_cache_v2`. Use the Refresh button or clear storage to force update.

## Deployment (Vercel)
A `vercel.json` is provided. Deploy with:

1. Install Vercel CLI (if not already): `npm i -g vercel`
2. From this directory run: `vercel` (first time) then `vercel --prod`

The config treats everything as static. No serverless functions needed.

## Replacing Remote Repo
To overwrite an existing GitHub repo (DANGEROUS: rewrites history):

```bash
git init
git add .
git commit -m "Initial import (retro portfolio)"
git branch -M main
git remote add origin git@github.com:michaelcortese/crtse.dev.git
git push -f origin main
```

Double‑check the remote URL before forcing.

## Customizing Intro
Edit the ASCII art inside the `<pre id="intro-ascii">` block and lines array in the inline script.
Set `localStorage.removeItem('intro_disabled_v1')` in DevTools console to see intro again if disabled.

## License Note
BOOTSTRA.386 theme assets are Apache 2.0 (per upstream). Bootstrap is MIT. Local themed assets are served from `bootstrap-4.4.1-dist/` (ensure not excluded if you want them deployed). Your own content: choose a license or keep all rights reserved.

## Vendor Assets / CDN Fallback
Currently referencing the local themed `bootstrap.css` & `bootstrap.bundle.js` for the retro styling. If deploying to an environment where you prefer CDN:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.4.1/dist/css/bootstrap.min.css">
```

Then append a small `<style>` override (colors, fonts) or host the Bootstra.386 CSS build on a CDN of your own. Keeping the local file guarantees the DOS font & palette.

## Possible Enhancements
- Add dark/amber/green CRT theme toggles
- Introduce command palette navigation
- Add pinned repos list override

PRs or issues (for your own tracking) welcome.
