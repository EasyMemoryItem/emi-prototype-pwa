# EMI Prototype v2

Hi-fi interactive prototype for **Easy Memory Item** — "Memory items that stick — and make you better."

Originally imported from the Claude Design project *High fidelity prototype
design*; `index.html` is now the only copy and is edited directly.

This is a **PWA** — installable, runs fully offline, **no backend required**.
`index.html` is the design-compiler runtime (`support.js` rendering the
prototype) with React/ReactDOM/Babel and the Inter font **vendored locally**, so
nothing is fetched from a CDN. A service worker precaches the whole app shell.

## Files

| File | What it is |
| --- | --- |
| `index.html` | **The PWA, and the only source.** Edit here. Holds the whole app: the Claude Design compiler markup (`<x-dc>`, `sc-if`/`sc-for`, `{{ }}` bindings), the `<script data-dc-script>` logic block, a local `window.__resources` map (points the runtime at `vendor/` instead of unpkg), local font, PWA `<head>` tags, the app-height fix, service-worker registration, and the install banner. Deploy and install this. |
| `manifest.webmanifest` | Web app manifest — name, icons, colours, `display: standalone`. |
| `sw.js` | Service worker. Precaches the app shell (listed in `PRECACHE`) and serves cache-first, so the installed app works offline from first launch. |
| `icons/` | App icons — the official EMI logo from easymemoryitem.com, used unmodified. `logo-1466.png` is the untouched original; every other file (`favicon-32`, `icon-192`, `icon-512`, `logo`, `apple-touch-icon`) is a straight downscale of it, no cropping or recolouring. |
| `vendor/` | Local copies of `react` / `react-dom` / `@babel/standalone` (18.3.1 / 7.29.0) and the Inter font (`inter.css` + `fonts/*.woff2`). Makes the app CDN-free and offline-capable. |
| `support.js` | Design-compiler runtime. Parses the markup and renders it; resolves CDN deps through `window.__resources` when present. |
| `ios-frame.jsx` | `IOSDevice` bezel/status-bar component. **No longer used** — the app moved to a full-screen responsive shell (`.emi-app`) instead of a simulated device, so nothing imports it. Kept for reference. |

## Run it

### Locally (to test install / offline)
Service workers only run over `http://localhost` or `https://`, so serve it —
opening `index.html` from `file://` won't register the worker:

```sh
./serve.sh          # http://localhost:8000/  → open, then DevTools ▸ Application to inspect/install
```

To verify offline: load once, stop the server, reload — it still runs from cache.

### Deploy (static host, no backend)
Upload the whole folder to any static host — GitHub Pages, Netlify, Vercel,
Cloudflare Pages. They serve over HTTPS, which is all a PWA needs. On the phone,
open the URL and use **Add to Home Screen** (iOS Safari) or the **Install**
prompt (Android Chrome). After the first load it runs offline.

> The Pages workflow stamps `CACHE_VERSION` in `sw.js` from the commit SHA on
> every push to `main`, so installed clients pick up a new version by
> themselves — there is nothing to bump by hand. On any other host, do that
> stamping yourself or edit the literal. Add any new precached file to the
> `PRECACHE` list in `sw.js`; that part is not automatic.

## Editing

**Edit `index.html`.** It is the deployed app and the only copy — the markup and
the `<script data-dc-script>` logic block both live there. `support.js` rarely
needs changes.

> There used to be a second copy, `EMI Prototype v2.dc.html`, kept for pushing
> the prototype back into Claude Design. It drifted badly — un-updated from
> 2026-07-21 while `index.html` took ~20 commits, until their design values had
> diverged (16px vs 14px system radius, among others) and the stale file got
> mistaken for the authority. It was deleted, along with the truncated
> `EMI Prototype v2 (standalone).html`. If you need a Claude Design export
> again, generate it from `index.html`: keep the `<x-dc>` markup, the `<style>`
> block and the `data-dc-script` block, swap the local font for the Google-Fonts
> links, and drop every PWA layer (manifest and icon tags,
> `window.__resources`, the `--app-h` script, SW registration, install banner).
> Generate it on demand; don't commit a second copy.
