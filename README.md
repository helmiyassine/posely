# Posely ✦ — Free AI Photo Coach

A free, mobile-friendly posing app inspired by the *idea* of camera posing coaches, with original UI and illustrations. No subscriptions, accounts, server, or paid API key.

## Features
- Six original pose reference guides; Standing, Sitting and Selfie filters
- Live camera + pose guide overlay
- On-device MediaPipe Pose Landmarker AI, joint-angle similarity score and simple real-time tips
- Front/back camera flip, guide toggle, photo capture & local download
- Local favorites (saved in your browser)
- Installable Progressive Web App (PWA), optional donation link

## Publish for free on GitHub Pages
1. Create a **public** GitHub repository, for example `posely`.
2. Upload **all four files** (`index.html`, `manifest.webmanifest`, `icon.svg`, `sw.js`) to its root folder. You can upload `README.md` too.
3. Go to **Settings → Pages → Build and deployment**. Choose **Deploy from a branch**, **main**, and **/(root)**. Click Save.
4. Your site will appear at `https://YOUR-USERNAME.github.io/posely/`. GitHub may take a few minutes to publish.
5. Open the link **on your phone**. The browser will ask for camera permission.

For local testing, run `python3 -m http.server 8000` in the folder and open `http://localhost:8000` on your computer. A plain `file://` open may block camera access or module loading. For phone testing, use the published HTTPS page.

## Add donations
Open `index.html`, find `const DONATION_URL = '';`, and set your real Ko-fi / Buy Me a Coffee URL between the quotes. Example:

```js
const DONATION_URL = 'https://ko-fi.com/YOUR_PAGE';
```

No payment service is integrated by default. The donation button remains hidden until you add a URL. All app features remain free.

## How the AI works (important limitations)
MediaPipe's **pose landmark** model runs in the browser and estimates body landmarks. Simple geometry compares your elbow and knee angles against hand-authored reference sketches. This is *not* a conversational or generative AI and does not understand image aesthetics, facial expressions, backgrounds or clothing. Scores are approximate and not a professional photography rating. Pose detection requires an internet connection initially to fetch the MediaPipe JS/WASM and model, though the core website caches for repeat visits. Browser/camera support varies.

Camera frames are processed on-device and are not sent to this app's server; third-party model assets are downloaded from Google's model hosting and jsDelivr. This is a client-only project. No analytics or tracking are included.

## Tech stack
Vanilla HTML/CSS/JS, MediaPipe Tasks Vision, GitHub Pages, PWA Service Worker. No build tooling required.

## Next iterations
- More original poses and layouts, refined visual alignment for each camera aspect ratio
- Multiple reference photos with explicit reusable licenses
- Voice guidance and accessibility improvements
- Optional local/offline image assessment model for richer AI coaching

This is an original starter project, not an affiliation with Pozea.
