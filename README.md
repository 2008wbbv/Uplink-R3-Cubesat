# Uplink

**An open-source, 3D-printable CubeSat platform for students.**

Uplink is a 1U CubeSat (10x10x10cm) chassis and reference build designed so any student with a 3D printer and a small parts budget can build a working CubeSat platform. The chassis is modular, the parts list is cheap, and everything is documented from day one.

Status: **Pre-alpha. Active development. First release (V2.0) targeted August 2026.**

## Why

Existing educational CubeSat kits are expensive, closed, or mechanically awkward. Uplink started as a redesign of a chassis used in an MIT Lincoln Labs student competition (fall 2025) where mounting and fit problems got in the way of the actual engineering. V2 is a ground-up redesign: simpler, cheaper, fully open, and built to be copied.

## Goals

- Anyone with a 3D printer can build one from this repo
- Total parts cost under $150 for the reference build
- All CAD, firmware, and documentation open from day one (MIT license)
- Modular internal mounting so future builders can swap payloads

## V2.0 Reference Build

The first release ships with a working reference configuration:

| Subsystem | Component |
|---|---|
| Compute | Raspberry Pi Zero 2W |
| Imaging | Pi Camera module |
| IMU | MPU6050 (or equivalent) |
| Storage | microSD via Pi |
| Power | LiPo battery + charging board |
| Solar | Panel mounts in chassis (electrical integration in V2.1) |
| Fasteners | M3 heat-set inserts + M3 screws |

**Demo target:** Powers from battery, boots Pi, captures camera images to SD card, logs IMU orientation data for 1 hour continuous.

## Roadmap

- **V2.0** (August 2026): Pi Zero 2W reference build, full chassis CAD, basic firmware, build guide
- **V2.1**: Full solar electrical integration, refined power management
- **V2.2+**: Additional SBC variants (Pi 4, ESP32), expanded payload options

## Repo Structure

```
/cad          Fusion 360 source files and exported STLs
/firmware     Pi Zero 2W code (Python, C)
/hardware     Wiring diagrams, BOM, schematics
/docs         Build guide, assembly instructions
README.md     This file
LICENSE       MIT
```

## Build Status

- [ ] Chassis CAD complete
- [ ] First 3D print successful
- [ ] Internal mounting tray designed
- [ ] BOM finalized and parts ordered
- [ ] Firmware boots and logs sensor data
- [ ] V2.0 demo achieved
- [ ] Build guide published

## Background

Uplink V1 (fall 2025) was a team project for an MIT Lincoln Labs CubeSat competition. V1 ran OpenCV-based obstacle avoidance with A* pathfinding, demoed on an RC car traversing a mocked lunar surface. V1 used a Lincoln Labs-provided chassis kit that had significant mechanical issues. Uplink V2 is a clean-sheet replacement: custom chassis, custom mounting, custom everything.

## License

MIT. See [LICENSE](LICENSE).

## Author

Ben Vaccaro. Built starting May 2026.
