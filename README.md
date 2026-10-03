# tubik-landing

Public landing site for **Tubik**, a calm video app for parents of young children (iPhone and iPad). Personal project of Vladimir Skromny — not an Appligent AI product.

Live: https://vskromny.github.io/tubik-landing/ (GitHub Pages, `main` / root, no custom domain yet).

## Structure

Plain static HTML/CSS, no build step, no JavaScript. What is committed is what ships.

| Path | What |
|---|---|
| `index.html`, `privacy.html`, `terms.html`, `support.html`, `imprint.html` | English pages |
| `de/` | German versions (same filenames, `impressum.html` for the imprint, `nutzungsbedingungen.html` for the terms), linked via `hreflang` |
| `player/index.html` | Player identity page (`noindex`, not in the sitemap) — see below |
| `404.html` | Uses absolute `/tubik-landing/` paths — update when a custom domain is added |
| `assets/style.css` | All styling; tokens mirror `tubik/product/design/tokens.json` ("Evening Shelf"), light/dark via `prefers-color-scheme` |
| `assets/fonts/` | Nunito variable woff2 (latin subset), self-hosted, SIL OFL 1.1 (`OFL.txt`) |
| `assets/img/` | App mockups (from `tubik/product/design/mockups/png`), OG image, placeholder icon |

`https://vskromny.github.io/tubik-landing/player/` is the base URL of the app's bundled video player page, so it is the HTTP Referer the YouTube embed sees; the page only explains that and must keep that URL.

Serve locally: `python3 -m http.server 8000`.

## Rules (from `tubik/product/POLICY.md`)

- Never use "YouTube"/"YT" in the product name or imply YouTube endorsement. Body copy may say
  the app plays videos from YouTube channels the parent approves. No red play-button imagery.
- Position the app for **parents of young children**, never as "for kids only" (not in the Kids category).
- No trackers, no cookies, no third-party scripts or font CDNs.
- Privacy policy must match `tubik/product/PRODUCT_SPEC.md` §12 data table.

## Open placeholders

- Support/imprint e-mail is `hello@recipics.app` (ReciPics address, per owner instruction); replace with a Tubik-specific address if one is created.
- The app icon (`assets/img/icon-512.png`, favicon) is a placeholder "T" mark, not the final icon.
- No App Store badge/link until the app is live.
