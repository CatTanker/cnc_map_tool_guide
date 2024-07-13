## General Support

Document aimed at creating a generalised page that support staff can link to from any cncnet mod (or vanilla if suitable). Typically catered towards YR/YR Mods however.



### Returning to the Client without actually launching the game (no error code)

Firstly, restarting your PC seems to be the most common fix.

If a restart fails, and you **are on Windows 10/11** , then check your syringe.log file (should be where your gamemd.exe is). If it has this error message, then continue.
```
[hh:mm:ss] SyringeDebugger::HandleException: Exception (Code: 0xC0000005 at 0x9772A090)!
[hh:mm:ss] Occured while loading 'cncnet5.dll'.
[hh:mm:ss] SyringeDebugger::Run: Done with exit code C0000005 (3221225477).
```
1. Open Windows Security -> App & browser control -> Exploit protection settings -> Program settings -> Add program to customise -> Choose exact file path and browse to your gamemd.exe file.

2. Under Force randomisation for images (Mandatory ASLR), Override system settings should be off.

3. Under Randomise memory allocations (Bottom-up ASLR), Override system settings should be off.

4. Save the settings and restart your PC.

### QRES - Screen mode not found

Open windows settings and follow Display --> Scale and Layout
Look for a drop down saying "Change the size of text, apps and other items"
Ensure this is 100% and apply changes.

### Syringe could not run excutable - requested operation requires elevation

Find your mod install, right click --> properties --> compatibility and select "Run this program as administrator" for the following files:

- Main Client Exe (MentalOmegaClient.exe, YRlauncher.exe, REClient.exe etc)

- Syringe.exe

- gamemd.exe


### Failed to open the excutable!

In some cases, antivirus can often have false positives on files that are contained within mods. This typically appears in your `syringe.log` file as the following:

```
[19:51:02] WinMain: Trying to load executable file "gamemd.exe"...

[hh:mm:ss] SyringeDebugger::RetrieveInfo: Retrieving info from the executable file...
[hh:mm:ss] SyringeDebugger::RetrieveInfo: Failed to open the executable!
[hh:mm:ss] WinMain: ERROR: Could not load executable file, exiting...
[hh:mm:ss] WinMain: Exiting on failure.

```
 Whitelisting your entire mod folder is often a good first step. If a file is isolated/removed, you will need to tell your AV to restore it. In most cases, this is either `Syringe.exe`,`ares.dll`, or one of the `client__.exe` files in resources.

### Fatal - String Manager failed to initialize properly

Ensure that you did not install your mod inside a windows protected area, such as Program Files (x86) or your Desktop.

If you have checked the above, find your mod install, right click --> properties --> compatibility and select "Run this program as administrator" for the following files:

- Main Client Exe (MentalOmegaClient.exe, YRlauncher.exe, REClient.exe etc)

- Syringe.exe

- gamemd.exe

if the problem persists, apply WinXP Service Pack 3 to gamemd.exe in compatibility settings.

### Campaign missions seem to break (e.g. scripted units refuse to move)

Ensure your launching the mission **fresh** from the client's mission selector
Do not launch it from:

- Restart Mission

- Mission Saves (the auto generated ones)

### External Links

[CnCnet FAQ](https://forums.cncnet.org/topic/6866-frequently-asked-questions/) - Covers a few topics that are not mentioned here, such as DroneBL Blacklisting.
[Linux Pages](https://cc-resource-docs.readthedocs.io/linuxsupport/) - Covers linux specific support


## Renderer Issues

if your getting any of the following errors or problems:

- Error - Unable to set video mode

- Poor Performance

- Invisible Mouse upon using tab (stats), esc (options)

Then head over to the [renderers page](https://cc-resource-docs.readthedocs.io/rendererresources/) for guidance and advice.

## Crash during the loading screen (Steam Only)

The latest version of YR from steam (and the EA App) require a special `syringe.exe` file. This can be downloaded from the [ares website](https://launchpad.net/ares/+download), by selecting the emergency update syringe.exe for Steam and EA App editions (and the mo specific one for mods that have customised their file extension to a specific one rather than ___md.*, such as ___mo.mix or ___re.mix files)

 Also a special thanks to Mo Discord Staff for putting together a quality guide that I could base parts of this article from.
