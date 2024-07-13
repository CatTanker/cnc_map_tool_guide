## General compatibility and Troubleshooting Advice

Most of the advice here is either Generic (applies to all methods of running cncnet) or a wine-specific issue that only applies if you choose to use winetricks instead of Bottles.

### Connection Issues [winetricks only]

If your game works fine in skirmish but upon connecting to cncnet or upon entering an online match you either can't connect or get a desync, follow these [instructions](https://wiki.winehq.org/FAQ#Failed_to_use_ICMP_.28network_ping.29.2C_this_requires_special_permissions). Also check your firewall is open and that it allows you to send/recieve packets.

### Permission Errors [general]
Getting an error complaining about permissions?
[chmod +x ...](https://wiki.archlinux.org/title/File_permissions_and_attributes) all of the exes in the game/mod folder. For the later client (dotnet 8) i found this let my game run when i used the native dotnet 8 client.
Also check you actually have access to the files and folders.

On the Dotnet 8 Client, using UniversalGl natively, if you have an error saying permissions denied when launching the game, such as this in `client.log`:
```
24.03. 16:53:52.899    Writing spawn.ini
24.03. 16:53:52.899    Writing map.
24.03. 16:53:52.899    Loading map INI from (path to map file)).map
24.03. 16:53:52.903    About to launch main game executable.
24.03. 16:53:52.919    Writing settings INI.
24.03. 16:53:52.919    Launch executable: (home --> client --> resources..)/wine-md.sh
24.03. 16:53:52.919    Launch arguments:  -SPAWN -LOG -CD -INCLUDE -INHERITANCE -ICON Resources/gameicon.ico
24.03. 16:53:52.920    Error launching wine-md.sh: System.ComponentModel.Win32Exception (13): An error occurred trying to start process '......Resources/Compatibility/Unix/wine-md.sh' with working directory '...../Mod Folder Name'. Permission denied
   at System.Diagnostics.Process.ForkAndExecProcess(ProcessStartInfo startInfo, String reso
```

enter properties of `YRLauncher.sh` and set this as **excutable** and make sure it has full RWX access. The head to the wine-md.sh file inside the `Resources/Compatibility/` section and give this the same permissions. The game should now run.


**Do Not** run wine as root however, this will cause more consequences and fix nothing. Administrator-related fixes tend to be as a result of permissions being incorrect. make sure to open the mod or game's folder and check everything has both read and write permissions, and make sure you apply any fixes to subfolders and subfiles too.

### Dotnet Not Found
if you get an error message, especially while attempting to run the dotnet 8 client (specifically the client, not the game), complaining something similar to "dotnet not a known command" or "dotnet unrecognised script", then you *need* to install dotnet 8 runtime. Check [Arch Wiki](https://wiki.archlinux.org/title/.NET#Installation) for further details. You would typically notice this if you run the linux script, e.g. `YRLauncher.sh`.

### Wine-Introduced Limitations

-  Often with 'mono' it appears that the client is without sound.
-  With some renderers the minimap is black and appears very glitchy ingame. Works in functionality though. This changes between runners (e.g. the default wine) and the [renderers chosen](https://cc-resource-docs.readthedocs.io/rendererresources/)
-  I usually listen to my own music while i play, but i have noticed that multiple runners seem to *fail* to load *music* from theme files, so while you can hear structures being built and "conscript reporting", you may not be able to listen to hell march through the game itself. I found that using the steam runtime in the [arch aur bottles](https://wiki.archlinux.org/title/Bottles) seemed to fix this, but ultimately it is recommended to use the flatpak version of bottles instead for better support, and since this fixed my audio issues without needing to use the steam-runtime. Using the steam runtime did also appear to increase the rate of desyncs, which would be interesting to investigate.

### General Support

There is now a [page for support](https://cc-resource-docs.readthedocs.io/generalsupport/) in mods that is intended for windows, but since lots of these fixes translate into wine it will be of use to you.


### Renderer Advice

I recommend checking the newly introduced [renderer wiki section](rendererresources.md). For Linux/Wine, CnC-DDraw is typically the best option as it was developed with linux compatibility in mind.


## External Sources and Notes

I have looked around into other guides for running CnC games on linux. There are quite a mix of methods, some requiring snap, some lutris and some just being general guidelines.<br>

A generic Linux Gaming post summarising all of the CnC Games, on [reddit](https://www.reddit.com/r/linux_gaming/comments/mtixee/a_linux_users_guide_to_command_conquer/) <br>
Advice on using CnCnet YR with linux, marginally outdated due to a change in client, but it is a useful [reference](https://www.speich.net/articles/en/2021/12/19/how-to-install-the-cncnet-client-on-linux/) <br>
Snap Package Github for CnCnet YR](https://github.com/mmtrt/cncra2yr>) <br>
When looking at Linux tutorials, you will find a lot of outdated sources. This is important because:<br>
- Wine has improved significantly in the past few years, especially with enhancements from proton due to the steam deck <br>
- Anything that uses packages can become unmaintained and quickly out of date, or is broken in dependency hell  <br>
- Linux distributions can change and drop out of favour, or the guide may advise on dependencies that no longer exist E.g. a guide may specify wine 4.5, when 8.xx is the current latest. Generally, use the latest wine where possible. <br>
- [ProtonDB](https://www.protondb.com) is now available for all the CnC games, which often has advice and how well they run on them, as well as little tweaks that people use. The steam community may also have advice. <br>

In theory, running the client and game through lutris is an option, however i have heard people who have tried this have noticed the game always instantly desyncs


## Next Steps
Although i have covered most of the *basics*, I am unable to test and approve everything myself. Parts may not work 100% consistently, and i only have EndeavourOS (Arch) to test on, and i am testing on an 13 y/o Desktop PC. This means that i am unable to test some new possibilities, such as combining vkd3d and cnc-ddraw.<br>
Any support from experienced users to expand this guide, such as tests with vulkan and certain graphical alterations would be greatly appreciated.
Contributions to this [repository](https://github.com/CatTanker/cnc_map_tool_guide) for any fixes and new methods or scripts would also be greatly appreciated.
