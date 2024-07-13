## Introduction
This guide gives mostly step-by-step instructions, useful tips and advice on running Yuri's Revenge, the Map Editor and indirectly Tiberian Sun on Linux.
These guides all assume *you are using the cncnet client, either officially or on a mod*

The first step you will need to do is to figure out which client version you are using.
Most pre-2024 CnCNet clients use the .NET framework. This includes, but is not limited to:<br>
    - YR CnCNet Official as of July 2024
    - Mental Omega 3.3.6 <br>
    - Rise of the East 3.0.0j <br>
    - RA20XX <br>
    - Red Ressurection <br>
    - C&C Reloaded <br>
    - Fading Dusk

According to the build instructions of the cncnet client in 2020:
```
	The client has 3 builds: Windows (DirectX11), OpenGL and XNA.

	The Windows and OpenGL builds rely on .NET Framework 4.5 and MonoGame.

	The XNA build relies on .NET Framework 4.0 and Microsoft's XNA Framework 4.0 Refresh.
```
The above lines are where most of my reasoning lies for the dependencies installed.

Following discussions within the CnCNet development team, the dotnet 7 build that has been developed was being being rolled back due to dotnet 7 providing [a conbsiderably worse user experience](https://github.com/CnCNet/xna-cncnet-client/pull/494), mostly through microsoft choosing not to provide this by default in windows like they did with Dotnet 4. Although a major part of this initial push was for better support on Mac / Linux, the vast majority of the userbase is on windows, and so the profits of this are limited.

However, as a result of this push, the current (March 2024) build appears to use dotnet 8 for native runnung on Mac/linux. 
```
	Windows: Windows 7 SP1 or higher is required. The preferred build is DirectX11 (.NET 4.8), i.e., clientdx.exe. If your GPU does not support DX11, consider using the OpenGL or XNA build instead. Advanced users may experiment with the .NET 8 builds at their discretion.
	Other OS: Use the Universal OpenGL build.

##

Linux requirements:

    The .NET 8.0 Runtime for your specific platform.

```
As a result, linux users using the latest client should head to the `Resources\BinariesNET8\OpenGL.dll`. Very few mods currently ship with the absolute latest client as of yet, so most advice is still catered towards running the slightly older clients. IF you run the exe of a newer client with something such as bottles, it should detect you as a WindowsOS, and so you should be able to run the new client fine.

The Bottles method is suited for people wanting a GNOME-like GUI, or even just a GUI that is more than lists and buttons.
The WineTricks method is suited to people who would prefer to not have a GUI.
Lutris is also an option. It contains a few packages to automatically install cncnet (just for the official YR CnCnet), but does require a little more work than bottles to setup.

The reason you will often see a ddraw or cnc-ddraw package mentioned as this means the game will use the ddraw supplied by the client, [such as cnc-ddraw](https://github.com/FunkyFr3sh/cnc-ddraw), which will improve your experience significantly.
