# beer-log

Personal beer tracker. Single-page app, no build step.

## Layout
- `index.html`  the app (storage, domain, and UI layers in one file)

## Data model
Entries live in the browser (localStorage key `beerlog.v2`), keyed by ISO date:

    { "2026-10-25": { "count": 2.5, "note": "..." } }

- A missing date is NULL (not entered).
- `count: 0` is a logged dry day.
- Counts move in half steps.
- The daily average is total / days logged.

## Rules
- No personal data or tokens in this repo. Data files are git-ignored.
- One commit per change set. No work-in-progress commits.
