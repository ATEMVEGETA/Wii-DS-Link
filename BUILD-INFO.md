# Build information - v0.2.0-beta.4

This Windows x64 pair adds the Driver: San Francisco Download Play fix while
retaining the parent-identity, per-instance settings and multi-DS features.
No Playnite build is included.

The public executables are rebuilt with release branding from the same
functional code as the candidate on which the tester confirmed Driver PAL
connectivity. A metadata-only rebuild is not a separate retail gameplay test.
Exact publication EXE hashes, source revisions and code identities are recorded
in `RELEASE-BUILD.json`; archive hashes are in `SHA256SUMS.txt`.

Sources remain based on melonDS 1.1 and Dolphin 2609a, not newer upstream:

- [melonDS source tag](https://github.com/ATEMVEGETA/melonDS/tree/wii-ds-link-v0.2.0-beta.4)
- [Dolphin source tag](https://github.com/ATEMVEGETA/dolphin/tree/wii-ds-link-v0.2.0-beta.4)

The compact melonDS uses UCRT64 GCC 16.1.0, Qt 6.8.3 and unchanged cached static
dependencies from vcpkg baseline `dd3097e305afa53f7b4312371f62058d2e665320`.
Dolphin uses MSVC 19.51.36260, VS 2026, Windows SDK 10.0.26100.0 and pinned
Qt 6.8.3. See each source repository's `WII-DS-BUILD.md` for build commands.
Rebuilds need not be bit-identical. Source ZIPs do not expand submodules;
restore their recorded pinned revisions recursively. Notices are included.

The melonDS change corrects the advertised size of version-1 Nintendo GameInfo
records after Download Play: 16 fixed bytes plus the declared user data, rather
than always 128 bytes. Unknown/malformed formats retain the bounded fallback.
No game-ID branch, game-binary patch or simulated application response is added.
Optional diagnostics remain disabled by default; the melonDS writer is buffered
and bounded to avoid per-event disk stalls.

Dolphin backports upstream PR #14983, commit
`f4b9fae9f53db163a36b39fde1837421016d6a5f`, removing Driver's USA/PAL frame-rate
speed-hack GameINIs and obsolete approvals. Packaged Sys data is checked as well
as source data. Wii–DS transport, WD/NCD identity and multi-DS code are preserved.
No shutdown-behavior change is included.

Validation includes generated native beacon packets across all 113 valid
user-data lengths, bounded fallback and Download Play/application phase changes;
a restored old encoder fails the short-record negative control. Lifecycle,
parent-identity, eight-client transport, diagnostic-writer, patch-allowlist and
standalone startup/runtime checks also passed. These do not certify every game,
region, save history or retail player count.

Retail coverage: Driver PAL connectivity was confirmed with the beta.4
functional candidate. Battle Revolution Mystery Gift receipt/repeat was
confirmed on beta.3. Ranch transfer/save/withdraw and four-player Battle
Revolution remain historical beta.1 coverage, not fresh complete beta.4 reruns.

The separate beta.3-macos.1 prerelease contains earlier native tester builds,
not this Driver fix. Actual Mac retail gameplay remains unverified.
