# Deck Snapshot

**Back up your customized Steam Deck and bring it back after reinstalling SteamOS.**

Deck Snapshot saves the parts of your Steam Deck setup that are annoying to rebuild by hand:

- installed Decky plugins
- supported plugin settings and data
- CSS Loader themes, profiles, and customization
- custom Steam artwork, including covers, heroes, logos, and icons

Backups are created and validated locally first.  
Google Drive backup is optional.

## Download

**[Download the latest Deck Snapshot installer](https://github.com/TAndrson/deck-snapshot-releases/releases/latest/download/deck_snapshot_installer.desktop)**

[Latest release](https://github.com/TAndrson/deck-snapshot-releases/releases/latest) · [View source](https://github.com/TAndrson/deck-snapshot-source)

## Install

On your Steam Deck:

1. Switch to **Desktop Mode**.
2. Download `deck_snapshot_installer.desktop`.
3. If Plasma asks, open **Properties → Permissions** and enable **Is executable**.
4. Open the installer.
5. Launch **Deck Snapshot** from the application menu.

The installer verifies the downloaded release before installing it for the current user.

Deck Snapshot does not update itself in the background. To update, install a newer release the same way. Existing backups and settings are kept.

## Create a backup

Open Deck Snapshot and select **Create Backup**.

Deck Snapshot:

1. creates the backup locally
2. validates it
3. optionally uploads a protected copy to Google Drive

If the cloud upload fails, the validated local backup remains available.

## Restore after reinstalling SteamOS

For a normal Google Drive recovery:

1. Install **Decky Loader**.
2. Install **Deck Snapshot**.
3. Connect the **same Google account** you used for your backups.
4. Open **Snapshots**.
5. Choose the backup you want to restore.
6. Review the restore plan.
7. Confirm the restore.

That's it.

Since v0.1.5, you do **not** need to keep or manually select a separate recovery file for the normal recovery flow.

Deck Snapshot automatically retrieves the recovery information associated with your Google account.

> Deck Snapshot does not install Decky Loader itself.

## What gets restored?

Deck Snapshot can restore supported customization such as:

- Decky plugins
- supported plugin settings and data
- CSS Loader customization
- custom Steam artwork

Plugins are restored using the current supported plugin source rather than blindly restoring old plugin binaries.

Some plugins may store data in unusual locations or change their settings format between versions. In those cases, Deck Snapshot may preserve or skip incompatible data instead of forcing it into the new installation.

## What Deck Snapshot does not back up

Deck Snapshot is **not a full SteamOS image**.

It does not generally back up:

- installed games
- normal game saves
- your complete Steam library
- shader caches or Proton prefixes
- personal documents
- the complete Linux / SteamOS system

The focus is your **Decky setup and Steam Deck customization**.

## Google Drive

Google Drive support is optional.

Cloud snapshots are stored in:

`My Drive/Deck Snapshot/Snapshots/`

Snapshots are encrypted on your Steam Deck before they are uploaded.

Deck Snapshot requests two limited Google Drive permissions:

- `drive.file` — access to the Drive files used by Deck Snapshot
- `drive.appdata` — access to Deck Snapshot's private recovery data

The recovery information is stored separately in Google's private app-data area so that a fresh Deck Snapshot installation can recover your encrypted backups after you connect the same Google account.

This means a copied or accidentally shared backup file remains encrypted.

It does **not** provide zero-knowledge protection against someone who has completely taken over the same Google account, because that account can potentially reach both the encrypted backups and their recovery information.

Manual recovery-key import and export remain available under Advanced as an optional fallback.

## Restore safety

Deck Snapshot does not immediately write a selected backup back to your Steam Deck.

Before a real restore it:

1. validates the snapshot
2. creates an exact restore plan
3. shows what will change
4. requires explicit confirmation
5. creates a recovery snapshot before production changes

If something does not look safe or compatible, Deck Snapshot is designed to stop rather than guess.

## Privacy

Deck Snapshot is local-first.

There is:

- no Deck Snapshot account
- no project-operated cloud backend
- no telemetry
- no analytics

Google login happens directly through Google.

## Source code

Clean source snapshots matching every public release are available at:

**[TAndrson/deck-snapshot-source](https://github.com/TAndrson/deck-snapshot-source)**

The development repository and its history remain private.

Release binaries, installers, checksums, and manifests are published in this repository.

## AI-assisted development

Deck Snapshot was substantially designed and implemented with OpenAI Codex under human product ownership, an approach sometimes called vibe coding.

Releases are still subject to automated testing, focused security review, checksum verification, and validation on a real Steam Deck.

AI assistance and testing do not guarantee error-free software.

## Disclaimer

Deck Snapshot is an independent hobby project and is not affiliated with or endorsed by Valve, Steam, Decky Loader, CSS Loader, Google, SteamGridDB, or rclone.

Backup and restore software necessarily reads and writes configuration data. No software can guarantee zero risk.

Keep independent copies of anything important and review the restore plan before confirming it.

For security issues, see [SECURITY.md](SECURITY.md). Do not post credentials, recovery material, snapshot contents, or private paths in a public issue.
