# Wii-DS Link v0.2.0-beta.4 - Driver Download Play fix

Update **both melonDS and Dolphin**, including Dolphin's supplied runtime
files. The matching Windows x64 pair fixes the post-download reconnection
failure confirmed with **Driver: San Francisco (PAL, SDVP41)**.

## What changed

- melonDS advertises version-1 Nintendo GameInfo at its declared size: 16
  fixed bytes plus user data, up to 128 bytes. The previous encoder always
  advertised the full multiboot storage size. Driver's downloaded client
  rejected the resulting short-record length mismatch before associating.
  The correction is generic, not a title-specific wireless workaround.
- Dolphin backports [upstream PR #14983](https://github.com/dolphin-emu/dolphin/pull/14983),
  commit `f4b9fae9f53db163a36b39fde1837421016d6a5f`, removing Driver's problematic
  USA/PAL frame-rate speed-hack patches and their obsolete approvals. Their
  absence is verified in packaged Sys data as well as source.
- Optional diagnostics add connection-stage evidence while remaining off by
  default and bounded. melonDS buffers diagnostic output instead of reopening
  and synchronously writing the file for each event.
- The Mystery Gift parent-identity fix, per-instance Wi-Fi settings and
  multi-DS support remain. No new shutdown behavior is introduced.

## Validation and limits

The tester confirmed working Driver PAL connectivity with the functional
candidate. Publication executables are rebuilt with release branding from
that same functional code and checked separately; a metadata-only rebuild
is not an additional retail test.

Generated-packet tests cover all 113 valid version-1 user-data lengths,
bounded fallback for unknown/malformed records and transitions between
Download Play and the launched application. Restoring the old fixed-size
encoder reproduces the short-record failure. Lifecycle, identity, eight-client
transport, logging, patch-allowlist and standalone runtime checks passed.

Battle Revolution Mystery Gift receipt/repeat is retained beta.3 coverage.
Ranch transfer/save/withdraw and four-player Battle Revolution are historical
beta.1 coverage, not fresh complete retail runs for beta.4. Other Driver
regions and every game mode remain unverified. This is still a beta, not
universal Wii–DS compatibility or an official upstream release.

Sources remain based on melonDS 1.1 and Dolphin 2609a. Games, BIOS, firmware,
NAND, saves, personal settings and private test logs are excluded. Source
archives, license notices and SHA-256 checksums accompany the binaries.

Windows is the gameplay-tested platform. The separately published
beta.3-macos.1 packages are earlier experimental tester builds without this
Driver fix; actual Mac gameplay is not verified.

See [HOW-TO-LINK.md](HOW-TO-LINK.md), [COMPATIBILITY.md](COMPATIBILITY.md) and
[BUILD-INFO.md](BUILD-INFO.md).
