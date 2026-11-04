# Build information - v0.2.0-beta.3

Both Windows x64 executables are updated for consistent Wii parent identity
and Battle Revolution Mystery Gift receipt. No Playnite build is included.
The exact tested EXEs are preserved, not rebuilt solely to change title text.

| Executable | SHA-256 |
| --- | --- |
| Dolphin.exe | 39d004a14c0a82bb472fdd3a0af01da1600b1b41a7d6efd005f96cf46d466fb8 |
| melonDS.exe | 09f3bd5d275d5adf9a2e5d276df255c5a0eb597f0751a612f0d134305173d2a5 |

These are EXE hashes. Use SHA256SUMS.txt for ZIP hashes. RELEASE-BUILD.json
records tagged source revisions and tested code-file identities.

Sources remain based on melonDS 1.1 and Dolphin 2609a, not newer upstream:

- [melonDS source tag](https://github.com/ATEMVEGETA/melonDS/tree/wii-ds-link-v0.2.0-beta.3)
- [Dolphin source tag](https://github.com/ATEMVEGETA/dolphin/tree/wii-ds-link-v0.2.0-beta.3)

The compact melonDS uses UCRT64 GCC16.1.0, Qt6.8.3 and unchanged cached static
dependencies from vcpkg baseline dd3097e305afa53f7b4312371f62058d2e665320.
Dolphin uses MSVC19.51.36260, VS2026, WindowsSDK10.0.26100.0 and pinned Qt6.8.3.
See each source repository's WII-DS-BUILD.md for build commands.

The EXEs were compiled from the preceding tagged bases plus the functional
changes now in beta.3, before publication docs. Embedded older Git/test labels
(including melonDS's Mystery Gift Test label) are retained intentionally.
Build records and source-file hashes map the exact payload to the release.
Rebuilds need not be bit-identical. Source ZIPs do not expand submodules;
restore their recorded pinned revisions recursively. Notices are included.

Fresh retail coverage: Battle Revolution Mystery Gift received with Pearl,
using the previously failing non-default MAC, and a repeat succeeded.
Other retail flows are historical beta.1 coverage, not freshly rerun here.
Automated checks: parent identity9, legacy lifecycle17, automatic lifecycle11,
eight-client transport13, standalone frontend10, Dolphin identity17 plus
multiplayer/helper suites, and private Dolphin startup/dependency audit.
These do not certify every game/region/reward, 15-player retail gameplay or Mac.

No macOS binary containing this fix is published yet. Pre-fix experimental
Mac packages must not be described as this update.
