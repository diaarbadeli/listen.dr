# Listen Roadmap

## Phase 0 — Research and baseline

- [ ] Confirm current Lotus branch/revision
- [ ] Build unmodified Lotus
- [ ] Record Android/Gradle/Kotlin/Compose versions
- [ ] Map Lotus playback architecture
- [ ] Map Lotus persistence/data layer
- [ ] Inspect YouTube candidates at source level
- [ ] Inspect Radio candidate at source level
- [ ] Verify licenses
- [ ] Choose exact implementation approach
- [ ] Update ARCHITECTURE.md and SOURCES.md

## Phase 1 — Lotus baseline

- [ ] Fork Lotus
- [ ] Build debug APK
- [ ] Install on test device
- [ ] Confirm existing behavior unchanged
- [ ] Tag baseline

## Phase 2 — Radio

- [ ] Add Radio tab
- [ ] Add station search
- [ ] Add station results
- [ ] Add playback through existing playback architecture
- [ ] Add local favorites
- [ ] Test background playback
- [ ] Test screen-off playback
- [ ] Test Bluetooth/headset controls
- [ ] Tag milestone

## Phase 3 — YouTube foundation

- [ ] Choose implementation
- [ ] Add source module
- [ ] Add search
- [ ] Add unified search/link input
- [ ] Resolve audio-only stream
- [ ] Render thumbnails/metadata
- [ ] Feed existing Lotus playback
- [ ] Test failures and unavailable videos

## Phase 4 — Listen YouTube library

- [ ] Local likes
- [ ] Local playlists
- [ ] Create/rename/delete playlists
- [ ] Add/remove/reorder
- [ ] Play playlist
- [ ] Ensure no YouTube playlist/account synchronization

## Phase 5 — Backup

- [ ] Versioned backup schema
- [ ] Export
- [ ] Import
- [ ] Validation
- [ ] Migration strategy
- [ ] Corrupt/incompatible backup handling

## Phase 6 — Updates

- [ ] Determine which updates can be automatic
- [ ] Implement only the minimum required
- [ ] Add manual update path where necessary
- [ ] Verify integrity/provenance
- [ ] Test rollback/failure path

## Phase 7 — Release

- [ ] Full regression test
- [ ] Test on target phone
- [ ] Test clean install
- [ ] Test upgrade
- [ ] Test backup restore
- [ ] Build release APK/AAB
- [ ] Publish GitHub release
- [ ] Document release
