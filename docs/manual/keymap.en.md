---
title: Customizing the Keymap
description: Remapping with VIA, and editing the source
---

# Customizing the Keymap

!!! note "Japanese is the source of truth"

    Some details are only filled in on the Japanese page: [キーマップの変更](keymap.md).

This keyboard is **VIA-enabled**: with VIA you can change the keymap without reflashing.

## Remapping with VIA

1. Open [VIA](https://usevia.app/)
2. If the keyboard is not detected automatically, pick it under `Authorize device`
3. Select a key and change its assignment

!!! warning "If changes are not saved"

    Your browser has to support WebHID (Chrome or Edge recommended).

## Mouse keycodes

| Purpose | QMK keycode |
| --- | --- |
| Left click | `KC_BTN1` |
| Right click | `KC_BTN2` |
| Middle click | `KC_BTN3` |

## Custom keycodes

Settings specific to this keyboard are changed with the keycodes below. Apart from scrolling they are not assigned in the default keymap, so assign the ones you need.

| Purpose | Keycode |
| --- | --- |
| Save the settings to EEPROM | `CUSTOM(0)` |
| Reset the EEPROM settings | `CUSTOM(1)` |
| Print the EEPROM settings (need to enable HID CONSOLE) | `CUSTOM(2)` |
| Change the pointer speed (hold and Up/Down to adjust) | `CUSTOM(3)` |
| Change the Sniper Layer pointer speed (same) | `CUSTOM(4)` |
| Change the scroll buffer size (same) | `CUSTOM(5)` |
| Sniper Mode while held | `CUSTOM(6)` |
| Toggle Sniper Mode | `CUSTOM(7)` |
| Scroll while held | `CUSTOM(8)` |
| Toggle scroll mode | `CUSTOM(9)` |
| Lock the scroll axis (none / horizontal / vertical) | `CUSTOM(10)` |
| Swap the scroll axes | `CUSTOM(11)` |

## Editing the source

For deeper customization, edit the keymap source.

[GitHub](https://github.com/kazubu/holykeebs-qmk/tree/hk-kazubu/keyboards/ai03/altair_x)

```
keyboards/ai03/altair_x/
├── config.h          # settings (default sensitivity and so on)
├── keyboard.json     # matrix and layout definition
└── keymaps/
    └── via/
        └── keymap.c  # VIA keymap
```

| Constant | Meaning |
| --- | --- |
| `AML_THRESHOLD` | Auto Mouse Layer sensitivity |
| `AML_TIMEOUT_MS` | How long Auto Mouse Layer stays active |
| `AUTO_MOUSE_LAYER` | The layer Auto Mouse Layer activates |
| `ALTTAB_LAYER` | On this layer, pressing Tab sends Alt + Tab |

After editing, build and flash as described in [Flashing Firmware](../build/05-firmware.md).
