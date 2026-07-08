<div align="center">

# Privacy Leak GO

**Desktop app to download your Privacy.com.br media — browser login, bulk downloads and HLS video, all local.**

`Windows` · `x64` · portable — no installer

[![Latest release](https://img.shields.io/github/v/release/KyoNinja/Privacy-Leak-Go?display_name=tag&sort=semver&label=latest&color=2ea44f)](https://github.com/KyoNinja/Privacy-Leak-Go/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/KyoNinja/Privacy-Leak-Go/total?label=downloads&color=1f6feb)](https://github.com/KyoNinja/Privacy-Leak-Go/releases)

<a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.1.2/PrivacyLeakGO-v1.1.2-windows-x64.exe">
  <img src="https://img.shields.io/badge/⬇%20Download%20for%20Windows-x64-2ea44f?style=for-the-badge&logo=windows&logoColor=white" alt="Download for Windows x64" height="46">
</a>

<sub>Current release: v1.1.2 · [all releases](https://github.com/KyoNinja/Privacy-Leak-Go/releases) · [changelog](CHANGELOG.md)</sub>

</div>

---

## Getting started

1. **[Download the app](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.1.2/PrivacyLeakGO-v1.1.2-windows-x64.exe)** (the button above).
2. Windows SmartScreen may warn about an unknown publisher — the build is unsigned. Click **More info → Run anyway**.
3. Double-click `PrivacyLeakGO-v1.1.2-windows-x64.exe`. It's portable; nothing gets installed.

## Features

- 🔐 Browser-based login (external Chrome/Edge) with automatic session capture
- ⬇️ Bulk download and a manual media-selection grid
- 🎞️ HLS video downloads with key handling and FFmpeg conversion
- 🗂️ Profiles page with public metadata, thumbnails and indexed media
- 📝 Per-profile logs with an in-app viewer
- 🌐 English / Português interface

## Requirements

- Windows 10 or 11 (x64)
- Google Chrome or Microsoft Edge — used for the login flow
- FFmpeg for HLS video conversion — the app can download a local copy for you

## Verify your download (optional)

Every release ships a matching `.sha256`. In PowerShell:

```powershell
Get-FileHash .\PrivacyLeakGO-v1.1.2-windows-x64.exe -Algorithm SHA256
```

Compare the result with the value in `PrivacyLeakGO-v1.1.2-windows-x64.exe.sha256` from the release.

## Updates

The app checks this repository for newer releases and links you back here. See the [changelog](CHANGELOG.md) for what changed.

---

<div align="center">
<sub>This repository hosts the Windows builds only — releases are published automatically.</sub>
</div>

