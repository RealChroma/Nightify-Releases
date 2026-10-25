# Local playback connections

Open **Connect devices** and tap an available device. Nightify discovers compatible receivers on the same Wi-Fi/Ethernet network and establishes the encrypted session automatically, without a pairing code or receiver address form. Receivers can also start from **Use as a speaker without signing in**. **Settings → Playback → Nearby connections** controls whether other devices on the local network can play here.

Use the same reachable Wi-Fi/Ethernet network and allow local-network access. Discovery uses `_nightify._tcp` DNS-SD and the v2 local protocol. Public hosts, credentialed URLs and redirects are rejected. Keep the receiving mobile app open for discovery/new connections; iOS does not guarantee a suspended app can accept a new connection. Code-free nearby access is limited to devices on the local network while Nearby connections is enabled; it does not transfer account credentials.

Tap the destination device. The destination resolves the selected catalog recording and confirms playback before the sender pauses. The sender's player controls then control that destination. **Play here instead** returns playback to the sender. Account-based connections remain available separately for the same Nightify account.

Local pairing does not share account tokens, libraries or a provider login. It transfers catalog song IDs, queue and position; the receiver plays using its own compatible catalog stream. Both devices still need internet for an online recording. Local imports and source-only downloads are not copied through this control protocol. They can be played through system wired/Bluetooth audio or, on iPhone, AirPlay. A USB data/charging cable alone does not turn a PC into a phone's audio receiver.

For game mods use the **desktop-only** radio bridge described in [desktop game-radio guide](game-radio/README.md). It exports the actual desktop audio, including local files, rather than transferring catalog IDs. The FH5/6 mod can read its MP3 radio URL; the FH2 project can use the supplied PCM/metadata/control adapter with its own rebuilt source integration. Real game-version compatibility requires testing in the game.

## Poor connections and offline playback

Downloaded audio is played directly from the device. Local playback, Pause/Next and system media metadata are independent of library refresh and device polling. Library refresh failures retain saved likes, playlists and recent tracks. Pause works while a stream is buffering. iPhone playback progress has its own observable timeline so it does not redraw the entire library on every tick. Android queue persistence and photo conversion run away from the main thread.

An unreachable device cannot receive current playback state. Account connections show reconnecting/offline state; they update when communication returns. Streaming an uncached song still needs a working connection. A provider's real age-verification restriction needs that provider's supported verification route; signing into Nightify alone does not verify a provider account. The app explains this and offers another available recording or local import.

## Verification

Local protocol tests cover automatic key agreement, malformed-handshake rate limiting, encrypted messages/tampering, replay rejection, private address validation, guest operation and disconnecting. UI checks assert a current-output card, tappable device rows and no setup forms or social features. Desktop, Kotlin and Swift use a shared P-256/HKDF/AES-GCM test vector. Radio tests decode MP3 and run the Windows PCM adapter with song text and stdin controls. Simulator/emulator checks cover native playback, photo-picker opening and Android system-session state. These checks supplement physical phone, router, Bluetooth/USB hardware and actual-game acceptance.
