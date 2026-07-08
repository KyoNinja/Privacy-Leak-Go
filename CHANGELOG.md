# Changelog

<!--
  Versions above v1.0.0 are generated automatically by release-please
  (in the "## [X.Y.Z]" format) from the Conventional Commits. Do not edit by hand.
  v1.0.0 is the historical baseline and stays in the old format.
-->

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
