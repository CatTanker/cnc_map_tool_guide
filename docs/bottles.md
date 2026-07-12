![BottlesImage](Assets/BottlesFirstImage.png)

[Bottles](https://usebottles.com) is a popular GUI Manager to run Windows software on Linux through wine. Follow their website for install instructions and further details on the software itself. Setting up Bottles is possibly the quickest and easiest way to run Tiberian Sun, Yuri's Revenge and mods, and is my method of choice. 

![BottlesRunnersImage1](Assets/BottlesLatestRunner.png)
Rather than being limited to the mainstream wine distribution that your package manager provides, bottles gives you easy access to most popular runners, including cutting edge builds and enhanced versions such as Valve's Proton that is used in steam. While the initial install only ships with Soda (at the time of writing), I personally find the latest version of Kron4ek works best, as well as being frequently updated with Wine's improvements, such as improved running under Wayland. At the time of writing the latest version of [Soda](https://usebottles.com/runners) is 9.0.1, which is a fair bit behind Kron4ek's version of 11.12. I have also had good experiences with Caffe working on all fronts, and so i recommend giving that a try. If you are not sure, you can skip this step and use Soda for now, which may work fine for you. To access this page, click the three lines at the top-right hand corner, preferences, and then Runners. You can also use the hotkey 'Ctrl + ,'.


## Setting up the bottle
![New Bottle Creation](Assets/BottlesUseLatestRunner.png)

To make a new bottle, click the + symbol in the top-left corner. Name it appropriately, selecting a new runner if you downloaded one. If not then you can proceed with Soda. Using either the Application or Gaming preset both work fine, I tend to use Application as i don't require all the runtimes that Gaming downloades for 3D rendering. Not always required, but i do recommend installing the CnC-DDraw dependency, which guarantees your game will run at a decent speed as well as fixing artifacts as it would on Windows. 

![CncDDraw](Assets/BottlesAddingCnCDDraw.png)

## Running the game

To start a CnCNet Client, simply select Launch Executable. Once you know this is the right exe, i recommend adding it as a shortcut to save time. I encourage you to open the Settings page, and turn on DXVk if it is not already installed, this may slightly improve performance, as explained in the [renderers page](rendererresources.md). 

## Troubleshooting
### Client won't open
If the client won't open, such as running 'MentalOmegaClient.exe' for Mental Omega, enter the 'Resources' page of the game and try the client___.exe files (ogl, dx, xna). One of these should open. 

If you get an error complaining that bottles failed to create a graphical device, you have likely updated your system. Flatpak is not automatically updated, and needs to have the same graphical drivers as your current system. Updating flatpak will fix the problem. 

If you are attempting to run the latest client, you may need to mess around further with runners, although through the instructions above i can smoothly run DTA even though it is on the newer client, so it is not a dependency issue. 

### Game won't open
This is a fairly broad issue. Contact your game's support team for direct advice if possible. Some error messages or being sent back to the client appear on Windows too, so often the windows solution fixes this. Since you cannot run things as admin as a fix, try setting up a new bottle using another runner. Clean installing a bottle with this runner is preferred to switching it, as like wine prefixes a bottle can become bugged or corrupted. I also recommend scrolling down the Settings page and finding Steam Runtime, which can provide a fix at times but may cause randomly timed desyncs ingame so i don't recommend it by default. Toggling DXVK may also help. 


### Issues Ingame
if you have no sound, and can confirm the game **should** give sound, especially if it is music, check you have installed the music pack for your game, and it appears in the ingame juxebox. If this doesn't appear after installing it, try turning on the Steam Runtime in settings. For any graphical issues, check the [renderers page](rendererresources.md). 

