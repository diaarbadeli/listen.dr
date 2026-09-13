# Sources and Research

This file records candidate projects and research. Exact code reuse must record a commit/revision before implementation.

## Lotus

Repository:
https://github.com/dn0ne/lotus

License:
GPL-3.0

Role:
Base application.

Relevant features documented by its README:

- Android music player
- local formats
- tracks/albums/artists/genres
- custom playlists
- lyrics
- Material You
- GitHub/F-Droid releases

## InnerTune

Repository:
https://github.com/z-huang/innertune

License:
GPL-3.0

Role:
YouTube Music implementation reference.

Relevant documented features:

- YouTube/YT Music playback
- no ads
- background playback
- search
- playlists
- Material 3

Caution:
Its listed stable release is old. Inspect current source before reuse.

## Metrolist

Repository:
https://github.com/MetrolistGroup/Metrolist

License:
Inspect current repository license before code reuse.

Role:
YouTube Music implementation reference.

Relevant documented features:

- YouTube Music streaming
- background playback
- local playlists
- search
- Material 3

Caution:
Repository currently says it is in maintenance mode.

## OuterTune

Repository:
https://github.com/OuterTune/OuterTune

Role:
Additional YouTube Music/local-player architectural reference.

Caution:
Repository currently says it is no longer actively developed.

## Radio

Repository:
https://github.com/Praeterii/Radio

License:
GPL-3.0

Role:
Radio Browser + Android Media3 reference.

Relevant documented features:

- Compose
- Material 3
- Radio Browser
- Media3/ExoPlayer
- MediaSessionService
- background playback
- HLS
- Coil

## yt-dlp-android

Repository:
https://github.com/ffmpegkit-maintained/yt-dlp-android

License:
MIT

Role:
Potential YouTube extraction fallback/reference.

Important current limitation:
yt-dlp is bundled into the AAR and cannot be updated in-app; updating requires a new library version.

The library documentation also states that the AAR is large because it embeds CPython through Chaquopy.

## youtubedl-android

Repository:
https://github.com/yausername/youtubedl-android

Role:
Alternative Android yt-dlp wrapper/reference.

Inspect maintenance status and current compatibility before selecting it.

## Selection rule

Do not select a source solely because it has the most features.

Select the smallest maintained implementation that:

- works with current Android/Gradle
- can feed Lotus's existing playback architecture
- supports required YouTube search/link/audio behavior
- has compatible licensing
- is maintainable
