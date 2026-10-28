# Nightify

Nightify is an independently maintained music player for desktop, iPhone and Android by RealChroma.

[Download the latest version](https://github.com/RealChroma/Nightify-Releases/releases/latest) · [Website](https://nightify.vercel.app/) · [Report an issue](https://github.com/RealChroma/Nightify-Releases/issues)

## Desktop installers

| Platform | Downloads |
| --- | --- |
| Windows | x64 setup installer (.exe) |
| Linux | x64 AppImage and Debian/Ubuntu (.deb) |
| macOS | Apple Silicon (arm64) and Intel (x64), DMG and ZIP |

## iPhone

The native iPhone app is available through the Nightify source in AltStore Classic or SideStore.

**[Install Nightify on iPhone: setup, background refresh, VPN and updates](ios/INSTALL.md)**

Add this source once in AltStore/SideStore:

```text
https://raw.githubusercontent.com/RealChroma/Nightify-Releases/main/ios/apps.json
```

Use the source listing to install future Nightify versions. Signing refresh keeps an installed version valid; it is separate from installing an app update. iPhone releases use their own update channel.

## Android

The native Android app uses Nightify's existing visual design, mobile features and account/device services.

**[Download Android 0.1.4](https://github.com/RealChroma/Nightify-Releases/releases/tag/android-v0.1.4)** · **[Install on Android or Android Auto](android/INSTALL.md)**

Install the signed APK on Android 9 or newer. Version 0.1.4 corrects song artist credits and matches album rows to the right song recording. The app checks for future Android releases and offers a download/install action. Android Auto's media service is included; compatibility with a particular phone and head unit still requires testing. Android releases have their own update channel.

## Connect devices

Open the existing **Connect devices** menu and tap a device on your Wi-Fi/Ethernet network. Nearby devices connect automatically. Use **Use as a speaker without signing in** for a receiver without a Nightify account. **Settings → Playback** contains Nearby connections and desktop-only Game radio.

[Local connections and offline playback](LOCAL_CONNECT.md) · [Desktop game-radio setup](game-radio/README.md)

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
