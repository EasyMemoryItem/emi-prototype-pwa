# EMI Prototype v2

Hi-fi interactive prototype for **Easy Memory Item** — "Memory items that stick — and make you better."

Imported from the Claude Design project *High fidelity prototype design*
(`EMI Prototype v2.dc.html`).

This is a **PWA** — installable, runs fully offline, **no backend required**.
`index.html` is the design-compiler runtime (`support.js` rendering the
prototype) with React/ReactDOM/Babel and the Inter font **vendored locally**, so
nothing is fetched from a CDN. A service worker precaches the whole app shell.

## Files

| File | What it is |
| --- | --- |
| `index.html` | **The PWA, and the source of truth.** Edit here. Adds to the shared body: a local `window.__resources` map (points the runtime at `vendor/` instead of unpkg), local font, PWA `<head>` tags, the app-height fix, service-worker registration, and the install banner. Deploy and install this. |
| `manifest.webmanifest` | Web app manifest — name, icons, colours, `display: standalone`. |
| `sw.js` | Service worker. Precaches the app shell (listed in `PRECACHE`) and serves cache-first, so the installed app works offline from first launch. |
| `icons/` | App icons — the official EMI logo from easymemoryitem.com, used unmodified. `logo-1466.png` is the untouched original; every other file (`favicon-32`, `icon-192`, `icon-512`, `logo`, `apple-touch-icon`) is a straight downscale of it, no cropping or recolouring. |
| `vendor/` | Local copies of `react` / `react-dom` / `@babel/standalone` (18.3.1 / 7.29.0) and the Inter font (`inter.css` + `fonts/*.woff2`). Makes the app CDN-free and offline-capable. |
| `EMI Prototype v2.dc.html` | **Export for Claude Design**, regenerated from `index.html` — not hand-edited. Claude Design compiler format (`<x-dc>`, `sc-if`/`sc-for`, `{{ }}` bindings) rendered by `support.js`. Identical body to `index.html`; differs only in that it loads Inter from Google Fonts (Claude Design has no `vendor/`) and omits every PWA layer. |
| `support.js` | Design-compiler runtime. Parses the markup and renders it; resolves CDN deps through `window.__resources` when present. |
| `ios-frame.jsx` | `IOSDevice` bezel/status-bar component. **No longer used** — the app moved to a full-screen responsive shell (`.emi-app`) instead of a simulated device, so nothing imports it. Kept for reference. |
| `EMI Prototype v2 (standalone).html` | Old single-file export — **truncated at 256 KB and does not render**. Kept only as a stub; ignore it. |

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

> When you change `index.html`, an icon, or anything in `vendor/`, bump
> `CACHE_VERSION` in `sw.js` so installed clients pick up the new version.
> Add any new precached file to the `PRECACHE` list in `sw.js`.

## Editing

**Edit `index.html`.** It is the deployed app and the source of truth — the
markup and the `<script data-dc-script>` logic block both live there. Bump
`CACHE_VERSION` in `sw.js` with every change. `support.js` rarely needs changes.

`EMI Prototype v2.dc.html` is a **generated export**, not a second place to
edit. Regenerate it from `index.html` by taking, in order: the `.dc.html` head
(support.js + thumbnail template), `<body><x-dc><helmet>`, the Google-Fonts
links, `index.html`'s `<style>` block, `</helmet>`, `index.html`'s markup from
`<div class="emi-app">` to its `</x-dc>`, and the `data-dc-script` block —
dropping every PWA layer (manifest and icon tags, `window.__resources`, the
`--app-h` script, SW registration, install banner). Then push it to the Claude
Design project with the `/design-sync` flow.

> The two files drifted badly once before: `.dc.html` went un-updated from
> 2026-07-21 while `index.html` took ~20 commits, and their design values
> diverged (16px vs 14px system radius, among others). Regenerate rather than
> hand-mirror, or it will happen again.
