# Nightify

Nightify is an independently maintained music player for desktop, iPhone and Android by RealChroma.

[Desktop downloads](https://github.com/RealChroma/Nightify-Releases/releases/latest) · [iPhone releases](https://github.com/RealChroma/Nightify-Releases/releases?q=iPhone&expanded=true) · [Android releases](https://github.com/RealChroma/Nightify-Releases/releases?q=Android&expanded=true) · [Website](https://nightify.vercel.app/) · [Report an issue](https://github.com/RealChroma/Nightify-Releases/issues)

## Desktop installers

| Platform | Downloads |
| --- | --- |
| Windows | x64 setup installer (.exe) |
| Linux | x64 AppImage and Debian/Ubuntu (.deb) |
| macOS 13 or newer | Apple Silicon (arm64) and Intel (x64), DMG and ZIP |

Desktop 0.4.2 fixes game-radio startup and repeated stop/start. It includes whole-playlist shuffle from any selected song, updated fullscreen lyrics, artist navigation, settings/storage controls and global playback shortcuts.

## iPhone

The native iPhone app is available through the Nightify source in AltStore Classic or SideStore.

**[Install Nightify on iPhone: setup, background refresh, VPN and updates](ios/INSTALL.md)**

Add this source once in AltStore/SideStore:

```text
https://raw.githubusercontent.com/RealChroma/Nightify-Releases/main/ios/apps.json
```

Use the source listing to install future Nightify versions. Signing refresh keeps an installed version valid; it is separate from installing an app update. iPhone releases use their own update channel.

[Browse iPhone release notes and IPA downloads](https://github.com/RealChroma/Nightify-Releases/releases?q=iPhone&expanded=true).

## Android

The native Android app uses Nightify's existing visual design, mobile features and account/device services.

**[Download the Android APK](https://github.com/RealChroma/Nightify-Releases/releases?q=Android&expanded=true)** · **[Install on Android or Android Auto](android/INSTALL.md)**

Install the signed APK on Android 9 or newer. Nightify checks for Android updates and offers an install action when a new version is available. Android Auto's media service is included. Compatibility varies by phone and head unit.

## Connect devices

Open the existing **Connect devices** menu and tap a device on your Wi-Fi/Ethernet network. Nearby devices connect automatically. Use **Use as a speaker without signing in** for a receiver without a Nightify account. **Settings → Playback** contains Nearby connections and desktop-only Game radio.

[Local connections and offline playback](LOCAL_CONNECT.md) · [Desktop game-radio setup](game-radio/README.md)

## Features

- Nightify accounts, synced library and playlists.
- Music search, artist pages, synced lyrics and playlist imports.
- Live now-playing rankings from Nightify listeners who opt into public activity and leaderboards.
- All-time listening charts, personal listening history and daily mixes.
- Thirteen Nightify branding choices, including the default and twelve accent logos.
- Updated desktop sign-in, settings navigation, collection pages and fullscreen player.
- Storage controls for cached music, saved liked songs and imported files.
- Combined YouTube and SoundCloud search, plus lyrics retained for offline listening.

Live charts refresh every 15 seconds. Active playback updates every 25 seconds, and disconnected listeners expire after 90 seconds. Rankings come from Nightify listeners who enable sharing.

## Releases and verification

Installers are published under [Releases](https://github.com/RealChroma/Nightify-Releases/releases). Each release includes SHA-256 checksums. Windows builds do not have a trusted publisher certificate, and macOS builds are not Apple-notarized.

From 0.3.2 onward, installed apps check for stable updates at startup and from About. Windows and Linux AppImage builds download updates in the app and offer an explicit restart and install action. macOS and Debian builds open the public release page for manual installation. Update-check failures display an error.

If you are running 0.3.0 or 0.3.1, install the latest version manually once to enable future update checks.

This repository distributes installers, release notes and issue reports. Nightify's development repository remains private. Applicable software license terms are included in LICENSE and the packaged application.
