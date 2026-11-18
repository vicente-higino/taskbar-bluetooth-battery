# Taskbar Bluetooth Device Battery Level (Windhawk Mod)

> **⚠️ AI Disclaimer:** This Windhawk mod was created and developed with the assistance of AI (Google DeepMind Antigravity). Please review the source code in [`mod.wh.cpp`](./mod.wh.cpp) before use.

Displays currently connected Bluetooth devices and their battery percentages directly on the Windows 11 taskbar system tray using a native XAML widget.

## Features

- **Classic Bluetooth & BLE Support**: Automatically detects connected Classic Bluetooth (Hands-Free / AVRCP) and Bluetooth Low Energy (GATT Battery Service `0x180F`) devices via Windows Configuration Manager (`CfgMgr32`), `BluetoothApis.dll`, and WinRT `BluetoothLEDevice`, grouped by `DEVPKEY_Device_ContainerId`.
- **Smart Device Category Icons**: Uses native Windows 11 `Segoe Fluent Icons` glyphs for headphones, headsets, speakers, mice, keyboards, controllers, pens/styluses, phones, watches, and generic Bluetooth devices.
- **Rich Hover Tooltip**: Hovering over the widget displays the full friendly name, category, and battery percentage of every connected Bluetooth device.
- **Battery Level Color Coding**: Automatically highlights low (`<= 20%` amber) and critical (`<= 10%` red) battery levels while inheriting the active Windows 11 Light/Dark taskbar text theme.
- **Event-Driven Updates**: Immediately updates when Bluetooth devices connect or disconnect via PnP Configuration Manager notifications (`CM_Register_Notification`), paired with a configurable background polling interval.
- **Quick Actions**: Clicking the widget opens the Windows 11 Quick Settings Bluetooth flyout (`ms-controlcenter:bluetooth`), Windows Bluetooth Settings (`ms-settings:bluetooth`), or triggers an immediate battery refresh.

## Configuration Settings

| Setting | Options / Default | Description |
| :--- | :--- | :--- |
| **Inline display format** | `iconAndPercentage` (Default), `nameAndPercentage`, `iconNameAndPercentage`, `batteryIconAndPercentage` | Choose what information is shown inline for each connected device. |
| **Multiple connected devices mode** | `all` (Default), `lowest` | Show all connected devices side-by-side (up to Max devices) or only the lowest-battery device inline. |
| **Maximum inline devices** | `5` (Default) | Maximum number of Bluetooth devices displayed side-by-side on the taskbar. |
| **Maximum inline device name length** | `12` (Default) | Maximum number of characters when displaying device names inline (`0` = unlimited). |
| **Taskbar tray position** | `beforeControlCenter` (Default), `afterControlCenter`, `beforeTrayIcons`, `insideControlCenter` | Where to place the Bluetooth battery widget in the Windows 11 system tray area. |
| **When no Bluetooth device is connected** | `hide` (Default), `showPlaceholder` | Hide the widget automatically or keep a dimmed Bluetooth placeholder (`--%`) visible. |
| **Battery level color coding** | `lowOnly` (Default), `always`, `none` | Colorize battery text/icons based on remaining battery level. |
| **Click action** | `openQuickSettings` (`ms-controlcenter:bluetooth`, Default), `openBluetoothSettings` (`ms-settings:bluetooth`), `refresh`, `none` | Action performed when clicking the widget on the taskbar. |
| **Show on secondary monitor taskbars** | `true` (Default) | Display the Bluetooth battery widget on secondary monitors in multi-monitor setups. |
| **Refresh interval (seconds)** | `15` (Default) | Background polling interval in seconds (in addition to instant connect/disconnect events). |
| **Font size** | `12` (Default) | Font size (in pixels) for the battery percentage text and icons. |
| **Spacing between devices (pixels)** | `8` (Default) | Spacing between multiple connected Bluetooth device items. |

## Installation

1. Open [Windhawk](https://windhawk.net/).
2. Click **Create a new mod** in the bottom-right corner.
3. Replace the template contents with [`mod.wh.cpp`](./mod.wh.cpp).
4. Click **Compile Mod** (`Ctrl+B`).

## License

Released under the [MIT License](https://opensource.org/licenses/MIT).
