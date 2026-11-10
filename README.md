# Hydroplane Visualization

An interactive scroll-driven 3D sketch-to-render page using the **original Sketch-to-3D player by Danny Stuart**.

## Live site

Published directly from the `main` branch via GitHub Pages.

https://pavlo-bondarchuk.github.io/hydroplane-visualization/

## How it works

The public `index.html` loads the prebuilt official player from the upstream repository via jsDelivr:

`https://cdn.jsdelivr.net/gh/dannystuart/sketch-to-3d@main/site/live/sketch-player.js`

It loads Polyfork's public GLB model:

`https://polyfork.dev/cdn/scrap-built-aeroplane-65ac95.glb`

The official engine runs in `play: 'pin'` mode with `end: 'hold'` and `drag: false`. This is the actual upstream engine, not a visual simulation.

### Publishing to GitHub Pages

In **Settings → Pages → Build and deployment**, set:

- **Source:** Deploy from a branch
- **Branch:** `main`
- **Folder:** `/(root)`

Save. Pages will publish the existing HTML without GitHub Actions or Node builds. This is required because the repository's Actions runner cannot start while the account has an unresolved GitHub billing restriction.

### Important

This version depends on two public CDNs at runtime. The page will not work offline, and no browser test has been completed in this development environment. A production-grade self-hosted build would require downloading the upstream bundle and the GLB into the repository.

The currently selected [Polyfork Scrap-built aeroplane](https://polyfork.dev/asset/scrap-built-aeroplane-65ac95) is a demonstration aircraft, **not** a historically faithful M-1 hydroplane.
