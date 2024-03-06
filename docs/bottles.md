## Bottles Instructions
I find bottles seems to give me the most reliable result on my many re-installs, find information about it [here](https://usebottles.com) and download it to your OS.<br>
Most guides seem to recommend using Flatpack for the download, which may help if you are experiencing issues, as well as providing some areas such as sandboxing, but I have tested on the non-flatpack version.

Below I have included the configuration that I use for Bottles so that you can produce the bottle in steps following the GUI. You should complete the main initial steps and then follow either Config 1 or Config 2 (Recommended).  There are also runner options included in a table a little further down.<br>
If you would prefer, I now include a bottles configuration .yml that you can [download](Assets/CnCNet_Bottles_Config.yml) and then import back into bottlesas a configuration.

### Dotnet 4.* Clients + OpenGl (ogl) Build - Manually Entered

Create new --> *Application* <br>
In Settings: <br>
- Runner: Check Runner Compatability Table <br>
- DXVK/VKD3D : Enabled <br>
- LatencyFleX : Disabled <br>
- Windows Version: Windows 10 (since some builds of phobos and other extensions require Windows 7 or higher) <br>

#### Config 1: Manually Entered

*Dll Overrides:*  (Assume :Native, then Builtin, unless specified otherwise)<br>
- ddraw as a DLL Override *Enter Manually* <br>

*Installed Dependencies:* <br>
- arial32/times32/courie32 [By Default] <br>
- Mono (Wine Mono) [Install Yourself] <br>


#### Config 2: CnC-DDraw dependency (Recommended)

*Installed Dependencies:*<br>
- arial32/times32/courie32 [By Default]<br>
- Mono (Wine Mono) [Install Yourself]<br>
- CnC-DDraw as a dependency [Install Yourself]<br>



After following all of the steps above, enter your bottle, click "Run Excutable", and guide it to your client folder / Resources, and then try "clientogl.exe", and the client should run fine, as well as the game. In some cases the xna client also seems to work, but try the ogl build first. **Do not expect the exe included in the root of the mod folder, eg. 'MentalOmegaClient.exe' to work, use the .ogl build!**<br>

### Runner Compatability
| Recommended | Runner | Client Compatability | Offline Compatability | Online Compatability | Notes |
| ------------ | ------------ | ------------- | ------------- | ------------- | ------------- |
| &#x2611; | Soda-7.0.9 | Fully Functional | Functional | Functional | Pressing esc --> Game Controls instantly closes gamemd |
| &#x2612; | Soda-8.0.2 | Fully Functional | Launches Incorrectly  | Unaccessible - launch Issue|  |
| &#x2612; | Vanigilla-8.6 | Not Functional | Unnaccesible  | Unaccessible | Error upon launching the client |
| &#x2612; | Lutris-7.2 | Fully Functional | Functional | Fails to connect to gamesurge - Error Denied | Port/ICMP Issue? |
| &#x2612; | wine-ge-proton8-25 | Fully Functional | Launches Incorrectly | Unaccessible - Launch Issue | Pressing esc --> Game Controls instantly closes gamemd |
| &#x2612; | Sys-Wine-9.1 (From package Manager) | Fully Functional | Syringe Issue | Unaccessible - Syringe Issue | Pressing esc --> Game Controls instantly closes gamemd |
| &#x2611; | Caffe-8.21 | Fully Functional | Fully Functional | Fully Functional | |
| &#x2611; | kron4ek-wine-8.20-amd64 | Fully Functional | Fully Functional | Fully Functional | |

This table has been tested using the Bottles Config 2 specifically on MO 3.3.6, with fully functional runners also tested on other mods. This was only tested with DXVK/VKD3D disabled due to physical limitations at the time.
You will need to install most of these runners from inside bottles, through the 'Main Menu' button in the top-right corner, 'Preferences', and then from the 'Runners' tab. 
