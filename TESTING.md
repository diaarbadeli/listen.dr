# Testing

## Baseline

Before changes:

- build Lotus
- install it
- confirm existing local playback
- confirm playlists
- confirm background playback
- confirm notification controls

## Radio

Test:

- search
- station with direct stream
- station with HLS if supported
- play/pause
- stop
- background
- screen off
- notification
- Bluetooth/headset
- favorite
- app restart
- bad/dead station
- network unavailable

## YouTube

Test:

- normal search
- empty search
- pasted YouTube URL
- invalid URL
- unavailable video
- audio-only playback
- thumbnail
- play/pause
- background
- screen off
- notification
- Bluetooth/headset
- like
- unlike
- add to playlist
- remove from playlist
- playlist playback
- app restart
- network failure

## Backup

Test:

- export empty profile
- export populated profile
- import on same install
- import after clean install
- duplicate import
- invalid file
- older schema
- newer unsupported schema
- missing optional fields

## Regression

Local Lotus music must continue working.

Do not accept a source integration that breaks existing Lotus behavior.
