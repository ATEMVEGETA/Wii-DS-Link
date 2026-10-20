# Build information — v0.2.0-beta.1

This release packages the exact emulator executables from the successful
local multi-DS test. Documentation and archive names were updated for
publication without recompiling those executables.

| Executable | SHA-256 |
| --- | --- |
| `Dolphin.exe` | `68b93fbf0512f51442136e633da2837a33626b77b2e9e9d8f69daac17cdc998c` |
| `melonDS.exe` | `dba30678b5ce7f72428be924d857e2d8dea69bd49b3a37b5f31f8c4b4dc3031d` |

These are executable hashes, not ZIP hashes. Use the release asset
`SHA256SUMS.txt` for the downloadable archives.

The melonDS window retains its **Multi-DS Test** label to preserve the tested
binary. The public release is still labeled beta.

The sources remain based on official melonDS 1.1 and Dolphin 2609a. This is
not a rebase to newer upstream versions. The public source revisions are
tagged `wii-ds-link-v0.2.0-beta.1` in both emulator repositories:

- [melonDS source](https://github.com/ATEMVEGETA/melonDS/tree/wii-ds-link-v0.2.0-beta.1)
- [Dolphin source](https://github.com/ATEMVEGETA/dolphin/tree/wii-ds-link-v0.2.0-beta.1)

The corresponding source archives are named
`melonDS-WiiDS-Link-source-v0.2.0-beta.1.zip` and
`Dolphin-WiiDS-Link-source-v0.2.0-beta.1.zip`. Submodule revisions remain
pinned; restore them recursively when building from a Git checkout. Preserve
the upstream and dependency notices included with each binary.

The local tester confirmed four-player Battle Revolution gameplay,
participant disconnect/rejoin, and one-DS Ranch transfer/save/shutdown
checks. Automated checks passed for eight DS clients. The bridge has 15
client slots, subject to each game's limit; no eight-player retail result is
claimed. See [COMPATIBILITY.md](COMPATIBILITY.md).
