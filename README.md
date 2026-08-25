# Privacy Leak GO

A desktop application for Windows and Linux that lets you browse followed Privacy.com.br profiles and download media available to your account. Login is completed in an external Chromium-based browser.

<p align="center">
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/latest"><img src="https://img.shields.io/github/v/release/KyoNinja/Privacy-Leak-Go?display_name=tag&sort=semver&label=latest&color=2ea44f" alt="Latest release"></a>
  <a href="CHANGELOG.md"><img src="https://img.shields.io/badge/changelog-read-6f42c1" alt="Read the changelog"></a>
</p>

> Current release: `v2.0.0` · Windows x64 portable executable · Ubuntu amd64 package · Linux x64 archive

## Download

| Target | Package | Notes |
| --- | --- | --- |
| Windows 10/11 · x64 | [`PrivacyLeakGO-v2.0.0-windows-x64.exe`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v2.0.0/PrivacyLeakGO-v2.0.0-windows-x64.exe) | Portable `.exe`; no installer |
| Ubuntu 24.04 · amd64 | [`PrivacyLeakGO-v2.0.0-linux-amd64.deb`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v2.0.0/PrivacyLeakGO-v2.0.0-linux-amd64.deb) | Native `.deb` package |
| Other Linux · x64 | [`PrivacyLeakGO-v2.0.0-linux-x64.tar.gz`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v2.0.0/PrivacyLeakGO-v2.0.0-linux-x64.tar.gz) | Portable `.tar.gz` archive |

## Install

### Windows

Download [`PrivacyLeakGO-v2.0.0-windows-x64.exe`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v2.0.0/PrivacyLeakGO-v2.0.0-windows-x64.exe) and run it. The executable is portable. Windows SmartScreen may display an unknown-publisher warning because the release is not code-signed.

### Ubuntu 24.04

Download [`PrivacyLeakGO-v2.0.0-linux-amd64.deb`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v2.0.0/PrivacyLeakGO-v2.0.0-linux-amd64.deb), then install it from the directory where it was saved:

```bash
sudo apt install ./PrivacyLeakGO-v2.0.0-linux-amd64.deb
```

### Other Linux systems

Extract [`PrivacyLeakGO-v2.0.0-linux-x64.tar.gz`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v2.0.0/PrivacyLeakGO-v2.0.0-linux-x64.tar.gz) and run the included executable from a terminal. Ubuntu 22.04 and other Debian-derived distributions are compatibility targets on a best-effort basis.

## Usage

1. Open the app and choose **Open Login Browser**.
2. Complete the login in the external Chromium window.
3. Load the followed profiles and select one or more profiles.
4. Start a bulk download, or open manual selection for a single profile.
5. Track collection, download, HLS, and conversion progress in **Downloads**. The **Debug** page and per-profile logs contain additional details when a request fails.

## Features

- Search and sort followed profiles, select several at once, inspect public metadata, and estimate new media.
- Downloads from **Feed**, **Purchased**, **Chat**, or **All**, with media-type filters and per-source limits.
- Manual media selection with filters for type, source, date, and only-new items.
- HLS playlist and encryption-key handling, segment progress, and FFmpeg video conversion.
- Configurable filename templates, collision-safe numbering, media indexes, and rotating per-profile logs.
- English and Portuguese interface.
- Optional uploads to supported file hosts, configured separately for images and videos.

## Technical overview

The app runs as a local desktop process. Wails embeds the production React bundle and exposes Go methods and events to the UI. Go handles authentication, network requests, filesystem access, and background jobs. The download path calls Privacy.com.br directly; uploads, when enabled, call the selected hosts. No separate service is required to run the app.

| Component | Technology | Role |
| --- | --- | --- |
| Desktop shell | Wails v2.13.0 | Native window, embedded frontend, and Go/JavaScript bridge |
| UI | React 18, TypeScript, Vite 5, Tailwind CSS 4 | Profiles, downloads, uploads, settings, progress, and logs |
| Backend | Go 1.25 | API client, authentication, scraping, and background jobs |
| Browser login | `chromedp` + Chrome DevTools Protocol | Headed Chromium-family login and session capture |
| Media | Go HTTP client, HLS pipeline + FFmpeg | Playlist/segment downloads and video conversion |
| Storage | JSON files, media indexes, and logs | Settings, session, cache, download state, and diagnostics |
| Uploads | Go `Uploader` interface | Host-specific authentication, albums/folders, retries, and progress |

The backend is organized into `api`, `auth`, `config`, `media`, and `uploadhost`. Upload providers share the `Uploader` interface; host-specific API code lives in `backend/uploadhost`.

## Files and session

Settings, session data, caches, media indexes, and logs are stored under `PrivacyDesktop`:

- Windows: `%APPDATA%\PrivacyDesktop`
- Linux: `~/.config/PrivacyDesktop`

The session file contains authentication tokens. Treat it as sensitive and do not share it.

## Optional uploads

The **Uploads** page can mirror completed files to configured destinations. Image and video destinations are configured separately:

| Host | Media |
| --- | --- |
| Bunkr | Photos and videos |
| CyberDrop | Photos and videos |
| Filester | Photos and videos |
| Turbo | Videos |
| GoonBox | Photos |

The app checks each host's authentication requirements and supported media types. Credentials are configured in Settings.

## Requirements

| Platform | Requirements |
| --- | --- |
| Windows 10/11 · x64 | A Chromium-family browser for login. FFmpeg is required for HLS video conversion; Windows can use a local binary managed by the app. |
| Ubuntu 24.04 · amd64 | GTK3, WebKitGTK 4.1, a Chromium-family browser, and FFmpeg available in `PATH`. |
| Other Linux · x64 | Compatible GTK3/WebKitGTK runtime, a Chromium-family browser, and FFmpeg in `PATH`; support is best effort. |

On Linux, login requires a Chromium-family browser; Firefox is not supported.

## Verify a download

Each release includes [`SHA256SUMS.txt`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v2.0.0/SHA256SUMS.txt), containing SHA-256 checksums for the published files.

**PowerShell (Windows)**

```powershell
Get-FileHash .\PrivacyLeakGO-v2.0.0-windows-x64.exe -Algorithm SHA256
```

**Linux**

```bash
sha256sum ./PrivacyLeakGO-v2.0.0-linux-x64.tar.gz
sha256sum ./PrivacyLeakGO-v2.0.0-linux-amd64.deb
```

## Releases

Download the current artifacts from the [latest release](https://github.com/KyoNinja/Privacy-Leak-Go/releases/latest). Changes are listed in [`CHANGELOG.md`](CHANGELOG.md).

Only download media you are authorized to access. Privacy.com.br and upload-host APIs can change independently of this project.

