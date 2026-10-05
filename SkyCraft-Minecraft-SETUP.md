# Setting up SkyCraft's Minecraft

Every "Minecraft X" mod on this page (RedCraft, GTACraft, CyberCraft, ReadyCraft, PeakCraft and
the rest) runs a real copy of Minecraft, hidden, next to the game. They all share the same one: the
Minecraft that [SkyCraft](https://github.com/chasmlol/SkyCraft) sets up.

This guide gets that Minecraft onto your PC. You do it **once**, and it then works for every mod.

**You do not need Skyrim.**

---

## What you need

| | What | Notes |
| --- | --- | --- |
| 1 | **Minecraft: Java Edition** | You must own it, on a Microsoft account. Bedrock Edition alone is not enough. |
| 2 | **SkyCraft's release** | Free, from <https://github.com/chasmlol/SkyCraft/releases> |
| 3 | About **1 GB** of free disk space | Minecraft, Java and the launcher |

---

## What you are setting up

A folder with a copy of **Prism Launcher** (a free, open-source Minecraft launcher) and a ready-made
Minecraft instance called **SkyCraft**. It has to be exactly here, because that is where the mods
look for it:

```
%LOCALAPPDATA%\SkyCraft\Prism
```

`%LOCALAPPDATA%` is a shortcut Windows understands. On most PCs it means
`C:\Users\<your name>\AppData\Local`.

Nothing is installed in the usual sense: it is a folder of files. It does not touch any Minecraft
you already have, your worlds, or the official launcher.

---

## Step 1: Do you already have it?

**If you play SkyCraft in Skyrim,** you have it already. SkyCraft unpacked it the first time Skyrim
started with SkyCraft installed. Go to [Step 4](#step-4-check-it).

**Everyone else:** carry on with Step 2.

---

## Step 2: Put the files in place

SkyCraft only unpacks its Minecraft when Skyrim starts. Without Skyrim, you unpack it yourself.
It takes about two minutes, all in File Explorer.

1. Go to <https://github.com/chasmlol/SkyCraft/releases> and download **`SkyCraft-0.1.2.zip`**
   (about 25 MB). You do not need the other files listed there.

2. Open that zip (double-click it). Go into **`SKSE`**, then **`Plugins`**, then **`SkyCraft`**.

3. In there is another zip, **`SkyCraft-Minecraft.zip`**. Open it too. You should see three things:
   - a `Prism` folder
   - a `defaults` folder
   - `bundle-version.txt`

4. Open a **second** File Explorer window. Click its address bar, type this and press Enter:

   ```
   %LOCALAPPDATA%
   ```

5. In the folder that opens, make a new folder called **`SkyCraft`** and open it.

6. Drag the three things from step 3 into your new `SkyCraft` folder. Wait for the copy to finish.

7. Open `defaults`, copy **`prismlauncher.cfg`**, and paste it into the **`Prism`** folder.
   (This gives the launcher sensible settings, such as fetching Java by itself.)

The other files in SkyCraft's zip (`SkyCraft.dll`, `SkyCraft.ini`) are for Skyrim. You can ignore
them.

---

## Step 3: Sign in and let it download Minecraft

The files from Step 2 do **not** contain Minecraft. The launcher downloads it from Mojang once you
have signed in with the account that owns it.

1. In `%LOCALAPPDATA%\SkyCraft\Prism`, start **`prismlauncher.exe`**.

   If Windows shows a blue "Windows protected your PC" box, click **More info**, then
   **Run anyway**. Prism Launcher is safe, but Windows does not recognise every open-source
   program.

2. Click the **account button** in the top right corner, choose **Manage Accounts**, then
   **Add Microsoft**. Follow the sign-in steps it shows.

3. Back in the main window, select the **SkyCraft** instance and click **Launch**.

   The first time, it downloads Minecraft and Java: about 700 MB, which takes a few minutes.

4. When Minecraft's title screen appears, you are done. Close Minecraft, then close the launcher.

You do not need to make a world or change any settings.

---

## Step 4: Check it

Paste this into File Explorer's address bar and press Enter:

```
%LOCALAPPDATA%\SkyCraft\Prism\instances\SkyCraft
```

If that folder opens, the files are in the right place. If you also saw Minecraft's title screen in
Step 3, everything is ready.

Now follow the setup guide of the mod you want. From here on, the mod starts this Minecraft by
itself, in the background, whenever you play. You will not see a Minecraft window.

---

## Good to know

- **One game at a time.** All the mods share this one Minecraft. Running two of them together, or
  one of them alongside Skyrim's SkyCraft, makes them fight over it.
- **It starts hidden.** When a mod is running, Minecraft is there but has no window. It closes by
  itself shortly after you close the game.
- **Your regular Minecraft is separate.** This copy has its own saves and settings inside the
  `SkyCraft` folder.
- **Adding your own Minecraft mods.** They go in
  `%LOCALAPPDATA%\SkyCraft\Prism\instances\SkyCraft\.minecraft\mods`. They must be **Fabric** mods
  for the same Minecraft version as the instance. A mod with a missing requirement stops Minecraft
  from starting at all, which breaks every "Minecraft X" mod until you take it out again.

---

## If something is wrong

**The game runs, but Minecraft's hotbar never appears**
- Do Step 4. If the folder does not open, the files are in the wrong place: redo Step 2 and check
  the folder is called exactly `SkyCraft`, directly inside `%LOCALAPPDATA%`.
- If the folder is there, you may have skipped Step 3. Start `prismlauncher.exe`, make sure an
  account is listed in the top right corner, and launch the SkyCraft instance once by hand.

**I ended up with `SkyCraft\SkyCraft-Minecraft\Prism` or `SkyCraft\SkyCraft\Prism`**
- One folder too many. Move `Prism`, `defaults` and `bundle-version.txt` up so that `Prism` sits
  directly inside `%LOCALAPPDATA%\SkyCraft`.

**The launcher says the account does not own Minecraft**
- You need Minecraft: **Java** Edition on that Microsoft account. Sign in with the account you
  bought it on, or buy it at <https://www.minecraft.net>.

**The launcher cannot download, or stops partway**
- Check your internet connection and click Launch again. It carries on from where it stopped.

**Minecraft's title screen never came up in Step 3**
- Launch the SkyCraft instance again and read what the launcher says. If it mentions Java, let it
  download Java when it asks.

**Minecraft seems to stay running after I close the game**
- Give it half a minute. If it is still there, open Task Manager and end `javaw.exe` and
  `prismlauncher.exe`.

**I want a clean start**
- Close everything, delete the `%LOCALAPPDATA%\SkyCraft` folder, and begin again at Step 2.

---

## Removing it

Delete this folder:

```
%LOCALAPPDATA%\SkyCraft
```

That removes the launcher, this copy of Minecraft and its saves. Nothing else on your PC was
changed, so there is nothing else to undo. (If you use SkyCraft in Skyrim, it will unpack the folder
again the next time Skyrim starts.)

---

## What is in the bundle

For anyone who wants to know what they are copying. All of it comes from SkyCraft's own release.

| Part | What it is | License |
| --- | --- | --- |
| Prism Launcher 11.1.1 | The launcher, as its unmodified portable Windows build | GPL-3.0 |
| SkyCraft mod | Lets the game and Minecraft talk to each other | MIT |
| Fabric API | The library Fabric mods are built on | Apache-2.0 |
| e4mc | Lets friends join over the internet | MIT |

Minecraft itself is not in the bundle. It is downloaded from Mojang by the launcher, under your own
account.

---

*SkyCraft is made by its own author and is not part of this project. This guide only explains how to
set up its Minecraft for use with the mods here. Not affiliated with Mojang or Microsoft.*
