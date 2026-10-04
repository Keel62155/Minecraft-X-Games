# Minecraft X Games

Experimental mods that put **Minecraft inside other games**. Minecraft runs hidden next to the game
and the two talk to each other: the game supplies the shape of its world, Minecraft supplies the
player's movement, its blocks, its hand and its hotbar. You walk, build, break, fight and blow
things up by Minecraft's rules, inside the other game's world.

These are prototypes. Expect rough edges.

## The mods

| Mod | Game | Kind of mod | Download |
| --- | --- | --- | --- |
| **RedCraft** | Red Dead Redemption 2 (story mode) | ASI plugin for Script Hook RDR2 | [Releases](../../releases) |
| **PeakCraft** | PEAK | BepInEx 5 plugin | [Releases](../../releases) |

Each release is a zip with the mod, a README for that game, and a second zip with the full source code.

## What every mod needs

**SkyCraft** — <https://github.com/chasmlol/SkyCraft>

All of these mods use SkyCraft's bundled Minecraft, which SkyCraft installs to
`%LOCALAPPDATA%\SkyCraft\Prism` (instance `SkyCraft`). Install SkyCraft first. It is not included here.

**Only run one of these mods at a time.** They all drive the same Minecraft, so two games at once
(or one of these next to Skyrim's SkyCraft) will fight over it.

---

## RedCraft — Red Dead Redemption 2

### You also need

1. **Script Hook RDR2** — <http://www.dev-c.com/rdr2/scripthookrdr2/>
   Copy `ScriptHookRDR2.dll` and `dinput8.dll` next to `RDR2.exe`.
2. **Graphics API set to DirectX 12** in the game's settings (Graphics > Advanced).
   On Vulkan nothing of Minecraft is shown.

### Install

1. Install SkyCraft and Script Hook RDR2.
2. Copy `RedCraft.asi` next to `RDR2.exe`.
3. Start the game in **story mode** and load a save where you are on foot.
4. Wait about half a minute: Minecraft starts by itself, and its hotbar appears when it is ready.

Story mode only. Script Hook closes the game if you go into Red Dead Online.

### Controls

| Key | What it does |
| --- | --- |
| WASD / Space / Shift | Move (Minecraft movement) |
| Mouse | Look; left click break / hit, right click place / use |
| 1-9, wheel | Hotbar |
| E / T | Inventory / chat |
| F5 | Third-person views |
| O | Minecraft's menu |
| Esc | The game's pause menu |
| F10 | Hand the player back to the game, and take them again |

### Remove

Delete `RedCraft.asi` (and `ScriptHookRDR2.dll` and `dinput8.dll` if you want the game fully stock).

---

## PeakCraft — PEAK

### You also need

**BepInEx 5** for PEAK, for example through Thunderstore Mod Manager or r2modman.

### Install

1. Install SkyCraft and BepInEx.
2. Make the folder `BepInEx\plugins\PeakCraft` in your BepInEx profile (or in the game folder).
3. Copy `PeakCraft.dll` into it.
4. Start PEAK. Minecraft starts by itself a second later, minimised; when its hotbar shows at the
   bottom of the screen it has the scout.

### Controls

| Key | What it does |
| --- | --- |
| WASD / Space / Shift, mouse | Minecraft's movement and looking |
| Left / right mouse | Break / place blocks |
| 1-5, wheel | Minecraft's hotbar |
| 6, 7, 8 | The scout's own three item slots (mouse buttons use the item) |
| 9 or F10 | PEAK mode: the scout climbs by the game's own rules (again to go back) |
| F | Pick up / interact (also opens luggage) |
| Q | Drop the scout's item while one is held |
| E / T | Minecraft's inventory / chat |
| O | Minecraft's menu |
| F5 | Third-person views |
| Esc | PEAK's pause menu |

Every new game starts with a clean Minecraft world: blocks placed, broken or dug in the last game
are not carried over.

### Remove

Delete the `PeakCraft` folder from `BepInEx\plugins`.

---

## Known problems

- **RedCraft:** while the game holds the player (cutscenes, scripted moments, riding, driving),
  Minecraft stays out until you are on foot again.
- **PeakCraft:** PEAK's own sound can go quiet while Minecraft has the scout. Digging into the
  mountain has had little testing. Other players in a lobby see your scout slide about rigidly.
- Both are single-player-minded: what you build is on your own screen only.

## When something goes wrong

| Mod | Where the log is |
| --- | --- |
| RedCraft | `%LOCALAPPDATA%\RedCraft\redcraft.log`, and `ScriptHookRDR2.log` next to `RDR2.exe` |
| PeakCraft | `BepInEx\LogOutput.log` in your profile (lines from `PeakCraft`) |
| Minecraft | `%LOCALAPPDATA%\SkyCraft\Prism\instances\SkyCraft\.minecraft\logs\latest.log` |

## Building from source

Each release contains a `*-source.zip` with its own build notes.

- **RedCraft:** C++ with CMake and Visual Studio 2022; needs the Script Hook RDR2 SDK.
- **PeakCraft:** C#; `build.ps1` compiles against your own copy of the game, with nothing downloaded.

## Credits

Built on [SkyCraft](https://github.com/chasmlol/SkyCraft), whose Minecraft side and shared-memory
bridge these mods talk to. Not affiliated with Mojang, Microsoft, Rockstar Games or the makers of PEAK.
Use at your own risk, and keep these out of online modes that do not allow mods.
