<div align="center">

# Privacy Leak GO

### A calm, local-first way to download your Privacy.com.br media

Browse followed profiles, choose exactly what you want, and keep the downloaded
files on your machine. Login happens in an external Chromium window; remote
mirrors are optional.

<p>
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-windows-x64.exe">
    <img src="https://img.shields.io/badge/Download%20for%20Windows-x64-2ea44f?style=for-the-badge&logo=windows&logoColor=white" alt="Download for Windows x64" height="42">
  </a>
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-amd64.deb">
    <img src="https://img.shields.io/badge/Install%20on%20Ubuntu-amd64-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Install on Ubuntu amd64" height="42">
  </a>
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-x64.tar.gz">
    <img src="https://img.shields.io/badge/Download%20for%20Linux-x64-2ea44f?style=for-the-badge&logo=linux&logoColor=white" alt="Download for Linux x64" height="42">
  </a>
</p>

<p>
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases/latest"><img src="https://img.shields.io/github/v/release/KyoNinja/Privacy-Leak-Go?display_name=tag&sort=semver&label=latest&color=2ea44f" alt="Latest release"></a>
  <a href="https://github.com/KyoNinja/Privacy-Leak-Go/releases"><img src="https://img.shields.io/github/downloads/KyoNinja/Privacy-Leak-Go/total?label=downloads&color=1f6feb" alt="Total downloads"></a>
  <a href="CHANGELOG.md"><img src="https://img.shields.io/badge/changelog-read-8b5cf6" alt="Read the changelog"></a>
</p>

<sub>Latest release: v1.9.0 · Windows x64 portable · Ubuntu amd64 package · Linux x64 archive</sub>

</div>

---

## Start here

| Platform | Package | Best for |
| --- | --- | --- |
| **Windows 10/11 · x64** | [Portable `.exe`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-windows-x64.exe) | Download, run, and go — no installer |
| **Ubuntu 24.04 · amd64** | [`.deb` package](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-amd64.deb) | Native installation with `apt` |
| **Other Linux · x64** | [Portable `.tar.gz`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-x64.tar.gz) | Manual extraction on compatible distributions |

## Install in a minute

### Windows

1. Download [`PrivacyLeakGO-v1.9.0-windows-x64.exe`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-windows-x64.exe).
2. If SmartScreen warns about an unknown publisher, choose **More info → Run anyway**. The build is portable and unsigned.
3. Double-click the executable. Nothing is installed system-wide.

### Ubuntu 24.04

```bash
sudo apt install ./PrivacyLeakGO-v1.9.0-linux-amd64.deb
```

Download [`PrivacyLeakGO-v1.9.0-linux-amd64.deb`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-amd64.deb) first, then run the command from
the folder where it was saved.

### Other Linux systems

Download [`PrivacyLeakGO-v1.9.0-linux-x64.tar.gz`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/PrivacyLeakGO-v1.9.0-linux-x64.tar.gz), extract the archive, and run
the included executable from a terminal. Ubuntu 22.04 and other Debian-derived
systems are best-effort compatibility targets.

## What you can do

<table>
  <tr>
    <td width="50%">🔐 <strong>Browser login</strong><br>Sign in through Chrome, Edge, or another Chromium-based browser and capture the session locally.</td>
    <td width="50%">🧭 <strong>Profile workspace</strong><br>Search, sort, multi-select, preview public metadata, and estimate what is already on disk.</td>
  </tr>
  <tr>
    <td>📥 <strong>Flexible downloads</strong><br>Use bulk downloads for Feed, Chat, Purchased, or All sources with streaming discovery and per-source limits.</td>
    <td>🎯 <strong>Manual selection</strong><br>Pick individual photos or videos in a grid with type, source, date, and “only new” filters.</td>
  </tr>
  <tr>
    <td>🎞️ <strong>Video pipeline</strong><br>Handle HLS playlists and keys, show segment progress, and convert videos through FFmpeg.</td>
    <td>🗂️ <strong>Organized files</strong><br>Use filename templates, collision-safe numbering, per-profile indexes, and rotating logs.</td>
  </tr>
  <tr>
    <td>☁️ <strong>Optional remote mirrors</strong><br>Send completed files to one or more configured hosts while always keeping the local copy.</td>
    <td>🌐 <strong>English + Português</strong><br>Switch the interface language from Settings without changing your downloaded files.</td>
  </tr>
</table>

## The workflow

<p align="center">
  <strong>1 · Login</strong> &nbsp;→&nbsp;
  <strong>2 · Choose profiles</strong> &nbsp;→&nbsp;
  <strong>3 · Select media</strong> &nbsp;→&nbsp;
  <strong>4 · Download</strong>
</p>

1. Open the app and choose **Open Login Browser**.
2. Complete the login in the external Chromium window.
3. Load followed profiles and select one or more profiles.
4. Start a bulk download, or switch to manual selection for a single profile.
5. Follow collection, file, HLS, and conversion progress in **Downloads**. Use
   **Debug** and the per-profile log viewer when you need technical details.

## Optional remote mirrors

The **Uploads** page can mirror completed downloads to several hosts. Uploading
never removes the local file and never blocks the download queue. You can choose
multiple destinations, keep separate photo/video routing, organize albums, and
re-send a file when needed.

| Host | Media |
| --- | --- |
| Bunkr | Photos and videos |
| CyberDrop | Photos and videos |
| Filester | Photos and videos |
| Turbo | Videos |
| GoonBox | Photos |

Host capabilities and authentication requirements are checked by the app. Only
configure the destinations you intend to use.

## Requirements

| Platform | Requirements |
| --- | --- |
| **Windows 10/11 · x64** | Chrome or Edge for login. FFmpeg is required for HLS video conversion; the app can manage a local copy. |
| **Ubuntu 24.04 · amd64** | A Chromium-based browser, GTK3/WebKitGTK, and FFmpeg available in `PATH`. |
| **Other Linux · x64** | A compatible GTK3/WebKitGTK desktop, a Chromium-based browser, and FFmpeg in `PATH`; support is best effort. |

Firefox is not a supported browser-login path on Linux.

## Verify your download

Every release includes [`SHA256SUMS.txt`](https://github.com/KyoNinja/Privacy-Leak-Go/releases/download/v1.9.0/SHA256SUMS.txt), covering all
published files. Compare the checksum produced on your machine with the matching
line in that file.

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

The app checks this repository for newer releases and links you back here. Visit
the [latest release](https://github.com/KyoNinja/Privacy-Leak-Go/releases/latest)
or read the [changelog](CHANGELOG.md) to see what changed.

## Responsible use

Use the app only for media you are authorized to access. The Privacy.com.br web
and API behavior can change over time, and high-volume activity may still be
recognized by the service. Never share your browser session or local session
file.

---

<div align="center">
<sub>Release assets and this page are maintained automatically · Windows x64, Ubuntu amd64, and Linux x64</sub>
</div>

