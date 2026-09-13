# AGENT INSTRUCTIONS — LISTEN

Read this file and the following before changing code:

1. PROJECT.md
2. SPEC.md
3. ARCHITECTURE.md
4. ROADMAP.md
5. DECISIONS.md
6. SOURCES.md
7. CHANGELOG.md

## Mission

Build Listen as a minimal Lotus-based Android music app with two additional sources:

- YouTube
- Radio

## Hard constraints

- Keep Lotus UI.
- Keep Lotus behavior unless a change is necessary for the new sources.
- No Spotify.
- No new audio engine.
- Reuse Lotus background playback.
- YouTube likes/playlists are Listen-local.
- Do not sync Listen playlists/likes to YouTube.
- Do not add video UI.
- YouTube tab uses one combined search/link input.
- Radio and YouTube should be source modules, not competing music players.
- Prefer mature existing open-source Android code over writing infrastructure.
- Prefer reliability and simplicity over feature count.
- Do not create a plugin system unless required.
- Do not add settings without a concrete user need.
- Do not silently expand scope.

## Working rules

Before modifying code:

- inspect the actual current repository
- inspect relevant dependency versions
- check licenses
- check existing data models and playback APIs
- make the smallest compatible change

Do not assume APIs from README files are still current.

When borrowing code:

- record source repository
- record revision/commit
- record license
- record what was used
- update SOURCES.md and LICENSES.md

## Phase discipline

Follow ROADMAP.md.

Do not jump to later phases because they look easy.

At the end of each meaningful step:

- update CHANGELOG.md with an ISO-8601 timestamp
- update ROADMAP.md
- record important decisions in DECISIONS.md
- leave the repository in a buildable state whenever practical

## If uncertain

Choose the smallest reliable solution.

If a feature requires a large new subsystem, stop and reassess against the hard constraints.

## Testing

Every new source must be tested with:

- normal playback
- pause/resume
- queue
- screen off
- background playback
- notification controls
- Bluetooth/headset controls
- network failure
- unavailable media
- app restart

Do not claim a test passed without actually running it.
