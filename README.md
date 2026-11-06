# Wii–DS Link

Unofficial paired builds of [melonDS](https://github.com/ATEMVEGETA/melonDS)
and [Dolphin](https://github.com/ATEMVEGETA/dolphin) for local Wii–Nintendo DS
communication on one computer. Windows is the recommended, gameplay-tested
download; macOS builds are available separately for experimental testing.

## Download

**[Download the combined Windows x64 package](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/download/v0.2.0-beta.4/Wii-DS-Link-Windows-x64-v0.2.0-beta.4.zip)**

This single ZIP contains the matching melonDS and Dolphin builds. Individual
emulator ZIPs and SHA-256 checksums are available on the
[v0.2.0-beta.4 release page](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/tag/v0.2.0-beta.4).

> [!IMPORTANT]
> This project has been tested so far with **My Pokémon Ranch** and
> **Pokémon Battle Revolution**, including four DS players in Battle
> Revolution's DS Battle Mode, and **Driver: San Francisco (PAL)** Download
> Play connectivity. Other Wii–DS titles and every game/save combination
> are not yet verified.

The current recommended Windows release is **v0.2.0-beta.4**. It fixes a generic
Nintendo beacon-length mismatch that prevented a downloaded DS application
from reconnecting, confirmed with Driver: San Francisco (PAL). Dolphin also
includes the upstream removal of that game's problematic frame-rate speed
hack. **Update both emulators and Dolphin's supplied runtime files.** The
Mystery Gift identity fix, per-instance settings and multi-DS support remain.
Earlier Pokémon results are retained coverage, not fresh retail regression
runs of every flow for beta.4.
Download the combined Windows package
from [Releases](https://github.com/ATEMVEGETA/Wii-DS-Link/releases), then follow
[HOW-TO-LINK.md](HOW-TO-LINK.md).

### Experimental macOS prerelease

**macOS gameplay is not yet verified.** The separate
[v0.2.0-beta.4-macos.1 prerelease](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/tag/v0.2.0-beta.4-macos.1)
contains matching native builds with the beta.4 Driver fix for testing:

- [Apple Silicon (arm64)](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/download/v0.2.0-beta.4-macos.1/Wii-DS-Link-macOS-arm64-experimental.zip)
- [Intel (x86_64)](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/download/v0.2.0-beta.4-macos.1/Wii-DS-Link-macOS-x86_64-experimental.zip)

**Both downloads require macOS 15 or newer.** The apps are ad-hoc signed,
not Apple Developer-ID signed or notarized. Evidence is limited to native
builds, package audits, no-ROM startup and loopback checks, plus 13 transport,
6 multiclient, 8 identity and 8 native-beacon test groups on both architectures.
These do not establish retail
gameplay, save-transfer safety, or full-speed performance on a Mac. The
gameplay results elsewhere in this README are Windows results.

Read [MACOS-TESTING.md](MACOS-TESTING.md) before opening the apps. Use only
your own game/BIOS material and backed-up copies of saves. Intel melonDS is
interpreter-only in this source base; Dolphin uses Metal/OpenGL with Vulkan,
built-in FFmpeg frame dumping and auto-update disabled. These experimental
packages do not replace the recommended Windows release.

## What this adds

- **Connect to Dolphin** in melonDS under **Config → Wi-Fi settings**.
  Wi-Fi settings is available in every instance, so an existing disabled link
  can be enabled without deleting or manually editing the TOML configuration.
  Stop a running game before changing the option.
- **Connect to melonDS** in Dolphin under
  **Configuration → Wii → Misc Settings**.
- Automatic discovery over IPv4 loopback once both options are enabled.
- Multiple melonDS instances can join the same Dolphin session. The bridge
  has 15 client slots; the Wii game determines how many players it accepts.
- Either emulator may be opened first; the games initiate the link from their
  own connection screens.
- The Wii game's real Download Play client is transferred and runs from DS RAM.
  The DS cartridge/save remains attached for game data and save updates.
- No external relay program or console window is needed.

This is a local, single-PC link for one Dolphin and one or more melonDS
instances. It is not internet play, physical Wi-Fi, or a bridge to real consoles.
Use both paired builds from this release when upgrading. An older melonDS
cannot represent arbitrary parent identities, so do not mix versions for this
fix. Do not edit or delete your existing configuration or saves as a workaround.
The macOS prerelease includes this identity fix, but still requires real-Mac
gameplay testing; see [MACOS-TESTING.md](MACOS-TESTING.md).

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
  copying were exercised with a correctly paired DS save. Four-player DS
  battles and a participant disconnect/rejoin were also confirmed by the
  tester. Battle Revolution's own save/cartridge identity rule can reject a
  technically working link.
- **Battle Revolution Mystery Gift:** receipt with Pokémon Pearl and a
  non-default Dolphin MAC was confirmed on v0.2.0-beta.3, including a repeated
  successful attempt. Other DS game/reward combinations remain unverified.
- **Driver: San Francisco (PAL):** the tester confirmed working Download Play
  connectivity with the beta.4 fix. Other regions and every game mode have
  not been certified.
- **Automated transport checks:** eight DS clients passed. This checks the
  transport, not eight-player retail gameplay; no eight-player game has been
  verified with this release.

The exact public package is deliberately labeled beta while it receives wider
testing. A successful result for these games is not a promise that every title
using Wii–DS communication follows the same application protocol.

## Legal and privacy notes

This project is not affiliated with or endorsed by Nintendo, The Pokémon
Company, melonDS, or Dolphin Emulator. Games, ROMs, BIOS, firmware, Wii NAND
data, and save files are not included. Use your own legally obtained material.

The emulator forks retain their upstream licenses. Dependency notices are
included in the release package. See [LICENSES.md](LICENSES.md).

## Development Note
This project was developed with the assistance of OpenAI Codex (AI), which helped with coding, debugging, and implementing new features. I provided the ideas, requirements, and direction for the project, along with testing and feedback throughout development.
