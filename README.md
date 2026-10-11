# Wii–DS Link

Unofficial paired Windows builds of [melonDS](https://github.com/ATEMVEGETA/melonDS)
and [Dolphin](https://github.com/ATEMVEGETA/dolphin) for local Wii–Nintendo DS
communication on one PC.

## Download

**[Download the combined Windows x64 package](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/download/v0.1.0-beta.1/Wii-DS-Link-Windows-x64-v0.1.0-beta.1.zip)**

This single ZIP contains the matching melonDS and Dolphin builds. Individual
emulator ZIPs and SHA-256 checksums are available on the
[v0.1.0-beta.1 release page](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/tag/v0.1.0-beta.1).

> [!IMPORTANT]
> This project has been tested so far with **My Pokémon Ranch** and
> **Pokémon Battle Revolution**. Other Wii–DS titles and every game/save
> combination are not yet certified.

The current release is **v0.1.0-beta.1**. Download the combined Windows package
from [Releases](https://github.com/ATEMVEGETA/Wii-DS-Link/releases), then follow
[HOW-TO-LINK.md](HOW-TO-LINK.md).

## What this adds

- **Connect to Dolphin** in melonDS under **Config → Wi-Fi settings**.
- **Connect to melonDS** in Dolphin under
  **Configuration → Wii → Misc Settings**.
- Automatic discovery over IPv4 loopback once both options are enabled.
- Either emulator may be opened first; the games initiate the link from their
  own connection screens.
- The Wii game's real Download Play client is transferred and runs from DS RAM.
  The DS cartridge/save remains attached for game data and save updates.
- No external relay program or console window is needed.

This is a local, single-PC experimental link for one Dolphin and one melonDS
instance. It is not internet play, physical Wi-Fi, or a bridge to real consoles.

## Repositories

| Repository | Purpose | Upstream |
| --- | --- | --- |
| [ATEMVEGETA/melonDS](https://github.com/ATEMVEGETA/melonDS) | melonDS Wii–DS Link source and standalone build | [melonDS-emu/melonDS](https://github.com/melonDS-emu/melonDS) |
| [ATEMVEGETA/dolphin](https://github.com/ATEMVEGETA/dolphin) | Dolphin Wii–DS Link source and standalone build | [dolphin-emu/dolphin](https://github.com/dolphin-emu/dolphin) |
| [ATEMVEGETA/Wii-DS-Link](https://github.com/ATEMVEGETA/Wii-DS-Link) | Combined download, setup guide, compatibility status, and release notes | Standalone project |

## Compatibility status

See [COMPATIBILITY.md](COMPATIBILITY.md) for the tested flows and limitations.
The short version:

- **My Pokémon Ranch:** deposit, withdraw, save, disconnect, and reconnect were
  exercised with compatible Pokémon Diamond/Pearl saves in the working test
  implementation.
- **Pokémon Battle Revolution:** DS discovery, Download Play, and Pokémon data
  copying were exercised with a correctly paired DS save. Battle Revolution's
  own save/cartridge identity rule can reject a technically working link.

The exact public package is deliberately labeled beta while it receives wider
testing. A successful result for these games is not a promise that every title
using Wii–DS communication follows the same application protocol.

## Legal and privacy notes

This project is not affiliated with or endorsed by Nintendo, The Pokémon
Company, melonDS, or Dolphin Emulator. Games, ROMs, BIOS, firmware, Wii NAND
data, and save files are not included. Use your own legally obtained material.

The emulator forks retain their upstream licenses. Dependency notices are
included in the release package. See [LICENSES.md](LICENSES.md).
