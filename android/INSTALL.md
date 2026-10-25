# Install Nightify on Android

Nightify is available as a standalone Android app. Use this guide to install it, receive updates and set up Android Auto.

## Install

[Download Nightify for Android](https://github.com/RealChroma/Nightify-Releases/releases/tag/android-v0.1.3). Choose `Nightify-Android-0.1.3.apk` from Assets.

1. Use an Android 9 or newer phone. Download the **Nightify-Android-0.1.3.apk** release package supplied by the Nightify owner. A `.sha256` file accompanies it for verification.
2. Open the APK. If prompted, allow **Install unknown apps** for the browser or Files app used to open it, then confirm installation.
3. Open **Nightify** and sign in or create a Nightify account. Use the same Nightify account on your desktop/iPhone to test device continuation. A new account password needs at least 15 characters.
4. Allow Nightify notifications if you want to see download progress. The app needs internet access for sign-in, search and streaming. Already downloaded/imported audio can play offline.

No Apple Account, local VPN or weekly signing refresh is needed. Future signed APKs use the same app identity/key so you can update in place; do not uninstall first. Android may present extra developer-verification steps depending on the phone and region. [Google's current installation rules](https://developer.android.com/developer-verification)

## Nearby playback

Open **Connect devices** on the sending app and tap a device. Nightify discovers receivers on the same Wi-Fi/Ethernet network and connects without entering a code. A receiver can also start from **Use as a speaker without signing in** on its sign-in screen. Allow local-network access and keep the mobile receiver open for new connections.

**Play here** returns playback to the sender. Online songs still need internet on the receiver. Source-only files are not copied. Wired headphones/USB audio and Bluetooth use Android's system output. Game-radio integration is desktop-only and is configured under desktop **Settings → Playback**. Disable **Nearby connections** in Settings to stop other devices on your local network from connecting.

## Test the phone app

| Check | What to try |
| --- | --- |
| Account and library | Sign in, close/reopen Nightify, check the same likes/playlists as desktop. |
| Search | Search a familiar title and try Songs, Artists, Albums and Playlists. Open the matching result. |
| Playback | Play several recordings, seek, queue another song, use Play next, shuffle/repeat, pause/resume. |
| Background audio | Lock the screen for several minutes and use notification/headphone/Bluetooth controls. Try a phone-call interruption and reconnecting headphones. |
| Lyrics | Open Now playing → Lyrics, try a timed song, seek by tapping a line and adjust the timing offset. Lyrics depend on the recording and available providers. |
| Downloads | Download a song and a playlist, try cancellation, then enable airplane mode and play the saved songs. Restart the app and repeat. |
| Local imports | Library → Import audio. Import your own audio file, then confirm Remove downloaded songs preserves it. |
| Sharing and artwork | Share a song and a public playlist. Check private-playlist publication asks first. Change/reset an owned playlist thumbnail and check it on desktop. |
| Device switching | With both apps open, move playback desktop → Android → iPhone and back, checking the song, position and queue. Try repeated switching; a failed transfer should leave the source playing. |
| Layout | Scroll to the final row above the mini-player, try light/dark mode and a larger text size. |

A provider may reject a particular recording or network. Include the exact song and error text when reporting this; do not treat a successful local-file playback as proof that all online streams work.

## Test Android Auto

Use a compatible car while parked. Sign into Nightify on the phone first.

1. Open **Android Auto settings** on the phone.
2. Find the version information and tap it ten times to enable Android Auto's developer mode. Confirm the prompt.
3. Open its developer settings from the menu and enable **Unknown sources** for sideloaded media testing.
4. Connect the phone to the car using its supported USB or wireless Android Auto connection.
5. Check Nightify appears, then browse Liked songs/Downloads/Recently played/Playlists. Test playback, artwork, pause/next/previous and steering-wheel controls. Test voice search if available.

Android Auto's dashboard uses its own media layout. Phone screens and scrolling lyrics are not mirrored into the driving interface. Android Auto support is included; compatibility with a particular phone/head unit should be checked while parked. [Google's official sideloaded-media testing instructions](https://developer.android.com/training/cars/testing#unknown-sources)

## Updates

Use **Nightify → Settings → Updates → Check for updates**. The app also checks periodically when opened. When a compatible release is published, select Download update, allow Nightify's **Install unknown apps** permission if requested, and confirm Android's installer. Download verification checks the APK size, SHA-256, app ID/version and signing certificate before opening the installer.

The update feed only advertises published versions; automatic checks are separate from Android's installation confirmation. Android asks you to confirm installation of each downloaded update.

## Report results

Send the Nightify owner the phone model, Android version, Nightify version, exact steps and error text. For Android Auto, also include the car/head-unit model and whether USB or wireless was used. Report phone playback, device continuation and car playback as separate checks. Never include passwords, account tokens or other people's private playlists.
