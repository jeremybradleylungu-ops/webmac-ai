# WEBMAC.AI VITALS — Upgrade 2 core build
Tested with headless Chromium (Playwright) on a 390px phone viewport + 1280px desktop, file:// origin.

Application: PASS (loads, 0 console errors across full run)
UI (built screens): PASS — Dashboard, AI Builder, Projects, Templates, Workspace, Source, Export, Settings
AI Builder: PASS — 4 prompts (laundry, football portfolio, fashion, restaurant) → 4 distinct types; empty prompt handled
AI Editing: PASS (limited) — rule-based: theme/luxury, button/background/accent colour, WhatsApp, testimonials, contact section, hero text, mobile rules; unrelated content preserved; unknown commands get a clear message
Live Preview: PASS — desktop/tablet/mobile, internal links navigate, no horizontal scroll on phone
Responsive Design: PASS (phone + desktop checked; tablet/other sizes not checked)
Projects: PASS — create, rename, duplicate, archive, delete, status, persist after reload (localStorage)
Source Code: PASS — real files; edit/save/search tested. Copy/format: copy not tested in browser, formatting not built
Export: PASS — ZIP, single HTML, backup JSON
ZIP Export: PASS — extracted with unzip, every page opened standalone at 2 widths, 0 errors
Ownership Independence: PASS (static sites)
Branding Check: PASS — no "webmac" text in generated or exported files
Version History: PASS — save, restore (rename/delete built, not browser-tested)
Undo/Redo: PASS
Security: PARTIAL — no keys in frontend; preview iframe sandboxed (no same-origin); input escaped. No backend, auth or upload validation yet (no uploads built)
Accessibility: NOT AUDITED — labels, focus outlines, 44px targets built; contrast and screen reader not measured
Performance: NOT PROFILED — single ~37 KB file, no dependencies
Build: N/A (no build system); JS parsed and executed cleanly
Console Errors: 0   Critical Bugs: 0 (found and fixed 2 during testing: literal </script> inside strings broke page load)

## PWA / install (added)
PASS (headless Chromium over http://localhost): manifest loads, service worker controls page, 7 shell files cached, dashboard reloads offline, generate + ZIP export work offline, 0 console errors, exports contain no manifest/service-worker/WebMac text.
NOT tested: real Android/iPhone install prompts, Add to Home Screen on iOS, HTTPS host behaviour, cache update flow after a new version (bump V in sw.js when you change files).

## NOT built / not tested
- Visual element editor (select element → controls)
- Asset Center; full template library (templates are starter prompts); full client-mode fields beyond name/status
- Remote AI provider path is wired but untested against a real server; open-ended AI edits need it
- Offline/network-failure, extreme-length-prompt, and API-failure scenarios not run
- Production needs: backend for AI keys, auth, storage beyond localStorage, upload validation, hosting

Release gate: NOT READY — visual editor and Asset Center are missing.
