# AGENTS.md

## Cursor Cloud specific instructions

This is a zero-dependency, single-file static HTML website (`index.html`). There is no build system, no package manager, no backend, and no automated tests.

### Running the application

Serve the file with any static HTTP server:

```sh
python3 -m http.server 8080
```

Then open `http://localhost:8080/` in a browser. The app uses hash-based routing (`#nils-investments`, `#niklas-investments`, `#schedule`, `#todos`).

### Architecture notes

- The entire application (~2050 lines) lives in `index.html` — HTML, CSS, and JS are all inline.
- All data is stored in the browser's `localStorage`; there is no database or API.
- Stock prices are fetched client-side from Stooq via a public CORS proxy (`api.allorigins.win`). This is optional and the app works without it.
- There are no lint, test, or build commands — changes are validated by opening the page in a browser.
