![Bottles](https://usebottles.com/uploads/bottle-creation-dark.png)

I find bottles seems to give me the most reliable result on my many re-installs, find information about it [here](https://usebottles.com) and download it to your OS.<br>
Most guides seem to recommend using Flatpack for the download, which is the only supported and official build so I highly recommend using it.

Below I have included the configuration that I use for Bottles so that you can produce the bottle in steps following the GUI. You should complete the main initial steps and then follow either Config 1 or Config 2 (Recommended).  There are also runner options included in a table a little further down.<br>
If you would prefer, I now include a bottles configuration .yml that you can [download](Assets/CnCNet_Bottles_Config.yml) and then import back into bottlesas a configuration.

### Setting up your bottle

Create new --> *Application* <br>
In Settings: <br>
- Runner: Check Runner Compatability Table <br>
- DXVK/VKD3D : Enabled <br>
- LatencyFleX : Disabled (Unless you want it)<br>
- Windows Version: Windows 10 <br>


*Installed Dependencies:*<br>
- arial32/times32/courie32 [By Default]<br>
- Mono (Wine Mono) [Install Yourself if it is not there by default]<br>
- CnC-DDraw as a dependency [Install Yourself]<br>



After following all of the steps above, enter your bottle, click "Run Excutable", and guide it to your client folder and select the main client (e.g. `YRLauncher.exe` or `MentalOmegaClient,exe`), and your client should load. In caseswhere this does not work, go into the Resources foler and then try "clientogl.exe", and the client should run fine, as well as the game. In some cases the xna client also seems to work, but try the ogl and dx builds first.

### Runner Compatability
| Recommended | Runner | Client Compatability | Offline Compatability | Online Compatability | Notes |
| ------------ | ------------ | ------------- | ------------- | ------------- | ------------- |
| &#x2611; | Soda-7.0.9 | Fully Functional | Functional | Functional | Pressing esc --> Game Controls instantly closes gamemd |
| &#x2612; | Soda-8.0.2 | Fully Functional | Launches Incorrectly  | Unaccessible - launch Issue|  |
| &#x2612; | Vanigilla-8.6 | Not Functional | Unnaccesible  | Unaccessible | Error upon launching the client |
| &#x2611; | Lutris-7.2 | Fully Functional | Functional | Fails to connect to gamesurge - Error Denied | Port/ICMP Issue? |
| &#x2611; | wine-ge-proton8-25 | Fully Functional | Launches Incorrectly | Unaccessible - Launch Issue | Pressing esc --> Game Controls instantly closes gamemd |
| &#x2611; | Sys-Wine-9.1 (From package Manager) | Fully Functional | Syringe Issue | Unaccessible - Syringe Issue | Pressing esc --> Game Controls instantly closes gamemd |
| &#x2611; | Caffe-8.21 | Fully Functional | Fully Functional | Fully Functional | |
| &#x2611; | kron4ek-wine-8.20-amd64 | Fully Functional | Fully Functional | Fully Functional | |

This table has been tested using the Bottles Config 2 specifically on MO 3.3.6, with fully functional runners also tested on other mods. This was only tested with DXVK/VKD3D disabled due to physical limitations at the time.
You will need to install most of these runners from inside bottles, through the 'Main Menu' button in the top-right corner, 'Preferences', and then from the 'Runners' tab.

Note the above runners were tested on the arch-specific [aur](https://wiki.archlinux.org/title/Bottles). I recently changed from this version due to minor bugs/limitations compared to the Flatpak version, and so runners on the next table may give a more reliable list. DXVK/DXD3D/DXVK NVAPI are in use. The ogl support seems to be better on flatpak, so i can now launch the main client esxe (e.g. `MentalOmegaClient.exe` rather than having to go into resources), and i have moved to using the ogl renderer instead of the dx/gdi one.

| Recommended | Runner | Client Compatability | Offline Compatability | Online Compatability | Notes |
| ------------ | ------------ | ------------- | ------------- | ------------- | ------------- |
| &#x2611; | Caffe-9-7 | Fully Functional | Fully Functional | Fully Functional | |
| &#x2611; | kron4ek-wine-9.11-amd64 | Fully Functional | Fully Functional | Fully Functional | Up to date renderer |
