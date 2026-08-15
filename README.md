# Deck Snapshot

Back up Decky plugins and their supported settings, CSS Loader customization, and custom Steam artwork before a SteamOS reset or re-image.

## Download

**[Download the latest Deck Snapshot installer](https://github.com/Fizzywood/deck-snapshot-releases/releases/latest/download/deck_snapshot_installer.desktop)**

[Open the latest release page](https://github.com/Fizzywood/deck-snapshot-releases/releases/latest) · [View Source Code](https://github.com/Fizzywood/deck-snapshot-source)

On your Steam Deck in Desktop Mode:

1. Download `deck_snapshot_installer.desktop`.
2. If Plasma asks, open **Properties → Permissions** and enable **Is executable**.
3. Open the installer and wait for the verified result.
4. Launch **Deck Snapshot** from the application menu.

The installer is version-bound, checks the downloaded archive against its embedded SHA-256 identity, and installs only for the current user. Deck Snapshot does not update itself in the background; install a newer release the same way when one is available. Existing backups and settings are kept.

## How it works

- **Create Backup** always creates and validates a local backup first.
- Optional Google Drive upload stores a client-side protected copy in `My Drive/Deck Snapshot/Snapshots/`.
- **Snapshots** lets you inspect local and available cloud backups.
- **Restore** always creates a preview first. A real restore requires a separately confirmed exact plan and a verified recovery backup before any production change.

Keep the recovery file created during Google Drive setup somewhere separate from the cloud snapshots. Losing it can make protected cloud backups unrecoverable.

Deck Snapshot is focused on Decky customization, CSS Loader state, and custom Steam artwork. It is not a system image and does not back up games, save games, complete Steam libraries, personal documents, or general Linux settings.

### Create a backup

1. Open Deck Snapshot and select **Create Backup**.
2. Keep the progress window open while the local backup is created and checked.
3. Confirm that the result says **Saved**. If Google Drive is connected and automatic upload is enabled, also confirm that it says **Stored**.

### Fresh SteamOS recovery

1. After the fresh SteamOS installation, switch to Desktop Mode and install Deck Snapshot.
2. Connect the same Google account and select the separate recovery file created during the original Google Drive setup.
3. Open **Snapshots** and choose the protected cloud backup.
4. Review the generated **Restore Plan** carefully.
5. Run the restore only after confirming that the plan contains exactly the expected paths and changes.

Google Drive is currently the supported cloud provider. Protected snapshots are stored in `My Drive/Deck Snapshot/Snapshots/`.

## Privacy and security

Deck Snapshot is local-first and has no project-operated backend and no telemetry or analytics. Google Drive is optional, and login happens directly through Google. New connections request exactly `drive.file`, which limits the app to files it creates or opens for the user. OAuth state is stored privately on the Steam Deck, snapshots are protected before upload, and recovery material is never uploaded beside them.

Release downloads, checksums, and strict manifests are published here. Inspectable source snapshots for each public release are published separately at **[Fizzywood/deck-snapshot-source](https://github.com/Fizzywood/deck-snapshot-source)**. The private development repository and its history remain private.

Please report security concerns privately as described in [SECURITY.md](SECURITY.md). Never post credentials, recovery material, snapshot contents, or private paths in a public issue.

## AI-assisted development disclosure

Deck Snapshot was substantially designed and implemented with OpenAI Codex under human product ownership, a development approach sometimes called vibe coding. Releases are still subject to automated tests, focused security review, checksum verification, and real Steam Deck validation. AI assistance and testing do not guarantee that the software is error-free; keep independent copies of important data and review every restore plan.

Deck Snapshot is an independent hobby project and is not affiliated with or endorsed by Valve, Steam, Decky Loader, CSS Loader, Google, SteamGridDB, or rclone. It reads and writes local configuration during backup and approved restore operations. Zero risk cannot be guaranteed; use it at your own risk.
