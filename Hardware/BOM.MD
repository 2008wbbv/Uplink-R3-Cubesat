# Uplink R3 — Bill of Materials

**Version:** 0.2
**Last updated:** May 2026
**Target build cost:** ~$180 base (excluding filament if printed at school/library)

This BOM covers the reference build for Uplink R3. The reference build includes a custom integrated PCB combining power management and sensor breakout. The chassis itself is payload-agnostic, so builders can substitute their own PCB or stack of breakouts for different payloads.

## Compute & Sensors

| Item | Suggested Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| SBC | Raspberry Pi Zero 2W | 1 | $15 | Pi Zero 2W specifically. Original Zero W lacks the CPU power for camera + IMU concurrent. |
| microSD | 32GB Class 10 | 1 | $8 | SanDisk or Samsung. Avoid no-name. |
| Camera | Pi Camera Module v2 | 1 | $15 | v3 works but costs more. v2 is sufficient for reference demo. |
| Camera cable | Mini CSI to standard CSI ribbon | 1 | $3 | Pi Zero uses the mini connector. |
| IMU | MPU6050 breakout board | 1 | $4 | I2C, 6-axis. Generic boards are fine for prototyping. The reference PCB exposes an I2C header for direct sensor connection. |

## Custom Integrated PCB

The reference PCB consolidates LiPo charging, 5V boost regulation, solar energy harvesting, and sensor breakout headers onto one board sized to the chassis internal tray.

| Item | Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| PCB fabrication | JLCPCB, 5-board minimum | 1 | $10 | Standard 2-layer, HASL finish |
| Charging IC | TP4056 | 1 | $1 | Single-cell LiPo linear charger |
| Boost converter | TPS61090 | 1 | $3 | 5V boost regulation from LiPo |
| Solar harvesting IC | BQ25504 | 1 | $5 | Energy harvesting with MPPT for solar input |
| Passives | Resistors, capacitors, inductors, Schottky diodes | — | $8 | Per reference designs in IC datasheets |
| Headers | 2x I2C, 1x SPI, 2x 8-pin GPIO, power rails | — | $4 | 2.54mm pitch |
| JST connectors | JST-PH for battery and solar input | 2 | $2 | Standard 2-pin |
| **PCB subtotal** | | | **$33** | |

## Power

| Item | Suggested Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| Battery | 3.7V LiPo, 2000mAh | 1 | $10 | JST-PH connector. Adafruit #2011 or equivalent. |
| Solar panels | 5V 1W mini solar panel | 4 | $20 | Mounted on chassis add-on panels, feed into PCB solar input. |

## Fasteners & Mounting

| Item | Suggested Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| Heat-set inserts | M3 brass inserts, 100pc kit | 1 | $10 | Requires soldering iron with flat tip. |
| Screws | M3 socket head cap screws, assorted lengths | 1 | $8 | M3x6, M3x10, M3x16. |
| Pi mounting | M2.5 brass standoffs, 4-pack | 1 | $6 | For mounting Pi Zero 2W to internal tray. |

## Wiring

| Item | Suggested Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| Jumper wires | Female-female + male-female assortment | 1 | $5 | For sensor breakout to Pi. |

## Consumables

| Item | Suggested Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| PLA filament | 1kg spool, any color | 1 | $0-20 | ~200-300g used per chassis. School/library printers often supply filament. |

## Totals

| Category | Cost |
|---|---|
| Compute & Sensors | $45 |
| Custom PCB | $33 |
| Power | $30 |
| Fasteners & Mounting | $24 |
| Wiring | $5 |
| Filament (if purchased) | $0-20 |
| **Subtotal** | **$137-157** |
| Shipping + tax (estimated) | ~$15 |
| **Total all-in** | **~$152-172** |

**Note:** The pitch lists $180 as the base figure to give honest headroom for first-order PCB bring-up (likely needs a revision spin, additional components for debugging, and small BOM padding for spare components).

## Payload-Specific Costs

The base build above validates the chassis, electronics, and reference PCB. The first payload is a ground-based environmental sensor module that adds:

- BME280 (pressure, humidity, temperature): $8
- Light/UV sensor: $5
- Anemometer or wind vane (optional): $20-40
- Payload-specific wiring and mounting: $5

Payload subtotal: **$30-50** depending on sensor selection.

## Vendor Notes

- **Adafruit:** Pi, Camera, LiPo battery. Reliable US shipping.
- **JLCPCB:** PCB fabrication. ~1-2 week turnaround.
- **DigiKey or Mouser:** ICs (TP4056, TPS61090, BQ25504), passives. Authentic parts with datasheets, vs. counterfeit risk on Amazon/AliExpress.
- **Amazon:** Screws, heat-set inserts, standoffs, jumper wires, filament.
- **Avoid AliExpress for ICs:** Counterfeit BQ25504s and TPS61090s exist and waste debug time. Get authentic from DigiKey or Mouser.

## Tools Required (Not Included in BOM)

- 3D printer with ~200x200mm build volume
- Soldering iron with flat tip for heat-set insert installation
- Fine-tip soldering iron for PCB assembly (SMD work)
- Multimeter for PCB bring-up
- Computer with KiCad (free) and Fusion 360 (free for students)
- USB cable for Pi Zero programming

## Substitution Policy

The reference build is designed around the parts listed above. Within-category substitutions (different LiPo capacity, equivalent IMU breakout) generally work. The chassis CAD is designed around the physical dimensions of the parts. Swapping to a physically different SBC (Pi 4, ESP32) is a future roadmap item.

The custom PCB is specific to the reference payload. Builders running different payloads are expected to design their own PCB or use a stack of off-the-shelf breakouts that fits the chassis internal tray mounting pattern. The tray mounting pattern is documented in /hardware/PCB/ for reference.

## License

MIT. Part of the Uplink project.
