# Tools
## Required Map Editors

### [FA2] Final Alert 2:

The Map Editor for Yuris Revenge. <br />
Contains patches which have been developed by multiple members of the community <br />
The patched FA2 link provides a clean working FA2 setup for the vanilla game (RA2/YR Unmodded)
The FA2Sp link directs you to the extension itself, which can be dropped into a mod's FA2, and should work fine assuming you check the changelog under releases <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Patched FA2 [Vanilla] | [PPM - Forum](https://ppmforums.com/topic-47342/final-alert-2-yr-v102-patches/) |
| FA2SP [Mods] | [Github - Main Page](https://github.com/secsome/FA2sp)|
| FA2SP [Mods] | [Github - Releases](https://github.com/secsome/FA2sp/releases)|

### [FS] Final Sun:

Description: The necessary Map Editor for Tiberian Sun + Firestorm <br />
The Patched FS option is directly compatible with TS. It contains some of fa2sp's features, so it is a massive improvement over the unmodded editor.
The toolkit option attempts to provide a direct application using several of the tools listed below. The forum contains a link to an older fork of FS that may be useful to some.
The Tiberian Sun Client [TSC] also includes a build.

| Topic | Source + Link |
| ------------ | ------------- |
| Patched FS [Vanilla] | [PPM - Forum](https://ppmforums.com/topic-47355/finalsun-101-patches/) |
| "Toolkit" + Clutter | [CnCNet - Forum](https://forums.cncnet.org/topic/6720-final-sun-complete-fixed/) |
| Tiberian Sun Client | [ModDB](https://www.moddb.com/mods/tiberian-sun-client) |

### Editor Modifications:
#### DDraw Renderer

Instead of using the system DDraw, FA2 and FS can instead use a local proxy DDraw.dll, improving the editor's speed considerably, which is especially useful for resource-heavy maps.
Several of the *patched* map editors have this included but not in use, so check your map editor's folder as the files may already exist, such as in a "ForWindows10" folder, containing a pre-configured setup. if you want an un-configured setup for unknown reasons, or simply want to know more about the wrapper, check the unconfigured link below. I also included a direct download, although i have lost which thread this is on so i am unable to verify if it is the latest download.

| Topic | Source + Link |
| ------------ | ------------- |
| Unconfigured  |[BitPatch](http://bitpatch.com/ddwrapper.html)|
| Pre-Configured|[PPM](https://ppmforums.com/download.php?id=72031&sid=5b50cb3c1696d792adb195e4360b46fd)|

#### Dark and Custom themes

Assuming you use the Sp version of the editor, it is certainly possible to modify the theme. This comes with a risk however, as on windows you have to modify your entire system's theme in order to achieve this, and if you install the wrong theme or mess something up you could easily break your system. There are a number of windows 'ricing' tutorials and lists online, but a lot of recommendations from major publishers seem to only use what windows 10+ already allows you to do, which doesn't really help you. I found and recommend [this](https://www.reddit.com/r/Windows10/comments/168y7dn/ultimate_simplified_guide_how_to_make_windows_10/) as it describes most options available for modernising windows 10, with a lot being applicable to Windows 11 as well. While you are of course free to read the entire section, you should focus on the `Before Starting` and the themes section. I have included below an example of what FA2 looks like using dark theme from [rectify11](https://rectify11.net) on Windows 11.

![Rectify11 FA2](Assets/win11_themed.png)

Another example is After Dark CC Blue, provided by SCIPCION on Windows 10
![AfterDarkCC](Assets/after_dark_cc.png)

Ultimately it is your decision if you wish to risk modifying windows in such a way, especially with WAE as a modern alternative. I have also written advice on applying a dark theme in [linux](linux.md), however the options are more limited.


<!---#| Github |[Link](https://github.com/FunkyFr3sh/cnc-ddraw)| -->
## Modern Alternatives:

### World Altering Editor : <br />
Author: Rampastring + Contributors  <br />
Description: The World Altering Editor (WAE) is an open source replacement to the traditional editors. unlike the originals, it is built using a modern code base, and as a result of being open source it does not require the use of dll injection to improve. Formerly known as the DTA Scenario Editor, as it was built for [Dawn of the Tiberium Age](https://www.moddb.com/mods/the-dawn-of-the-tiberium-age), it has since been growing in compatability for TS/YR. A release for TSClient and Vanilla YR both available on the the releases page. As of v0.9.6 the editor now has a voxel renderer, meaning that the editor can effectively replace FA2 for all quality PCs using win7 or later, although it is arguably still behind in a few areas.

| Topic | Source + Link |
| ------------ | ------------- |
| World Altering Editor | [Github - Main Page](https://github.com/Rampastring/TSMapEditor) |
| World Altering Editor | [Github - Releases](https://github.com/Rampastring/TSMapEditor/releases) |
| Mod Haven Channel | [Discord](https://discord.gg/k4SVuMm) |

<iframe width="560" height="315" src="https://www.youtube.com/embed/jIcr3nCqx7M?si=sHyZGT08GEpVWEnU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/RIgVMWZy80I" title="World Altering Editor - A new map editor coming to RotE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

### Others:
Relert ++                                             : <https://github.com/secsome/relertplusplus> <br />
Relert Sharp Private Thread                           : <https://github.com/FrozenFog/relertsharp> <br />
https://github.com/FrozenFog/rs-dev-public-snapshot/blob/dev/pic/preview-migdal.png
https://github.com/FrozenFog/rs-dev-public-snapshot

## Additional Tools:

### Trigger Analyser (html/java) <br />
Author: Whensons <br />
Description: A tool in javascript to analyse and map out triggers in a graph. This shows the connections, links and is useful for spotting issues within your triggers, and is excellent for collaborative projects. <br />
Although it is hosted on GitHub you can download the page and use it offline. <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Self-documentation | [Github - Main Page](https://github.com/whensonZWS/Trigger-Analyzer) |
| Hosted Tool | [Github Pages](https://whensonzws.github.io/Trigger-Analyzer/) |

###  Trigger Analyser (Python) <br />
Author: FrozenFrog <br />
Description: A script to generate a trigger map graphically on the TS/RA2 Engine.<br />

| Topic | Source + Link |
| ------------ | ------------- |
| Self-documentation | [Github - Main Page](https://github.com/FrozenFog/Ra2-Map-TriggerNetwork) |

### Map Conversion Tool <br />
Author:  Starkku <br />
Description: A tool which can convert the theatre, tiles, rules and overlay of maps based off user-configurable scripts. Essential if you wish to change the theatre of a map.  <br />

| Topic | Source + Link |
| ------------ | ------------- |
| General Information | [Github - Main Page](https://github.com/Starkku/MapTool) |
| Preset Documentation | [Github - Main Page](https://github.com/Starkku/MapTool/blob/master/Conversion-Profile-Documentation.md) |
| Preset Download | [Github - Releases](https://github.com/Starkku/MapTool/releases/tag/2.0.1.0) |
| Forum Thread | [PPM - Forum](https://ppmforums.com/topic-43411/) |

### Tunnel Drawer <br />
Author: Q45 <br />
Description: A tool to generate tunnels in TS/YR Maps.  <br />
This allows customisation of coordinates, direction, path, ect <br />
However, it is .SWF so requires a flash player. <br />
WARNING: No longer supported as it requires flash, i recommend using WAE's tunnel tools instead. <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Forum Thread | [PPM - Forum](https://ppmforums.com/topic37881/tsra2tunneldrawer/) |
| Flash Player | [Adobe](https://www.adobe.com/support/flashplayer/debug_downloads.html) |

### Wavemaker <br />
Author: PTapioK <br />
Description: A brilliant tool which streamlines the production of mission and survival maps <br />
It allows manipulation of Triggers, Scripts, Taskforces, Teams and Variables on both a single and batch scale through an easy-to-see user interface. <br />


| Topic | Source + Link |
| ------------ | ------------- |
| Forum Thread | [PPM - Forum](https://ppmforums.com/viewtopic.php?t=40202&start=0&postdays=0&postorder=asc&highlight=&sid=4e24b30fb8ab401c146e831491db9400) |
| Source Code| [Github - Main Page](https://github.com/PTapioK/TSWaveMaker) |

### Map Renderer <br />
Author: zzattack + Others <br />
Description: A Full Map Preview Renderer for maps <br />
Also contains other features such as height maps, position markers as well as debug features! <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Forum Thread | [PPM - Forum](https://ppmforums.com/topic-29554-page-5/cnc-maps-renderer-rewritten-works-for-tiberian-sun-and-ra2/?postorder=asc) |
| Source Code| [Github - Original Source (https://github.com/zzattack/ccmaps-net) |


### Map Resize Tool <br />
Author: E1 Elite <br />
Description: A tool to resize maps. Unlike the standard map editor this moves everything, including tunnels and smudges. The UI is also very simply to understand. <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Forum Thread | [PPM - Forum](https://ppmforums.com/topic55391/mapresize/) |
| Source Code| [Github - Main Page](https://github.com/E1Elite/MapResize) |

### Final Sun Toolkit <br />
Author: Holland (and various other authors for the tools) <br />
Description: Software which contains multiple tools with it, as well as other optimisations. TS Only <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Forum Thread | [PPM - Forum](https://ppmforums.com/topic48112/afinalsunstandalonewithcncmodsandtoolkit/) |

### Map Rename Tool <br />
Author: Snark <br />
Description: This program will convert your .map file names to the map name written internally. It's useful for organizing the maps that you download inside the cncnet client that are given a random file name, and means you can tell which map is which <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Direct Download | [Google Drive](https://drive.google.com/file/d/1IVkd7O1uWMVXdEi2BFbULCHilAHTGXU/view?usp=sharing) |

### Trigger Index Parameter Tool <br />
Author: Starkku <br />
Description: A simple GUI program for adjusting numerical index values used as parameters for map trigger events & actions aswell as AI team scripts in Command & Conquer: Tiberian Sun & Red Alert 2. Useful for Mod / Mission developers to fix any issues that occur after a house index change. <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Source Code | [Github - Main Page](https://github.com/Starkku/TriggerIndexParamTool) |

### Map Tool <br />
Author: vananasun <br />
Description: A command line tool to manipulate Red Alert 2 Yuri's Revenge maps <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Source Code | [Github - Main Page](https://github.com/vananasun/yr-maptool) |

### MISTEST  Map Checker <br />
Author: GE <br />
Description: "Mission Tester is designed primarily to help troubleshoot mission maps, but is useful for quickly resolving trigger or object placement errors on mutiplayer maps as well. It will warn of errors like objects outside of the map bounds, often caused by resizing maps, it will find errors like missing waypoints for actions, or even nonexistent sounds being played." <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Forum Thread | [PPM - Forum](https://www.ppmforums.com/topic-68090/) |

