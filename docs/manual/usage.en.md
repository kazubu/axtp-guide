---
title: Basics & Layers
description: Basic operation and layer layout
---

# Basics & Layers

!!! note "Japanese is the source of truth"

    Some details are only filled in on the Japanese page: [基本操作とレイヤー](usage.md).

## Connecting

1. Connect the keyboard to your PC with a USB-C cable

No extra drivers are needed — the TrackPoint is recognised as a standard USB mouse.

!!! warning "Do not touch the stick at power-on"

    The module calibrates itself when powered up; touching it during boot makes the cursor drift.

## Key layout

Check the current layout in VIA.

The TrackPoint sits in the **innermost column of the right half**.

![The pointing stick in the innermost column of the right half](../assets/images/hero.jpg){ loading=lazy }

## Layers

<!-- TODO: 実際のキーマップに合わせて更新 -->

| Layer | Activation | Purpose |
| --- | --- | --- |
| 0: Base | default | Typing |
| 1: Lower | left layer key | Numbers and so on |
| 2: Raise | right layer key | Symbols and so on |
| 3: Adjust | both layer keys | Function keys and so on |
| 4: End | unused | unused |
| 5: Mouse | Auto Mouse Layer | Mouse buttons and scrolling |
| 6: Pointer | unused | unused |

## Auto Mouse Layer

This keyboard supports **Auto Mouse Layer**: moving the TrackPoint activates the mouse layer automatically, and it returns to the previous layer after a period of inactivity. That means you can click without holding a layer key.

| Behaviour | Default |
| --- | --- |
| Layer activated automatically | Layer 5 (Mouse) |
| Time before returning | 500 ms |
| Mouse buttons while it is active | left-hand thumb keys |

Disabling Auto Mouse Layer or changing the timing means editing the constants in `keymap.c` and rebuilding ([Customizing the Keymap](keymap.md)).

!!! tip "When you cannot tell which layer you are on"

    On Windows, the [Layer Status App](status-app.md) shows the active layer as the colour of the mouse cursor and the tray icon.

---

For pointer speed and similar settings, see [Customizing the Keymap](keymap.md).
