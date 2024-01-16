# Linux
## Introduction
This guide gives mostly step-by-step instructions, useful tips and advice on running Yuri's Revenge, the Map Editor and indirectly Tiberian Sun on Linux.
These guides all assume *you are using the cncnet client, either officially or on a mod*

The first step you will need to do is to figure out which client version you are using.
Most pre-2024 CnCNet clients use the .NET framework. This includes, but is not limited to:<br>
    - Mental Omega 3.3.6 <br>
    - Rise of the East 3.0.0j <br>
    - RA20XX <br>
    - Red Ressurection <br>
    - C&C Reloaded <br>
    - Mods forked off [TSClient](https://www.moddb.com/mods/tiberian-sun-client) <br>

According to the build instructions of the cncnet client in 2020:
```
The client has 3 builds: Windows (DirectX11), OpenGL and XNA.

The Windows and OpenGL builds rely on .NET Framework 4.5 and MonoGame.

The XNA build relies on .NET Framework 4.0 and Microsoft's XNA Framework 4.0 Refresh.
```
The above lines are where most of my reasoning lies for the dependencies installed.

Despite a later (2023) push towards updating the client to use dotnet7, as of early 2024 these changes are being rolled back due to dotnet 7 providing [a conbsiderably worse user experience](https://github.com/CnCNet/xna-cncnet-client/pull/494). Although a major part of this initial push was for better support on Mac / Linux, the vast majority of the userbase is on windows, and so the profits of this are limited. I also noticed that dotnet 7 clients tended to have a lot of bugs when run on linux, but looked/worked fine on windows,included strange placements of objects inside the client and no maps or scenarios even being listed in the client. The client also has a few minor oversights, such as the fact that the client runs your global wine rather than a dedicated prefix, causing issues such as extremely poor fps for several users, and in some cases an instant desync upon entering a game through linux, but without any issues if entered from the same files on windows. Any advice provided from the dotnet 7 builds is as a result less-well tested and in the future may be kept for legacy support. While there are much fewer mods that use the dotnet 7 client, there may be cases where such support is needed. Example cases include early builds of TS Rubicon, Rote's Beta (as of january 2024), and Project Phantom's client.


The reason you will often see a ddraw or cnc-ddraw package mentioned as this means the game will use the ddraw supplied by the [client](https://github.com/FunkyFr3sh/cnc-ddraw), which will improve your experience significantly. I *highly recommend* you perform this recommendation.



## Bottles Instructions
I find bottles seems to give me the most reliable result on my many re-installs, find information about it [here](https://usebottles.com) and download it to your OS.
Most guides seem to recommend using Flatpack for the download, which may help if you are experiencing issues, as well as providing some areas such as sandboxing, but I have tested on he non-flatpack version.

### Dotnet 4.* Clients + OpenGl (ogl) Build

Create new --> Application <br>
In Settings: <br>
- Runner: Soda <br>
- DXVK/VKD3D : Disabled <br>
- LatencyFleX : Disabled <br>
- Windows Version: Windows 10 (since some builds of phobos and other extensions require Windows 7 or higher) <br>

#### Config 1: Manually Entered
--
*Dll Overrides:*  (Assume :Native, then Builtin, unless specified otherwise)

- ddraw as a DLL Override *MANUALLY ENTERED* <br>

*Installed Dependencies:* <br>
- arial32/times32/courie32 [By Default] <br>
- Mono (Wine Mono) [Install Yourself] <br>


#### Config 2: CnC-DDraw dependency

*Dll Overrides:*  (Assume :Native, then Builtin, unless specified otherwise)
- *ddraw through the cnc-ddraw dependency (**do not manually add** check the next step for details)

*Installed Dependencies:*
- arial32/times32/courie32 [By Default]
- Mono (Wine Mono) [Install Yourself]
- THEN install CnC-DDraw as a dependency [Install Yourself]


After following all of the steps above, enter your bottle, click "Run Excutable", and guide it to your client folder / Resources, and then try "clientogl.exe", and the client should run fine, as well as the game. In some cases the xna client also seems to work, but try the ogl build first.



## Winetricks Instructions

[Winetricks](https://wiki.archlinux.org/title/wine#WINEPREFIX) is another method we can use to run TS and YR through cncnet. While it is possible to perform all of this using wine only, it is not recommended and will require a few extra steps and alterations.

- Install `wine` (Ideally a recent one, personally i have tested the above on wine-8.14 on Arch Linux), through your package manager. <br>
- Install `winetricks` for greater control over individual prefixes (just do it)<br>



### Dotnet 4.* Clients + OpenGl (ogl) Build

After installing relevant dependencies, open up a command line and put in
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/cncnet_4_X_ddraw" winetricks cnc_ddraw
```

The next step is to see if wine-mono is installed or not. Run
```
WINEPREFIX="/home/main-i5-user/.local/share/wineprefixes/cncnet_4_X_ddraw" wine uninstaller
```

If you see Wine Mono Runtime & Wine Mono Windows Support, you have wine-mono installed and you should be safely able to move on to running the application (skip to the next section)

If you do not have Wine Mono Runtime & Wine Mono Windows Support listed, you can either install [wine mono](https://wiki.winehq.org/Mono), which i recommend doing through your distribution's package manager, *or* you can run:

```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/cncnet_4_X_ddraw" winetricks dotnet48
```

Okay, you have your prefix set up. There are several ways you can how run your exe. Both methods require some terminal usage.

#### Running through your prefix completely in the terminal
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/cncnet_4_X_ddraw" wine "Absolute path to your client's /.... /resources/clientogl.exe"
```
You can navigate to your mod's resources folder through a file explorer, right click to find "Open Terminal Here", and then simply use the line above but with clientogl.exe only rather than the entire absolute path.

#### Running through your prefix completely in the terminal
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/cncnet_4_X_ddraw" winetricks
```
Run this inside the terminal and a basic GUI will open up. Select "Select Default Wineprefix", and at the top of the GUI it should have a path that matches the WINEPREFIX= line.
Scroll down to find the "Run Arbitary Excutable" option. Select it and click ok, then navigate to your client's clientogl.exe excutable, run it and it should open fine.

### Dotnet 7+ Client: Native
#### Running it natively

First of all, make sure you have the [dotnet runtime](https://dotnet.microsoft.com/en-us/download/dotnet/7.0), either from microsoft directly or downloaded through your [Distribution](https://wiki.archlinux.org/title/.NET#Installation)
The Dotnet7 Client should be able to run natively with linux, only using wine for running the game itself. Most mods using dotnet 7 should provide a .sh script alongside the main exe, which should run the client if run through your command line. if it exists, you should be able to run it with bash if your file explorer allows it, or you can simply open up that folder in terminal and type `bash scriptname.sh`
If it does not exist, use this:
```
#!/bin/sh
dotnet Resources/Binaries/UniversalGL/clientogl.dll
```

Although wine has very little support for running dotnet 7, mostly due to it's advertisement of running natively,and how recent dotnet 7 is, I have recently noticed that lutris and winetricks both have a dotnet 7 dependency. I have tried this prefix instillation and had **no success**, although i am leaving this hear in case someone wishes to try further, or if in the future it works.

```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/cncnet_7_ddraw" winetricks cnc_ddraw dotnetdesktop7
```


#### Game Compatability
One issue that i noticed several of the dotnet 7 builds have is that in order to run the game they use a .sh script to run a .bat script to run the game. While this works fine in principle, it uses the default wine prefix, which will not have any ddraw modifications, and therefore means that the game will run extremely slow and may even have graphical artifacts.

if you notice this, first of all make a new prefix which just contains the ddraw dependency. I am listing ddraw manually as an override for this instance, although the cnc_ddraw method i used earlier should work fine.
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/only_ddraw_override" winecfg
```
This should take a moment and then open wine configuration. Once this opens, you need to head to the Libraries tab and write `ddraw` into the entrybox below "New Override for library", then click add, apply, and then ok.
You then need to go into the Resources/Compatability/Unix folder of the game/mod, there should be a gamemd.sh script or something similar. Edit this with a text editor of your choosing so that it matches the text below.
```
#!/bin/sh

export WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/only_ddraw_override

wineconsole Resources/Compatibility/Unix/gamemd.bat & <-- this line should pre-exist and you should therefore not need to modify it, but the .bat file name may differ.
BACK_PID=$!
wait $BACK_PID
```
Be warned, most mod updaters *Will Override This File* - Back it up to save you repeating this process later on.


Try launching the game again, and it should be a bit smoother. 
You may still notice some major artefacts/glitches when using the esc menu and returning to the game. Go into the client options and try all of the renderers in there, and hopefully (as with windows) one runs like a charm. For me, most tend to work (Default/CnC-DDraw), but TS-DDraw GDI fixes the esc menu breaking and lets me enter/exit between my game and other applications as I please.


## General Compatability and Troubleshooting Advice
### Connection Issues
if your game works fine in skirmish but upon connecting to cncnet or upon entering an online match you either can't connect or get a desync, follow these [instructions](https://wiki.winehq.org/FAQ#Failed_to_use_ICMP_.28network_ping.29.2C_this_requires_special_permissions). Also check your ports / firewall allows you to send/recieve packets.
### Permission Errors
Getting an error complaining about permissions?
[chmod +x](https://wiki.archlinux.org/title/File_permissions_and_attributes) All of the exes in the game/mod folder. For the later client, i found this fixed a permissions issue on the dotnet 7 client.
Also check you as a non-root user actually have access to the files and folders

**Do Not** run wine as root however, this will cause more consequences than and fix nothing. Administrator-related fixes tend to be as a result of permissions being incorrect. make sure to open the mod or game's folder and check everything has both read and write permissions, and make sure you apply any fixes to subfolders and subfiles too.

### Dotnet Not Found
if you get an error message, especially while attempting to run the dotnet7 client (specifically the client, not the game), complaining something similar to "dotnet not a known command" or "dotnet unrecognised script", then you *need* to install dotnet 7. Check [Arch Wiki](https://wiki.archlinux.org/title/.NET#Installation) for further details.


### General Suppor
As a general word of advice, if there is a known and trusted fix for an issue in a formal location, then it's alternative will likely work in linux.
If your having an issue with a **specific** mod, i advise looking at their discord and asking for help there, just don't ask in another mod's support channel.
[Mental Omega's Discord](https://discord.gg/KpJzhWY) has a Support Solutions FAQ, as well as an active support channel, so if you are struggling to run MO then i recommend seeking help there.
[CnCNet also has a FAQ](https://forums.cncnet.org/forum/87-faqs/) webpage that you may find useful.


### Renderer Advice
Most cncnet clients off only one build of CnC-DDraw, and often limited builds of other renderers such as TS-DDraw. If you want to test your renderer options thoroughly, check your game's main folder for a file called `ddraw.ini`.
Open it through a text editor, and look for a tag called `Renderer=`
This is likely set to Auto, but i recommend manually changing this for each option on CnC-DDraw and TS-DDraw.
```
; Select the renderer, opengl, gdi, auto. Default = auto = if OpenGL fails automatically use GDI
renderer=auto
```
NOTE: I seem to recall a third option of dx, requires verification.


## Final Alert 2 (and FS)
Linux provides several new opportunities for people using FA2(SP) and FS(SP)
The map editor can be run straight out of wine / bottles without any dependencies needed.
### FA2SP with a Dark Theme
--
A Word of warning: there are a LOT of windows themes out there, i tried a few on my previous install and some seemed to work but most were a little dodgy (Some panels didn't change, some didn't sit nicely, some were too sharp....).<br>
You can change themes using winecfg through the terminal (better yet through a wineprefix)<br>
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/map_editor" winecfg
```
I believe this *only works* on recently [patched Fa2s](https://github.com/secsome/FA2sp].
Mental Omega 3.3.6, RR 2.2.13 and any mod which has not been updated since 2020 do not have this patch, and so you will need to add it yourself if you want a dark theme.<br>
I found this [gist](https://gist.github.com/Zeinok/ceaf6ff204792dde0ae31e0199d89398) which on my system seems to provide a fully functioning dark theme based on Breeze, guidance for usage is included. As i run KDE Plasma this worked fairly well for me, matching the theme i used.<br>
![Breeze Theme Screenshot](Assets/breeze_fa2.png)
Note that the missing + icons to the left are a result of running it through my system's wine, but if you use [Bottles](https://usebottles.com) the glitch no longer occurs.

I seem to recall [this](https://www.reddit.com/r/linux_gaming/comments/n8hf6v/make_wine_look_like_windows_10/) working as well, providing a more modern light theme option. Sadly this was a while back and i am unable to confirm so. The script also downloads off discord rather than a formal file source, and given discord's proposed changes to stop external download links, this may need to be mirrored.
### Multi-Monitor Support
While i am unsure if this is imply an original bug in FA2, or as a result of patches, but the application simply cannot be stretched between two screens.
This may require some adjustment

```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/map_editor" winecfg
```
This will take a moment and open wine configuration. head to `Graphics` and click emulate a virtual desktop. Make sure the size is decent, you can move the virtual desktop around like a window, but make sure it does not have a length/width too large or you may have clipping issues, such as the screenshopt above where the bottom banner is completely cut off.
You then run the map editor from this wineprefix like as I recommended in the Winetricks section. Alternatively you can use bottles to do the same.

![Multiple-Monitors](Assets/multi_monitor_fa2.png)
## External Sources and Notes

I have looked around into other guides for running CnC games on linux. There are quite a mix of methods, some requiring snap, some lutris and some just being general guidelines.<br>

A generic Linux Gaming post summarising all of the CnC Games <https://www.reddit.com/r/linux_gaming/comments/mtixee/a_linux_users_guide_to_command_conquer/> <br>
Advice on using CnCnet YR with linux, marginally outdated due to a change in client, but it is a useful reference <https://www.speich.net/articles/en/2021/12/19/how-to-install-the-cncnet-client-on-linux/> <br>
Snap Package Github for CnCnet YR] - <https://github.com/mmtrt/cncra2yr> <br>
When looking at Linux tutorials, you will find a lot of outdated sources. This is important because:<br>
- Wine has improved significantly in the past few years, especially with enhancements from proton due to the steam deck <br>
- Anything that uses packages can become unmaintained and quickly out of date, or is broken in dependency hell  <br>
- Linux distributions can change and drop out of favour, or the guide may advise on dependencies that no longer exist E.g. a guide may specify wine 4.5, when 8.xx is the current latest. Generally, use the latest wine where possible. <br>
- Sadly most of the CnC games are not on steam, but if they are then check <https://www.protondb.com> for how well they run on linux from people's experiences, including computer specs and comments. wineHQ's application databse <https://appdb.winehq.org> is fairly limited, often outdated, but may be worth a check. Same applies to CrossOver <https://www.codeweavers.com/compatibility>   <br>

In theory, running the client and game through lutris is an option, however i have heard people who have tried this have noticed the game always instantly desyncs


## Next Steps
Although i have covered most of the *basics*, I am unable to test and approve everything myself. Parts may not work 100% consistently, and i only have EndeavourOS (Arch) to test on, and i am testing on an 13 y/o Desktop PC. This means that i am unable to test some new possibilities, such as combining vkd3d and cnc-ddraw.<br>
Any support from experienced users to expand this guide, such as tests with vulkan and certain graphical alterations would be greatly appreciated.
Contributions to this [repository](https://github.com/CatTanker/cnc_map_tool_guide) for any fixes and new methods or scripts would be greatly appreciated.
