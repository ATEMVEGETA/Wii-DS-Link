# Compatibility

## Tested so far

| Wii title | DS title/save | Confirmed result | Notes |
| --- | --- | --- | --- |
| My Pokémon Ranch | Pokémon Diamond | Connected; deposit, save, disconnect, reconnect, and withdrawal exercised | Game and save must be compatible with Ranch |
| My Pokémon Ranch | Pokémon Pearl | Connected and transfer exercised | Same Wii–DS link path as the Diamond test |
| Pokémon Battle Revolution | Compatible DS Pokémon game with correctly paired save | Connected; Download Play and Pokémon data copy exercised | A previously paired Battle Revolution save can reject a different DS game/save identity |
| Pokémon Battle Revolution, DS Battle Mode | Four compatible DS Pokémon games/saves | Four DS players connected and gameplay worked; participant disconnect/rejoin confirmed | Four is this game's player limit |
| Pokémon Battle Revolution, Mystery Gift | Pokémon Pearl | Gift received and repeated successfully on v0.2.0-beta.3 | Normal non-default Dolphin MAC; no manual workaround |
| Driver: San Francisco (PAL, SDVP41) | DS Download Play | Working connectivity confirmed with the beta.4 fix | Other regions and all game modes are not certified |

The current Windows public package is **v0.2.0-beta.4**. Driver PAL connectivity
was confirmed with this fix. Mystery Gift receipt was confirmed on beta.3
with a non-default parent MAC and repeated. The other Pokémon retail rows
are from beta.1, including multi-DS and Ranch; those full flows were not
freshly rerun for beta.4. These
user reports and automated checks do not establish compatibility with every
region, revision, or save.

## Capacity and automated validation

The bridge can track 15 associated DS clients. Each Wii game applies its own
player limit; Battle Revolution's DS Battle Mode accepts four. Automated
checks passed with eight DS clients, including separate processes, and
covered one-DS regressions, lifecycle, radio identity, and disconnect handling.
Eight-player retail gameplay has not been tested. The 15-client capacity is
an implementation limit, not a claim that a particular game supports 15 players.

The beta.4 fix passed tests against actual generated beacon packets: all 113
valid version-1 user-data lengths, bounded fallback for unknown/malformed
records, and transitions between Download Play and the launched application.
A negative control using the previous fixed-length encoder reproduces the
short-record failure. Lifecycle, parent-identity, eight-client transport and
standalone startup checks also passed. These are protocol/runtime checks,
not fresh Pokémon retail transfer or save-safety tests.

The v0.2.0-beta.2 settings hotfix passed an actual Qt dialog fixture with 11
checks, 10 standalone frontend modes, and 13 multi-DS backend cases covering
eight contexts. These verify settings availability, per-instance persistence,
network-reset behavior, startup, and transport regressions; they are not
new retail gameplay tests.

## Not certified yet

- Other Wii–DS game combinations.
- Retail gameplay with more than four DS participants.
- Internet or LAN play between two computers.
- Connections to a physical Wii or Nintendo DS.
- Every region, revision, emulator timing setting, or save history.
- Mystery Gift with every DS title/reward combination.
- Native macOS gameplay. The separate beta.3-macos.1 tester builds are
  published, but do not yet include the beta.4 Driver fix.

Wii–DS software shares lower-level Nintendo wireless mechanisms, but games can
use different Download Play clients, timing, framing, application protocols,
and cartridge/save identity checks. Therefore success in one game is valuable
protocol coverage, not automatic proof for every title.

When reporting a new result, state the Wii game and region, DS game and region,
exact release version, whether the connection completed, and the last screen
shown by each game. Do not attach copyrighted game data or personal saves.
