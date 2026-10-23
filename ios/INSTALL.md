# Install Nightify on iPhone

Use this guide to install Nightify through **AltStore Classic**, receive future Nightify updates from its source, and enable automatic signing refresh. Instructions checked October 23, 2026.

## What you need

- An iPhone running **iOS 17.4 or later** for the current AltStore Classic. Nightify itself supports iOS 16+, but this guide uses the newer AltStore installation route.
- Your own Apple Account and access to its verification codes. A paid Apple Developer membership is not required for this setup.
- A Windows PC or Mac, a USB cable, and Wi-Fi for initial installation and pairing.
- [LocalDevVPN from the App Store](https://apps.apple.com/us/app/localdevvpn/id6755608044).

Your Apple Account signs the app; your **Nightify account** signs you into your music library. These are separate accounts. Enter Apple credentials only in the official AltStore/AltServer prompts. Do not exchange passwords, verification codes, or pairing files with friends.

## 1. Install AltStore Classic

Follow the official instructions for your computer:

- [Windows installation](https://faq.altstore.io/altstore-classic/how-to-install-altstore-windows). This includes the required Apple iTunes/iCloud components and Wi-Fi sync setup. Follow its instructions if you already use the Microsoft Store iCloud version.
- [Mac installation](https://faq.altstore.io/altstore-classic/how-to-install-altstore-macos). Pair the iPhone and enable its Finder Wi-Fi visibility as instructed.

In either case, connect and unlock the iPhone, trust the computer, then use **AltServer → Install AltStore → your iPhone**. Sign in using your own Apple Account and complete verification. On the iPhone, trust the developer profile under **Settings → General → VPN & Device Management** if requested. Enable **Settings → Privacy & Security → Developer Mode**, restart, and confirm when prompted.

Open AltStore Classic. Use the current official version; version 2.3.1 includes recent signing and background-refresh fixes. [AltStore release notes](https://faq.altstore.io/release-notes/altstore)

## 2. Set up Remote AltServer

1. In **AltStore → Settings**, tap **Set up Remote AltServer…**.
2. Complete its computer-pairing instructions. Keep the computer available until setup finishes.
3. Install and open **LocalDevVPN**, approve its VPN configuration, and connect it.
4. Connect the iPhone to **Wi-Fi**. Remote AltServer currently requires Wi-Fi rather than a cellular-only connection.
5. Enable **Prefer Remote AltServer** if that switch is shown.

After successful setup, your own computer does not need to stay on for Remote AltServer installations or signing refreshes. The selected remote service still needs to be available. [Official Remote AltServer guide](https://faq.altstore.io/altstore-classic/remote-altservers)

## 3. Add Nightify and install it

In AltStore's **Sources** screen (normally under Browse), choose **+ / Add Source** and paste:

```text
https://raw.githubusercontent.com/RealChroma/Nightify-Releases/main/ios/apps.json
```

Confirm the source is **Nightify**, by **RealChroma**. Open the Nightify listing and tap its install button. Keep Wi-Fi and LocalDevVPN connected until installation finishes; complete any Apple sign-in or verification prompt.

Open **Nightify** and sign in or create a Nightify account. To use your existing desktop library and playback continuation, use the same Nightify account on both devices.

The source URL stays the same for future releases. [Nightify releases](https://github.com/RealChroma/Nightify-Releases/releases)

## 4. Enable background signing refresh

1. In **AltStore → Settings**, enable **Background Refresh**.
2. In **iPhone Settings → General → Background App Refresh**, enable the system feature and allow **AltStore**. A Wi-Fi setting is sufficient for the Remote AltServer route.
3. Allow AltStore notifications so refresh failures and available updates are visible.
4. With Wi-Fi and LocalDevVPN connected, open **AltStore → My Apps → Refresh All** once. Confirm that both AltStore and Nightify refresh successfully.

With a free Apple Account, installed apps normally expire after **7 days**. AltStore attempts to renew signing in the background, including its own installation. iOS decides when background work runs, so automatic renewal is not guaranteed. Check My Apps every few days and refresh manually while days remain. AltStore also counts toward the usual three active sideloaded-app limit. [AltStore background refresh and account limits](https://faq.altstore.io/altstore-classic/your-altstore)

Low Power Mode disables iOS Background App Refresh. Turn it off when troubleshooting unattended refresh. After a restart, reopen AltStore and confirm LocalDevVPN is connected. Avoid routinely force-quitting AltStore if you want background work to run. [Apple's Low Power Mode explanation](https://support.apple.com/en-us/101604), [Apple's background-app guidance](https://support.apple.com/en-us/118408)

## Does LocalDevVPN need to stay on 24/7?

**Nightify does not need the tunnel to play music.** AltStore's remote installation/signing route needs it while doing those operations.

| What you want to do | LocalDevVPN needed? |
| --- | --- |
| Play music in Nightify, including with the screen locked | No |
| Install, update, or manually refresh through Remote AltServer | Yes, with Wi-Fi |
| Let AltStore refresh signing without opening it yourself | Leave it connected so it is available when iOS schedules the refresh |

If you turn the tunnel off between uses, reconnect it and manually refresh before the apps expire. Leaving it connected is the simplest option for unattended refresh; it is not needed every second to keep an already signed app running. This recommendation follows from the remote route's connection requirements and iOS's unpredictable scheduling.

LocalDevVPN creates a local device tunnel. It does not route your normal internet traffic through a commercial VPN provider or hide your IP address. Remote AltServer and Apple authentication still use internet services. [LocalDevVPN project](https://github.com/jkcoxson/LocalDevVPN)

## How Nightify updates work

When a new tested Nightify build is published and added to this source, AltStore detects the new version and can notify you. Open **My Apps** and tap **Update** for Nightify. Keep the same Apple signing account and update the existing app to retain its data.

**Signing refresh** extends the installed app's validity. **Update** installs a newer Nightify version. Enabling background signing refresh does not mean new Nightify versions silently install. You do not need to add the source again or manually find a new IPA. [AltStore update documentation](https://faq.altstore.io/developers/updating-apps)

## If installation or refresh fails

**AppleDeveloperError 3000 / Apple's authentication servers returned HTTP 503:**

1. Go to **AltStore → Settings → Remote AltServer → Choose Server**.
2. Select another available server, confirm **Wi-Fi + LocalDevVPN** are connected, and retry once.
3. If necessary, restart the iPhone, reconnect the tunnel, and retry later. Check that AltStore is current.

Changing the server resolved the Nightify installation reported by our tester. It is a workaround, not a universal fix: the same authentication failure has been reported with current AltStore releases. [Official remote-server troubleshooting](https://faq.altstore.io/altstore-classic/remote-altservers), [matching authentication report](https://github.com/altstoreio/AltStore/issues/1842)

**Cannot reach Remote AltServer:** check Wi-Fi and the tunnel, then try another server. If you choose to use your computer's AltServer instead, disable Prefer Remote AltServer, run AltServer on that computer, and connect the iPhone by USB for troubleshooting.

**AltStore itself has expired and will not open:** reinstall AltStore in place with your computer's AltServer and the same Apple Account. Do not delete it first. Once it opens, refresh Nightify. [Official recovery instructions](https://faq.altstore.io/altstore-classic/altserver)

For a Nightify playback or account problem after installation, [report it here](https://github.com/RealChroma/Nightify-Releases/issues). Include the Nightify version, iOS version, and exact error text; omit credentials and pairing material.
