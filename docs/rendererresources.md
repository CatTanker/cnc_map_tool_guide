# Renderer Conguration
## Renderer Choices

Typically bundled with the CnCNet Client, there are several renderers you have that you can choose from. These improve compatibility with modern operating systems and if you pick right could make the game playable as well as drastically impact performance.

For most users, you should start with [CnC-DDraw](https://github.com/FunkyFr3sh/cnc-ddraw), which is currently the most developed and maintained renderer. Most mods ship this simply as a `CnC-DDraw` option inside the client's options menu. If the game seems to run or you face issues such as being unable to return to the game itself after clicking the pause menu (or have an invisible mouse), head into `ddraw.ini` and change `renderer=auto` to `ogl`, then `dx`, then `gdi` and see which provides you with the best experience. Be aware that the changes you make in the cnc-ddraw configuration exe tend to be overwriten by the client on game launch.

Assuming this does not solve your issue, you should try the [TS-DDraw](https://github.com/CnCNet/ts-ddraw/releases) renderer and all of the choices available (OpenGL, GDI, etc, same as CnC-DDraw)

Another popular renderer assuming the above two struggle is [DDrawCompat](https://github.com/narzoul/DDrawCompat) which is another DLL wrapper which works using the native DirectDraw libraries, rather than converting it to a later format such as cnc-ddraw. This is not compatible with DXVK however, and is included in the Steam edition of YR by default.

There are also a number of edge case renderers such as DxWnd, DDWrapper and IE-DDraw which are much smaller, often an older development and have relatively little support, configuration and documentation available. These may help a small minority of people but other alternatives should be preferred and tested first.


## Using DXVK
### Summary
![Vulkan Logo](https://d29g4g2dyqv443.cloudfront.net/sites/default/files/Vulkan_Logo.png)

[DXVK](https://github.com/doitsujin/dxvk) is a Vulkan-based translation layer for Direct3D 9/10/11 that was initially intended for usage on Linux systems using wine/proton. I highly recommend enabling this if you are using Linux as it requires very little effort to set up, especially if you are using GUI tools such as [bottles](bottles.md), winetricks or lutris. This is well-tested and is in some cases enabled by default for people running Windows games on Steam using Proton.

While this does not have a major effect, comparing using the `renderer=gdi` inside `draw.ini`, I received around 30 more fps (with uncapped fps) running the same 1v1 skirmish map inside MO 3.3.6 with dxvk enabled than with it disabled. I also felt the game was a bit smoother, with the fps having less variance and rarely dropping below 300 with dxvk on compared to running often around the 280-310 mark without dxvk. Tested using Bottles Caffe on Linux, with an I5-2500K. I am also using an NVIDIA GPU, and given that dxvk was initially developed for AMD I am likely not receiving the full performance benefit. In comparisons using Fading Dusk, I also received around 30fps more in each renderer setting, although the overall fps was consistently lower on all settings due to TS's smaller cell size meaning more is rendered at once. Other users have confirmed the average increase to more accurately be at around a 10% FPS increase, or at around 10-15fps in more realistic settings.

Performance increases will vary between PCs. Older PCs that support Vulkan will certainly notice the difference and if you do not regularly achieve 60fps, you may be able to now. Top-of-the-range PCs will benefit less, as the chances are your CPU can cope with whatever is thrown at it. It may help if you decide to run an extremely intensive map, such as some of the larger campaign maps included in mods. Since it is typically very hard to play at anything above 200fps, and online can sometimes struggle to reach 30fps given connection limitations, the benefits may be missed.

However, although support may be more limited due to Windows not being the the original development target, you can use this on Windows for YR and TS, simply check below.

NOTE: Your GPU **NEEDS** to support Vulkan for you to use this.

### Installation for Windows
Please note this assumes your game works without any issues. You may also need to install Vulkan libraries if you haven't already.

Pre-Instillation: please run the game and follow `Settings/Pause Menu --> Game Controls --> keyboard --> Development --> FPS Counter` and set the hotkey of this to something that you can easily access but doesn't overwrite anything, such as `/`. For TS, you need to find the Toggle Info Panel option and set that to an unused hotkey instead. This allows us to compare the speeds of the game beforehand and afterward. I recommend heading ingame and taking note of the FPS you can achieve in a game with uncapped speed control.

DXVK has also received light testing on YR and MO. I am aware that several people have extensively used this method, and both in an online environment and in singleplayer. There have been no reports of this leading to a desync, so this should be safe to use, and i recommend it especially if you are using `renderer=dx`.

1. Install DXVK into your game's folder
    1. Head to DXVK's [releases page](https://github.com/doitsujin/dxvk/releases).
    2. Download the `dxvk.x.x.tar.gz` file and open it. You may need a [file archiver](https://www.7-zip.org/) to open it.
    3. Head into the x32 folder and copy only the **d3d9.dll** file.
    4. Paste this into your game's top folder, where gamemd.exe or TiberianSun.exe are located.

2. Install CnC-DDraw.
    Your instillation, especially if it uses cncnet, likely already has cnc-ddraw. Updating to the latest version is recommended.
    1. Open the client, and make sure the renderer is set on cnc-ddraw in settings. If it is not, then change it.
    2. Exit the client.
    1. Head to CnC-DDraw's [releases page](https://github.com/FunkyFr3sh/cnc-ddraw/releases).
    2. Download `CnC-DDraw.zip` to your PC.
    3. Extract this into your game's top folder, where gamemd.exe or TiberianSun.exe are located.


3. Testing
    If you are not using the cncnet client, then the following section will apply directly to you. If you are, you will need to follow these steps by editing the `ddraw.ini` fine manually. if you are using a recent build of the cncnet client and/or have configured phobos to set the 6 speed options to a specific rate, then you will not be able to test the unlimited fps amount.
    1. Open the configuration exe listed above, head to Advanced Settings, and turn off limit frame rate.
        1. Renderer and change from `automatic` to `Direct3D 9`. For cncnet client users, you need to enter `ddraw` and change `renderer=(presumably "auto")` to `renderer=dx`
        2. Run the game. Use the hotkey you assigned earlier to study the FPS, and check that entering the tab menu (diplomacy menu) and options menus (save game, game controls, exit game) and heading back into the game itself all work fine.
        3. Exit and make a note of the FPS and how well it runs (compatibility as listed above, and how smooth the game feels).
        4. Repeat the last 3 steps but using OpenGL (`ogl`) and (`gdi`).
    3. Open `cnc-ddraw config.exe` again and set the renderer to always be the best running one. For cncnet client users, you simply need to edit the `ddraw.ini` file back to using the ideal renderer.
    4. Decide if you want to turn on `limit frame rate` again.
4. Profit!


If you decide that your game is less stable, you run into difficulties or simply have fps drops then to uninstall you simply delete `d3d9.dll` from your folder.

## Scaling with CnC-DDraw

[Example Image Requested (see the footer)]]

For a game without any zoom functions such as TS and YR, and given the games were intended for 800x600 screens 20 years ago, visibility can become an issue. Especially apparent in TS due to the game having smaller cells, parts such as infantry and minimaps may become extremely difficult to distinguish.

Before starting, I highly recommend that you head to CnC-DDraw's [releases page](https://github.com/FunkyFr3sh/cnc-ddraw/releases) to overwrite your existing ddraw components and ensure you have the latest.

Follow [this tutorial](https://www.moddb.com/members/rampastring/blogs/tutorial-sharp-scaling-dta-and-other-client-based-games-with-cnc-ddraw) on setting up scaling for DTA. This also applies to every mod using cnc-ddraw and the cncnet client. If the resolution you need to scale from, such as 960x540 for 1080p scaling, does not exist as an option inside the client, then you can add this to your game's original ini file, such as SUN.ini for TS.


If you wish to configure the upscaling process further, follow the steps below.

For OpenGL:

According to the latest `ddraw.ini`:
```ini
; Preliminary libretro shader support - (Requires 'renderer=opengl*') https://github.com/libretro/glsl-shaders
; 2x scaling example: https://imgur.com/a/kxsM1oY - 4x scaling example: https://imgur.com/a/wjrhpFV
; You can specify a full path to a .glsl shader file here or use one of the values listed below
; Possible values: Nearest neighbor, Bilinear, Bicubic, Lanczos, xBR-lv2
shader=...
```
Note this is also configurable from `cnc-ddraw config.exe` that is provided from CnC-DDraw's [releases page](https://github.com/FunkyFr3sh/cnc-ddraw/releases).

For the Direct3D9 renderer, enter ddraw.ini and test out the following options ingame to see which you prefer.
According to the latest `ddraw.ini`:
```ini
; Upscaling filter for the direct3d9* renderers
; Possible values: 0 = nearest-neighbor, 1 = bilinear, 2 = bicubic, 3 = lanczos (bicubic/lanczos only support 16/32bit color depth games)
d3d9_filter=...
```

GDI as a renderer does not scale well there is no scaling option other than linear scaling.


Image Request:
Rather than using Rampastring's example image in his moddb post, I would appreciate any donation examples of such scaling in use in a non-DTA environment, to show how it performs in a non-total-conversion mod. The screenshots an be in a game or mod of your choice, as long as you provide a before (same rewsolution but without scaling) and after (with scaling) plus a config. Message me on discord or file an issue if you are willing to lend a hand. Thanks! Native resolution should be QHD or higher.
