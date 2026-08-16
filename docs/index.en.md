---
title: Introduction
description: Overview of the Altair-X TrackPoint Mod
---

# Altair-X TrackPoint Mod

!!! note "Japanese is the source of truth"

    Some details are only filled in on the Japanese page: [はじめに](index.md).

![The pointing stick in the innermost column of the right half](assets/images/hero.jpg){ loading=lazy }

A mod that adds a **Sprintek SK8707-01-004 pointing stick** — mounted on a dedicated mount PCB — to the innermost column of the right half of the [ai03 Altair-X](https://github.com/ai03-2725), so you can move the cursor without leaving the home position. This site hosts the **build guide** and the **user manual**.

## What this mod adds

- Cursor control from the innermost column of the right half
- Auto Mouse Layer: moving the stick temporarily activates a mouse layer
- Scrolling while a layer key is held
- Runtime settings for sensitivity and scrolling — no reflashing needed

## Specifications

| Item | Value |
| --- | --- |
| Base | ai03 Altair-X |
| Layout | Split column-staggered |
| Controller | RP2040 |
| Pointing device | Sprintek SK8707-01-004 on a dedicated mount PCB (internal PS/2) |
| Firmware | QMK + VIA |
| Connection | Wired USB-C |

## Documentation

- **[Build Guide](build/01-bom.md)** — parts, PCB assembly, TrackPoint integration, firmware
- **[User Manual](manual/usage.md)** — layers, Auto Mouse Layer, keymap, the layer status app
- **[Troubleshooting](troubleshooting.md)**
- **[FAQ](faq.md)**

## Before you start

!!! warning "Build at your own risk"

    This is an unofficial modification. It may damage your keyboard or the pointing stick module. Neither the designer of the original Altair-X nor the author of this documentation is responsible for the outcome.

!!! danger "ESD and soldering"

    - Discharge static electricity before handling the PCB or the module.
    - Soldering irons get hot. Work in a ventilated area.

## Difficulty and time required

| Item | Estimate |
| --- | --- |
| Difficulty | ★★★★☆ (fine soldering required) |
| Time | About 1.5 – 2 hours |
| Skills needed | Soldering (including the fine-pitch pads of the SK8707-01-004), handling small screws |

## License / Credits

- The original Altair-X is designed by [ai03](https://ai03.com/).
