# Updates

## Goal

Updates should be boring.

Preferred order:

1. normal app release/update
2. normal dependency update shipped in a new release
3. only if necessary, a simple manual download/install action

Do not build a general-purpose runtime plugin/package manager.

If a separately downloadable component becomes necessary:

- use HTTPS
- pin the official source
- verify checksum/signature
- verify compatibility
- keep previous version for rollback where practical
- tell the user exactly what will happen

Do not execute arbitrary downloaded code.
