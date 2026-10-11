# Compatibility

## Tested so far

| Wii title | DS title/save | Result in the working test implementation | Notes |
| --- | --- | --- | --- |
| My Pokémon Ranch | Pokémon Diamond | Connected; deposit, save, disconnect, reconnect, and withdrawal exercised | Game and save must be compatible with Ranch |
| My Pokémon Ranch | Pokémon Pearl | Connected and transfer exercised | Same Wii–DS link path as the Diamond test |
| Pokémon Battle Revolution | Compatible DS Pokémon game with correctly paired save | Connected; Download Play and Pokémon data copy exercised | A previously paired Battle Revolution save can reject a different DS game/save identity |

The public package is **v0.1.0-beta.1**. It uses the same protocol work as the
successful tests and has passed isolated transport/startup validation, but the
exact packaged official-base binaries still need broader independent retail
transfer testing.

## Not certified yet

- Other Wii–DS game combinations.
- More than one melonDS participant at a time.
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
