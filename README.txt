RedCraft - Minecraft inside Red Dead Redemption 2 (story mode)
================================================================

An experimental mod. Minecraft runs hidden next to the game: you move, build, break, fight and
blow things up with Minecraft's rules, inside RDR2's world.

IN THIS ZIP
  RedCraft.asi          the mod (put it next to RDR2.exe)
  RedCraft-source.zip   the full source code, ready to upload to GitHub
  README.txt            this file

YOU ALSO NEED (not included)
  1. Script Hook RDR2   http://www.dev-c.com/rdr2/scripthookrdr2/
                        Copy ScriptHookRDR2.dll and dinput8.dll next to RDR2.exe.
  2. SkyCraft           https://github.com/chasmlol/SkyCraft
                        RedCraft uses SkyCraft's bundled Minecraft, which SkyCraft installs to
                        %LOCALAPPDATA%\SkyCraft\Prism (instance "SkyCraft").
  3. Graphics API = DirectX 12 in the game's settings (Graphics > Advanced). On Vulkan,
     nothing of Minecraft is shown.

INSTALL
  1. Install the two things above.
  2. Copy RedCraft.asi next to RDR2.exe.
  3. Start the game in STORY MODE and load a save where you are on foot.
  4. Wait about half a minute: Minecraft starts by itself, and its hotbar appears when it is ready.

CONTROLS
  WASD / Space / Shift   move (Minecraft movement)
  Mouse                  look, left click break / hit, right click place / use
  1-9, wheel             hotbar
  E / T                  inventory / chat
  F5                     third-person views
  O                      Minecraft's menu
  Esc                    the game's pause menu
  F10                    give the character back to the game (and back to Minecraft)

GOOD TO KNOW
  - Story mode only. Script Hook closes the game if you go into Red Dead Online.
  - Riding, driving and cutscenes hand the character back to the game until you are on foot.
  - Arrows do not hurt characters yet. TNT, building and breaking work.
  - Blocks show through walls, and collision has holes here and there. It is a prototype.
  - A log is written to %LOCALAPPDATA%\RedCraft\redcraft.log
  - To remove the mod, delete RedCraft.asi.

Not affiliated with Rockstar Games, Mojang or Microsoft.