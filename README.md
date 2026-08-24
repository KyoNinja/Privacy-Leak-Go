# Privacy Leak GO

A Wails desktop client for browsing followed Privacy.com.br profiles and downloading accessible media to disk. Login is completed in an external Chromium-based browser. Uploading to file hosts is optional; the local download is always kept.

<p align="center">
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-windows-x64.exe"><img src="https://img.shields.io/badge/Windows%20x64-download-2ea44f?style=flat-square&logo=windows&logoColor=white" alt="Download for Windows x64"></a>
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-amd64.deb"><img src="https://img.shields.io/badge/Ubuntu%20amd64-.deb-E95420?style=flat-square&logo=ubuntu&logoColor=white" alt="Download Ubuntu amd64 package"></a>
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-x64.tar.gz"><img src="https://img.shields.io/badge/Linux%20x64-tar.gz-1f6feb?style=flat-square&logo=linux&logoColor=white" alt="Download Linux x64 archive"></a>
</p>

<p align="center">
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/latest"><img src="https://img.shields.io/github/v/release/KyoNinja/Privacy-Leak-Go?display_name=tag&sort=semver&label=latest&color=2ea44f" alt="Latest release"></a>
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases"><img src="https://img.shields.io/github/downloads/KyoNinja/Privacy-Leak-Go/total?label=downloads&color=1f6feb" alt="Total downloads"></a>
  <a href="CHANGELOG.md"><img src="https://img.shields.io/badge/changelog-read-6f42c1" alt="Read the changelog"></a>
</p>

> Current release: `v1.9.0` · Windows x64 portable executable · Ubuntu amd64 package · Linux x64 archive

## Download

| Target | Package | Notes |
| --- | --- | --- |
| Windows 10/11 · x64 | [`PrivacyLeakGO-v1.9.0-windows-x64.exe`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-windows-x64.exe) | Portable `.exe`; no installer |
| Ubuntu 24.04 · amd64 | [`PrivacyLeakGO-v1.9.0-linux-amd64.deb`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-amd64.deb) | Native `.deb` package |
| Other Linux · x64 | [`PrivacyLeakGO-v1.9.0-linux-x64.tar.gz`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-x64.tar.gz) | Portable `.tar.gz` archive |

## Install

### Windows

Download [`PrivacyLeakGO-v1.9.0-windows-x64.exe`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-windows-x64.exe) and run it. The executable is portable. Windows SmartScreen may display an unknown-publisher warning because the release is not code-signed.

### Ubuntu 24.04

Download [`PrivacyLeakGO-v1.9.0-linux-amd64.deb`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-amd64.deb), then install it from the directory where it was saved:

```bash
sudo apt install ./PrivacyLeakGO-v1.9.0-linux-amd64.deb
```

### Other Linux systems

Extract [`PrivacyLeakGO-v1.9.0-linux-x64.tar.gz`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-x64.tar.gz) and run the included executable from a terminal. Ubuntu 22.04 and other Debian-derived distributions are compatibility targets on a best-effort basis.

## Usage

1. Open the app and choose **Open Login Browser**.
2. Complete the login in the external Chromium window.
3. Load the followed profiles and select one or more profiles.
4. Start a bulk download, or open manual selection for a single profile.
5. Track collection, download, HLS, and conversion progress in **Downloads**. The **Debug** page and per-profile logs contain additional details when a request fails.

## Features

- Profile search, sorting, multi-select, public preview, and local “new media” estimates.
- Bulk downloads from **Feed**, **Purchased**, **Chat**, or **All**, with media-type filters and per-source limits.
- Manual media selection with filters for type, source, date, and already-downloaded items.
- HLS playlist/key handling, segment progress, and FFmpeg conversion for video.
- Configurable filename templates, collision-safe numbering, media indexes, and rotating per-profile logs.
- English and Portuguese interface.
- Optional uploads to several file hosts. Uploads run independently of the download queue and never remove the local file.

## Architecture

The application runs locally as a single Wails process. The React interface is embedded into the desktop binary and communicates with the Go backend through Wails bindings and events. The backend talks directly to Privacy.com.br and, when enabled, to the configured upload hosts; there is no project server involved in the normal desktop flow.

| Area | Stack | Responsibility |
| --- | --- | --- |
| Desktop shell | Wails v2.13.0 | Native window, embedded frontend, Go/JavaScript bindings, and runtime events |
| Frontend | React 18, TypeScript, Vite 5, Tailwind CSS 4 | Profiles, downloads, uploads, settings, progress, and logs |
| Application backend | Go 1.25 | API client, authentication, scraping, download jobs, settings, and upload jobs |
| Browser login | `chromedp` + Chrome DevTools Protocol | Opens a headed Chromium-family browser and captures the authenticated session |
| Media pipeline | Go HTTP/HLS code + FFmpeg | Discovers media, downloads HLS playlists/segments, and converts video |
| Local state | JSON files, media indexes, and log files | Settings, session tokens, profile cache, downloaded-media state, and diagnostics |
| Upload adapters | Go `Uploader` interface | Provider-specific authentication, folders/albums, retries, progress, and routing |

The main Go application coordinates the backend packages under `backend/`: `api`, `auth`, `config`, `media`, and `uploadhost`. Upload providers are isolated behind an interface so each host can implement its own API and authentication rules.

## Local data

User data is stored below `PrivacyDesktop` in the platform configuration directory:

- Windows: `%APPDATA%\PrivacyDesktop`
- Linux: `~/.config/PrivacyDesktop`
- macOS: `~/Library/Application Support/PrivacyDesktop`

This directory contains settings, the saved session, profile caches, media indexes, and logs. Treat the session file as sensitive and do not share it.

## Optional uploads

The **Uploads** page can mirror completed files to configured destinations. Routing is separate for photos and videos:

| Host | Media |
| --- | --- |
| Bunkr | Photos and videos |
| CyberDrop | Photos and videos |
| Filester | Photos and videos |
| Turbo | Videos |
| GoonBox | Photos |

Authentication requirements and host capabilities are checked by the app. Configure only destinations you trust; these services are independent third parties and are not backups.

## Requirements

| Platform | Requirements |
| --- | --- |
| Windows 10/11 · x64 | A Chromium-family browser for login. FFmpeg is required for HLS video conversion; Windows can use a local binary managed by the app. |
| Ubuntu 24.04 · amd64 | GTK3, WebKitGTK 4.1, a Chromium-family browser, and FFmpeg available in `PATH`. |
| Other Linux · x64 | Compatible GTK3/WebKitGTK runtime, a Chromium-family browser, and FFmpeg in `PATH`; support is best effort. |

Firefox is not a supported browser-login path on Linux.

## Verify a download

Each release includes [`SHA256SUMS.txt`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/SHA256SUMS.txt), containing SHA-256 checksums for the published files.

**PowerShell (Windows)**

```powershell
Get-FileHash .\PrivacyLeakGO-v1.9.0-windows-x64.exe -Algorithm SHA256
```

**Linux**

```bash
sha256sum ./PrivacyLeakGO-v1.9.0-linux-x64.tar.gz
sha256sum ./PrivacyLeakGO-v1.9.0-linux-amd64.deb
```

## Updates and changelog

See the [latest release](https://github.com/KyoNinja/Privacy-Leak-Go/releases/latest) for downloads and [`CHANGELOG.md`](CHANGELOG.md) for release notes.

Use the app only for media you are authorized to access. Privacy.com.br and third-party upload-host APIs can change independently of this project.

---

<p align="center"><sub>Release assets and this README are synchronized automatically from the source repository.</sub></p>

