# Radio Implementation Notes

## Preferred source

Radio Browser is the preferred discovery source.

A small existing Android reference is:

https://github.com/Praeterii/Radio

It uses Compose, Material 3, Media3, MediaSessionService, Radio Browser and Coil.

Another candidate is radioMii; inspect it if needed.

## Required behavior

- search
- results
- play
- favorite
- background playback through existing Lotus infrastructure

Keep the UI consistent with Lotus.

Do not add a separate radio player.
