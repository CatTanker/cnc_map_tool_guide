This guide gives mostly step-by-step instructions, useful tips and advice on running Yuri's Revenge, the Map Editor and indirectly Tiberian Sun on Linux.

Bottles Instructions: Intended for usage on the Dotnet 4.5 (?) Client, which YR is currently moving away from and TS still uses. 
I find bottles seems to give me the most reliable result on my many re-installs, find information about it here: https://usebottles.com and download it to your OS.
Most guides seem to recommend using Flatpack for the download, which may help if you are experiencing issues, but I have tested on he non-flatpack version and had no further issues
Create new --> Application
In Settings:
- Runner: Soda
- DXVK/VKD3D : Disabled (my system doesnot support vulkan, but you can probably leave this on enabled)
- LatencyFleX : Disabled
- Windows Version: Windows 10

Config 1:  //////////

Dll Overrides:  (Assume :Native, then Builtin, unless specified otherwise)
- ddraw as a DLL Override MANUALLY ENTERED

Installed Dependencies:
- arial32/times32/courie32 (installed by default for applications in bottles)
- Mono (Wine Mono)

Config 2:  //////////
Dll Overrides:  (Assume :Native, then Builtin, unless specified otherwise)
- *ddraw through the cnc-ddraw dependency (**do not manually add** check the next step for details)

Installed Dependencies:
- arial32/times32/courie32 (installed by default for applications in bottles)
- Mono (Wine Mono)
- THEN install CnC-DDraw as a dependency

Doesn't work on the exe in the main folder?
Go into the /Resources folder and try the 3 client...exes inside there, chances are one will work. In my experience the ogl build is the most reliable.


FA2SP with a Dark Theme
A Word of warning: there are a LOT of windows themes out there, i tried a few on my previous install and some seemed to work but most were a little dodgy (Some panels didn't change, some didn't sit nicely, some were too sharp....). You can changethemes using winecfg through the terminal (better yet through a wineprefix)

I found this gist (below) which on my system seems to provide a fully functioning dark theme based on Breeze, guidance for usage is included. As i run KDE Plasma this worked fairly well for me.
Gist:   https://gist.github.com/Zeinok/ceaf6ff204792dde0ae31e0199d89398
![Breeze Theme Screenshot](/assets/breeze_fa2.png)


Winetricks instructions: Intended for usage on the Dotnet 7+ client, but should work on the older client. 

- Install wine (Ideally a recent one, personally i have tested the above on wine-8.14 on Arch Linux), through your package manager.
- Install winetricks for greater control over individual prefixes

Run winetricks, and you Should have a screen similar to https://media.discordapp.net/attachments/1101919157970284604/1147626796624400426/image.png . While you can complete the next steps globally, i highly recommend making a new wineprefix for CnC, and so will i in this guide
--> Create new wineprefix
/ 64 Architecture
/ Name it whatever you like, keep it suitable and ideally without spaces
If you are prompted to install wine mono, do so if you ever intend to run the Dotnet 4.5 client. I did so when i tested for the 7+ client, and i  have had no side effects.

--> Install a windows DLL or component
Search for cnc_ddraw, tick the box and select ok to download it. 

Alright, you have your prefix set up, now lets use it.

Dotnet 4.5 Client:
> find your main mod directory, then the resources folder, right click and open in terminal, or find your way there using the <cd directory> command
> Run <WINEPREFIX=([1] wine client(ogl/dx/xna).exe>
[1] Means the absolute path to the wineprefix you just made, which can be found from the Browse Files selection in Winetricks and then copying the entire path it provides you in the top of your file explorer into [1]
> hope it works, check the logs in the terminal for details, **but try all 3 exes **
> 
> e.g.:
```
○ → WINEPREFIX="/home/username_goes_here/.local/share/wineprefixes/CnCNet_Winetricks/" wine clientogl
```



Dotnet 7+ Client:
> Navigate to the main folder of the mod/game, and look for a launcher bash script. Names will vary
E.G., in RotE, it is REClient.sh in the beta, and i believe CnCNet YR's is YRLauncher.sh (needs to be verified)
> Try executing it, if nothing happens go into the terminal and type <bash (name of the script)>
if you get a message saying something along the lines of dotnet is not understood, you need to install the latest version.
https://wiki.archlinux.org/title/.NET#Installation

You should be able to start the game at this point, however it may have poor fps and various graphical glitches.
If you go into the Resources/Compatability/Unix folder of the game/mod, there should be a gamemd.sh script or something similar. Consider this as [2].sh.  Edit this with a text editor, using the some information from [1] a bit above this line.
```
#!/bin/sh

export WINEPREFIX=[1]

wineconsole Resources/Compatibility/Unix/[2].bat &
BACK_PID=$!
wait $BACK_PID
```

Try launching the game again, and it should be a bit smoother. 
You may still notice some major artefacts/glitches when using the esc menu and returning to the game. Go into the client options and try all of the renderers in there, and hopefully (as with windows) one runs like a charm. For me, most tend to work (Default/CnC-DDraw), but TS-DDraw GDI fixes the esc menu breaking and lets me enter/exit between my game and other applications as i please.

The above applies to all of the solutions for playing YR on Linux, assuming you use the cncnet client
Lutris should be a possible alternative but i do not use it so i can't offer any advice on it, but it should be a similar method to Bottles


Help! My game works fine but upon connecting to cncnet it crashes (Or if cncnet works but connecting to online games crashes instantly)
Follow these instructions, you may need to modify the path if you are using bottles https://wiki.winehq.org/FAQ#Failed_to_use_ICMP_.28network_ping.29.2C_this_requires_special_permissions

Getting an error complaining about permissions?
chmod +x All of the exes. For the later client, i found this fixed a permissions issue when i did it on the script [2].sh