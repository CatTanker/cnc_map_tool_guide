## Using DXVK
### Summary
![Vulkan Logo](https://d29g4g2dyqv443.cloudfront.net/sites/default/files/Vulkan_Logo.png)

[DXVK](https://dxvk.org/) is a Vulkan-based translation layer for Direct3D 8/9/10/11 that translates such calls into Vulkan, which is an effecient cross platform graphics API that can reduce CPU bottlenecks. I suggest reading more about it in their own explanation [here](https://dxvk.org/can-dxvk-fix-stuttering-issues/). While this was initially developed for Linux Gaming, this can be used on Windows and may provide minimal improvements to the smoothness of the game. I recommend enabling it for any Linux users, as shown in the Linux Guide i wrote, which requires minimal effort to apply and use for all intended applications.

The influence of DXVK on your system's fps may be marginal, and you do require a card that supports vulkan to use it. On my system i received around 30fps more in a 1v1 skirmish map in Mental Omega 3.3.6, and the same on brief testing of a Fading Dusk map with this enabled. Inside MO I went from frequently dropping below 300 to consistently being in the 290-310 mark, which for users in high Hz monitors may be a nicer experience. Note this is with uncapped fps and on Linux with Bottles. Other users who tested it on Windows and sent me their results said they got around a 10-15% fps increase. 

DXVK has also received light testing on YR and MO. I am aware that several people have extensively used this method, and both in an online environment and in singleplayer. There have been no reports of this leading to a desync or crash, so this should be safe to use. DXVK in itself is also heavily used in other applications and games, such as Fallout 4 and GTA IV to improve stability, as well as Minecraft recently changing the renderer fro OpenGL to Vulkan showing the API's uptake.

### Installation for Windows
Please note this assumes your game works without any issues beforehand. It is recommended especially if you have `renderer=dx` set rather than `auto` or `ogl`, but can be used either way. it is best used with `TS-DDraw` or `CnC-DDraw`.

Before and after, make sure you record your game's fps in the same scenario. To do this, run the game and follow `Settings/Pause Menu --> Game Controls --> keyboard --> Development --> FPS Counter` and set this to an unused hotkey, such as `/`.Run the game for a minute or two and record the average. It is up to you if you wish to check the uncapped fps or have it in a realistic 60fps or 45fps environment.

Note DXVK has also received light testing on YR and MO. I am aware that several people have extensively used this method, and both in an online environment and in singleplayer. There have been no reports of this leading to a desync, so this should be safe to use, and i recommend it especially if you are using `renderer=dx`. Be aware that this may not work on mods that use ReShade, such as Rise of the East, Tiberian Sun - Warzone, and Tiberium Crisis 1 & 2. 

To Install:
1. Head to DXVK's [releases page](https://github.com/doitsujin/dxvk/releases)
2. Download the latest `dxvk.x.x.tar.gz` file and open it. You may need a [file archiver such as 7-zip](https://www.7-zip.org/) to open it.
3. Head into the `x32` folder and copy only the `d3d9.dll` file.
4. Paste this into your game's top folder, where `gamemd.exe` or `TiberianSun.exe` are located.

If you decide that your game is less stable, you run into difficulties or simply have fps drops then to uninstall you simply delete `d3d9.dll` from your folder.
