# Backup Format

Use a versioned archive/data file.

Example logical structure:

```text
listen-backup/
  manifest.json
  settings.json
  youtube/
    likes.json
    playlists.json
  radio/
    favorites.json
```

The exact physical format may be a ZIP or another robust portable format.

Manifest should include:

- format name
- schema version
- export timestamp
- app version

Import rules:

- validate manifest
- reject unsupported future schemas cleanly
- migrate known older schemas
- never overwrite data without clear user intent
- never import secrets
