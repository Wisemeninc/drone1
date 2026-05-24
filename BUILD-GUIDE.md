# DIY Drone Build Guide — Outdoor 5" Quadcopter

A complete reference for building your own FPV drone from scratch, optimized for outdoor use.

## Documentation Index

| Document | Contents |
|----------|----------|
| [COMPONENTS.md](./COMPONENTS.md) | Every component category with specific models, pros/cons, and recommendations |
| [SOLDERING-GUIDE.md](./SOLDERING-GUIDE.md) | Tools, techniques, joint types, and beginner tips |
| [BUDGET-TIERS.md](./BUDGET-TIERS.md) | Budget / Mid-Range / Premium complete build breakdowns |
| [TRADE-OFFS.md](./TRADE-OFFS.md) | Distance vs Speed vs Flight Time analysis and decision matrix |
| [DISTANCE-RANGE.md](./DISTANCE-RANGE.md) | How far you can fly — range limits by build type, video system, and battery |
| [REGULATIONS.md](./REGULATIONS.md) | US FAA and EU EASA rules for outdoor flying |
| [SHOPPING-LIST.md](./SHOPPING-LIST.md) | Copy-paste shopping lists for each budget tier |
| [2026-UPDATES.md](./2026-UPDATES.md) | Latest 2026 changes — DJI O4, ELRS 4.0, Betaflight 2025.12 |

---

## Why a 5" Quad?

The 5-inch propeller quadcopter is the standard first DIY build because:

- **Best community support** — most tutorials, parts, and firmware targets
- **Balanced performance** — fast enough for racing, stable enough for filming
- **Repairable** — cheap replacement parts, standardized mounting (20x20mm and 30.5x30.5mm stacks)
- **Outdoor capable** — handles wind, has enough power for altitude, 3-8 min flight times
- **Learning platform** — skills transfer to all other sizes (3", 7", long-range)

## Build Order (Recommended Assembly Sequence)

1. Mount motors to frame arms
2. Solder motor wires to ESC pads (or connect via plugs)
3. Mount FC+ESC stack to frame with standoffs
4. Solder battery lead (XT60) to ESC power pads
5. Solder receiver to FC UART pads
6. Mount and solder VTX + antenna
7. Mount and connect camera
8. Flash firmware (Betaflight / iNav)
9. Configure radio link (bind TX to RX)
10. Set up PID tuning (start with defaults)
11. Mount props (LAST — never power up with props until ready to fly)

## Key Decisions Before You Buy

| Decision | Impact |
|----------|--------|
| **4S vs 6S battery** | 4S = lighter, cheaper, more forgiving. 6S = more efficient, more power. |
| **Analog vs Digital FPV** | Analog = cheap entry ($80-150). Digital = expensive ($350-500) but far better image. |
| **Freestyle vs Long-range** | Determines motor KV, battery size, prop pitch, and radio frequency. |
| **BetaFlight vs iNav** | BetaFlight = acro/freestyle. iNav = GPS waypoints, return-to-home, long-range. |

## Firmware Quick Reference

| Firmware | Best For | GPS Support | Waypoints |
|----------|----------|-------------|-----------|
| **Betaflight** | Freestyle, racing | Basic rescue only | No |
| **iNav** | Long-range, autonomous | Full (RTH, position hold) | Yes |
| **Ardupilot** | Mapping, commercial, complex | Full | Yes |

---

## Safety Essentials

- **Never arm with props on indoors**
- **Always do a pre-flight check** (props tight, battery secure, antenna attached)
- **Set a failsafe** in Betaflight/iNav (motor stop or RTH on signal loss)
- **Use a smoke stopper** on first power-up (a current-limiting inline fuse that prevents magic smoke)
- **Fly in open areas** away from people until comfortable
- **Set a battery voltage alarm** (3.5V per cell minimum)
- **Carry a LiPo-safe bag** for battery transport and storage
