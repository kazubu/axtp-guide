---
title: PCB Assembly
description: Switch sockets and preparation for mounting the TrackPoint
---

# PCB Assembly

Work on the Altair-X PCB itself. Get the board working as a plain keyboard before installing the TrackPoint.

## 1. Inspect the PCB

- [ ] Check for warping, scratches and missing pads
- [ ] Check the orientation (front / back) against the silkscreen

## 2. Switch sockets

Solder the hot-swap sockets to the PCB. The three keys in the innermost column have pads, but you do not need to install sockets there.

![Hot-swap sockets and the TrackPoint connector](../assets/images/build/02-sockets.jpg){ loading=lazy }

## 3. Standoff for the TrackPoint mount

Using the M2 x 3mm screw and two washers, attach an M2 x 3mm hex standoff to the PCB.

Stack them in this order: screw｜washer｜PCB｜washer｜hex standoff.

![The hex standoff mounted on the PCB](../assets/images/build/02-standoff.jpg){ loading=lazy }

## 4. FPC cable for the TrackPoint

Insert the FPC cable into the J2 connector on the back of the PCB, then fold it in this order before routing it to the front side:

1. The cable leaves J2 heading right — a **45° diagonal fold** turns it downward
2. **Fold it back 180°** so it points up
3. Route it through the **center-pole hole of the topmost switch position**, up and to the right of J2, to the front side

The fold-back is what gets the contacts of the reversed-contact FPC cable onto the correct side: the 45° diagonal fold turns the cable by 90° but swaps its faces, and the 180° fold-back swaps them again.

--8<-- "snippets/fpc-fold.en.svg"

![The FPC cable inserted into the connector](../assets/images/build/02-fpc.jpg){ loading=lazy }

!!! warning "Get each crease right the first time"

    Re-folding at the same spot, or pressing a sharp crease with a fingernail, will break the conductors. Press each fold down gently with a fingertip.

## 5. Test before installing the TrackPoint

Flash the firmware once at this point and check that every key responds.

1. Connect the board to your PC over USB
2. Flash it as described in [Flashing Firmware](05-firmware.md)
3. Check every key with a [key tester](https://config.qmk.fm/#/test)

- [ ] Every key responds
- [ ] No chattering or phantom keys

Note that input may lag while the TrackPoint module is not connected. Test again with the module connected before final assembly.

!!! success "If everything works"

    Continue to [TrackPoint Integration](03-trackpoint.md). If a key does not respond, check [Troubleshooting](../troubleshooting.md) first.
