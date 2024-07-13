
![Winetricks](https://upload.wikimedia.org/wikipedia/commons/a/a9/WINE-logo.svg)

## Winetricks Instructions

[Winetricks](https://wiki.archlinux.org/title/wine#WINEPREFIX) is another method we can use to run TS and YR through cncnet. While it is possible to perform all of this using wine only, it is not recommended and will require a few extra steps and alterations. It is mostly run from the command line with a very limited GUI, so i recommend Bottles instead, although winetricks should be fully functional.<br>

- Install `wine` (Ideally a modern verion, as this is a dependency for winetricks), through your package manager. <br>
- Install `winetricks` for greater control over individual prefixes (just do it) <br>



### Dotnet 4.* Clients + OpenGl (ogl) Build
#### Instillation of prefixes

After installing relevant dependencies listed above, open up a command line and put in
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/cncnet_4_X_ddraw" winetricks cnc_ddraw
```

The next step is to see if wine-mono is installed or not. Run
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/cncnet_4_X_ddraw" wine uninstaller
```

If you see Wine Mono Runtime & Wine Mono Windows Support, you have wine-mono installed and you should be safely able to move on to running the application (skip to the next section)

If you do not have Wine Mono Runtime & Wine Mono Windows Support listed, you can either install [wine mono](https://wiki.winehq.org/Mono), which i recommend doing through your distribution's package manager, *or* you can run:

```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/cncnet_4_X_ddraw" winetricks dotnet48
```

Okay, you have your prefix set up. There are several ways tha you can run your client's exe. Two methods require some terminal usage.
#### Running through your prefix completely in the terminal
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/cncnet_4_X_ddraw" wine "Absolute path to your client's /.... /resources/clientogl.exe"
```
You can navigate to your mod's resources folder through a file explorer, right click to find "Open Terminal Here", and then simply use the line above but with clientogl.exe only rather than the entire absolute path.

#### Running through your prefix mostly in the terminal
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/cncnet_4_X_ddraw" winetricks
```
Run this inside the terminal and a basic GUI will open up. Select "Select Default Wineprefix", and at the top of the GUI it should have a path that matches the WINEPREFIX= line.
Scroll down to find the "Run Arbitary Excutable" option. Select it and click ok, then navigate to your client's clientogl.exe excutable inside the resources folder, run it and it should open fine.

#### User Interface Only
In some installs you may be able to search for a `winetricks` application from your system's menu. From here you a GUI called `Winetricks - choose a wineprefix` will appear. Scrtoll down the list until you find the wineprefix you just made, `cncnet_4_X_ddraw`, and select ok. Scroll down to find the "Run Arbitary Excutable" option. Select it and click ok, then navigate to your client's clientogl.exe excutable inside the resources folder, run it and it should open fine.

### Dotnet 8 Client - Native
#### Running it
First of all, make sure you have the [dotnet runtime](https://dotnet.microsoft.com/en-us/download/dotnet/8.0), either from microsoft directly or downloaded through your [Distribution](https://wiki.archlinux.org/title/.NET#Installation).
The Dotnet 8 Client should be able to run natively with linux, only using wine for running the game itself. Most mods using dotnet 8 should provide a .sh script alongside the main exe, which should run the client if run through your command line. if it exists, you should be able to run it with bash if your file explorer allows it, or you can simply open up that folder in terminal and type `bash scriptname.sh`.
If it does not exist, use this directly in the command line from the top of your mod folder:
```
#!/bin/sh

dotnet Resources/BinariesNET8/UniversalGL/clientogl.dll "$@"
```

#### Game compatibility
One issue that i noticed several of the dotnet 8 builds have is that in order to run the game they use a .sh script to run a .bat script to run the game. While this works fine in principle, it uses the default wine prefix, which will not have any ddraw modifications, and therefore means that the game will run extremely slow and may even have graphical artifacts.

if you notice this, first of all make a new prefix which just contains the ddraw dependency. I am listing ddraw manually as an override for this instance, although the cnc_ddraw method i used earlier should work fine.
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/only_ddraw_override" winecfg
```
This should take a moment and then open wine configuration. Once this opens, you need to head to the Libraries tab and write `ddraw` into the entrybox below "New Override for library", then click add, apply, and then ok.
You then need to go into the Resources/Compatibility/Unix folder of the game/mod, there should be a gamemd.sh script or something similar. Edit this with a text editor of your choosing so that it matches the text below.
```
#!/bin/sh

export WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/only_ddraw_override

wineconsole Resources/Compatibility/Unix/gamemd.bat & <-- this line should pre-exist and you should therefore not need to modify it, but the .bat file name may differ.
BACK_PID=$!
wait $BACK_PID
```
Be warned, most mod updaters **Will Override This File** - Back it up to save you repeating this process later on.


Try launching the game again, and it should be a bit smoother, meaning it is time to actually use [the renderers guide,](https://cc-resource-docs.readthedocs.io/rendererresources/)
