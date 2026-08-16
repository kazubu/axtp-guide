---
title: Layer Status App
description: Showing the active layer as a cursor and tray icon colour with QMK Keyboard Status
---

# Layer Status App

!!! note "Japanese is the source of truth"

    Some details are only filled in on the Japanese page: [レイヤー状態の通知アプリ](status-app.md).

[QMK Keyboard Status](https://github.com/kazubu/QMK_KeyboardStatus) is a Windows app that shows the active layer as the colour of the **mouse cursor** and of its **system tray icon**.

Auto Mouse Layer switches layers without a keypress, which makes it easy to lose track of whether the mouse layer is currently active. With this app running, the cursor colour tells you at a glance.

## Requirements

| Item | Value |
| --- | --- |
| OS | Windows |
| Keyboard | QMK firmware including the `companion_hid` module |

!!! success "The released firmware works as-is"

    The VIA firmware published on [Releases](https://github.com/kazubu/axtp-guide/releases) is built with the `companion_hid` module from [bskaplou/qmk_modules](https://github.com/bskaplou/qmk_modules), so there is nothing to reflash.

## Installing

1. Download `release.zip` from [Releases](https://github.com/kazubu/QMK_KeyboardStatus/releases)
2. Extract it wherever you like
3. Run the executable — it lives in the system tray

## Settings

Open **Layer Settings...** from the tray icon's context menu to configure each layer (up to 16):

| Item | Meaning |
| --- | --- |
| Layer name | The name shown in the list |
| Cursor colour | Mouse cursor colour on that layer |
| Icon colour | Tray icon colour on that layer |
| Colour change on / off | Whether that layer changes the colours at all |

The layer numbers match the table in [Basics & Layers](usage.md). Giving layer 5 (Mouse) — the one Auto Mouse Layer activates — a distinctive colour makes it obvious when you are still on the mouse layer.

## Building from source

Open `QMKStatus.sln` in Visual Studio. See the [repository](https://github.com/kazubu/QMK_KeyboardStatus) for details.

## If you build the firmware yourself

When building from source as described in [Flashing Firmware](../build/05-firmware.md), check that the keymap's `keymap.json` contains:

```json
"modules": ["bskaplou/companion_hid"]
```

Without it the keyboard sends no layer notifications and the app cannot track the state.
