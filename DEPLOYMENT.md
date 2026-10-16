# Research website publishing workflow

## Currently browser-verified public report

Open the rendered report here:

https://htmlpreview.github.io/?https://github.com/wawa8777/long-lived-ip-research/blob/main/index.html

This preview reads the `main` branch HTML and resolves the report's local asset paths to the image files in this repository. It is a working public preview, not the Cloudflare Pages production domain.

## Where images live

All real case-image files are stored in `assets/images/`:

- `one-piece.jpg`
- `pokemon.png`
- `hello-kitty.jpg`
- `snoopy.jpg`
- `ultraman.png`
- `simpsons.jpg`
- `shinchan.png`

The article embeds them in the related case cards and the Crayon Shin-chan deep-dive section. Each figure/card contains a direct link to the project file, an original-image URL, and an official/reference source link. Do not replace these photographs/artwork with self-drawn placeholders when a real case image is required.

## Repeatable workflow for future research reports

1. Edit `index.html` to write the research narrative and embed each figure where it supports the explanation.
2. Save the actual image file in `assets/images/`; use a descriptive, stable filename.
3. Add useful `alt` text and visible links to the local project image and source page.
4. Push the changes to `main`.
5. Review the **Verify deployed research website and images** Actions run. It opens the public report in Chromium on desktop and mobile, checks that all seven current images have non-zero intrinsic dimensions and visible layout boxes, confirms source-link labels, checks mobile overflow, and uploads screenshots as artifacts.
6. If images or their source URLs change, inspect the download/verification logs instead of assuming a successful Git commit implies a successful deployment.

## Cloudflare production status

As of 2026-10-16, `https://long-lived-ip-research.pages.dev/` was still serving the previous report with SVG placeholder art instead of the current case images. The current GitHub Actions environment did not expose a Cloudflare API token, Cloudflare Account ID, or existing Pages deploy hook as repository secrets, so it could not inspect or change the Pages project's live build settings or force a production deployment. The repository's Cloudflare diagnostic workflow remains available through **Run workflow** if authorized secrets are configured.

For the original Cloudflare domain to publish this report, its Pages project must use this repository, production branch `main`, the repository root as the static site directory, and no build command for the plain HTML site. Alternatively, configure a Cloudflare Pages deploy hook or the API token/account-ID secrets securely in GitHub Actions; never paste deployment credentials into the HTML, README, or chat.

The GitHub Pages fallback cannot initialize a new Pages site with the current GitHub app permissions, so it is not used as a publishing target.
