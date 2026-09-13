# Listen Product Specification

## 1. Base application

Fork Lotus and preserve its existing behavior and UI.

Lotus currently provides local music playback, library browsing, playlists, lyrics, Material You styling, and background playback.

The first engineering task is to verify the current Lotus revision and its playback architecture before modifying it.

## 2. YouTube tab

### Input

Use one input field with dual behavior:

`Search YouTube or paste a link`

- Normal text -> YouTube search.
- Recognized YouTube URL -> resolve/play the linked item.
- Do not make users choose between separate Search and URL fields.

### Results

Audio-first presentation only.

A result should contain:

- thumbnail
- title
- creator/channel
- duration if available
- play action
- local Like action
- add-to-Listen-playlist action

Do not expose a video player.

### Local likes

Likes belong to Listen.

They are NOT:

- YouTube Likes
- a YouTube account playlist
- synced to YouTube
- visible in normal YouTube

The user can browse their Listen likes inside the YouTube tab.

### Local playlists

All Listen playlists are app-local.

Required operations:

- create
- rename
- delete
- add item
- remove item
- reorder where practical
- play playlist

Playlist records should store stable source identifiers/URLs plus enough metadata to render the item.

## 3. Radio tab

Use a mature Android implementation backed by Radio Browser where practical.

Required:

- search stations
- show station name
- show favicon when available
- play
- local favorite
- browse useful categories only if they improve simplicity

Do not add a new audio engine. Reuse the existing Lotus playback path if technically practical; otherwise adapt the radio source into the existing Android media/playback layer rather than creating a parallel player architecture.

## 4. Shared playback

Lotus already has background playback. Preserve and reuse it.

Before implementation, verify:

- background playback
- notification controls
- lock-screen controls
- audio focus
- headset/Bluetooth controls
- queue behavior

Do not add a second playback engine unless a concrete Lotus limitation makes it unavoidable.

## 5. Backup

Settings -> Backup

Actions:

- Export Listen backup
- Import Listen backup

Backup should be a versioned, portable file.

Suggested logical contents:

- schema version
- app-owned settings
- YouTube local likes
- Listen playlists
- radio favorites
- other app-owned preferences/data

Never include:

- passwords
- authentication tokens
- browser cookies
- private credentials

Import must validate schema and fail safely.

## 6. Updates

Settings -> Updates

Preferred behavior:

- automatic update for ordinary app releases when a normal Android distribution mechanism supports it
- otherwise a clear Check for updates button
- manual download/install for components that cannot safely update themselves

Do not create arbitrary executable-code downloading.

Any downloaded component must have a clear provenance and integrity check.

## 7. Non-goals

Explicitly out of scope:

- Spotify
- redesigning Lotus
- replacing Lotus player
- a CLIAMP Android port
- a new audio engine
- YouTube account playlist synchronization
- YouTube Likes synchronization
- video playback UI
- a large plugin ecosystem
- unnecessary settings
