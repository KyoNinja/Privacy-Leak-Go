# Changelog

<!--
  Versions above v1.0.0 are generated automatically by release-please
  (in the "## [X.Y.Z]" format) from the Conventional Commits. Do not edit by hand.
  v1.0.0 is the historical baseline and stays in the old format.
-->

## [1.2.0](https://github.com/JustShinobi/privacy-leak-go/compare/v1.1.2...v1.2.0) (2026-07-20)


### Features

* **media:** add {caption} token to the filename template ([#58](https://github.com/JustShinobi/privacy-leak-go/issues/58)) ([ad3702e](https://github.com/JustShinobi/privacy-leak-go/commit/ad3702ef3e26d9c1f6ce43959714c2f2107de1cf))
* **media:** restore chat media and rebuild selection UI ([48c1ded](https://github.com/JustShinobi/privacy-leak-go/commit/48c1dedf69c2e2c7f8744bb121c1540c968292b8))
* **release:** show development commit hashes and sync app versions ([4978c38](https://github.com/JustShinobi/privacy-leak-go/commit/4978c38b1a485bec181a383e2d1dc8fcf2b2f2a8))


### Bug Fixes

* reject filename templates without media id ([#52](https://github.com/JustShinobi/privacy-leak-go/issues/52)) ([ea76567](https://github.com/JustShinobi/privacy-leak-go/commit/ea76567577834f1ca4644163bf657ca684b841b0))

## 1.1.2 (2026-07-08)


### Bug Fixes

* **app:** sanitize public changelog links (d9109da)

## 1.1.1 (2026-07-08)


### Bug Fixes

* **ci:** strip private-repo links from public changelog and release notes (c5a80ae)

## 1.1.0 (2026-07-08)


### Features

* **anti-bot:** add a configurable anti-bot mode (jitter, warm-up and limits) (6d88552)
* **logs:** mirror the runtime log to a file for offline diagnostics (535300f)
* **settings:** add a Privacy & bot-detection settings section (7229b4a)


### Bug Fixes

* **auth:** restore browser login and harden the session against Privacy's WAF (dcb20cf)
* **ci:** delimit the branch var in release-public notes step (c3cd79c)
* **ci:** pass --repo to gh run download in release-public (20870b7)
* **scraper:** migrate the profile feed to the timelinequeries endpoint (3fdb167)

## v1.0.0

Initial stable desktop release baseline.

### Highlights

- Browser-based login flow (external Chromium) with automatic session capture
- Bulk download and manual media selection grid
- HLS video downloads with key handling and FFmpeg conversion
- Per-profile file logs with rotation and in-app Log Viewer
- Profiles page with public metadata, thumbnails, local heuristics and indexed media IDs
- English / Portuguese UI support
- E2E smoke test suite for external endpoint contracts
