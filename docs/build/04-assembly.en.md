---
title: Case Assembly
description: Installing the module, mounting the cover, and final assembly
---

# Case Assembly

Assemble the left half exactly as described in the [official Altair-X build guide](https://ai03.com/info/build-guides/altair/).

For the right half, follow the official guide up to [Assembling the internals](https://ai03.com/info/build-guides/altair/4/), then continue with the steps below. Do not install the switches in the innermost column where the TrackPoint module goes.

## 1. Installing the TrackPoint module

- [ ] Insert the TrackPoint mounting part through the plate and fix it with the M2 x 5mm screw
- [ ] Route the FPC cable from the back of the PCB through the hole so it comes out of the mounting part

    ![The TrackPoint mounting part and the FPC cable](../assets/images/build/04-mounting-part.jpg){ loading=lazy }

- [ ] Insert the M1.6 nuts into the left and right holes of the mounting part (the left one especially) — take care not to drop them in a later step

    ![Seen from the side — the M1.6 nuts go in through the holes on each side](../assets/images/build/04-nuts-side.jpg){ loading=lazy }

- [ ] Continue the build as described in [Putting it all together](https://ai03.com/info/build-guides/altair/5/) and fix the PCB in the case
- [ ] Connect the FPC cable to the mount PCB

    ![Connecting the FPC cable to the mount PCB](../assets/images/build/03-mount-pcb.jpg){ loading=lazy }

- [ ] Slide the mount PCB into the mounting part and fix it with the M1.6 x 5mm screws (do not overtighten)

    ![The mount PCB installed](../assets/images/build/04-done.jpg){ loading=lazy }

## 2. Cover and keycaps

- [ ] Fix the TrackPoint module cover with the two M2 flat-head screws
- [ ] Fit the stick cap

Finish the rest of the build following the official guide.

## 3. Flashing the firmware

Following [Flashing Firmware](05-firmware.md), flash TrackPoint-enabled firmware to **both halves**.

## 4. Final checks

- [ ] Every key responds
- [ ] The TrackPoint moves in every direction
- [ ] Auto Mouse Layer works
- [ ] Scrolling works
- [ ] Mouse buttons work
- [ ] The cursor does not move on its own while typing

---

Once assembled, see the [User Manual](../manual/usage.md).
