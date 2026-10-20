# Wii–DS Link v0.2.0-beta.2

This melonDS settings hotfix makes **Config → Wi-Fi settings** available in
every instance, including windows created with **Launch new instance**.
An extra window whose **Connect to Dolphin** setting is disabled can now
enable it normally, without deleting or manually editing the TOML file.

Dolphin is unchanged from v0.2.0-beta.1. Existing users need only replace
`melonDS.exe`, with all melonDS instances closed; keep existing settings and
saves. No Playnite custom version was changed.

## Download

- [Combined Windows x64 package](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/download/v0.2.0-beta.2/Wii-DS-Link-Windows-x64-v0.2.0-beta.2.zip)
- [melonDS Windows x64 package](https://github.com/ATEMVEGETA/melonDS/releases/download/wii-ds-link-v0.2.0-beta.2/melonDS-1.1-WiiDS-Link-Windows-x64-v0.2.0-beta.2.zip)
- [Dolphin Windows x64 package, unchanged](https://github.com/ATEMVEGETA/dolphin/releases/download/wii-ds-link-v0.2.0-beta.1/Dolphin-2609a-WiiDS-Link-Windows-x64-v0.2.0-beta.1.zip)

## Changes

- Every melonDS instance can open Wi-Fi settings and edit its own
  **Connect to Dolphin** option. This remains a per-instance setting; changing
  the first window does not silently change other existing windows.
- Shared LAN settings remain read-only in additional instances. Changing only
  the Wii link option, or cancelling the dialog, does not restart the shared
  LAN network.
- Opening and accepting settings preserves a saved LAN adapter selection
  even if that adapter is temporarily unavailable.
- Duplicate Wi-Fi dialogs are prevented without leaving the emulator paused
  or retaining a stale dialog reference.
- The existing requirement to stop a running game before changing the link
  option remains, as do command-line overrides.

Use **System → Stop** if needed, then **Config → Wi-Fi settings → Connect to
Dolphin** in each participant. See the updated
[setup guide](https://github.com/ATEMVEGETA/Wii-DS-Link/blob/v0.2.0-beta.2/HOW-TO-LINK.md).

## Validation and compatibility

The hotfix passed an actual Qt dialog fixture with 11 checks, 10 standalone
frontend modes, and 13 multi-DS backend cases covering eight contexts.
Fresh retail gameplay confirmation for this updated melonDS executable is
still pending. The previous v0.2.0-beta.1 release was confirmed with **My
Pokémon Ranch** and **Pokémon Battle Revolution**, including four DS players
and participant disconnect/rejoin. Those results are compatibility history,
not a claim of a fresh retail test of this hotfix.

The bridge still supports local same-PC communication with up to 15 client
slots, subject to each game's player limit. Eight-client automated checks
do not prove eight-player retail compatibility. Games, ROMs, BIOS, firmware,
Wii NAND data, personal configurations, Miis, and saves are not included.

The release includes matching source archives, license notices, and SHA-256
checksums. Executable hashes and source provenance are recorded in
[BUILD-INFO.md](https://github.com/ATEMVEGETA/Wii-DS-Link/blob/v0.2.0-beta.2/BUILD-INFO.md).
