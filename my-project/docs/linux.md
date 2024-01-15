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

Despite a later (2023) push towards updating the client to use dotnet7, as of early 2024 these changes are being rolled back after dotnet 7 providing [a conbsiderably worse user experience](https://github.com/CnCNet/xna-cncnet-client/pull/494). Although a major part of this initial push was for better support on Mac / Linux, there were conflicts  with existing methods. This included strange placement of objects inside the client, the fact that the client runs your global wine rather than a dedicated prefix, causing issues such as extremely poor fps, and in some cases an instant desync upon entering a game through linux, but without any issues if entered from the same files on windows.Any advice provided from the dotnet 7 builds is as a result less-well tested and in the future may be kept for legacy support. While there are much fewer mods that use the dotnet 7 client, there may be cases where such support is needed. Example cases include early builds of TS Rubicon, RotE (as of december 2023) internal beta's client, and Project Phantom's internal client.


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

[Winetricks](https://wiki.archlinux.org/title/wine#WINEPREFIX) is another method we can use to run TS and YR through cncnet. While it is possible to perform all of this using wine, it is not recommended.

- Install `wine` (Ideally a recent one, personally i have tested the above on wine-8.14 on Arch Linux), through your package manager.
- Install `winetricks` for greater control over individual prefixes (just do it)

Run winetricks (`winetricks` in your command line), and you Should have a screen similar to ![Winetricks First Menu](/Assets/winetricks_1.png) .
While you can complete the next steps globally, i highly recommend making a new wineprefix for CnC, and so I will in this guide.

--> *Create new wineprefix* <br>
- 64 Architecture <br>
-  Name it whatever you like, keep it suitable and ideally without spaces <br>
If you are prompted to install wine mono, *do so*.

--> *Install a windows DLL or component*

- Search for cnc_ddraw, tick the box and select ok to download it.

Alright, you have your prefix set up, now lets use it. Depending on which client(s) you intend to run, do the following:


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

### Dotnet 7+ Client: Winetricks
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


If you go into the Resources/Compatability/Unix folder of the game/mod, there should be a gamemd.sh script or something similar. Edit this with a text editor of your choosing so that it matches the text below.
```
#!/bin/sh

export WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/only_ddraw_override

wineconsole Resources/Compatibility/Unix/[2].bat &
BACK_PID=$!
wait $BACK_PID
```
Be warned, most mod updaters *Will Override This File* - Back it up to save you repeating this process later on.


Try launching the game again, and it should be a bit smoother. 
You may still notice some major artefacts/glitches when using the esc menu and returning to the game. Go into the client options and try all of the renderers in there, and hopefully (as with windows) one runs like a charm. For me, most tend to work (Default/CnC-DDraw), but TS-DDraw GDI fixes the esc menu breaking and lets me enter/exit between my game and other applications as i please.

The above applies to all of the solutions for playing YR on Linux, assuming you use the cncnet client
Lutris should be a possible alternative but i do not use it so i can't offer any advice on it, but it should be a similar method to Bottles

## General Compatability and Troubleshooting Advice*
### Connection Issues
if your game works fine but upon connecting to cncnet (if your using the dotnet4.5 client, or an immediate desync in the dotnet 7 client) wine crashes, follow these instructions, you may need to modify the path if you are using bottles https://wiki.winehq.org/FAQ#Failed_to_use_ICMP_.28network_ping.29.2C_this_requires_special_permissions
### Permission Errors
Getting an error complaining about permissions?
chmod +x All of the exes in the game/mod folder. For the later client, i found this fixed a permissions issue when i did it on the script [2].sh
Also check you as a non-root user actually have access to the files and folders

if you get an error message, especially while attempting to run the dotnet7 client (specifically the client, not the game), complaining something similar to "dotnet not a known command" or "dotnet unrecognised script", then you *need* to install dotnet 7. Check https://wiki.archlinux.org/title/.NET#Installation for further details

As a general word of advice, if there is a known and trusted fix for x issue in y location, then it's alternative will likely work in linux
*Do Not* run wine as root however, this will cause more consequences than it will ever fix. Administrator-related fixes tend to be as a result of permissions being incorrect. make sure to open the mod or game's folder and check everything has both read and write permissions, and make sure you apply any fixes to subfolders and subfiles too. Also check the chmod fix.

If your having an issue with a *specific* mod, i advise looking at their discord and asking for help there, just don't ask in another mod's support channel.



Note: Although i have covered most of the *basics*, I am unable to test and approve everything myself. Parts may not work 100% consistently, and i only have EndeavourOS (Arch) to test on, and i am testing on an old PC meaning that i am unable to test some new possibilities, such as combining vkd3d and cnc-ddraw.
Any support from experienced users to expand this guide, such as tests with vulkan and certain graphical alterations would be greatly appreciated.




Theory based methods tried:
XNA using dotnet 4.0/4.5, and xna4.0 depdendecy. Always returned an error on the xna build
also tried with mono
ultimately redundant, use ogl instead


**FA2SP with a Dark Theme**
--
A Word of warning: there are a LOT of windows themes out there, i tried a few on my previous install and some seemed to work but most were a little dodgy (Some panels didn't change, some didn't sit nicely, some were too sharp....).
You can change themes using winecfg through the terminal (better yet through a wineprefix)
I believe this *only works* on recently patched Fa2s, using https://github.com/secsome/FA2sp, *but i have not tested on older editors* ///CHECK END OF DOCUMENT
Mental Omega 3.3.6, RR 2.2.13 and any mod which has not been updated since 2020 will not have this patch.
I found this gist (below) which on my system seems to provide a fully functioning dark theme based on Breeze, guidance for usage is included. As i run KDE Plasma this worked fairly well for me, matching the theme i used.
Gist:   https://gist.github.com/Zeinok/ceaf6ff204792dde0ae31e0199d89398
![Breeze Theme Screenshot](/Assets/breeze_fa2.png)
I seem to recall https://www.reddit.com/r/linux_gaming/comments/n8hf6v/make_wine_look_like_windows_10/ working as well, but this was a while back and i am unable to confirm so.

full terminal
env WINEPREFIX="/prefixes/cncnet_dotnet4_X_ogl/" wineboot -u
env WINEPREFIX="/prefixes/cncnet_dotnet4_X_ogl/" winetricks cnc_ddraw

