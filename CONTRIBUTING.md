# Contributing to MyPixel

Serve the repository root with `python -m http.server 8000` and open `http://localhost:8000`. Use small, licensed fixtures from [`demo`](demo) or create your own pixel art.

## Review a change

- For processing changes, compare upscaling and vectorization on crisp edges and transparent backgrounds. Check image dimensions and transparency in the downloaded output.
- For batch changes, try multiple inputs of different sizes, a failed file, and a second run in the same session.
- For offline or install changes, verify a new load and a reload with an existing service worker. The app entry point is [`index.html`](index.html) and the worker is [`sw.js`](sw.js).

Include the input fixture, settings, browser, and before and after output when you report an image-processing difference.
