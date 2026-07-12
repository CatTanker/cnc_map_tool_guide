## Introduction to running CnC on Linux

Linux compatability with the game has only increased over the years, and now takes very little effort to set up. For most mods and official releases, the client now comes with built-in linux support, with the client automatically running the game in wine for you. The client is now also built using the latest dotnet, meaning it runs natively on Linux. This should be run in the form of a`.sh` inside the top of the game folder, such as `YRLauncher.sh`. 

**Both** of the current Tiberian Sun & Yuri's Revenge clients off [cncnet](cncnet.org) have this script, and so upon running it you should be good to go. Certain mods such as [Dawn of the Tiberian Age]
(https://cncnet.org/dawn-of-the-tiberium-age) also work extremely well through this native client. You will need to install the required dotnet version to run the client natviely, which as of writing is typically dotnet 8, but this should be offered in a pop-up upon running the client. 


--- 

For users of other Mods, this is very dependent on the mod itself. Mods such as Mental Omega 3.3.6, Red Resurrection, Twisted Insurrection, and many that haven't been updated since 2024 **do not** have the native client build, so you need to run it entirely through wine. 

On this website there are three main documented ways. 
One is using wine & winetricks traditionally, which is the most space effecient method but easily the hardest, as well as providing no other benefits other than with very recently updated cncnet clients, although this may be useful information if you run into issues with the native build's ability to run the game smoothly. 

There is a Lutris guide, however the application can be confusing / counter-intuitive and so it not my preference. It does however have some pre-made user / third-party scripts running both old versions of the client and perhaps some mods. 

For the third method, there is Bottles, which is the way I recommend and personally use, and is the most updated of the guides. If configured correctly, this can run any of the older mods and, in most cases, run the windows builds of the latest clients as well. 

There is little reason to run the latest client through these methods, however using Lutris or Bottles will let you easily set up DXVK and other small tweaks that may slightly improve performance of the game itself.
