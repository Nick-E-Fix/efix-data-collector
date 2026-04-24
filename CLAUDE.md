# E-Fix Data Collector

Single-file PWA (`index.html`, ~1650 lines) for electricians to collect job data and generate PDF certificates.

## What it does
- Multi-step form: select cert type → client details → installation info → circuits → PDF download
- Cert types: EICR, EIC, Minor Works, Fire Alarm, Emergency Lighting
- Generates a landscape PDF via jsPDF (loaded on demand)
- Saves drafts to localStorage
- Mobile-first, max-width 480px, styled for iOS PWA use

## Key structure (all in index.html)
- **CSS** — top of file, CSS variables: `--blue`, `--red`, `--green`, `--dark`, etc.
- **HTML** — minimal shell (`<div id="app">`)
- **JS** — bottom of file, vanilla JS:
  - `state` object holds all form data
  - `render()` rebuilds the UI on every change
  - `generatePDF()` — jsPDF export, landscape for circuits page
  - `saveDraft()` / `loadDraft()` — localStorage persistence
  - `startNew()` — reset state and save draft

## Where files live
- Canonical working file: `~/Documents/GitHub/efix-data-collector/index.html`
- Older v2 snapshot: `~/Desktop/efix-data-collector-v2.html` (Apr 14, ignore this)

## Notes
- No build step — edit `index.html` directly, open in browser to test
- jsPDF loaded from CDN only when user taps "Download PDF"
- Desktop v2 file on Desktop is outdated — always use the GitHub repo copy
