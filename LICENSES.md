# Licenses and source

Wii–DS Link is an aggregate release of two separately licensed emulator forks.

- **melonDS fork and Wii–DS additions:** GPL-3.0-or-later. See the melonDS
  source repository's `LICENSE` and source headers.
- **Dolphin fork and Wii–DS additions:** GPL-2.0-or-later. See the Dolphin
  source repository's `COPYING` file and source headers.
- Bundled third-party libraries and data retain their own licenses. Their
  notices are included beside the corresponding binary in the release package.

Matching modified source for the v0.2.0-beta.2 package is published in:

- [melonDS source tag](https://github.com/ATEMVEGETA/melonDS/tree/wii-ds-link-v0.2.0-beta.2)
- [Dolphin source tag, unchanged from v0.2.0-beta.1](https://github.com/ATEMVEGETA/dolphin/tree/wii-ds-link-v0.2.0-beta.1)

The release pages also provide source archives corresponding to the binaries.
GitHub's automatically generated source archives do not expand Git submodules;
a source checkout requires `git submodule update --init --recursive` to restore
the pinned dependencies. Build provenance and tested executable hashes are
recorded in [BUILD-INFO.md](BUILD-INFO.md).
The two emulator names and upstream project trademarks belong to their
respective owners. This project is unofficial and is not endorsed by either
upstream project or Nintendo.
