# WebMac.AI — Upgrade 2 (core build)

Open `index.html` in a browser, or install it on your phone (below).

## Install on your phone (needs HTTPS hosting, one time)
1. Upload ALL files in this folder to a free static host (GitHub Pages, Netlify, Cloudflare Pages).
2. Open the https link: Android Chrome → menu → Install app; iPhone Safari → Share → Add to Home Screen.
3. After the first load it works offline. Projects live in that browser on that address; use Export → Project backup now and then.
Opening index.html straight from the Files app still works on most Android browsers, but without install/offline caching.

Built: dashboard, AI Builder with real pipeline stages, multi-page generation (HTML/CSS/JS files),
live preview (desktop/tablet/mobile, sandboxed), rule-based AI editor, page manager,
source editor (HTML/CSS/JS, search/copy/save), versions, undo/redo, projects (create/open/rename/
duplicate/archive/delete/status/client), website health + auto-fix, branding scan,
ZIP / single-HTML / project-backup export, settings with replaceable AI provider.

Exports contain no WebMac branding and need nothing from WebMac.AI to display.

Production integration point: Settings → "Your backend endpoint". Your server holds the model API key,
receives {brief}, returns plan JSON {name,pages,svc,desc,...}. Never put API keys in this page.
See VITALS.md for exactly what was tested and what is not built yet.
