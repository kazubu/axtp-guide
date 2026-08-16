---
title: Troubleshooting
description: Symptom-based checks
---

# Troubleshooting

!!! note "Japanese is the source of truth"

    Some details are only filled in on the Japanese page: [トラブルシュート](troubleshooting.md).

Find the symptom below. If you cannot pin down the cause, report it at [Issues](https://github.com/kazubu/axtp-guide/issues) with a description and photos.

## Keyboard

??? failure "Not detected by the PC"

    - [ ] Try another USB-C cable or port (is it a charge-only cable?)
    - [ ] Hold BOOTSEL while plugging in and check that it mounts as `RPI-RP2`
      (if it does, the hardware is alive — reflash the firmware)
    - [ ] Check for bad joints or shorts around the RP2040 and the USB connector
    - [ ] Unplug the FPC cable and check whether it is detected (isolates a power short)

??? failure "A key does not respond"

    - [ ] Check that the switch pins are not bent
    - [ ] Redo the solder joints of the hot-swap socket
    - [ ] If a whole row or column is dead, suspect the PCB side

??? failure "One keypress produces several (chatter)"

    - [ ] Swap the switch to isolate it
    - [ ] Check for bad solder joints
    - [ ] Increase the debounce time (`DEBOUNCE` in `config.h`)

## Pointing stick

??? failure "Cursor does not move at all"

    - [ ] Check that the FPC cable is fully seated and latched at both the PCB and the mount PCB
    - [ ] Check the orientation of the FPC contacts (both ends face the board)
    - [ ] Check that no conductor is broken at a crease
    - [ ] Check the SK8707-01-004 controller and stick boards for bad joints and bridges
    - [ ] Check with a multimeter that VCC and GND are not shorted

??? failure "Cursor drifts on its own"

    - [ ] Do not touch the stick while the keyboard powers up — it calibrates at boot
    - [ ] Unplug USB and reconnect without touching the stick
    - [ ] Check that the cover or a keycap is not pressing on the stick
    - [ ] Check that the FPC cable is not pulling on the mount PCB
    - [ ] Check that the mount PCB screws are not overtightened

??? failure "Directions are wrong or inverted"

    - [ ] Check the orientation of the module
    - [ ] If only scrolling is inverted, try `CUSTOM(11)` (swap the scroll axes)

??? failure "Movement is jumpy"

    - [ ] Suspect a bad FPC contact — unplug and reseat it
    - [ ] Lower the pointer speed (`CUSTOM(3)`, [Customizing the Keymap](manual/keymap.md))

??? failure "Scrolling does not work"

    - [ ] Check that scroll mode is active (`CUSTOM(8)` / `CUSTOM(9)`, [Customizing the Keymap](manual/keymap.md))
    - [ ] Check the scroll buffer size (`CUSTOM(5)`)

??? failure "Clicks do not work"

    - [ ] Check that mouse buttons are assigned in the keymap
    - [ ] Check that they are on the layer Auto Mouse Layer activates

??? failure "Auto Mouse Layer misbehaves"

    - [ ] Check whether `AML_THRESHOLD` is too high for the layer to activate
    - [ ] Conversely, raise the threshold if it triggers on the slightest movement
    - [ ] Check that the hold time (`AML_TIMEOUT_MS`) is not too short
    - [ ] Changing these constants requires a rebuild ([Customizing the Keymap](manual/keymap.md))

## Last resorts

- [ ] Clear the EEPROM to reset the settings (`CUSTOM(1)` or `QK_CLEAR_EEPROM`)
- [ ] Reflash the firmware (hold BOOTSEL while plugging in, copy the `.uf2` to `RPI-RP2`)
- [ ] Unplug the FPC cable and check that the keyboard alone still works
