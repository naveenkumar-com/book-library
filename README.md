# Master Book Library — PWA

This folder is a installable Progressive Web App. To turn it into a real "app"
on an Android phone, the files need to be served over **https** (or localhost) —
PWAs cannot install from a bare `file://` HTML file, since manifest/service-worker
loading requires a real origin. A few free ways to do that:

## Option A — GitHub Pages (free, permanent)
1. Create a new GitHub repo, upload all files in this folder to it.
2. Repo Settings → Pages → deploy from the `main` branch, root folder.
3. Open the resulting `https://<you>.github.io/<repo>/` link on your Android
   phone in Chrome.
4. Tap the Chrome menu (⋮) → "Add to Home screen" / "Install app" — or use the
   in-page "↓ Install" button that appears in the toolbar.

## Option B — Netlify Drop (free, 30 seconds, no account needed)
1. Go to https://app.netlify.com/drop on a computer.
2. Drag this whole folder onto the page.
3. Netlify gives you an instant https:// URL — open that on your phone.

## Option C — Test locally first
From inside this folder on a computer on the same Wi-Fi as your phone:
```
python3 -m http.server 8000
```
Then on your phone's Chrome, visit `http://<your-computer's-LAN-IP>:8000`.
(This works for testing, but "https" hosting like A or B is what you'll want
for a link you can actually share/install for real.)

## What's inside
- `index.html` — the library itself
- `manifest.json` — app name/icons/colors so Android treats it as an app
- `sw.js` — service worker that caches everything for offline use
- `icon-*.png` — home-screen icons
