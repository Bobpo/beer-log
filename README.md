# beer-log

Personal beer tracker. Single-page app, no build step.

## Layout
- `index.html`  the app (storage, domain, and UI layers in one file for now)

## Data
Entries are stored in the browser (localStorage, key `beerlog.v1`), keyed by ISO date.
Planned: sync to a separate private repo (`beer-data`) through the GitHub API.
Never commit personal data or tokens to this repo.
