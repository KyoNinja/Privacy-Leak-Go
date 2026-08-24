<div align="center">

# Privacy Leak GO

**Desktop app to download your Privacy.com.br media — browser login, bulk downloads and HLS video, all local.**

`Windows` · `x64` · portable — no installer  ·  `Linux` · `x64` · `.tar.gz`

[![Latest release](https://img.shields.io/github/v/release/KyoNinja/Privacy-Leak-Go?display_name=tag&sort=semver&label=latest&color=2ea44f)](https://github.com/KyoNinja/Privacy-Leak-Go/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/KyoNinja/Privacy-Leak-Go/total?label=downloads&color=1f6feb)](https://github.com/KyoNinja/Privacy-Leak-Go/releases)

<a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-windows-x64.exe">
  <img src="https://img.shields.io/badge/⬇%20Download%20for%20Windows-x64-2ea44f?style=for-the-badge&logo=windows&logoColor=white" alt="Download for Windows x64" height="46">
</a>
<a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-x64.tar.gz">
  <img src="https://img.shields.io/badge/⬇%20Download%20for%20Linux-x64-2ea44f?style=for-the-badge&logo=linux&logoColor=white" alt="Download for Linux x64" height="46">
</a>
<a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-amd64.deb">
  <img src="https://img.shields.io/badge/⬇%20Install%20on%20Ubuntu-amd64-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Install on Ubuntu amd64" height="46">
</a>

<sub>Current release: v1.9.0 · [all releases](https://github.com/KyoNinja/Privacy-Leak-Go/releases) · [changelog](CHANGELOG.md)</sub>

</div>

---

## Getting started

1. **[Download the app](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-windows-x64.exe)** (the button above).
2. Windows SmartScreen may warn about an unknown publisher — the build is unsigned. Click **More info → Run anyway**.
3. Double-click `PrivacyLeakGO-v1.9.0-windows-x64.exe`. It's portable; nothing gets installed.
4. On Ubuntu 24.04, download [`PrivacyLeakGO-v1.9.0-linux-amd64.deb`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-amd64.deb) and run `sudo apt install ./PrivacyLeakGO-v1.9.0-linux-amd64.deb`.
5. On other Linux systems, download [`PrivacyLeakGO-v1.9.0-linux-x64.tar.gz`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-x64.tar.gz), extract it, and run the included executable from a terminal.

## Features

- 🔐 Browser-based login (external Chrome/Edge) with automatic session capture
- ⬇️ Bulk download and a manual media-selection grid
- 🎞️ HLS video downloads with key handling and FFmpeg conversion
- 🗂️ Profiles page with public metadata, thumbnails and indexed media
- 📝 Per-profile logs with an in-app viewer
- 🌐 English / Português interface

## Requirements

- Windows 10 or 11, or Ubuntu 24.04 (x64); Ubuntu 22.04 and other Debian-based systems are best effort
- Google Chrome or Microsoft Edge — used for the login flow
- FFmpeg for HLS video conversion — the app can download a local copy for you
- Linux also needs GTK3/WebKitGTK and a Chromium-based browser for the login flow

## Verify your download (optional)

Every release ships a [`SHA256SUMS.txt`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/SHA256SUMS.txt) covering all published files. In PowerShell:

```powershell
Get-FileHash .\PrivacyLeakGO-v1.9.0-windows-x64.exe -Algorithm SHA256
```

Compare the result with the line for `PrivacyLeakGO-v1.9.0-windows-x64.exe` in `SHA256SUMS.txt`.

On Linux, run `sha256sum ./PrivacyLeakGO-v1.9.0-linux-x64.tar.gz` and compare it with the line for
`PrivacyLeakGO-v1.9.0-linux-x64.tar.gz` in `SHA256SUMS.txt`.
For the Ubuntu package, use `sha256sum ./PrivacyLeakGO-v1.9.0-linux-amd64.deb` and compare it with the
corresponding line in `SHA256SUMS.txt`.

## Updates

The app checks this repository for newer releases and links you back here. See the [changelog](CHANGELOG.md) for what changed.

---

<div align="center">
<sub>Windows x64, portable Linux x64 and Ubuntu amd64 builds are published automatically.</sub>
</div>

