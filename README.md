# Escenas

Learn Spanish through everyday scenes — voice-powered practice for real-life moments. Fully offline PWA.

## Files

```
escenas/
├── index.html              ← main app (single file, no build step)
├── manifest.json           ← PWA manifest
├── service-worker.js       ← offline caching
└── icons/
    ├── icon-192.png
    ├── icon-512.png
    ├── icon-maskable-512.png
    └── favicon.png
```

## Deploy to GitHub Pages

1. Create a new repo (e.g. `faoitea/escenas`)
2. Copy all files above into repo root
3. Push to `main`
4. Repo settings → Pages → Deploy from branch `main`, folder `/ (root)`
5. Wait for the green tick in the Actions tab
6. Live at `https://faoitea.github.io/escenas/`

## Testing "Add to home screen"

**Android Chrome:**
1. Visit the URL
2. Menu (⋮) → "Add to Home screen"
3. Icon appears on home screen, launches full-screen with no browser chrome
4. Turn on airplane mode → still works

**iOS Safari:**
1. Visit the URL
2. Share button → "Add to Home Screen"

## Testing offline

After first visit, the service worker caches the shell. Turn on airplane mode and reopen — should still work fully. Speech recognition needs internet on most devices (uses Google's cloud service), but speech synthesis and all scripted dialogues work fully offline.

## Updating

When you change any file, bump `CACHE_VERSION` in `service-worker.js` (e.g. `escenas-v1` → `escenas-v2`). Otherwise clients will keep serving the old cached shell.

## Adding scenes

Every scene is data at the top of `index.html`. Copy an existing entry in the `SCENES` array and edit — no other code changes needed.
