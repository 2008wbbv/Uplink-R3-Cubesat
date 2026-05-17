# Uplink V2.0 — Bill of Materials

**Version:** 0.1
**Last updated:** May 2026
**Target build cost:** ~$130-150 (excluding filament if printed at school/library)

This BOM covers the reference build for Uplink V2.0. All parts are commodity items available from standard hobbyist suppliers. Substitutions are generally fine — see notes per item.

## Compute & Sensors

| Item | Suggested Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| SBC | Raspberry Pi Zero 2W | 1 | $15 | Pi Zero 2W specifically. Original Zero W lacks the CPU power for camera + IMU concurrent. |
| microSD | 32GB Class 10 | 1 | $8 | SanDisk or Samsung. Avoid no-name. |
| Camera | Pi Camera Module v2 | 1 | $15 | v3 works but costs more. v2 is sufficient for V2.0 demo. |
| Camera cable | Mini CSI to standard CSI ribbon | 1 | $3 | Pi Zero uses the mini connector. Standard Pi cameras need this adapter ribbon. |
| IMU | MPU6050 breakout board | 1 | $4 | I2C, 6-axis. Generic boards are fine. |

## Power

| Item | Suggested Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| Battery | 3.7V LiPo, 2000mAh | 1 | $10 | JST-PH connector. Adafruit #2011 or equivalent. |
| Power management | Adafruit PowerBoost 1000C | 1 | $20 | Handles LiPo charging + 5V boost in one board. |
| Solar panels | 5V 1W mini solar panel | 4 | $20 | For chassis mounting demo only in V2.0. Full electrical integration in V2.1. |

## Fasteners & Mounting

| Item | Suggested Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| Heat-set inserts | M3 brass inserts, 100pc kit | 1 | $10 | Requires soldering iron with flat tip to install. |
| Screws | M3 socket head cap screws, assorted lengths (M3x6, M3x10, M3x16) | 1 | $8 | Black oxide or stainless. |
| Pi mounting | M2.5 brass standoffs, 4-pack | 1 | $6 | For mounting Pi Zero 2W to internal tray. |

## Wiring

| Item | Suggested Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| Jumper wires | Female-female + male-female assortment | 1 | $5 | For IMU and breadboard prototyping. |
| JST connectors | JST-PH pigtails | 1 | $5 | For battery and power connections. |

## Consumables

| Item | Suggested Part | Qty | Est. Cost | Notes |
|---|---|---|---|---|
| PLA filament | 1kg spool, any color | 1 | $0-20 | ~200-300g used per chassis. School/library printers often supply filament. |

## Totals

| Category | Cost |
|---|---|
| Compute & Sensors | $45 |
| Power | $50 |
| Fasteners & Mounting | $24 |
| Wiring | $10 |
| Filament (if purchased) | $0-20 |
| **Subtotal** | **$129-149** |
| Shipping + tax (estimated) | ~$15 |
| **Total all-in** | **~$144-164** |

## Vendor Notes

Recommended sources by reliability and speed:

- **Adafruit:** Pi, Camera, PowerBoost, LiPo battery. Higher cost, fast US shipping, reliable parts.
- **Amazon:** Screws, heat-set inserts, standoffs, jumper wires, filament. Cheap and fast, quality varies on no-name electronics.
- **PiShop / Pimoroni / Sparkfun:** Acceptable alternatives to Adafruit.
- **Avoid AliExpress for this build:** Shipping times conflict with the V2.0 August target.

Builders should source from whatever vendor works in their region. The BOM lists generic part types; brand names are suggestions.

## Tools Required (Not Included in BOM)

- 3D printer with ~200x200mm build volume (school, library, or makerspace printer is fine)
- Soldering iron with flat tip for heat-set insert installation
- Small Phillips and hex screwdrivers (M3 hex, Pi standoff Phillips)
- Computer with Fusion 360 (free for students) to modify CAD if desired
- USB cable for Pi Zero programming

## Substitution Policy

V2.0 is designed around the parts listed above. Substitutions in the same category (e.g., different LiPo capacity, different IMU breakout) generally work but may require firmware adjustment. The chassis CAD is designed around the **physical dimensions** of the parts listed. Swapping to a physically different SBC (e.g., Pi 4) is a V2.1+ roadmap item and is not supported in V2.0.

## License

This BOM is part of the Uplink project, released under MIT License.
