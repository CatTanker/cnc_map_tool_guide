## General Support

Document aimed at creating a generalised page that support staff can link to from any cncnet mod (or vanilla if suitable).



### Returning to the Client without actually launching the game (no error code)

#### Fix 1

Restart your Computer

#### Fix 2 [Win10/11 Only]

Restart failed, what now? Check your syringe.log file (should be where your gamemd.exe is). If it has this error message, then continue with Fix 2.
```
[hh:mm:ss] SyringeDebugger::HandleException: Exception (Code: 0xC0000005 at 0x9772A090)!
[hh:mm:ss] Occured while loading 'cncnet5.dll'.
[hh:mm:ss] SyringeDebugger::Run: Done with exit code C0000005 (3221225477).
```
1. Open Windows Security -> App & browser control -> Exploit protection settings -> Program settings -> Add program to customise -> Choose exact file path and browse to your gamemd.exe file.
2. Under Force randomisation for images (Mandatory ASLR), Override system settings should be off.
3. Under Randomise memory allocations (Bottom-up ASLR), Override system settings should be off.
4. Save the settings and restart your PC.

### QRES- Screen mode not found

Open windows settings and follow Display --> Scale and Layout
Look for a drop down saying "Change the size of text, apps and other items"
Ensure this is 100% and apply changes.

### Syringe could not run excutable - requested operation requires elevation

Find your mod install, right click --> properties --> compatibility and select "Run this program as administrator" for the following files:
- Main Client Exe (MentalOmegaClient.exe, YRlauncher.exe, REClient.exe etc)
- Syringe.exe
- gamemd.exe

### Fatal - String Manager failed to initialize properly

#### Fix 1

Ensure that you did not install your mod inside a windows protected area, such as Program Files (x86) or your Desktop.

#### Fix 2

Find your mod install, right click --> properties --> compatibility and select "Run this program as administrator" for the following files:
- Main Client Exe (MentalOmegaClient.exe, YRlauncher.exe, REClient.exe etc)
- Syringe.exe
- gamemd.exe
if the problem persists, apply WinXP Service Pack 3 to gamemd.exe in compatibility settings.

### Campaign missions seem to break (e.g. scripted units refuse to move)

Ensure your launching the mission **fresh** from the client's mission selector
Do not launch it from:
- Restart Mission
- Mission Saves (the auto generated ones)

## Renderer Issues

if your getting any of the following errors or problems:
- Error - Unable to set video mode
- Poor Performance
- Invisible Mouse upon using tab (stats), esc (options)

Head over to the renderers option in the client and try others. Also have a read of (link to renderers doc).
