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

Following discussions within the CnCNet development team, the dotnet 7 build that has been developed was being being rolled back due to dotnet 7 providing [a conbsiderably worse user experience](https://github.com/CnCNet/xna-cncnet-client/pull/494), mostly through microsoft choosing not to provide this by default in windows like they did with Dotnet 4. Although a major part of this initial push was for better support on Mac / Linux, the vast majority of the userbase is on windows, and so the profits of this are limited. In my experience i also met several issues with the dotnet 7 build that i did not meet in the dotnet 4.5 build, mostly down to the client initialising wine rather than using wine to run the client and the game.

However, as a result of this push, the current (March 2024) build appears to use dotnet 8 for native runnung on Mac/linux. 
```
	Windows: Windows 7 SP1 or higher is required. The preferred build is DirectX11 (.NET 4.8), i.e., clientdx.exe. If your GPU does not support DX11, consider using the OpenGL or XNA build instead. Advanced users may experiment with the .NET 8 builds at their discretion.
	Other OS: Use the Universal OpenGL build.

##

Linux requirements:

    The .NET 8.0 Runtime for your specific platform.

```
As a result, linux users using the latest client should head to the `Resources\BinariesNET8\OpenGL.dll`. Ideally, the launcher in the main folder should detect the correct framework though.

The Bottles method is suited only for those using older client frameworks, including but not limited to the list above. This is easy to follow and requires barely any command line usage, none if you choose to use a GUI package manager. 
The WineTricks method is suited for the older client frameworks as well, but also requires much more command line usage for arguably less customisable results. This does include parts that may help people using the Dotnet 7/8 client though.


The reason you will often see a ddraw or cnc-ddraw package mentioned as this means the game will use the ddraw supplied by the [client](https://github.com/FunkyFr3sh/cnc-ddraw), which will improve your experience significantly. I *highly recommend* you perform this recommendations. Although for some users the game may run fairly well without such support, this should improve your experience.

