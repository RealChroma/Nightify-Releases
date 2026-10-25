# Nightify desktop game radio

In the desktop app, open **Settings → Playback → Desktop game radio → Enable game radio**. Play a track, then copy its stream URL. Only programs on the same computer can read it. Disable **Also play through desktop speakers** to avoid hearing both outputs.

The URL expires when game radio stops or Nightify exits. It is a local capability URL; do not put it in a shared configuration file. This feature is desktop-only. Phones use local paired playback, AirPlay or system wired/Bluetooth audio output.

## FH5/6 mod

The [matkhl mod](https://github.com/matkhl/FH6-Spotify-Radio) accepts a custom internet-radio URL. Select its radio source and paste the Nightify MP3 URL. The stream includes ICY song metadata when requested. Its game-specific hooks still depend on the installed game/mod version; Nightify's loopback stream test does not establish an in-game result.

## FH2 source adapter

The [FH2 mod](https://github.com/Bullet4fun/FH2_ModsCollection/tree/main/spotify-radio) starts a child process whose standard output supplies stereo signed 16-bit PCM at 44.1 kHz. It sends `next`, `prev` and `playpause` lines to that child's standard input and reads UTF-16LE song information from `nowplaying.txt`.

`nightify-radio-client.c` implements those inputs/outputs using Nightify's local radio service, without a Spotify account. It is original adapter code; the mod itself remains a separate project.

Download [Nightify Game Radio Adapter 0.3.7](https://github.com/RealChroma/Nightify-Releases/releases/download/v0.3.7/Nightify-Game-Radio-Adapter-0.3.7.zip). It includes the Windows adapter, original C source, guide and license. Extract it to a new folder.

In your own FH2 mod source checkout, change the two `librespot.exe` executable-name references in `spotify-radio/spotify_bridge.c` to `NightifyRadio.exe`, then rebuild the mod using its own instructions. The old command-line options can remain; this adapter ignores them. Preserve the original mod files separately.

Place `NightifyRadio.exe` in that rebuilt mod's own working folder. In the same folder, create `nightify-radio-url.txt` containing the stream URL copied from Nightify, on one line. Start Nightify's game radio before starting the game. Updating the URL file takes effect when the adapter restarts.

This source integration needs acceptance in the actual game. The adapter can be checked without the game: run it from that folder, capture stdout as PCM, inspect `nowplaying.txt`, and send its three control lines on stdin. No existing Spotify credentials need to be changed or shared.

## Other integrations

The same key query parameter authorizes these loopback endpoints:

| Endpoint | Response |
| --- | --- |
| `GET /live.mp3` | MP3 audio; optional ICY metadata |
| `GET /live.pcm` | Raw signed little-endian PCM, stereo, 44,100 Hz |
| `GET /live.wav` | Live WAV wrapper around the same PCM |
| `GET /now-playing` | Current recording, position, playing/loading state |
| `GET /now-playing.txt` | Title and artist lines in UTF-16LE |
| `POST /control` | JSON action: play, pause, toggle, next, previous, seek or volume |

Seek values are milliseconds; volume is 0–1. A local integration should stop or reconnect when the radio service closes. Slow consumers are disconnected to keep Nightify's audio thread responsive.
