# Nightify

Nightify is an independently maintained **desktop-first music player** by RealChroma.

[Download the latest version](https://github.com/RealChroma/Nightify-Releases/releases/latest) · [Website](https://nightify.vercel.app/) · [Report an issue](https://github.com/RealChroma/Nightify-Releases/issues)

## Desktop installers

| Platform | Downloads |
| --- | --- |
| Windows | x64 setup installer (.exe) |
| Linux | x64 AppImage and Debian/Ubuntu (.deb) |
| macOS | Apple Silicon (arm64) and Intel (x64), DMG and ZIP |

**Android & iOS** support is planned as a Progressive Web App (PWA).

## Features

- Nightify accounts, synced library and playlists.
- Music search, artist pages, synced lyrics and playlist imports.
- Live now-playing rankings from Nightify listeners who opt into public activity and leaderboards.
- All-time listening charts, personal listening history and daily mixes.
- Thirteen Nightify branding choices, including the default and twelve accent logos.

Live charts refresh every 15 seconds. Active playback updates every 25 seconds, and disconnected listeners expire after 90 seconds. No Spotify or Liner popularity statistics are used by Nightify's charts.

## Releases and verification

Installers are published under [Releases](https://github.com/RealChroma/Nightify-Releases/releases). Each release includes SHA-256 checksums. Windows builds do not have a trusted publisher certificate, and macOS builds are not Apple-notarized.

From 0.3.2 onward, installed apps check for stable updates at startup and from About. Windows and Linux AppImage builds download updates in the app and offer an explicit restart and install action. macOS and Debian builds open the public release page for manual installation. Update-check failures display an error.

If you are running 0.3.0 or 0.3.1, install the latest version manually once to enable future update checks.

This repository distributes installers, release notes and issue reports. Nightify's development repository remains private. Applicable software license terms are included in LICENSE and the packaged application.
