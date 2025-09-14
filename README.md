# crtse.dev (Retro Portfolio)

Retro-styled personal portfolio using the BOOTSTRA.386 theme (Bootstrap 4.4.1 variant) with an ASCII boot intro and dynamic GitHub projects loader.

## Features
- 1980s DOS aesthetic (BOOTSTRA.386 / Bootstrap 4.4.1 via CDN)
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
BOOTSTRA.386 theme assets are Apache 2.0 (per upstream). Bootstrap is MIT. CDN links are used; no vendor dist committed. Your own content: choose a license or keep all rights reserved.

## Vendor Assets
The original `bootstrap-4.4.1-dist/` folder is intentionally ignored in git (`.gitignore`). If you need to work offline without CDN access, download the dist and remove that ignore line, or host the files yourself.

## Possible Enhancements
- Add dark/amber/green CRT theme toggles
- Introduce command palette navigation
- Add pinned repos list override

PRs or issues (for your own tracking) welcome.
