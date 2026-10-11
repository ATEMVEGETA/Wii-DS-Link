# Wii–DS Link v0.1.0-beta.1

First public beta of the matched melonDS and Dolphin Wii–DS Link builds for
Windows x64.

## Included

- melonDS 1.1-based compact single-executable build with
  **Config → Wi-Fi settings → Connect to Dolphin**.
- Dolphin 2609a-based portable build with
  **Configuration → Wii → Misc Settings → Connect to melonDS**.
- Automatic same-PC discovery over IPv4 loopback; emulator launch order does
  not matter after both saved options are enabled.
- Normal Wii-provided Download Play client execution in DS RAM.
- Optional bounded diagnostic logging, disabled by default.
- Setup guide, compatibility notes, license notices, and SHA-256 checksums.

## Tested scope

The link has been tested so far with **My Pokémon Ranch** and
**Pokémon Battle Revolution**. Ranch deposit/withdraw/save flows and Battle
Revolution's Download Play/Pokémon copy flow were exercised in the working test
implementation. Battle Revolution requires the correct paired DS/Wii saves.

This beta does not claim universal Wii–DS compatibility. The exact packaged
official-base binaries have passed automated transport/startup validation and
need wider retail transfer testing.

## Limits

- One Dolphin and one selected melonDS instance on the same computer.
- No real-console, physical Wi-Fi, LAN, or internet bridge.
- No games, ROMs, BIOS, firmware, Wii NAND data, or saves are included.
