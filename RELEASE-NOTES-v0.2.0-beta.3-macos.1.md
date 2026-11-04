# Wii-DS Link for macOS — experimental tester build 1

This is a **macOS testing prerelease**, not a verified stable Mac release.
It contains the beta.3 Wii–DS Link/Mystery Gift fix in matching native builds
of melonDS 1.1 and Dolphin 2609a. The existing Windows release is unchanged.

## Choose your download

- **Apple Silicon (M-series):** `Wii-DS-Link-macOS-arm64-experimental.zip`
- **Intel:** `Wii-DS-Link-macOS-x86_64-experimental.zip`

**Both require macOS 15 or newer.** These are separate native packages, not
a Universal binary. Each combined ZIP includes both emulators. Individual
ZIPs are also supplied; do not mix old Windows/pre-fix experimental builds.

Extract the complete ZIP on the Mac and keep its folder layout. Use your own
games/BIOS/firmware and copies of backed-up saves. None of these, Wii NAND,
Miis or personal profiles are supplied. No Wi-Fi adapter or relay is needed:
this is same-Mac loopback, not physical-console, LAN or internet connectivity.

Enable melonDS **Config → Wi-Fi settings → Connect to Dolphin** in each DS
instance and Dolphin **Configuration → Wii → Misc Settings → Connect to
melonDS**. Either app may launch first; overlap the in-game connection screens.

Read [the Mac testing guide](https://github.com/ATEMVEGETA/Wii-DS-Link/blob/main/MACOS-TESTING.md),
also supplied as a release asset and TESTING.md inside each ZIP.

## Verified and unverified

Both architectures passed native compilation, bundle dependency/signature
audits, no-ROM app startup/discovery, 13 transport cases, six multiplayer
groups and eight parent-identity groups. Package checks verify the pinned
sources, executable architecture/permissions, safe symlinks, complete member
hashes and absence of game/private files. Publication changes only the guide,
its manifest/checksums and removable build-helper bytecode; every app payload,
signature, symlink and executable permission is unchanged from the audited CI
output.

**Actual macOS retail gameplay, transfers, normal melonDS GUI shutdown and
recording performance have not yet been verified.** Windows gameplay results
are not evidence of Mac gameplay. Test Ranch deposit/withdraw/save/reopen,
Battle Revolution copying with matching saves, Mystery Gift and DS Battle
Mode; report Mac chip/model, macOS version, title/version and exact results.
Redact private information from any shared logs. Use copies of saves.

## Limitations

- Apps are **ad-hoc signed, not Developer-ID signed or notarized**. If macOS
  blocks an app, only use its normal Privacy & Security approval after verifying
  the source/checksum and choosing to trust it. Do not disable Gatekeeper or SIP.
- Intel macOS melonDS is interpreter-only in this source base.
- Dolphin uses Metal/OpenGL; Vulkan, built-in FFmpeg dumping and auto-update
  are disabled in this candidate.
- No full-speed, 1080p/60fps recording or universal-game compatibility promise.

Exact sources, build scripts, source patch and license notices are included or
linked in the assets. `MACOS-SHA256SUMS.txt` verifies release assets;
`MACOS-PACKAGE-VERIFICATION.json` records ZIP checks, not real-game approval.
Source revisions: melonDS `60a07cca86189ac8b9e0cd1cc6516f575ed60ca3`, Dolphin
`b24e2427a0ab5aec6102f3b5014d581699b9b4a4`, macOS helpers
`08aed1efc4fb76607a58c99d1c20e6b93aeb751b`.
