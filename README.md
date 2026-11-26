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

- `hugo.toml`: canonical URL, contact address, and the TestFlight and web app links.
- `layouts/home.html`: landing-page copy and screenshot descriptions.
- `layouts/surfs.html` and `content/surfs.md`: the Surf tracking page (Apple Watch recording, Surfs tab and Scoreboard).
- `layouts/_partials/device.html`: framed device pictures from `assets/images/devices/<name>.png`, resized to WebP at 1x and 2x by Hugo. `access.html` is the shared access panel; `waves.html` the hero's wave edge.
- `content/help.md` and `content/privacy.md`: support and privacy pages.
- `assets/css/main.css`: responsive styles, bundled and fingerprinted by Hugo.
- `assets/images/devices/`: app screenshots framed in Apple's simulator device artwork (iPhone 18 Pro, iPad Air 13-inch, Apple Watch Ultra). Made with `scripts/frame-screenshot.swift` in the stokeranker-ios repo from simulator captures of the app's synthetic journal (`STOKERANKER_TEST_JOURNAL=synthetic`, `STOKERANKER_TEST_JOURNAL_AS_WATCH=1`) and the Watch demo (`-demo lastwave -demoBreak "Emerald Beach"`), so no personal data is shown. `static/images/`: branding.

No JavaScript, third-party fonts, analytics or cookies are used by this public site. Access CTAs link to the public TestFlight beta and the web app (`testflight` and `webApp` in `hugo.toml`). Spot-check invite links are still never published.

## Publishing

The site is live at https://stokeranker.com/. Pushing `master` to the GitHub remote (`origin`) publishes it: the host builds with `hugo --gc --minify` and serves `public/`, including the generated `404.html` for missing paths. There is no separate deploy step.

The privacy text was checked against the native client and web-service source on 4 November 2026, and its Surfs and Apple Watch section on 16 November 2026. Confirm infrastructure log/backup retention and provider arrangements with the live hosting configuration before App Store submission. The policy is published at `https://stokeranker.com/privacy/`. Apple also requires an easily accessible privacy-policy link inside the app, and accurate App Store Connect privacy disclosures; publishing this page alone does not configure those. The app's Settings → Help and privacy shows a summary of the app's part of this policy and links here for the full text (stokeranker-ios `HelpContent.swift`); keep the two consistent.
