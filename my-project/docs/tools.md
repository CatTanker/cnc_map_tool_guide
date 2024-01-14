# Tools
This documentation contains a comprehensive list of tools and resources (listed below) for producing maps for Tiberian Sun and Yuris Revenge, including source locations as well as a brief description
This github page also contains a growing volume of compatability tips and advice, including guidance on using CnC with Linux , within seperate .md files included in the github hierarchy. 
## Required Map Editors

### [FA2] Final Alert 2:

The Map Editor for Yuris Revenge. <br />
Contains patches which have been developed by multiple members of the community <br />
The patched FA2 link provides a clean working FA2 setup for the vanilla game (RA2/YR Unmodded)
The FA2Sp link directs you to the extension itself, which can be dropped into a mods FA2, and should work fine assuming you check the changelog under releases <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Patched FA2 [Vanilla] | [PPM - Forum](https://ppmforums.com/topic-47342/final-alert-2-yr-v102-patches/) |
| FA2SP [Mods] | [Github - Main Page](https://github.com/secsome/FA2sp)|
| FA2SP [Mods] | [Github - Releases](https://github.com/secsome/FA2sp/releases)|

PPM:     <https://ppmforums.com/topic47342/finalalert2yrv102patches/> <br />
Github:  <https://github.com/secsome/FA2sp>

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

### Additions to the Editor:

DDraw Renderer

Instead of using the system DDraw, FA2 and FS can instead use a local proxy DDraw.dll, improving the editor's speed considerably, which is especially useful for resource-heavy maps.
Several of the *Patched* map editors have this included but not in use, so check your map editor's folder as the files may already exist, such as in a "ForWindows10" folder, containing a pre-configured setup. if you want an un-configured setup for unknown reasons, or simply want to know more about the wrapper, check the Link below. I also included a direct download, although i have lost which thread this is on so i am unable to verify if it is the latest

| Topic | Source + Link |
| ------------ | ------------- |
| Unconfigured  |[BitPatch](http://bitpatch.com/ddwrapper.html)|
| Pre-Configured|[PPM](https://ppmforums.com/download.php?id=72031&sid=5b50cb3c1696d792adb195e4360b46fd)|

<!---#| Github |[Link](https://github.com/FunkyFr3sh/cnc-ddraw)| -->
## Modern Alternatives:

### World Altering Editor : <br />
Author: Rampastring + Contributors  <br />
Description: The World Altering Editor (WAE) is an open source replacement to the traditional editors. unlike the originals, it is built using a modern code base, and as a result of being open source it does not require the use of dll injection to improve. Formerly known as the DTA Scenario Editor, as it was built for [Dawn of the Tiberium Age](https://www.moddb.com/mods/the-dawn-of-the-tiberium-age),it has since been growing in compatability for TS/YR, with a TSClient build already produced and the YR build being WIP .  <br />
As of 4/8/22, it has just had it's first release for Tiberian Sun, and the only feature it is missing compared to FS is voxel rendering support. Otherwise, it is fully functional and with several improvements over the traditional editor. There are several PRs with partial YR support implimented, but it is not fully compatible yet.<br />

| Topic | Source + Link |
| ------------ | ------------- |
| World Altering Editor | [Github - Main Page](https://github.com/Rampastring/TSMapEditor) |
| World Altering Editor | [Github - Releases](https://github.com/Rampastring/TSMapEditor/releases) |
| Mod Haven Channel | [Discord](https://discord.gg/k4SVuMm) |

<iframe width="560" height="315" src="https://www.youtube.com/embed/jIcr3nCqx7M?si=sHyZGT08GEpVWEnU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<iframe width="1482" height="835" src="https://www.youtube.com/embed/RIgVMWZy80I" title="World Altering Editor - A new map editor coming to RotE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

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
Description: A script to generate a trigger map of maps on the TS/RA Engine <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Self-documentation | [Github - Main Page](https://github.com/FrozenFog/Ra2-Map-TriggerNetwork) |

### Map Conversion Tool <br />
Author:  Starkku <br />
Description: A tool which can convert the theatre, tiles, rules and overlay of maps.  <br />

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
It allows manipulation of Triggers, Scripts, Taskforces, Teams and Variables on both a single and batch scale <br />


| Topic | Source + Link |
| ------------ | ------------- |
| Forum Thread | [PPM - Forum](https://ppmforums.com/viewtopic.php?t=40202&start=0&postdays=0&postorder=asc&highlight=&sid=4e24b30fb8ab401c146e831491db9400) |
| Source Code| [Github - Main Page](https://github.com/PTapioK/TSWaveMaker) |

### Map Renderer <br />
Author: zzattack <br />
Description: A Full Map Preview Renderer for maps <br />
Also contains other features such as height maps, position markers as well as debug features! <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Forum Thread | [PPM - Forum](https://ppmforums.com/topic-29554-page-5/cnc-maps-renderer-rewritten-works-for-tiberian-sun-and-ra2/?postorder=asc) |
| Source Code| [Github - Original Source (https://github.com/zzattack/ccmaps-net) |


### Map Resize Tool <br />
Author: E1 Elite <br />
Description: A tool to resize maps, unlike the map editor this also moves smudges, tunnels ect <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Forum Thread | [PPM - Forum](https://ppmforums.com/topic55391/mapresize/) |
| Source Code| [Github - Main Page (https://github.com/E1Elite/MapResize) |

 **Final Sun Toolkit <br />
Author: Holland (and various other authors for the tools) <br />
Description: Software which contains multiple tools with it, as well as other optimisations <br />
| Topic | Source + Link |
| ------------ | ------------- |
| Forum Thread | [PPM - Forum](https://ppmforums.com/topic48112/afinalsunstandalonewithcncmodsandtoolkit/) |

### Map Rename Tool <br />
Author: Snark <br />
Description: This program will convert your .map file names to the map name (all credits to @Snark ). It's useful for organizing the maps that you download inside the cncnet client that are given a random file name, and means you can tell which map is which <br />
| Topic | Source + Link |
| ------------ | ------------- |
| Direct Download | [Google Drive](https://drive.google.com/file/d/1IVkd7O1uWMVXdEi2BFbULCHilAHTGXU/view?usp=sharing) |

### Trigger Index Parameter Tool <br />
Author: Starkku <br />
Description: A simple GUI program for adjusting numerical index values used as parameters for map trigger events & actions aswell as AI team scripts in Command & Conquer: Tiberian Sun & Red Alert 2. Useful for Mod / Mission developers to fix any issues that occur after a house index change <br />

| Topic | Source + Link |
| ------------ | ------------- |
| Source Code | [Github - Main Page]](https://github.com/Starkku/TriggerIndexParamTool) |

### Map Tool <br />
Author: vananasun <br />
Description: A command line tool to manipulate Red Alert 2 Yuri's Revenge maps <br />
| Topic | Source + Link |
| ------------ | ------------- |
| Source Code | [Github - Main Page]](https://github.com/vananasun/yrmaptoo) |

 **MISTEST  Map Checker <br />
Author: GE <br />
Description: "Mission Tester is designed primarily to help troubleshoot mission maps, but is useful for quickly resolving trigger or object placement errors on mutiplayer maps as well. It will warn of errors like objects outside of the map bounds, often caused by resizing maps, it will find errors like missing waypoints for actions, or even nonexistent sounds being played." <br />
PPM: <https://www.ppmforums.com/topic68090/mistestascripttotestmissionmapcodeandcheckmapobjectsforerrors/> <br />



##Map Tutorials:

I have outlined several useful mapping tutorials and mapping archives, so note this is not every available source. <br />
Burg   <https://www.youtube.com/playlist?list=PLPTX4WpN_n2Pd1duBlBT8Ht5OFiuKy_JS> <br />
YosefAnan  <https://www.youtube.com/playlist?list=PLa9Udz4hdmEOVfsjXD36XUgvSigAPMpST> <br />
Holland <https://www.youtube.com/channel/UCmO2G8WEni2JH70QPjqQBTQ> <br />
RaVaGe  <https://forums.cncnet.org/topic/8245howtomakera2yrmapsfinalalert2tutorial/> <br />
McPwny  <https://ppmforums.com/topic47332/thecompleteanddefinitivemappingindex/> <br />
PPM         <https://ppmforums.com/topic36348/howtoattachtriggerstotriggers/> <br />
[FC]        <https://www.youtube.com/watch?v=KywxRxdLzus&list=PLwlPpv3OXxX__Cex3sZEYsEnf3hUtayQ> <br />
CnCnet LucasSK     <https://forums.cncnet.org/topic/9934finalsuncompletetutorial/> <br />
CatTanker   <https://youtu.be/HAH43FvXvxc>
Flying Z https://sites.google.com/site/flyingzmaps/Home

##Community Mapping Archives:

PPM Forums                 <https://ppmforums.com/index.php?f=140> <br />
MadHQ's Graveyard  <http://zombapro.ppmsite.com/index.php?page=Yuri%27s+Revenge> <br />
CnCNet Forums      <https://forums.cncnet.org/forum/63ra2yrmaps/> <br />
Cncnet Map Search   <https://mapdb.cncnet.org/search/?game=td&search=> <br />
CnC Headquarters    <https://cnchq.de/cnctiberiansun/downloads/maps/> <br />
Cnc Creatives       <https://discord.gg/6gBHSBMYh7> <br />
YR Discord          <https://discord.gg/NX2PnauTVh> <br />
Mod Haven Discord   <https://discord.gg/P7R7ZhUhmJ> <br />
YRTS Map Factory   <https://discord.gg/wBEhaWNRRW> <br />
Chrono Storm        <https://www.csra2.com> <br />



##Noteworthy Projects:


MadHQ has remade the RA2 Allied and Soviet Campaigns entirely, designed for the vanilla game 
Link: <http://zombapro.ppmsite.com/index.php?page=Missions>

Almost Perfect Red Alert 2 (APRA2) is a fan project to produce a Red Alert 2 campaign in Mental Omega.  <br />
The team has made a quantity of high quality work that is publicly available, and consists of quite a few skilled and experienced mappers who can likely offer experience and advice. An excellent benchmark for any modern campaign developers who intend to use a mod's features to a high standard  <br />
Discord Link  <https://discord.gg/Z7HsWA5pTv>

Dawn of the Tiberium Age has been working on recreating the original TD Campaigns as CoOps  <br />
ModDB Post: <https://www.moddb.com/mods/thedawnofthetiberiumage/news/annoucingourtdgdicampaigncoopremake>  <br />
Discord: <https://discord.gg/YczsdZC>

Flipped Missions is a mod for YR which reverses the roles of original YR missions so you play as the other side, another project woth a look at!  <br />
ModDB: <https://www.moddb.com/mods/ra2fm>  <br />
Discord: <https://discord.gg/tYuP82S>


##Contributions / Future Uses:

While the primary purpose of this repository has been achieved, i do intend to maintain this for the foreseeable future. <br />
In the event you believe i have missed a tool or tutorial, please make an issue and i will sort it when i can. <br />
If you are able to make a PR and provide all the relevant information yourself, it will save me time as i can simply review and merge, which is much appreciated. <br />

I aim to place this on ReadTheDocs to improve access. As usual, any support would be appreciated. 

2023 October  Added a Linux Guide to this repository.
