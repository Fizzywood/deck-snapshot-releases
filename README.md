# Deck Snapshot Releases

This public repository contains verified Deck Snapshot distribution artifacts only. The source repository is private.

Each GitHub Release may contain only:

- `deck_snapshot_installer.desktop`
- `deck-snapshot-linux-amd64.tar.gz`
- `deck-snapshot-linux-amd64.sha256`
- `stable.json` for a final release, or a versioned RC manifest

Never publish source history, OAuth credentials, client secrets, tokens, cloud recovery material, user data, or private CI logs here.

The desktop installer is version-bound. It downloads the matching archive and checksum from this repository, requires its embedded archive SHA-256, validates the archive inventory, and installs only below the current user's home directory.

Background update checks and automatic installation are not enabled in v0.1.1. See the release notes for the exact validation status of each build.
