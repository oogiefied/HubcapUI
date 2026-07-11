# HubcapUI

HubcapUI adds Hubcap controls directly to Steam without requiring a separate launcher.

It lets you download, remove, and manage Lua files from the Steam Store and Library. It also displays your Hubcap usage and supports automatically organizing games into a Steam collection with Group Lua.

## Features

- Download or remove Lua directly from Steam Store pages.
- Manage installed Lua from the Steam Library.
- Automatically handle DLC and its base game.
- View daily Hubcap usage.
- Edit your Lua folder and API key from Steam.
- Open Lua files directly from the Library.
- Keep games with Lua organized using Group Lua.
- Automatically refresh when Lua files or Hubcap settings change.
- No separate launcher or public debugging port.

## Requirements

- Windows 10 or Windows 11.
- 64-bit Steam.
- HubcapTool installed and configured.
- A valid Hubcap API key.

You can manage your API key at [Hubcap API Keys](https://hubcapmanifest.com/api-keys/stats).

## Installation

1. Download `HubcapUI-v1.0.zip` from the [Releases](../../releases) page.
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

## Updating

1. Download the newest HubcapUI release.
2. Fully exit Steam.
3. Replace the existing `mswsock.dll` beside `steam.exe`.
4. Start Steam again.

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

### Logs

HubcapUI keeps up to five recent logs here:

```text
%LOCALAPPDATA%\HubcapUI\logs
```

## Important

Steam updates may occasionally require HubcapUI to be reinstalled or updated.

This repository is used for HubcapUI documentation and binary downloads. Source code is not included. It mainly use my HubcapLauncher's logic, but im not sharing my hooking method ;P
