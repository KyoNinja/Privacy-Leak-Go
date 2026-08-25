# Changelog

<!--
 Versions above v1.0.0 are generated automatically by release-please
 (in the "## [X.Y.Z]" format) from the Conventional Commits. Do not edit by hand.
 v1.0.0 is the historical baseline and stays in the old format.
-->

## 2.0.0 (2026-08-25)


### Features

* **downloads:** rework the download screen into a three-step composer (6a972f9)
* **downloads:** preserve post media grouping and source publication timestamps (98000c1, e64a8a3)
* **downloads:** browse and download media by account chat room (5e7bd81)
* **uploads:** rebuild the Uploads screen as a three-step composer with batch history (de9f106, 6307df0, 77bbef8)
* **uploads:** add PixelDrain and Gofile upload providers (63107c2, 6f60053)
* **uploads:** add external folder batch uploads (6a23e2c)
* **uploads:** support selecting existing destination albums and creating PixelDrain lists (e10ccc9, 41b4fde)
* **uploads:** configure worker pools per destination host (19c3cea)
* **profiles:** redesign profiles library with row layout, detail drawer and Mirror Matrix (cad827c)
* **profiles:** show archived purchase records (94adb3c)
* **backend:** add batch profile mirror summaries and health metrics bridge (79bb80d)


### Bug Fixes

* **downloads:** preserve IDs and content fingerprints across migrations (cfab76b)
* **downloads:** bind archived chat scans to rooms (150b9fa)
* **uploads:** detect incomplete GoonBox sessions and finalize collections (99de18f, d35171d)
* **uploads:** preserve routed status semantics and handle empty destination selections (c28d70c, 73c52ca)
* **uploads:** align content fingerprint migration and provider folder handling (55ae7fd, ba84af5, a9f9882)


### Performance

* **uploads:** reuse listing snapshot for transfer counts (91aa1c9)


### Refactoring & Chores

* **profiles:** modernize profile state estimation and selection hooks (53f855e)
* **deps:** update frontend packages and align React 19 types (c8af5fb)
* **ci:** automate release back-sync pipeline and improve promotion resilience (81b1ac9)

## 1.9.0 (2026-08-24)


### Features

* **linux:** add native Ubuntu package (#121) (75fedc7)

## 1.8.0 (2026-08-24)


### Features

* **linux:** add Ubuntu cross-platform support (#112) (e578db0)

## 1.7.0 (2026-08-24)


### Features

* **uploads:** add parallel uploads, album management, and CyberDrop provider (#109) (aed4495)

## 1.6.0 (2026-08-23)


### Features

* promote startup update to develop (ae42a25)
* **ui:** standardize settings and page layouts (#103) (ac90b4e)
* **ui:** standardize settings layout and polish uploads workspace (#107) (7a94b06)

## 1.5.0 (2026-08-23)


### Features

* **app:** show startup update notification (#100) (aeab9fc)
* **upload:** enhance uploads workflow and profile-scoped queue (#95) (80bed80)

## 1.4.0 (2026-08-01)


### Features

* **ui:** prompt to install missing FFmpeg on app startup (#90) (2c8a1c3)

## 1.3.0 (2026-07-20)


### Features

* **wails:** resolve portability and v3 migration gaps (#67) (cdd7808)

## 1.2.0 (2026-07-20)


### Features

* **media:** add {caption} token to the filename template (#58) (ad3702e)
* **media:** restore chat media and rebuild selection UI (48c1ded)
* **release:** show development commit hashes and sync app versions (4978c38)


### Bug Fixes

* reject filename templates without media id (#52) (ea76567)

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
