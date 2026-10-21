# T-Rex AR • Dinosaur Encounter

A mobile-first dinosaur experience built with Three.js and WebXR. Uses the existing `assets/psone/t-rexaur.obj` and its original textures.

## Features
- Interactive 3D dinosaur viewer: rotate and zoom
- Android WebXR AR: scan a horizontal surface and tap to place a T-Rex
- Life-sized (~4.1 m tall) or miniature dinosaur
- Rotate and reset controls
- Graceful fallback to 3D mode when AR isn't available

## Running locally
Serve the repository using a local web server, e.g. `python -m http.server 8000`, then open `http://localhost:8000`.

## AR requirements
WebXR immersive AR requires HTTPS and a supported Android browser/device (typically Chrome with Google Play Services for AR). iOS Safari does not support this WebXR hit-test implementation; the regular 3D viewer still works. Camera and AR permissions must be granted.

## Deployment
Host as a static site over HTTPS (e.g. Cloudflare Pages). No build step is needed. The Three.js modules are fetched from jsDelivr, so an internet connection is required.

## Credits
Romell Bermundo. Original T-Rexaur model retained from the repository; verify original model/texture redistribution rights before making a public deployment.
