> [!IMPORTANT]
> **Maintenance Status: Unmaintained**
>
> This project is no longer actively maintained. No further feature updates, bug fixes, or compatibility updates are planned.
>
> The source code and existing releases will remain available for learning, reference, and use. Once archived, the repository is read-only and no longer accepts new Issues or Pull Requests. Maintenance may resume in the future.

<div align="center">


[![English](https://img.shields.io/badge/English-Current%20Page-4A90D9?style=for-the-badge)](./README.en.md)
[![简体中文](https://img.shields.io/badge/%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-%E5%88%87%E6%8D%A2-9CA3AF?style=for-the-badge)](./README.md)

<img src="./docs/assets/readme/cinema-beat-smoke.png" alt="Mineradio — Private Visual Radio" width="720" />

<br /><br />


</div>

# Mineradio macOS

Mineradio macOS is an unofficial macOS-focused port of [XxHuberrr/Mineradio](https://github.com/XxHuberrr/Mineradio). This repository previously focused on a Mac-first desktop experience: completing macOS packaging, platform paths and update asset selection, and exploring macOS-native motion, window layering and immersive playback on top of it. It is no longer actively maintained.

**Disclaimer:** this is *not* an official Mac release from the original author. The code, design and branding of the original project belong to the upstream repository; the modifications published here remain publicly available under the GPL-3.0 license.

## Project Positioning

- A macOS adaptation of Mineradio (unmaintained)
- Preserves the immersive music-player core experience of the original project
- Previously prioritized fixes for macOS runtime, packaging, paths, updates and desktop integration
- Previously planned to add interactions, animations and visual details that fit Mac usage habits; no further development is planned

If you need the official Windows installer, please go to the upstream repository:

[XxHuberrr/Mineradio](https://github.com/XxHuberrr/Mineradio)

## Current Status

- Current version: **1.1.3**
- macOS adaptation status:
  - Development and local runs on macOS are supported
  - Public installers currently target Apple Silicon Macs (arm64 / Apple M series)
  - Building macOS `.app`, `.dmg` and `.zip` artifacts is supported
  - Rhythm analysis cache, login cookies and the update download directory have been moved to the user data directory
  - Update assets are selected per platform; macOS prefers `latest-mac.yml` and `.dmg` / `.zip`
  - Windows-only Direct3D Chromium flags have been removed on macOS

## Support Scope

Current release installers are built and tested for Apple Silicon Macs first:

- **Apple Silicon:** arm64 installers are published, for M1 / M2 / M3 / M4 series Macs
- **Intel Mac:** not published as a formally supported platform. There are no plans to evaluate or publish x64 or Universal installers

If you are using an Intel Mac, please do not treat the current arm64 installer as a usable build. The project is unmaintained and no longer accepts new Issues or provides further compatibility verification.

## Core Features

- Open-Meteo weather radio: generates play queues from location, city and weather mood
- NetEase Cloud Music account, search, playlists, podcasts and lyrics
- QQ Music search, login state and supplementary audio sources
- Lyrics stage, custom lyrics, lyric positioning and visual controls
- Tempo-driven cinematic camera visual system
- Dedicated visual modes for long podcasts and DJ tracks
- Wallpaper galaxy home background and playback-state visual transitions
- Right-click to summon the 3D playlist shelf for browsing playlist queues
- GitHub Releases update detection and download entry point

## macOS Build

```bash
npm install
npm start
```

Build an unpacked `.app` for the current Mac architecture:

```bash
npm run build:mac:dir
```

Build `.dmg` and `.zip` for the current Mac architecture. Public releases currently use Apple Silicon / arm64 builds:

```bash
npm run build:mac
```

To build both Intel x64 and Apple Silicon arm64 artifacts:

```bash
npm run build:mac:all
```

> Note: `build:mac:all` only means the x64 build capability is preserved in the configuration — it does **not** mean Intel Macs are formally adapted or release-verified.

Without an Apple Developer ID configured, you can temporarily skip signing for local build verification:

```bash
CSC_IDENTITY_AUTO_DISCOVERY=false npm run build:mac
```

## Update Mechanism

Mineradio queries the GitHub Releases `latest` endpoint to detect new versions. The macOS build reads `latest-mac.yml` first and downloads the `.dmg` / `.zip` artifact matching the current platform.

To validate the update flow locally, point `MINERADIO_UPDATE_MANIFEST` at a local manifest JSON or an HTTP URL to simulate an online release.

## Third-Party Music Platforms

Mineradio macOS is not an official client of NetEase Cloud Music, QQ Music, Tencent Music Entertainment Group, or the original Mineradio project, and is not affiliated with any music platform.

The third-party platform integrations in this project are intended solely for personal learning, local client experience and playback assistance with the user's own account. Please comply with each platform's terms of service, copyright rules and membership benefit rules. This project does not provide, and will not provide, any capability to bypass payment, bypass membership, crack audio quality, or redistribute music content.

## User Data & Privacy

Login cookies, search history, custom covers, custom lyrics, rhythm analysis cache and similar data should only be stored in the local user data directory or browser local storage, and must never be committed to the repository.

See [PRIVACY.md](./PRIVACY.md) for details.

## Acknowledgements

Thanks to **XxHuberrr** for creating Mineradio and open-sourcing it under GPL-3.0. The macOS adaptation work in this repository builds on that foundation.

The co-creators, experience feedback contributors and release-preparation helpers listed in the upstream README provided an equally important foundation for the previous adaptation and maintenance of Mineradio.

## Copyright & License

Copyright (C) 2026 XxHuberrr.

Modifications in this repository were previously maintained by AkiZephyr and remain licensed under GPL-3.0. See [LICENSE](./LICENSE).

The MR logo, the Mineradio name, UI visual design and original visual expression belong to the original author; this repository uses those assets and the name only as an unofficial macOS adaptation. Third-party dependencies and third-party services are subject to their respective licenses and terms of service.
