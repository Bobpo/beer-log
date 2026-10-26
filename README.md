# beer-log

Personal beer tracker. Single-page app, no build step.

## Layout
- `index.html`  the app (storage, domain, sync, and UI layers in one file)
- `manifest.webmanifest`, `icon-*.png`, `apple-touch-icon.png`  home screen install
- `sw.js`  offline shell, network first so new releases load when online

## Data model
Entries live in the browser (localStorage key `beerlog.v2`), keyed by ISO date:

    { "2026-10-25": { "count": 2.5, "note": "..." } }

- A missing date is NULL (not entered).
- `count: 0` is a logged dry day.
- Counts move in half steps.
- The daily average is total / days logged.

## Sync
- Optional. Settings (repo, file, token) are typed into the app and kept on the device only. Nothing identifying is in the code.
- Every save is one commit to a separate private repo, as a single-day change on top of the latest file. Stale writes retry.
- Offline changes queue on the device and send when the connection returns.
- The page may only contact api.github.com (Content-Security-Policy).

## Rules
- No personal data or tokens in this repo. Data files are git-ignored.
- One commit per change set. No work-in-progress commits.
