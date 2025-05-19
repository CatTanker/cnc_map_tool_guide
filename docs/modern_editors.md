<!---#| Github |[Link](https://github.com/FunkyFr3sh/cnc-ddraw)| -->
# World Altering Editor <br />
Author: Rampastring + Contributors  <br />
Description: The World Altering Editor (WAE) is an open source replacement to the traditional editors. unlike the originals, it is built using a modern code base, and as a result of being open source it does not require the use of dll injection to improve. 
Formerly known as the DTA Scenario Editor, as it was built for [Dawn of the Tiberium Age](https://www.moddb.com/mods/the-dawn-of-the-tiberium-age), it has since been growing in compatability for TS/YR.
A release for [TS Client](https://www.moddb.com/mods/tiberian-sun-client) and  YR both available on the the releases page. 
 
The editor requires the latest dotnet desktop runtime to operate, and has heightened requirements, but does have a lot of major benefits (listed below).


| Topic | Source + Link |
| ------------ | ------------- |
| World Altering Editor | [Github - Main Page](https://github.com/CnCNet/WorldAlteringEditor) |
| World Altering Editor | [Github - Releases](https://github.com/CnCNet/WorldAlteringEditor/releases) |
| Mod Haven Channel | [Discord](https://discord.gg/k4SVuMm) |

Videos demonstating older versions of WAE:

<iframe width="560" height="315" src="https://www.youtube.com/embed/jIcr3nCqx7M?si=sHyZGT08GEpVWEnU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/RIgVMWZy80I" title="World Altering Editor - A new map editor coming to RotE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

While the editor does have the drawback of increasing load times and a much higher minimum spec requirement than the original core editors, it does present a growing wealth of new features.

## Highly Configurable

The World Altering Editor has been build with mods and the cncnet client in mind, and operates on a highly configurable structure of ini config files. This allows for the editor to support a wide range of mod structures, including that of TSClient where MIX and INI files are split into several subfolders, and that of the put it all in the root structure of YR. MIX load orders can be configured easily, and there are rules/art override files available. Any theater can be defined, so mods which modify the theaters available no longer need to hex edit and ship multiple FA2/Fs instillations with their mod.

[ Example of the config folder + sample INI ]

## Interface Features

A growing volume of interface features have been developed. One of the more evident examples is a zoom in/out function, which is greatly missed in the WW2.5D series of map editors. The editor also includes a search tool so you can find a specific item much easier, better catagorized lists, and a configurable LAT panel. Furthermore, there is also a map-wide overlay option, which can display a selected image file stretched across the entire map, which is extremely useful when combined with the zoom tools as map designs can easily be traced.

[Video of zooming in/out + searching + overlay]

## New Tools
There are also several automative tools available for WAE, including a configurable terrain generator to decorate natural environments, a WIP cliff drawer, and the possibilities of user-made scripts that can perform advanced tasks, such as smoothing out water tiles. The editor can also draw complex tunnels, which do not break unlike the unpatched FA2's tunnels, has a check distance tool that can follow pathfinding, and allows users to configure what is copied and deleted.

[Example of the terrain generator + Cliff Drawer]
