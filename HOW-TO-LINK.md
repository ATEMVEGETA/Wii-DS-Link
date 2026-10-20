# How to link melonDS and Dolphin

These steps apply to Wii–DS Link v0.2.0-beta.2: the updated melonDS paired
with the unchanged Dolphin from v0.2.0-beta.1.

## 1. Extract both emulators

Download the combined Windows ZIP from the
[Wii–DS Link releases](https://github.com/ATEMVEGETA/Wii-DS-Link/releases) and
extract the entire archive to a normal writable folder. Do not run either
emulator from inside the ZIP.

The package contains:

- `melonDS-1.1-WiiDS-Link/melonDS.exe`
- `Dolphin-2609a-WiiDS-Link/Dolphin.exe`

Games, DS BIOS/firmware, Wii NAND data, and saves are not supplied. Configure
each emulator normally with your own legally obtained material.

## 2. Enable the paired link once

In melonDS:

1. If a game is running, use **System → Stop** first, then open
   **Config → Wi-Fi settings**.
2. Enable **Connect to Dolphin**.
3. Apply the setting.

In Dolphin, while no game is running:

1. Open **Configuration → Wii**.
2. Under **Misc Settings**, enable **Connect to melonDS**.
3. Close the configuration window.

Both settings are saved. You do not need to repeat them for every session.
For multiplayer, enable **Connect to Dolphin** in every melonDS instance.
The option is per instance, not a global switch: changing it in the first
window does not change other existing windows. In v0.2.0-beta.2, every window
can open Wi-Fi settings and edit its own Wii link option, including windows
whose saved setting is disabled. You do not need to delete or edit the TOML.
Shared LAN settings remain read-only in additional instances; they are
separate from the editable **Connect to Dolphin** option. A command-line
override, if used, still takes precedence over the saved link setting.

## 3. Start the games

You may open melonDS or Dolphin first. Emulator launch order does not matter.
The link becomes active only when the running games use their own Wii/DS
connection screens.

Use the normal in-game flow for the selected pair:

- **My Pokémon Ranch:** choose the DS connection option in Ranch and
  **Connect to Wii** in the compatible DS Pokémon game.
- **Pokémon Battle Revolution, Pokémon copy:** begin the copy/connection flow
  in Battle Revolution and choose **Connect to Wii** in the compatible DS game.
- **Pokémon Battle Revolution, multiplayer:** follow the steps below for DS
  Battle Mode.

Keep both games on their connection flows until Download Play and the
application link complete. Once connected, follow the games' own prompts and
save/disconnect normally.

## 4. Connect multiple DS players

Battle Revolution's **DS Battle Mode** supports up to four DS players.

1. Keep one Dolphin instance open. In melonDS, use **System → Launch new
   instance**, or open another process of the matching melonDS executable.
2. Enable **Connect to Dolphin** in each instance before loading its game.
   If already running, stop that instance's game first, change the option,
   and restart the game. There is no need to close the other instances.
   Give each player a separate writable game/save copy. Extra instances may
   use `.sav.2`, `.sav.3`, etc., falling back to the original save if a suffixed
   file is absent; do not let two instances write to the same save.
3. Make sure all instances continue running when unfocused. Disable
   pause-on-focus-loss if needed.
4. In Battle Revolution choose **DS Battle Mode → Start Entry** and wait for
   **Entry Standby**. The **Copy Pokémon** feature is a separate one-DS flow.
5. Choose **Connect to Wii** in each DS game, one after another, and complete
   its Download Play prompts. Leave connected participants running while the
   others join.
6. Continue once the trainers appear in Battle Revolution. Use the games'
   own controls to finish the battle and disconnect normally.

Opening order does not assign player numbers. The bridge has 15 client
slots, but each game enforces its own player limit. Four-player Battle
Revolution gameplay was confirmed on v0.2.0-beta.1; fresh retail confirmation
of this settings hotfix is pending. Eight-client automated transport checks
do not establish eight-player retail compatibility.

## Upgrading from v0.2.0-beta.1

With all melonDS instances closed, replace `melonDS.exe` with the
v0.2.0-beta.2 executable. Keep your existing TOML configuration and saves.
Dolphin is unchanged and does not need replacing. Previously disabled Wii
link settings in extra instances can now be enabled through Wi-Fi settings.

## Upgrading from v0.1.0-beta.1

Extract v0.2.0-beta.2 to a new folder and use both supplied emulators together.
Keep the older installation and your save backups until the new pair is
configured. Do not merge an old Dolphin `User` directory into the new package
as part of installing the binaries; transfer your own saves/settings
deliberately, with the emulators closed. The clean download includes no
personal configuration or saves.

## Important save rule for Battle Revolution

Battle Revolution can bind its save data to the DS game/save identity used for
an earlier copy. If it says the Pokémon copy failed while the DS was found and
Download Play ran, test with the correctly paired saves. This is a game rule,
not necessarily a transport failure.

Always keep backups before testing transfers. Do not close either emulator
while a game is actively saving.

## If it does not connect

1. Use v0.2.0-beta.2 melonDS with the supplied Dolphin, which is unchanged
   from v0.2.0-beta.1.
2. Confirm both connection options are enabled.
3. Use only one Dolphin instance. For multiplayer, use the new matching
   melonDS build for every participant and stay within the game's player limit.
4. Retry from both games' initial connection menus.
5. For Battle Revolution, confirm the Wii and DS saves belong to the expected
   paired game/save identity.
6. If Windows asks about network access, allow the programs on private
   networks. The bridge itself binds only to local IPv4 loopback ports
   `7065`–`7080`; it does not send traffic to real consoles or the internet.

Optional diagnostic logs are off by default. When enabled in each emulator:

- melonDS writes `wii-ds-bridge.log` in its working directory.
- Dolphin writes `User/Logs/wii-ds-bridge.log`.

The dedicated bridge logs contain scalar transport events, not game payloads,
Pokémon data, saves, or RAM dumps. When reporting a problem, include the game
regions, emulator release version, exact screen reached by each game, and the
two diagnostic logs if available. Do not upload copyrighted games, BIOS,
firmware, NAND data, or personal saves.
