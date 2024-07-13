 
![Lutris](https://upload.wikimedia.org/wikipedia/commons/9/99/Lutris_Game_Platform_%28Logo%29.svg)

Lutris is a fairly popular game launcher for Linux. Note you **need** to do the custom runner to restore multiplayer functionality to cncnet, as well as probably fix some misc errors or bugs.

### Setting up your bottle (For flexibility and mod usage)

Pre-Setup:

Install Lutris and wine.
Download the latest wine-*-**-amd64.tar.xz [custom runner](https://github.com/Kron4ek/Wine-Builds/releases) and extract this to:
```
/home/[USERNAME]/.local/share/lutris/runners/wine/
```
Setting it up:


1. Select the + icon top-left

2. Add Locally Installed Game

3. Select the Runner as wine

4. In Runner Options, select the runner you just downloaded

5. Name the mod/game in Game Options, and point the excutable to that mod/game's excutable, then save

6. Open the Wine Prefix entry, and guide it to an empty folde somewhere that doesn't interrupt you, such as in a folder where your mods all are, and give it a name so you have an idea what it is, and save

7. Head to the bottom of Lutris --> select winetricks --> select create a new wineprefix and tell it to save  --> Install a windows DLL or component --> cnc-ddraw

8. press cancel twice to escape winetricks.

9. Try it out!


You can duplicate the launcher by right clicking and selecting duplicate, duplicate, and then changing the exe launcher path to another mod or game.

If you get asked to install mono, say yes and follow the instructions, then continue on.


### CnCNet Vanilla YR
There are scripts if you select Search the Lutris website for installers that will let you open up the EA App/Origin, and guide you through installing cncnet.
