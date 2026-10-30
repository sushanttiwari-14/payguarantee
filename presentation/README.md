# Retained PayProof presentation

This separate Remotion project renders an edited demonstration of upstream PayProof results. It is included as part of the reconstructed source, not as evidence of newly performed live tests.

Use Node.js 22 or newer. Run `npm ci`, `npm run lint`, and `npm run captions` in this directory. `npm run dev` starts the loopback-only Studio at http://127.0.0.1:4324; `npm run build` bundles the composition. `npm run render` renders the `PayProof-Demo` composition into `out/payproof-demo.mp4`.

Scene components live in `src/`, the composition is registered in `src/Root.tsx`, and saved audio, captions, screenshots, and fonts are under `public/`. Narration inputs are in `narration.json`. Read [NOTICE.md](NOTICE.md) for original attribution, generated voice disclosure, and third-party terms. Saved Sandbox and AI footage must not be presented as a new transaction or inference run.
