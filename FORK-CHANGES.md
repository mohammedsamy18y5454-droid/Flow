# Flow (fork by Mohammed Samy)

This is a fork of [Flow](https://github.com/Flow-Tube/Flow) v3.0.5 by A-EDev and the Flow contributors.
All credit for the app goes to them. Please go check out and support the original project.

This fork adds features for casting to **old TVs** (tested target: Samsung LA32D550, 2011).
The changes were written with help from Claude (an AI assistant) and have only been tested through GitHub builds.

## What this fork adds

### Casting
- **Legacy codec compatibility mode** (Settings > Casting). Casts only H.264 video and AAC audio and never AV1, VP9, HEVC or HLS playlists, which old TVs reject with "file format not supported".
- **MP4 builder.** When YouTube has no ready-made MP4, Flow downloads the video and audio streams and joins them into one plain MP4 on the phone, without re-encoding. The index is moved to the front of the file so old TVs can start playing.
- **Quality for casting** (Settings > Casting). Choose 360p, 480p or 720p for the MP4 Flow builds. Lower is ready sooner.
- **Progress card.** A Material 3 card at the bottom of the app and a notification show percent done, time left and a Cancel button while the MP4 is built.
- **Forbid casting** (Settings > Casting). Turns casting off completely: no device search, no pickers, nothing is sent to a TV.
- **Send to TV button for music.** The music player's top bar always shows a cast icon, not only while casting.

### Other
- A credit line at the bottom of Settings with links to Flow, its creator and this fork.

## Known limits
- Not compiled or tested on a real TV by the author of the patch; it may need fixes.
- Building the MP4 means waiting before playback starts. Longer videos wait longer.
- Subtitles are not supported when casting.
- Music casting depends on the TV supporting the audio format.

## How this fork is built
The changes live in `Flow-patch-v3.0.5.zip`. The GitHub Action in `.github/workflows/build-patched.yml`
downloads Flow v3.0.5, applies the patch and builds a debug APK (**Actions > Build patched APK > Run workflow**).

## License
Flow is licensed under the GNU GPL v3, and so are the changes in this fork.
See the `License` file of the original project.
