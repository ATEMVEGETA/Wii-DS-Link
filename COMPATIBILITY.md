# Compatibility

## Tested so far

| Wii title | DS title/save | Confirmed result | Notes |
| --- | --- | --- | --- |
| My Pokémon Ranch | Pokémon Diamond | Connected; deposit, save, disconnect, reconnect, and withdrawal exercised | Game and save must be compatible with Ranch |
| My Pokémon Ranch | Pokémon Pearl | Connected and transfer exercised | Same Wii–DS link path as the Diamond test |
| Pokémon Battle Revolution | Compatible DS Pokémon game with correctly paired save | Connected; Download Play and Pokémon data copy exercised | A previously paired Battle Revolution save can reject a different DS game/save identity |
| Pokémon Battle Revolution, DS Battle Mode | Four compatible DS Pokémon games/saves | Four DS players connected and gameplay worked; participant disconnect/rejoin confirmed | Four is this game's player limit |

The public package is **v0.2.0-beta.1**. It contains the same emulator
executables used for the successful multi-DS test. The tester also confirmed
the one-DS Ranch transfer/save/shutdown regression checks. These are user
reports, alongside the automated checks below; they do not establish
compatibility with every region, revision, or save.

## Capacity and automated validation

The bridge can track 15 associated DS clients. Each Wii game applies its own
player limit; Battle Revolution's DS Battle Mode accepts four. Automated
checks passed with eight DS clients, including separate processes, and
covered one-DS regressions, lifecycle, radio identity, and disconnect handling.
Eight-player retail gameplay has not been tested. The 15-client capacity is
an implementation limit, not a claim that a particular game supports 15 players.

## Not certified yet

- Other Wii–DS game combinations.
- Retail gameplay with more than four DS participants.
- Internet or LAN play between two computers.
- Connections to a physical Wii or Nintendo DS.
- Every region, revision, emulator timing setting, or save history.

Wii–DS software shares lower-level Nintendo wireless mechanisms, but games can
use different Download Play clients, timing, framing, application protocols,
and cartridge/save identity checks. Therefore success in one game is valuable
protocol coverage, not automatic proof for every title.

When reporting a new result, state the Wii game and region, DS game and region,
exact release version, whether the connection completed, and the last screen
shown by each game. Do not attach copyrighted game data or personal saves.
