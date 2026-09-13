# YouTube Implementation Notes

## Required behavior

One field:

`Search YouTube or paste a link`

Search:
- return audio-oriented results
- thumbnail
- title
- creator
- duration when available

URL:
- recognize supported YouTube URLs
- resolve the media
- play audio only

## Local data

Listen stores likes and playlists locally.

No YouTube account synchronization is required.

## Candidate technology

Current research shows that InnerTune and Metrolist already implement the difficult YouTube Music side, including search, background playback and ad-free playback.

The project must inspect their current source before choosing what to reuse.

An Android yt-dlp wrapper is a fallback/reference, but the currently researched `yt-dlp-android` bundles a fixed yt-dlp version and does not support in-app yt-dlp updates.

## Reliability rule

YouTube extraction is the highest-risk subsystem.

Prefer a maintained Android-native implementation with a clean media URL/output interface.

Do not duplicate a complete YouTube client inside Listen.

## Security/privacy

Do not require Google/YouTube login for the required local Listen functionality.

Do not store browser cookies in Listen backups.
