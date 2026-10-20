# Wii–DS Link v0.2.0-beta.1

Multiple melonDS instances can now join one Dolphin session on the same PC.
This release packages the exact executables used in the successful local
multi-DS test, with updated documentation and matching source tags.

## Download

- [Combined Windows x64 package](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/download/v0.2.0-beta.1/Wii-DS-Link-Windows-x64-v0.2.0-beta.1.zip)
- [melonDS Windows x64 package](https://github.com/ATEMVEGETA/melonDS/releases/download/wii-ds-link-v0.2.0-beta.1/melonDS-1.1-WiiDS-Link-Windows-x64-v0.2.0-beta.1.zip)
- [Dolphin Windows x64 package](https://github.com/ATEMVEGETA/dolphin/releases/download/wii-ds-link-v0.2.0-beta.1/Dolphin-2609a-WiiDS-Link-Windows-x64-v0.2.0-beta.1.zip)

Use both new emulators together. Enable **Connect to Dolphin** in every
melonDS participant and **Connect to melonDS** in Dolphin. The emulators may
be opened in either order. See [HOW-TO-LINK.md](https://github.com/ATEMVEGETA/Wii-DS-Link/blob/v0.2.0-beta.1/HOW-TO-LINK.md) for setup,
multiplayer, saves, and upgrade instructions.

## Changes

- One Dolphin can track up to 15 associated DS clients; the Wii game still
  determines its own player limit. Battle Revolution supports four players.
- Each melonDS instance uses a distinct local socket and in-memory radio
  identity. **Launch new instance** and separate processes are supported.
- Multiplayer rounds collect actual replies from targeted DS clients,
  preserving per-client failures and keeping existing players connected when
  another joins, leaves, or reconnects.
- Optional diagnostic logs remain off by default. No relay or console window
  is required.

## Tested scope

The tester confirmed four DS players in **Pokémon Battle Revolution's DS
Battle Mode**, participant disconnect/rejoin, and the one-DS **My Pokémon
Ranch** transfer/save/shutdown regression checks. Earlier Ranch
Diamond/Pearl deposit/withdraw flows and Battle Revolution Pokémon copying
remain covered by the compatibility history.

Automated checks passed with eight DS clients and covered one-DS regression,
lifecycle, radio identity, disconnect, and startup behavior. Eight-player
retail gameplay has not been tested. The bridge's 15-client capacity does not
establish universal compatibility or override a game's player limit.

The melonDS window retains **Multi-DS Test** in its title so the release can
use the exact tested executable without a rebuild. The bases remain melonDS
1.1 and Dolphin 2609a. Executable hashes and source tags are recorded in
[BUILD-INFO.md](https://github.com/ATEMVEGETA/Wii-DS-Link/blob/v0.2.0-beta.1/BUILD-INFO.md).

## Limits

- Same-PC communication only; no real-console, physical Wi-Fi, LAN, or
  internet bridge.
- Do not mix old and new builds in a multiplayer session.
- Battle Revolution's Pokémon copy feature still requires the expected
  paired DS/Wii save identity.
- Other Wii–DS games, regions, revisions, and save histories are not all
  verified. See [COMPATIBILITY.md](https://github.com/ATEMVEGETA/Wii-DS-Link/blob/v0.2.0-beta.1/COMPATIBILITY.md).
- Games, ROMs, BIOS, firmware, Wii NAND data, and saves are not included.

The release includes license notices, matching source archives, and SHA-256
checksums. The forks are unofficial and retain their upstream licenses.
