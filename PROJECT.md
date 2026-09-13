# Listen

## Purpose

Listen is a minimal Android music app based on Lotus.

The goal is deliberately narrow:

> Keep Lotus as Lotus. Add two source tabs: YouTube and Radio.

Do not redesign Lotus, replace its player, add Spotify, or create a new audio engine.

## Product

Existing Lotus functionality remains intact.

New top-level sources:

- YouTube
- Radio

### YouTube

One combined input:

`Search YouTube or paste a link`

Search results are audio-focused. Do not present video playback UI.

Each result may show:

- thumbnail
- title
- channel/artist
- duration where available
- play
- Listen-local like

Listen-local playlists live entirely inside the app. They are not YouTube playlists and must never sync back to YouTube.

### Radio

Provide:

- station search
- station results
- playback
- Listen-local favorites
- useful browsing such as country/genre only if the chosen implementation already supports it cleanly

## Backup

Settings must provide Import and Export for all Listen-owned user data/settings, including:

- YouTube likes
- Listen playlists and their contents
- radio favorites
- Listen preferences
- other user-owned app data that is safe and meaningful to restore

Do not export credentials, cookies, secrets, or unnecessary device data.

Use a versioned backup format.

## Updates

Prefer automatic updates when they are genuinely simple and reliable.

Where Android or a dependency makes automatic updating inappropriate, provide a simple button to download the update and let the user install it manually.

Do not build a complicated package manager unless technical research proves it necessary.

## Core principles

1. Dead simple.
2. Reliable beats clever.
3. Reuse mature Android implementations.
4. Lotus remains the UI and main player.
5. No new audio engine.
6. No Spotify.
7. No unnecessary abstractions.
8. Do not silently expand scope.
9. Keep YouTube and Radio as source modules.
10. Document every important architectural decision.
