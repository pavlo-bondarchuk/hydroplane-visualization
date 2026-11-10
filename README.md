# Hydroplane Visualization

Scroll-driven 3D sketch-to-render presentation.

The website uses the **original** [Danny Stuart Sketch-to-3D](https://github.com/dannystuart/sketch-to-3d) web player with `play: 'pin'`, not a simulated effect.

## Live site

https://pavlo-bondarchuk.github.io/hydroplane-visualization/

## Model

The current demonstration uses [Scrap-built aeroplane](https://polyfork.dev/asset/scrap-built-aeroplane-65ac95) by Polyfork. It is **not** a historically accurate M-1 hydroplane model.

GitHub Actions downloads the free GLB from the Polyfork CDN during the build, and generates the site assets using the upstream `scripts/web.mjs`. Polyfork free GLB redistribution is permitted under CC BY 4.0 with attribution; attribution is included on the page.

## Deployment

1. In repository **Settings → Pages**, set **Build and deployment → Source** to **GitHub Actions**.
2. Open **Actions → Build and publish hydroplane visualization**.
3. Run the workflow or push to `main`.
4. Once both jobs succeed, open the live site.

The workflow needs network access to GitHub, npm and Polyfork. It fails explicitly if the downloaded file is not a GLB.

## Local development

The rendered output needs HTTP, not `file://`, because the original player loads the GLB via fetch.

For a local build, follow the commands in `.github/workflows/deploy.yml`, then serve the `dist/` folder.
