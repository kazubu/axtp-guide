---
title: Flashing Firmware
description: Flashing the prebuilt firmware and building from source
---

# Flashing Firmware

The firmware is **QMK** (VIA-enabled). Since the controller is an RP2040, flashing is just a UF2 drag-and-drop.

!!! info "Flash both halves"

    This is a split keyboard — flash the same firmware to **both the left and the right half**.

## 1. Get the firmware

The latest firmware is available on [Releases](https://github.com/kazubu/axtp-guide/releases).

| File | Purpose |
| --- | --- |
| `ai03_altair_x_via.uf2` | VIA-enabled keymap |

## 2. Entering the bootloader

When the RP2040 enters its bootloader, it mounts as a drive named **`RPI-RP2`**.

=== "From the keyboard"

    Assign `QK_BOOT` to a key in VIA and press it.

=== "BOOTSEL button"

    With the USB cable unplugged, hold the BOOTSEL button on the back of the PCB and plug it in.

    ![The RESET / BOOT buttons on the PCB](../assets/images/build/05-button.jpg){ loading=lazy }

=== "Reset button"

    Press the reset button on the back of the PCB twice quickly.

    ![The RESET / BOOT buttons on the PCB](../assets/images/build/05-button.jpg){ loading=lazy }

## 3. Flashing

1. Enter the bootloader and open the `RPI-RP2` drive
2. Copy the `.uf2` file to the drive
3. The board reboots automatically — flashing is done

## 4. Building from source

```bash
# One-time QMK setup
python3 -m pip install --user qmk
qmk setup

# Get the firmware for this mod
git clone https://github.com/kazubu/holykeebs-qmk.git
cd holykeebs-qmk

# Build (produces ai03_altair_x_via.uf2 in the repository root)
make ai03/altair_x:via -e USER_NAME=holykeebs -e POINTING_DEVICE=trackpoint -e POINTING_DEVICE_POSITION=right -e OLED=no -e CONSOLE=no -j8
```

For Auto Mouse Layer — the feature that temporarily activates a mouse layer after you move the pointer — see [Customizing the Keymap](../manual/keymap.md).

## 5. After flashing

- [ ] Keys type correctly
- [ ] The TrackPoint moves the cursor
- [ ] Auto Mouse Layer works (the layer switches after pointer movement)
- [ ] Layers switch

!!! tip "Resetting the settings"

    If the board misbehaves, clearing the EEPROM often helps. Assign `CUSTOM(1)` (reset the EEPROM settings) or `QK_CLEAR_EEPROM` to a key and press it.

---

For remapping, see [Customizing the Keymap](../manual/keymap.md).
