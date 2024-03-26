## Final Alert 2 (and FS)
Linux provides several new opportunities for people using FA2(SP) and FS(SP)
The map editor can be run straight out of wine / bottles without any dependencies.
### FA2SP with a Dark Theme
A Word of warning: there are a LOT of windows themes out there, i tried a few on my previous install and some seemed to work but most were a little dodgy (Some panels didn't change, some didn't sit nicely, some were too sharp....).<br>
You can change themes using winecfg through the terminal (better yet through a wineprefix)<br>
```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/map_editor" winecfg
```
I believe this *only works* on recently [patched Fa2s](https://github.com/secsome/FA2sp).
Mental Omega 3.3.6, RR 2.2.13 and any mod which has not been updated since 2020 do not have this patch, and so you will need to add it yourself if you want a dark theme.<br>
I found this [gist](https://gist.github.com/Zeinok/ceaf6ff204792dde0ae31e0199d89398) which on my system seems to provide a fully functioning dark theme based on Breeze, guidance for usage is included. As i run KDE Plasma this worked fairly well for me, matching the theme i used.<br>
![Breeze Theme Screenshot](Assets/breeze_fa2.png)
Note that the missing + icons to the left are a result of running it through my system's wine, but if you use [Bottles](https://usebottles.com) the glitch no longer occurs.

I seem to recall [this](https://www.reddit.com/r/linux_gaming/comments/n8hf6v/make_wine_look_like_windows_10/) working as well, providing a more modern light theme option. Sadly this was a while back and i am unable to confirm so. The script also downloads off discord rather than a formal file source, and given discord's proposed changes to stop external download links, this may need to be mirrored.

Wine supports the theme engine of **XP**, so a lot of your choices are limited, although any modifications you make only apply to your wineprefix, so unlike windows you cannot brick your system with it. There are also a surprising amount of decent Xp themes lying around on places such as DevianArt, so i recommend looking for some free ones and trying them out.

### Multi-Monitor Support
While i am unsure if this is simply an original bug in FA2, or as a result of patches, but the application simply cannot be stretched between two screens.

```
WINEPREFIX="/home/YOUR_USERNAME_GOES_HERE/.local/share/wineprefixes/map_editor" winecfg
```
This will take a moment and open wine configuration. head to `Graphics` and click emulate a virtual desktop. Make sure the size is decent, you can move the virtual desktop around like a window, but make sure it does not have a length/width too large or you may have clipping issues, such as the screenshopt above where the bottom banner is completely cut off.
You then run the map editor from this wineprefix like as I recommended in the Winetricks section. Alternatively you can use bottles to do the same.

![Multiple-Monitors](Assets/multi_monitor_fa2.png)

## World Altering editor

is it possible to run the World Altering Editor on linux. While a native linux buildcould be a future goal, for now the editor can run using a compatability layer.
I highly recommend using [Bottles](https://usebottles.com) for this as it allows possibly the easiest instillation and customisation of new runners.

    1.Preparing the bottle:

        1. Create a new bottle, as an application (not gaming or custom).
        2. Head to Settings and make sure the runner's version is above 9.0.
            If it is not:
                1. Head to the main page where you select bottles
                2. Click on the 3 dots ore lines (theme dependent) by the search arrow
                3. Select Preferences
                4. Head to the runners tab
                5. Download a runner version that is =>9.0. I recommend Caffe-9.2, and kron4ek-wine-9.4-amb64
                6. Go back to the bottle and select either of thse as a runner.
            Note that the latest wine versions should also work if you select them as a runner. This would need to be installed onto yourr system from your distribution or building from source though, rather than through bottles.

    2. Installing Dotnet 8 Desktop Runtime
        2. Head to [Microsoft's Dotnet page](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) and download the latest x64 installer for **.NET Desktop Runtime 8.x.x**, the one which only has an installer for Windows.
        3. Go into your bottle, click `Run Excutable` and select the exe you have just downloaded.
        4. Head through the instillation page, agreeing and telling it to install it.

    3. Running the World Altering Editor
        1. Find your World Altering Editor inside your bottle's `Run Excutable`
        2. Open `WorldAlteringEditor.exe`
        3. Click on `Browse` and use wine's clunky file browser to find your mod/game's folder
        4. Select a map, either using browse again or using the built in file browser to select the map
        5. Open the map and enjoy!`


