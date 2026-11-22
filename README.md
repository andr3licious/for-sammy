# For Sammy ✨

A personal, pastel digital scrapbook and Progressive Web App (PWA) built with zero dependencies and zero build step.

**Live Site:** [https://andr3licious.github.io/for-sammy/](https://andr3licious.github.io/for-sammy/)

## Features

- **Real-Time Check-In & Live Clock**: Dynamic time-of-day greetings, a live clock, and a daily mood check-in saved per device in `localStorage` with one-tap toggle or reset.
- **Moments & Memories Gallery**: 20 interactive 3D-flippable Polaroid cards (10 Sammy, 10 Cute Companions) with category filters, back-of-card notes, a fullscreen lightbox, and client-side Polaroid PNG export.
- **Jar of Smiles & Daily Notes**: Daily Manila-time origami notes, random note draws, a fresh note composer, saved Favorites, and a Keepsake QR modal with downloadable QR assets and one-tap link copying.
- **Highlight Reels**: 3 short video reels with custom poster thumbnails and coordinated playback/mute controls.
- **Kind Words & Giggles**: 18 pastel quote cards with category filters (`All`, `Daily Motivation`, `Quick Laughs`) and a `Surprise me` picker.
- **Mini Cassette Player**: Plays soft piano background music (*Beautiful Dream* by Diego Nava) alongside a built-in Web Audio API Starlight Lofi synth track.
- **Daylight & Starlight Themes**: Switchable light and cozy night modes, floating reaction particles, and responsive layouts across desktop, tablet, and mobile viewports.
- **Installable PWA**: Includes [`manifest.webmanifest`](./manifest.webmanifest) and a network-first Service Worker ([`sw.js`](./sw.js)) for immediate updates with offline asset fallback.

## Project Structure

```text
.
├── .github/
│   └── workflows/
│       └── pages.yml      # GitHub Actions workflow for GitHub Pages deployment
├── .nojekyll              # Serves static files directly without Jekyll processing
├── index.html             # Single-file HTML, CSS, and JavaScript application
├── sw.js                  # Service Worker (network-first HTML & media fallback)
├── manifest.webmanifest   # PWA manifest and app icons
├── README.md              # Project overview and usage guide
└── assets/
    ├── apple-touch-icon.png
    ├── icon-192.png
    ├── icon-512.png
    ├── audio/             # Background music track
    ├── photos/            # 20 scrapbook gallery photos
    ├── qr/                # Keepsake QR code SVG/PNG and printable card
    └── videos/            # 3 highlight reel videos and poster images
```

## Local Preview

Because this is a pure static site with no bundler or build dependencies, serve the repository root with any local static server:

```bash
# Using Python 3
python3 -m http.server 8000

# Or using Node.js
npx serve .
```

Then open `http://localhost:8000` in your browser.

## Deployment (GitHub Pages)

The site deploys automatically to GitHub Pages via [`.github/workflows/pages.yml`](./.github/workflows/pages.yml) on every push to `main` (and can also be triggered manually via `workflow_dispatch`).

- **Live URL**: [https://andr3licious.github.io/for-sammy/](https://andr3licious.github.io/for-sammy/)
- **Cache Busting**: When making site updates, bump the Service Worker cache version (`for-sammy-v24`) in both [`sw.js`](./sw.js) and [`index.html`](./index.html) so returning devices refresh immediately.

## Credits

- Background music: *Beautiful Dream* by Diego Nava via [Mixkit Free Stock Music](https://mixkit.co/free-stock-music/mood/romantic/).
- Fonts: [Nunito](https://fonts.google.com/specimen/Nunito) & [Caveat](https://fonts.google.com/specimen/Caveat) via Google Fonts.
- Confetti effects: [canvas-confetti](https://github.com/catdad/canvas-confetti).
