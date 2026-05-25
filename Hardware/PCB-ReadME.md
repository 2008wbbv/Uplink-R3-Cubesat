# Uplink Reference PCB

**Status:** In design (schematic capture in progress).

This folder will contain the KiCad project files, schematic, layout, fab files, and bring-up notes for the Uplink R3 reference PCB.

## What it does

The reference PCB consolidates power management and sensor breakout onto one board sized to fit the chassis internal mounting tray. It replaces what would otherwise be three separate hobby breakout boards in a typical Pi Zero + LiPo + solar build.

## Core ICs

| IC | Role |
|---|---|
| TP4056 | Single-cell LiPo linear charger. Handles charging the 3.7V battery from USB or solar input. |
| TPS61090 | 5V boost converter. Steps the LiPo voltage up to a stable 5V rail for the Pi Zero 2W. |
| BQ25504 | Solar energy harvesting IC with MPPT (maximum power point tracking). Manages variable solar panel input and feeds it into the charging path. |

## Exposed headers

The board breaks out:

- 2x I2C headers (for IMU and additional I2C sensors)
- 1x SPI header (for future SPI peripherals)
- 2x 8-pin GPIO breakouts
- 3.3V, 5V, and GND power rails
- JST-PH connector for battery input
- JST-PH connector for solar panel input

## Mounting

The PCB is sized to the chassis internal tray mounting pattern. Mounting hole spacing and PCB dimensions will be published here once the layout is finalized, so builders running different payloads can design replacement boards that fit the same tray.

## Why custom instead of stacked breakouts

A typical hobby build for the same functionality would stack:

1. A TP4056 charging breakout
2. A separate boost converter board
3. A separate solar charge controller (if MPPT is wanted)
4. A protoboard or wiring harness for sensor headers

That stack is fragile, hard to package inside a 1U CubeSat chassis, and not reproducible at scale. Consolidating onto one designed-for-purpose board makes the build cleaner, more reliable, and easier for other students to build from a published design.

## Files (planned)

- `/schematic/` — KiCad schematic source
- `/layout/` — KiCad PCB layout
- `/fab/` — Gerber files, drill files, BOM and CPL for JLCPCB
- `/bringup/` — Notes from first-article bring-up and any revisions

## Design References

The schematic follows the reference designs in the IC datasheets:

- TP4056 datasheet (NanJing Top Power)
- TPS61090 datasheet (Texas Instruments)
- BQ25504 datasheet (Texas Instruments)

Any deviations from the reference designs will be documented inline in the schematic.
