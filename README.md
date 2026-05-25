# Uplink

**An open-source, 3D-printable CubeSat platform for students.**

Uplink is a 1U CubeSat (10x10x10cm) chassis and reference build designed so any student with a 3D printer and a small parts budget can build a working CubeSat platform. The chassis is modular, the parts list is cheap, and everything is documented from day one.

Status: **Pre-alpha. Active development. First reference build (R3) targeted August 2026.**

## Why

Educational CubeSat kits run $500 to $2000+ and are usually closed-source or mechanically awkward. Uplink started as a redesign of a chassis used in an MIT Lincoln Labs student CubeSat competition (fall 2025) where mounting and fit problems got in the way of the actual engineering. R3 is a ground-up redesign: simpler, cheaper, fully open, and built to be copied.

## Goals

- Anyone with a 3D printer can build one from this repo
- Total base build cost under $200 including a custom integrated PCB
- All CAD, firmware, PCB design files, and documentation open from day one (MIT license)
- Modular internal mounting so future builders swap payloads instead of redesigning the chassis

## R3 Reference Build

The reference configuration validates the chassis, electronics, mounting, and PCB end-to-end as a ground-based sensor platform before anyone tries to fly one.

| Subsystem | Component |
|---|---|
| Compute | Raspberry Pi Zero 2W |
| Imaging | Pi Camera Module v2 |
| IMU | MPU6050 |
| Storage | microSD via Pi |
| Power + sensor breakout | Custom integrated PCB (TP4056 LiPo charger + TPS61090 5V boost + BQ25504 solar harvesting + I2C/SPI/GPIO headers) |
| Battery | 3.7V LiPo, 2000mAh |
| Solar | 5V 1W panels on add-on chassis panels, feeding PCB solar input |
| Fasteners | M3 heat-set inserts + M3 screws |

**Demo target:** Powers from battery via custom PCB, boots Pi, captures camera images to SD card, logs IMU orientation data for 1 hour continuous.

## Architecture

The chassis is structured as:

- Top plate + bottom plate + 4 corner rails forming the load-bearing frame
- 4 fixed side walls (closed by default)
- A universal mounting pattern replicated on all 4 walls so builders can attach add-on panels (solar mounts, sensor mounts, antenna mounts) without changing the chassis design

The reference PCB is specific to the reference payload. The internal mounting tray uses a standard pattern documented in `/hardware/PCB/`, so builders running different payloads can substitute their own PCB or a stack of off-the-shelf breakouts that fit the same tray.

## Roadmap

- **R3** (August 2026): Pi Zero 2W reference build, full chassis CAD, custom PCB designed and validated, basic firmware, build guide
- **R4**: Refined PCB revision based on R3 bring-up lessons, expanded solar integration, additional payload references (high-altitude balloon, weather station)
- **R5+**: Additional SBC variants (Pi 4, ESP32), expanded payload library, contributor-submitted payload modules

## Repo Structure

```
/cad              Fusion 360 source files and exported STLs
/firmware         Pi Zero 2W code (Python, C)
/hardware
  /BOM.md         Bill of materials
  /PCB            KiCad schematic, layout, fab files, PCB README
/docs             Build guide, assembly instructions
README.md         This file
LICENSE           MIT
```

## Build Status

- [x] Repo created
- [x] Spec and BOM drafted (v0.2 with custom PCB)
- [ ] Chassis CAD complete
- [ ] First 3D print successful
- [ ] Internal mounting tray designed
- [ ] PCB schematic complete in KiCad
- [ ] PCB layout complete
- [ ] PCB fabricated and assembled
- [ ] PCB bring-up validated
- [ ] Firmware boots and logs sensor data
- [ ] R3 demo achieved
- [ ] Build guide published

## Use Cases the Platform Supports

The same chassis is designed to support multiple payload configurations:

- High-altitude weather balloon payloads (atmospheric data, GPS, descent imaging)
- Storm chasing rigs (pressure, humidity, wind logging)
- Ground-based weather stations (solar + LiPo for unattended operation)
- Ham radio platforms (transceiver + antenna for amateur satellite work or APRS)
- Educational sensor research (any I2C/SPI/serial sensor)
- Future orbital builds (form factor is CubeSat-spec)

The R3 reference build is a ground-based sensor platform. Other payloads are listed as roadmap and contributor opportunities.

## Background

The original (V1) project was a team CubeSat build for an MIT Lincoln Labs student competition in fall 2025. V1 ran OpenCV-based obstacle avoidance with A* pathfinding, demoed on an RC car traversing a mocked lunar surface. V1 used a Lincoln Labs-provided chassis kit that had significant mechanical issues. Uplink R3 is a clean-sheet replacement: custom chassis, custom mounting, custom PCB.

## License

MIT. See [LICENSE](LICENSE).

## Author

Ben Vaccaro. Built starting May 2026.
