# Mornings

A private, on-device streak tracker. No account, no server — your data lives
only in your phone's browser storage.

## Files

- `index.html` — the whole app (structure, styling, logic)
- `manifest.json` — makes it installable as a home-screen app (PWA)
- `service-worker.js` — lets it keep working offline after the first load
- `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` — app icons

## Deploy it (GitHub Pages — recommended, free)

You already have a GitHub account from `python-review`, so this will feel familiar.

1. Create a new repository, e.g. `mornings`.
2. Add all the files in this folder to it:
   ```bash
   cd mornings-app
   git init
   git add .
   git commit -m "Initial version of Mornings"
   git branch -M main
   git remote add origin https://github.com/<your-username>/mornings.git
   git push -u origin main
   ```
3. On GitHub: go to the repo → **Settings** → **Pages** → under "Build and
   deployment", set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. After a minute or two, GitHub will give you a URL like:
   `https://<your-username>.github.io/mornings/`
5. Open that URL in Safari on your iPhone → tap Share → **Add to Home Screen**.
   It'll behave like a real app: full screen, its own icon, works offline.

## Updating it later

Whenever you want to change something (new messages, colors, features):

```bash
git add .
git commit -m "describe the change"
git push
```

GitHub Pages redeploys automatically within a minute or two. Reopen the app
on your phone (or pull down to refresh) to get the update — the service
worker checks for a fresh version on every load.

## Alternative: Netlify Drop (no git required)

If you'd rather skip GitHub entirely: go to https://app.netlify.com/drop on
a computer and drag this whole folder onto the page. It gives you a live
URL immediately. To update later, just drag the folder again.

## Notes

- Your streak data is stored with `localStorage`, scoped to this exact URL.
  If you ever move it to a different domain, the streak starts fresh there.
- Nothing is sent to any server — everything stays on your phone.
