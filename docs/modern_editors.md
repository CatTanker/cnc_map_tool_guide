This section covers improving the core experience of mapping. This includes both modifications to the original editors, and the alternatives that the community has made since, specifically the World Altering Editor.

### Editor Modifications:
#### DDraw Renderer

Instead of using the system DDraw, FA2 and FS can instead use a local proxy DDraw.dll, improving the editor's speed considerably, which is especially useful for resource-heavy maps.
Several of the *patched* map editors have this included but not in use, so check your map editor's folder as the files may already exist, such as in a "ForWindows10" folder, containing a pre-configured setup. if you want an un-configured setup for unknown reasons, or simply want to know more about the wrapper, check the unconfigured link below. I also included a direct download, although i have lost which thread this is on so i am unable to verify if it is the latest download.

| Topic | Source + Link |
| ------------ | ------------- |
| Unconfigured  |[BitPatch](http://bitpatch.com/ddwrapper.html)|
| Pre-Configured|[PPM](https://ppmforums.com/download.php?id=72031&sid=5b50cb3c1696d792adb195e4360b46fd)|

#### Dark and Custom themes

Assuming you use the Sp version of the editor, it is certainly possible to modify the theme. This comes with a risk however, as on windows you have to modify your entire system's theme in order to achieve this, and if you install the wrong theme for your windows version, your windows updates and therefore becomes incompatible with the theme you are using, or of course simply mess something up you could easily break your system and be left to the mercy of restore points or a fresh boot. There are a number of windows 'ricing' tutorials and lists online, but a lot of recommendations from major publishers seem to only use what windows 10+ already allows you to do, which doesn't really help you. I found and recommend [this reddit post](https://www.reddit.com/r/Windows10/comments/168y7dn/ultimate_simplified_guide_how_to_make_windows_10/) for the basics as it describes most options available for modernising theming 10, with a lot being applicable to Windows 11 as well. While you are of course free to read the entire section, you should focus on the `Before Starting` and the themes section.  If you decide to further rice your system, i [recommend this, as although it focuses on Windows 11 a lot of the tools work with 10.](https://github.com/twonth/winning-at-windows)

I have included below an example of what FA2 looks like using dark theme from [rectify11](https://rectify11.net) on Windows 11, which is available for free. Sadly the Windows 11 elements carry over, including spacings in dropdowns, and the extremely dark colour scheme doesn't sit too well.
![Rectify11 FA2](Assets/win11_themed.png)
---
Another example is After Dark CC Blue, provided by SCIPCION on Windows 10. I believe this is no longer available for free however.
![AfterDarkCC](Assets/after_dark_cc.png)
---
This example uses [fluent from niivu's Windows 10 Themes](https://github.com/niivu/Windows-10-themes). The creator also has a large collection of other windows 10 & 11 [themes](https://www.deviantart.com/niivu/gallery) that you can experiment with as well.
![Win10_Fluent](Assets/fluent.png)

Ultimately it is your decision if you wish to risk modifying windows in such a way, especially with WAE as a modern alternative. I have also written advice on applying a dark theme in [linux](linuxtools.md), however the options are more limited.


<!---#| Github |[Link](https://github.com/FunkyFr3sh/cnc-ddraw)| -->

### World Altering Editor : <br />
Author: Rampastring + Contributors  <br />
Description: The World Altering Editor (WAE) is an open source replacement to the traditional editors. unlike the originals, it is built using a modern code base, and as a result of being open source it does not require the use of dll injection to improve. 
Formerly known as the DTA Scenario Editor, as it was built for [Dawn of the Tiberium Age](https://www.moddb.com/mods/the-dawn-of-the-tiberium-age), it has since been growing in compatability for TS/YR.
 A release for TSClient and Vanilla YR both available on the the releases page. As of v0.9.6 the editor now has a voxel renderer, meaning that the editor can effectively replace FA2 for all quality PCs using win7 or later, 
 although it is arguably still behind in a few areas. As of version 1.0, the editor will require dotnet runtime 8, and is only built for Windows, although running it through modern wine solutions are an option for linux.

I **highly** recommend trying this editor out, as it contains a lot of new features that would be out of scope for FA2/FS. Check the [releases page](https://github.com/Rampastring/WorldAlteringEditor/releases) for an up-to-date YR and TSClient build. 
The releases page also includes a full changelog, which at the moment is the most comprehensive list of features. 

| Topic | Source + Link |
| ------------ | ------------- |
| World Altering Editor | [Github - Main Page](https://github.com/Rampastring/TSMapEditor) |
| World Altering Editor | [Github - Releases](https://github.com/Rampastring/TSMapEditor/releases) |
| Mod Haven Channel | [Discord](https://discord.gg/k4SVuMm) |

<iframe width="560" height="315" src="https://www.youtube.com/embed/jIcr3nCqx7M?si=sHyZGT08GEpVWEnU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/RIgVMWZy80I" title="World Altering Editor - A new map editor coming to RotE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

### Incomplete / WIP:
Mostly remains here as an archive of github links that *once* existed. Might be a useful reference one day.
Relert ++                                             : <https://github.com/secsome/relertplusplus> <br />
Relert Sharp Private Thread                           : <https://github.com/FrozenFog/relertsharp> <br />
https://github.com/FrozenFog/rs-dev-public-snapshot/blob/dev/pic/preview-migdal.png
https://github.com/FrozenFog/rs-dev-public-snapshot

