# Decisions

## 2026-09-13

### Use Lotus as the base

Decision:
Fork Lotus rather than merge two complete applications.

Reason:
The user wants Lotus to remain visually and behaviorally intact.

Rejected:
- new standalone player
- full CLIAMP Android port
- major UI rewrite

### No CLIAMP

Decision:
Do not port CLIAMP into Android.

Reason:
CLIAMP is desktop-oriented and would introduce unnecessary Go/TUI/audio architecture into an Android app. Existing Android YouTube and Radio projects are better starting points.

### No Spotify

Decision:
Spotify is permanently out of the current scope.

### No new audio engine

Decision:
Use Lotus's existing playback/background infrastructure.

### YouTube-local library

Decision:
Likes and playlists belong to Listen only.

They must not become YouTube Likes or YouTube account playlists.

### Unified YouTube input

Decision:
One input accepts both searches and pasted YouTube links.

### Audio-only results

Decision:
The YouTube tab presents audio-oriented results. No video playback UI.

### Minimal updates

Decision:
Prefer ordinary app/dependency updates where safe. Only add a user-facing manual update mechanism when necessary.

### Backup

Decision:
Listen-owned settings and user data must be exportable/importable in a versioned format.
