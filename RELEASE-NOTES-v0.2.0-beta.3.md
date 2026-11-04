# Wii-DS Link v0.2.0-beta.3 - Mystery Gift fix

Update BOTH melonDS and Dolphin. This Windows x64 pair fixes Battle Revolution
Mystery Gift receipt when Dolphin's normal MAC differs from the old fixed
virtual-radio address. No manual MAC change or save editing is required.

The actual parent identity now accompanies the original Nintendo beacon
atomically. Radio filtering, association, commands and ACKs use that per-radio
identity. Old incompatible clients are not silently accepted. The existing
multi-DS and per-instance Wi-Fi settings features remain.

The tester confirmed gift receipt with Pearl and a non-default address, and
a repeated attempt succeeded. The game's signal-located notice appeared on
the first attempt, not the second; it has not been suppressed. Exact notice
persistence/trigger rules have not been established for every game.

Eight-client automated transport, lifecycle, identity and runtime checks pass.
Ranch transfer/save/withdraw and four-player Battle Revolution results remain
historical beta.1 coverage; their complete flows were not rerun for beta.3.
The upstream bases remain melonDS1.1 and Dolphin2609a. This is still a beta,
not universal Wii-DS compatibility or an official upstream release.

The EXEs are the exact tested builds; older embedded Git/test labels are
documented in BUILD-INFO.md and RELEASE-BUILD.json. Games, BIOS, firmware,
NAND, saves, personal settings and test logs are excluded. Source archives,
license notices and SHA-256 checksums accompany the binaries.

Windows only for this publication. Fixed macOS binaries still need rebuilding
and testing; earlier experimental Mac packages do not contain this fix.

See [HOW-TO-LINK.md](HOW-TO-LINK.md) and [COMPATIBILITY.md](COMPATIBILITY.md).
