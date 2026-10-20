# Build information — v0.2.0-beta.2

This release updates the compact melonDS executable to fix Wi-Fi settings
access in additional instances. The Dolphin executable and runtime files are
unchanged from v0.2.0-beta.1. No Playnite custom build is included or modified.

| Executable | SHA-256 |
| --- | --- |
| `Dolphin.exe` | `68b93fbf0512f51442136e633da2837a33626b77b2e9e9d8f69daac17cdc998c` |
| `melonDS.exe` | `a9bf19529ef0fec7778e40af9131c2fbb59334d11698dcd5b8d4cfbaf7a0f931` |

These are executable hashes, not ZIP hashes. Use the release asset
`SHA256SUMS.txt` for the downloadable archives.

The melonDS window identifies this candidate as **WiFi Settings Fix**. The
public release remains beta. The functional hotfix source commit is
`ced7bb74087235f451b113f7cbb23975408bd1c2`; the publication tag also includes
the updated release documentation. The unchanged Dolphin source revision is
`22060863a04f086bd0c51a6fdf7500e27470d35d`.

The sources remain based on official melonDS 1.1 and Dolphin 2609a. This is
not a rebase to newer upstream versions:

- [melonDS source, `wii-ds-link-v0.2.0-beta.2`](https://github.com/ATEMVEGETA/melonDS/tree/wii-ds-link-v0.2.0-beta.2)
- [Dolphin source, unchanged `wii-ds-link-v0.2.0-beta.1`](https://github.com/ATEMVEGETA/dolphin/tree/wii-ds-link-v0.2.0-beta.1)

The corresponding source archives are named
`melonDS-WiiDS-Link-source-v0.2.0-beta.2.zip` and
`Dolphin-WiiDS-Link-source-v0.2.0-beta.1.zip`. They contain the tracked source
and build documentation; Git submodule contents are not expanded. Submodule
revisions remain pinned; restore them recursively when building from a Git
checkout. Preserve the upstream and dependency notices included with each
binary.

The settings hotfix passed an actual Qt dialog fixture with 11 checks, 10
standalone frontend modes, and 13 multi-DS backend cases covering eight
contexts. Fresh retail confirmation for this new melonDS executable is still
pending. The prior v0.2.0-beta.1 tester confirmed four-player Battle Revolution
gameplay, participant disconnect/rejoin, and one-DS Ranch
transfer/save/shutdown checks. No eight-player retail result is claimed.
See [COMPATIBILITY.md](COMPATIBILITY.md).
