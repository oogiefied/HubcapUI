# HubcapUI

HubcapUI adds Hubcap controls directly to Steam without requiring a separate launcher or installer.

It lets you download, remove, and manage Lua files from the Steam Store and Library, displays your Hubcap usage, supports Multiplayer Mode, and can automatically organize Lua games into a Steam collection.

## Features

- Download or remove Lua directly from Steam Store pages.
- Manage installed Lua through Lua Settings dropdowns in the Steam Library.
- Open or remove Lua files directly from Library pages.
- Enable Multiplayer Mode for individual games.
- See Multiplayer Mode indicators beside enabled games in the Library list.
- Automatically handle DLC and its base game.
- View daily Hubcap usage.
- Edit your Lua folder and API key from Steam.
- Keep games with Lua organized using Group Lua.
- Automatically refresh when Lua files or Hubcap settings change.
- Check for HubcapUI updates automatically.
- Review release changes and choose **Update Now** or **Later**.
- Install future updates from HubcapUI.
- No separate launcher or installer.

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

5. Copy `mswsock.dll` into that folder beside `steam.exe`.
6. Start Steam normally.

HubcapUI will load automatically when Steam starts.

The release also provides a standalone `mswsock.dll`. The ZIP and standalone download contain the same DLL; the ZIP additionally includes installation and license documentation.

## Updating

HubcapUI v1.0.3 and newer check for updates automatically.

- When an update is available, HubcapUI shows the changelog and offers **Update Now** or **Later**.
- Choosing **Later** keeps an Update button available across Steam pages.
- Clicking the Update button opens the changelog and update options again.
- Follow the prompts to install the update and restart Steam.

You can still update manually:

1. Download the newest release ZIP.
2. Fully exit Steam.
3. Replace the existing `mswsock.dll` beside `steam.exe`.
4. Start Steam normally.

Version 1.0.2 and older must update to v1.0.3 manually before automatic updates are available.

## Uninstalling

1. Fully exit Steam.
2. Open the folder containing `steam.exe`.
3. Delete `mswsock.dll`.
4. Start Steam normally.

Removing the DLL does not delete your downloaded Lua files or HubcapTool configuration.

## Troubleshooting

### HubcapUI does not appear

- Make sure Steam was fully closed before copying the DLL.
- Confirm `mswsock.dll` is beside `steam.exe`.
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
