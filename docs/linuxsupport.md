## General Compatability and Troubleshooting Advice
### Connection Issues
if your game works fine in skirmish but upon connecting to cncnet or upon entering an online match you either can't connect or get a desync, follow these [instructions](https://wiki.winehq.org/FAQ#Failed_to_use_ICMP_.28network_ping.29.2C_this_requires_special_permissions). Also check your firewall is open and that it allows you to send/recieve packets.
### Permission Errors
Getting an error complaining about permissions?
[chmod +x ...](https://wiki.archlinux.org/title/File_permissions_and_attributes) all of the exes in the game/mod folder. For the later client, i found this fixed a permissions issue on the dotnet 7 client.
Also check you as a non-root user actually have access to the files and folders

**Do Not** run wine as root however, this will cause more consequences and fix nothing. Administrator-related fixes tend to be as a result of permissions being incorrect. make sure to open the mod or game's folder and check everything has both read and write permissions, and make sure you apply any fixes to subfolders and subfiles too.

### Dotnet Not Found
if you get an error message, especially while attempting to run the dotnet7 client (specifically the client, not the game), complaining something similar to "dotnet not a known command" or "dotnet unrecognised script", then you *need* to install dotnet 7 runtime. Check [Arch Wiki](https://wiki.archlinux.org/title/.NET#Installation) for further details.

### Wine-Introduced Limitations

-  Often with 'mono' it appears that the client is without sound.
-  With some renderers the minimap is black and appears very glitchy ingame. Works in functionality though. **Changes between renderers.**
-  I usually listen to my own music while i play, but i have noticed that multiple runners seem to *fail* to load *music* from theme files, so while you can hear structures being built and "conscript reporting", you may not be able to listen to hell march through the game itself. *Requires Investigation.*

### General Support
As a general word of advice, if there is a known and trusted fix for an issue in a formal location, then it's alternative will likely work in linux.
If your having an issue with a **specific** mod, i advise looking at their discord and asking for help there, just don't ask in another mod's support channel.
[Mental Omega's Discord](https://discord.gg/KpJzhWY) has a Support Solutions FAQ, as well as an active support channel, so if you are struggling to run **MO** then i recommend seeking help there.
[CnCNet also has a FAQ](https://forums.cncnet.org/forum/87-faqs/) webpage that you may find useful, as well as an active support channel in their discord.


### Renderer Advice
Most cncnet clients offer only one build of CnC-DDraw, and often limited builds of other renderers such as TS-DDraw. If you want to test your renderer options thoroughly, check your game's main folder for a file called `ddraw.ini`.
Open it through a text editor, and look for a tag called `Renderer=`
This is likely set to Auto, but i recommend manually changing this for each option on CnC-DDraw and TS-DDraw.
```
; Select the renderer, opengl,dx, gdi, auto. Default = auto = if OpenGL fails automatically use GDI
renderer=auto
```

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
Contributions to this [repository](https://github.com/CatTanker/cnc_map_tool_guide) for any fixes and new methods or scripts would also be greatly appreciated.
