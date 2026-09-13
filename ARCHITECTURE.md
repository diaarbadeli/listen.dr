# Listen Architecture

## Target architecture

```text
Listen (Lotus fork)
|
+-- Existing Lotus UI
|   +-- existing library/tabs
|   +-- existing player UI
|   +-- existing playlists
|   +-- existing background playback
|
+-- YouTube Source
|   +-- unified search/link input
|   +-- YouTube/YouTube Music discovery
|   +-- audio-only media resolution
|   +-- thumbnails/metadata
|   +-- Listen-local likes
|   +-- Listen-local playlists
|
+-- Radio Source
|   +-- Radio Browser discovery
|   +-- station metadata
|   +-- stream URLs
|   +-- Listen-local favorites
|
+-- Backup
|
+-- Update handling
```

## Key architectural rule

Sources produce media items for the existing playback system.

Do not create a second audio engine.

## Candidate source implementations

### YouTube

Current research found mature Material 3 Android clients such as InnerTune and Metrolist. They demonstrate YouTube Music search, background playback and ad-free streaming.

Metrolist is currently in maintenance mode, so do not blindly fork it for new features.

InnerTune is GPL-3.0 and has the relevant feature set, but its latest listed stable release is old. Treat it as an implementation reference/source of reusable code only after checking the current repository and license compatibility.

Another option is an Android yt-dlp wrapper. The current `ffmpegkit-maintained/yt-dlp-android` project provides a Java API and bundles yt-dlp through Chaquopy, but its documentation states that yt-dlp is not updateable in-app; updating requires a new library release. It also has a large AAR footprint.

Therefore the implementation choice must be made after a code-level inspection of the current Lotus and candidate projects.

### Radio

`Praeterii/Radio` is a small GPL-3.0 Android radio app using:

- Jetpack Compose
- Material 3
- Media3/ExoPlayer
- MediaSessionService
- Radio Browser API
- Coil

It is a useful reference for the Radio source. Do not copy code until license and architectural compatibility are checked.

## Why not CLIAMP

CLIAMP is a desktop-oriented Go/TUI application. It is not needed for Listen.

The original idea of embedding CLIAMP would add unnecessary complexity. Mature Android YouTube and Radio implementations are a better fit.

## Playback rule

The source layer should hand the existing Lotus playback system a playable media item.

If the current Lotus playback architecture cannot represent a stream source, make the smallest possible adaptation to the existing playback system. Do not introduce a parallel player.

## Data ownership

Listen owns:

- local likes
- local playlists
- radio favorites
- Listen settings

YouTube owns none of these.

Nothing should sync to normal YouTube unless a future scope change explicitly says so.
