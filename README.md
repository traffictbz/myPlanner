# Focus Blocks

A private, offline-ready daily focus-block timer built with vanilla HTML, CSS, and JavaScript. The mobile-first interface separates planning, the spatial, responsive multi-column Day Board, and a minimal dedicated block timer screen. Each block keeps a distinct rotating color theme across its planning card, day-board card, and focus screen. There are no third-party packages, analytics, or network APIs.

## Preview locally

From this folder run:

```sh
python3 -m http.server 8000
```

Then visit `http://localhost:8000`. Localhost permits service workers in modern browsers. Opening `index.html` using `file://` does not support service workers or reliable installation.

## Install on a phone

Publish this folder to a static host such as GitHub Pages or Netlify and open the HTTPS URL on your device. Use the browser’s Install / Add to Home Screen option. The service worker caches the app files after its first successful visit; offline use is available thereafter. Installation and service workers require HTTPS, except for localhost development.

## Data and use

Blocks, focus-session intervals, interruption notes, and completion notes are stored under `focus-blocks-v1` in this browser's local storage on this device. Export JSON backups from **Backup & info** regularly; import validates data and asks before replacing current data. Notes are rendered as plain text.

Plan blocks using a positive whole-minute budget, then choose **Done Planning / View Day Board** to see today's large status cards. Tap any card to open its dedicated timer (showing only block title, state, large timer, and primary controls); starting from that screen or a planning card opens the timer automatically. Only one block can run at once. Pause and finish take effect before their optional note prompt. Focus time is bounded by planned plus manually extended budget; when the limit is reached, the session auto-pauses at the exact crossing time, including while the page is in the background. Reports split recorded intervals at local midnight and support daily/weekly views.

## Storage caveat

If local storage is blocked or full, the app displays a notice; unsaved changes may be lost. Reports use local calendar dates and the device’s current time zone. The standalone HTML file embeds the same current HTML, CSS, and JavaScript and works without external app files (PWA service-worker caching is available only to the folder-based app).
