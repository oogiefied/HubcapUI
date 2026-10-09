# HubcapUI

HubcapUI adds Hubcap controls directly to Steam without requiring a separate launcher or installer.

It lets you download, remove, and manage Lua files from the Steam Store and Library, displays your Hubcap usage, supports Multiplayer Mode, and can automatically organize Lua games into a Steam collection.

## Latest release: v1.2.1

- Fixed the settings cog failing to open outside Library after navigating between Steam pages.
- Improved click responsiveness by processing buffered events immediately.
- Fixed a reconnect race that could leave Hubcap's UI buttons unresponsive.
- Removed expired page sessions and added a settings fallback when no visible web page is available.
- Improved diagnostics for page connections, slow responses, and UI injection failures.

Verified working on: Steam build 1788652215

## Features

- Download or remove Lua directly from Steam Store pages.
- Manage installed Lua through Lua Settings dropdowns in the Steam Library.
- Open or remove Lua files directly from Library pages.
- Enable Multiplayer Mode (works for some games).
- See Multiplayer Mode indicators beside enabled games in the Library list.
- Automatically handle DLC and its base game.
- View daily Hubcap usage.
- Edit your Lua folder and API key from Steam.
- Keep games with Lua organized using Group Lua.
- Set up CloudRedirect providers and manage cloud-save settings from Steam.
- Download CloudRedirect and manage its updates separately from HubcapUI.
- View HubcapTools update status, release notes, and verified prepared updates.
- Collect detailed startup and runtime logs for troubleshooting.
- Automatically refresh when Lua files or Hubcap settings change.
- Check for HubcapUI updates automatically.
- Review release changes and choose **Update Now** or **Later**.
- Install future updates from HubcapUI.
- No separate launcher or installer.

Verified working on: Steam build 1788652215

## Requirements

- Windows 10 or Windows 11.
- 64-bit Steam.
- HubcapTool installed and configured.
- A valid Hubcap API key.

You can manage your API key at [Hubcap API Keys](https://hubcapmanifest.com/api-keys/stats).

## Installation

1. Download the newest `HubcapUI-vX.Y.Z.zip` from the [Releases](../../releases) page.
2. Fully exit Steam using **Steam -> Exit**.
3. Extract the downloaded ZIP.
4. Find your Steam installation folder, which is the folder containing `steam.exe`.

   The default location is:

   ```text
   C:\Program Files (x86)\Steam
   ```

5. Back up any previous HubcapUI DLL outside the Steam folder. Remove only the old HubcapUI `mswsock.dll`, if present, then copy `cfgmgr32.dll` from the ZIP beside `steam.exe`. Do not overwrite a DLL belonging to another tool.
6. Start Steam normally.

HubcapUI will load automatically when Steam starts.

The raw `mswsock.dll` release asset is used by automatic updates for compatibility with older versions. For manual installation, use `cfgmgr32.dll` from the ZIP. Both contain identical DLL bytes; the ZIP also includes installation and license documentation.

## Updating

HubcapUI v1.0.3 and newer check for updates automatically.

Updating from v1.0.9 to v1.1.0 or newer automatically migrates HubcapUI from `mswsock.dll` to `cfgmgr32.dll` after the usual Update Now and Restart & Update prompts. Steam performs an additional automatic restart to complete the migration. Existing settings, Lua files, and unrelated HubcapTool DLLs remain in place. The old Safe Mode game detection and startup recovery workaround have been removed.

- When an update is available, HubcapUI shows the changelog and offers **Update Now** or **Later**.
- Choosing **Later** keeps an Update button available across Steam pages.
- Clicking the Update button opens the changelog and update options again.
- Follow the prompts to install the update and restart Steam.

You can still update manually:

1. Download the newest release ZIP.
2. Fully exit Steam.
3. Back up the previous HubcapUI DLL outside the Steam folder. Remove only the old HubcapUI `mswsock.dll`, if present, and install the ZIP's `cfgmgr32.dll` beside `steam.exe`. Preserve unrelated tools and their DLLs.
4. Start Steam normally.

Version 1.0.2 and older must update to v1.0.3 manually before automatic updates are available.

## Uninstalling

1. Fully exit Steam.
2. Open the folder containing `steam.exe`.
3. Remove only the HubcapUI `cfgmgr32.dll` from the Steam folder. If using an older HubcapUI version, its DLL is named `mswsock.dll`.
4. Start Steam normally.

Removing the DLL does not delete your downloaded Lua files or HubcapTool configuration.

## Troubleshooting

### HubcapUI does not appear

- Make sure Steam was fully closed before copying the DLL.
- Confirm `cfgmgr32.dll` from the release ZIP is beside `steam.exe`.
- Restart Steam after installing the DLL.

### Hubcap config missing

HubcapTool must be installed and configured before HubcapUI can download or manage Lua files.

### Multiplayer Mode

Multiplayer Mode may help compatible setups find and join the same lobbies, but compatibility is not guaranteed. Removing a game's Lua file through HubcapUI also turns off Multiplayer Mode for that game.

### An update fails

If an automatic update does not complete, use the manual update steps above.

### Logs

HubcapUI keeps up to five recent logs here:

```text
%LOCALAPPDATA%\HubcapUI\logs
```

## Important

Steam updates may occasionally require HubcapUI to be reinstalled or updated.

This repository is used for HubcapUI documentation and binary downloads. Source code is not included. HubcapUI uses much of HubcapLauncher's behavior, while its Steam hooking implementation remains private ;P
