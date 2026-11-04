# StokeRanker website

Hugo marketing, support and privacy website for https://stokeranker.com/.

## Build and preview

Requires Hugo 0.146 or later (no Node, theme download or external asset service required).

```sh
hugo --gc --minify
hugo server --bind 127.0.0.1 --port 1313 --disableFastRender
```

The publish directory is `public/`; deploy that directory rather than the repository root. Generated output is ignored. The previous root placeholder has been removed so it cannot silently mask the Hugo build.

## Editing

- `hugo.toml`: canonical URL, contact address and email CTA text.
- `layouts/home.html`: landing-page copy and screenshot descriptions.
- `content/help.md` and `content/privacy.md`: support and privacy pages.
- `assets/css/main.css`: responsive styles, bundled and fingerprinted by Hugo.
- `static/images/`: existing branding and app screenshots from the iOS project.

No JavaScript, third-party fonts, analytics or cookies are used by this public site. All access CTAs open a prefilled email; invite URLs are deliberately not published.

## Before publishing

No hosting or production deployment has been configured by this change. Set the host build command to `hugo --gc --minify`, output `public`, and pin a compatible Hugo version. Serve the generated `404.html` for missing paths.

The privacy text was checked against the native client and web-service source on 4 November 2026. Confirm infrastructure log/backup retention and provider arrangements with the live hosting configuration before submission. Its published address will be `https://stokeranker.com/privacy/`. Apple also requires an easily accessible privacy-policy link inside the app, and accurate App Store Connect privacy disclosures; publishing this page alone does not configure those. The current native source has an About website link but no dedicated privacy link.
