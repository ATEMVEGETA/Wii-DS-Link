# Experimental macOS testing

The **v0.2.0-beta.3-macos.1** prerelease provides a matching melonDS/Dolphin
pair for testing Wii–DS Link on one Mac. It is experimental, not a stable or
gameplay-verified macOS release. Windows remains the recommended,
gameplay-tested download.

These beta.3 Mac packages do **not** contain the newer beta.4 Driver Download
Play fix available for Windows. A matching updated Mac tester build is still
being prepared; do not treat Windows Driver results as Mac confirmation.

## Choose the native package

Both packages require **macOS 15 or newer**:

- Apple Silicon: [Wii-DS-Link-macOS-arm64-experimental.zip](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/download/v0.2.0-beta.3-macos.1/Wii-DS-Link-macOS-arm64-experimental.zip)
- Intel: [Wii-DS-Link-macOS-x86_64-experimental.zip](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/download/v0.2.0-beta.3-macos.1/Wii-DS-Link-macOS-x86_64-experimental.zip)

Use the architecture matching your Mac's chip and update both emulators
together. Download checksums and package records from the
[prerelease page](https://github.com/ATEMVEGETA/Wii-DS-Link/releases/tag/v0.2.0-beta.3-macos.1).
Do not mix an older melonDS with this Dolphin for the parent-identity fix.

## What has and has not been tested

Evidence is limited to native builds, package audits, no-ROM startup and
loopback checks, plus automated suites of 13 transport, 6 multiclient and
8 identity tests. Those checks do not prove a complete retail-game connection.
No native Mac retail gameplay, save transfer, or full-speed gameplay has been
verified for these packages. The compatibility results in
[COMPATIBILITY.md](COMPATIBILITY.md) are not Mac gameplay confirmations.

Known build limitations:

- Intel melonDS is interpreter-only in this source base. Performance can
  differ substantially between Intel and Apple Silicon.
- Dolphin uses Metal/OpenGL. Vulkan, built-in FFmpeg frame dumping and
  auto-update are disabled. External screen recording is separate and has
  not been verified here.
- No full-speed gameplay or 1080p/60fps recording guarantee is made.
- The bridge is local IPv4 loopback on one Mac, not LAN/internet play,
  physical Wi-Fi, or a connection to real consoles.

These packages retain the source defaults for performance and CPU settings;
this guide does not require changing them.

## Install and open safely

1. Verify the downloaded ZIP against its published SHA-256 checksum.
2. Extract the entire ZIP to a new, normal writable folder. Do not run the
   apps inside the ZIP, from a read-only disk image, or in a protected system
   directory. Keep your existing emulator installation and backups intact.
3. Keep the supplied folder layout, including melonDS's adjacent `portable`
   folder and Dolphin's adjacent `portable.txt` marker. The test profiles
   remain alongside this package instead of replacing an existing install.
4. The apps are **ad-hoc signed, not Apple Developer-ID signed or notarized**.
   macOS may block a downloaded app initially. Only if you trust the build
   and have verified its checksum, attempt to open it and use macOS's normal
   **Privacy & Security → Open Anyway** process if offered. Do not globally
   disable Gatekeeper. No paid Apple Developer account is needed to test.

Games/ROMs, BIOS/firmware, Wii NAND data, Miis, personal configurations and
saves are not included. Configure the apps with your own legally obtained
material. Copy backed-up saves into the test profiles deliberately, with both
emulators closed; do not test against your only copy. Never let two running
instances write to the same save path, and never interrupt an active save.

## Enable the link

1. In **each melonDS instance**, stop the game if necessary, then open
   **Config → Wi-Fi settings** and enable **Connect to Dolphin**. Apply the
   setting. It is per instance, not a global switch; do not delete or manually
   edit the configuration to enable it.
2. In Dolphin, while no game is running, open
   **Configuration → Wii → Misc Settings** and enable **Connect to melonDS**.
3. Launch the games in either order. Overlap their in-game connection screens
   until discovery, Download Play and the application connection complete.
   Opening order does not determine whether the link works.

No USB Wi-Fi adapter or external relay is needed. Use one Dolphin instance
and matching melonDS builds for all DS participants. See
[HOW-TO-LINK.md](HOW-TO-LINK.md) for the game-specific connection flows and
save-identity rules; its Windows executable paths and Windows firewall advice
do not apply to these Mac packages.

## Suggested retail tests

Use backed-up copies of saves and note each result separately:

- **My Pokémon Ranch:** use a compatible Diamond/Pearl save; test connection,
  deposit, save, clean disconnect, close/reopen, reconnect and withdrawal.
- **Pokémon Battle Revolution copying:** use the correctly paired DS/Wii save
  identity. A copy rejection after discovery/Download Play may be the game's
  save-binding rule rather than a bridge failure.
- **Battle Revolution Mystery Gift:** test the desired distribution with a
  compatible DS game, then verify receipt and saving. The fixed parent-identity
  support does not require a manual MAC-address workaround.
- **Battle Revolution DS Battle Mode:** add DS instances one at a time, enable
  each instance's link option, keep all participants running when unfocused
  (disable pause-on-focus-loss if needed), and stay within the game's
  four-player limit. Give each player a separate writable game/save copy.
  Test a clean participant disconnect/rejoin if the initial battle succeeds.

The transport has 15 client slots; that is not a retail-game player limit or
proof of compatibility. Follow each game's own save/disconnect prompts and
keep the original backups after testing.

## Report results

Include:

- Mac model and chip, macOS version, and package architecture.
- Release tag, game titles/regions/versions, and number of DS instances.
- Exact steps, each emulator's last screen, expected result and actual result.
- Whether the result repeats, whether saves were preserved, and the outcome
  of reconnecting or reopening after a clean save/disconnect.
- Relevant diagnostic logs if available. Bridge logs are off by default;
  when enabled, melonDS writes `wii-ds-bridge.log` in its working directory
  and Dolphin writes `User/Logs/wii-ds-bridge.log` in its portable profile.

Review and redact private paths, usernames and other personal information
before sharing logs or screenshots. Do not upload games/ROMs, BIOS/firmware,
NAND data, personal saves or memory dumps. Logs and screenshots should show
only what is needed to explain the result.

## Source identity

The experimental pair was built from these source revisions:

| Component | Revision |
| --- | --- |
| melonDS | `60a07cca86189ac8b9e0cd1cc6516f575ed60ca3` |
| Dolphin | `b24e2427a0ab5aec6102f3b5014d581699b9b4a4` |
| Build helpers | `08aed1efc4fb76607a58c99d1c20e6b93aeb751b` |

Keep the package's build information, licenses and checksums with the apps
when reporting a result.
