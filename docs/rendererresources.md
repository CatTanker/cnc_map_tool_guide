# Renderer Conguration
## Renderer Choices

Typically bundled with the CnCNet Client, there are several renderers you have that you can choose from. These improve compatibility with modern operating systems and if you pick right could make the game playable as well as drastically impact performance.

### CnC-DDraw
For most users, you should start with [CnC-DDraw](https://github.com/FunkyFr3sh/cnc-ddraw), which is currently the most developed and maintained renderer. Most mods ship this simply as a `CnC-DDraw` option inside the client's options menu. If the game seems to run slowly or you face issues such as being unable to return to the game itself after clicking the pause menu (or have an invisible mouse), head into `ddraw.ini` and change `renderer=auto` to `ogl`, then `dx`, then `gdi` and see which provides you with the best experience. ideally this would be a client option or through the exe listed below. 

If you are not using the CnCNet Client, or are using a mod that has an updated client as of 2026, then you can use the `cnc-ddraw config.exe` application to configure settings rather than doing it through `ddraw.ini` manually in the root or topmost folder of your game.

If you are on an older client, and wish to use `cnc-ddraw config.exe` , the you may need to move this into your Resources folder and edit the `Resources/cnc-ddraw.ini` file here, as on launch the client copies certain settings to the root folder (mostly scaling features).

### TS-DDraw
Assuming this does not solve your issue, you should try the [TS-DDraw](https://github.com/CnCNet/ts-ddraw/releases) renderer and all of the choices available (through the same method as you would with Cnc-DDraw above). Ultimately TS-DDraw is a much older, unmaintained renderer compared to CnC-DDraw, so typically fixing settings on CnC-DDraw is a more effective method. Several mods include the backend renderer options above, so in cases this can quickly fix an issue if you have issues such as not being able to return to the game after pausing, which GDI often seems to fix. Clicking an options such as TS-DDraw-GDI is often the quickest way to fix the tab breaking the game bug, although it is at the cost of using an outdated renderer. 

### DDrawCompat
Another popular renderer is [DDrawCompat](https://github.com/narzoul/DDrawCompat) which is another DLL wrapper which works using the native DirectDraw libraries, rather than converting it to a later format such as CnC-DDraw. This is not compatible with DXVK however (see below), but is nonetheless a popular choice and is still maintained. 

### Other
There are also a number of edge case renderers such as DxWnd, DDWrapper and IE-DDraw which are much older, relatively unmaintained and often not included in CnCNet. These often have a highly specific purpose that has relatively no use for most users. There have been discussions regarding dropping thse from mod clients altogether, and in cases this has already happened, so it is not recommended to use these unless you know what you are doing, and even then the purpose of these renderers may exist elsewhere, such as in CnC-DDraw.

## Scaling with CnC-DDraw

[Example Image Requested (see the footer)]

For a game without any zoom functions such as TS and YR, and given the games were intended for 800x600 screens 20+ years ago, visibility can become an issue. This is especially apparent in TS due to the game having smaller cells, parts such as infantry and minimaps may become extremely difficult to distinguish.

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
Rather than using Rampastring's example image in his moddb post, I would appreciate any donation examples of such scaling in use in a non-DTA environment, to show how it performs in a non-total-conversion mod. The screenshots can be in a game or mod of your choice, as long as you provide a before (same resolution but without scaling) and after (with scaling) plus a config (which renderer settings were being used). Message me on discord or file an issue if you are willing to lend a hand. Thanks! Native resolution should be QHD or higher.
