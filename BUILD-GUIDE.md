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
| [VIDEOS.md](./VIDEOS.md) | Curated YouTube tutorials — soldering, building, flying, iNav, Ardupilot, inspiration |
| [2026-UPDATES.md](./2026-UPDATES.md) | Latest 2026 changes — DJI O4, ELRS 4.0, Betaflight 2025.12 |

---

## Why a 5" Quad?

The 5-inch propeller quadcopter is the standard first DIY build because:

- **Best community support** — most tutorials, parts, and firmware targets
- **Balanced performance** — fast enough for racing, stable enough for filming
- **Repairable** — cheap replacement parts, standardized mounting (20x20mm and 30.5x30.5mm stacks)
- **Outdoor capable** — handles wind, has enough power for altitude, 3-8 min flight times
- **Learning platform** — skills transfer to all other sizes (3", 7", long-range)

## IMPORTANT: Simulator First

**Before you build, buy your radio and practice in a simulator.**

| Simulator | Price | Platform | Notes |
|-----------|-------|----------|-------|
| **Velocidrone** | $20 | PC | Most realistic physics, competitive community |
| **Liftoff** | $20 | PC/Console | Good graphics, beginner friendly |
| **TRYP FPV** | $20 | PC | Modern, good freestyle feel |

**Why this matters:**
- 10-20 hours in a simulator teaches you to fly without breaking anything
- Your RadioMaster radio connects via USB as a game controller
- Muscle memory transfers directly to real flying
- **Saves $200-500+ in crashed parts** during your first month

Buy your radio first, fly the sim for 2-4 weeks while the rest of your parts ship.

## Optional: Indoor Training Drone (Tiny Whoop)

A **Tiny Whoop** is a 65-75mm ducted micro quad (25-35g) that flies indoors safely. It bounces off walls, won't hurt people/pets/furniture, and builds real stick skills faster than a simulator alone.

### Why Get One

- **Real physics** — simulators are good but nothing replaces actual flight feel
- **No regulations** — under 250g, fly anywhere indoors, no registration
- **Crash-proof** — ducts protect props and surroundings, replacement parts $3-5
- **Same radio** — uses your RadioMaster with ELRS, identical stick muscle memory
- **Rainy day drone** — you'll use it forever, even after your 5" is built
- **Teaches repairs** — good intro to motor swaps, prop changes, and Betaflight config on a cheap platform

### What to Buy

**If you already have (or are buying) a RadioMaster radio:**

| Drone | Price | Size | Battery | Notes |
|-------|-------|------|---------|-------|
| **BetaFPV Meteor75 (ELRS)** | $90-110 | 75mm | 1S | **Best beginner whoop** — stable, durable, great parts support |
| **Happymodel Mobula7 (ELRS)** | $80-100 | 75mm | 1S/2S | Popular alternative, strong community |
| **BetaFPV Meteor65 (ELRS)** | $70-90 | 65mm | 1S | Smaller — better for tight apartments |
| **Emax TinyHawk III** | $80-100 | 75mm | 1S | Durable, flies indoor AND outdoor |

**You also need cheap analog FPV goggles** (your DJI goggles won't work with whoops):

| Goggles | Price | Notes |
|---------|-------|-------|
| **Eachine EV800D** | $50-60 | Box-style, cheap, works great for whoops |
| **Skyzone Cobra Lite** | $70-90 | Better optics, same purpose |

**Total indoor training setup: ~$140-180** (whoop + cheap goggles)

### DJI-Compatible Option (One Pair of Goggles)

If you want to use your DJI Goggles 2 for everything:

| Drone | Price | Notes |
|-------|-------|-------|
| **BetaFPV Aqua (DJI O4 Lite)** | $150-180 | Works with DJI Goggles 2/3, heavier than analog whoops |

More expensive, but means you only buy one set of goggles total.

### All-In-One Starter Kit (No Existing Radio)

If you haven't bought anything yet and want the cheapest possible entry:

| Kit | Price | Includes | Limitation |
|-----|-------|----------|-----------|
| **BetaFPV Cetus Pro RTF** | $100-120 | Drone + radio + goggles | Cheap radio/goggles won't grow with you — plan to upgrade both |

**My recommendation:** Skip the RTF kit. Buy the RadioMaster Pocket ($65) you'll use for your 5" build + Meteor75 ELRS BNF ($100) + cheap goggles ($55). Total ~$220 and nothing gets wasted.

### Indoor Training Batteries

Tiny Whoops use 1S 300-450mAh batteries (2-3 min flights). Buy 6-8 batteries ($3-4 each) so you can fly continuously while others charge. A simple USB 1S charger ($8-12) charges 6 at a time.

| Item | Qty | Price |
|------|-----|-------|
| GNB 1S 450mAh 80C (PH2.0) | 8 | $24 |
| 6-port 1S USB charger | 1 | $10 |
| **Total** | | **~$34** |

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
| **BetaFlight vs iNav** | BetaFlight = acro/freestyle (now with altitude/position hold). iNav = GPS waypoints, return-to-home, long-range. |

## Firmware Quick Reference

| Firmware | Best For | GPS Support | Waypoints |
|----------|----------|-------------|-----------|
| **Betaflight 2025.12** | Freestyle, racing | **Altitude hold, position hold, GPS rescue** | No |
| **iNav** | Long-range, autonomous | Full (RTH, position hold, cruise) | Yes |
| **Ardupilot** | Mapping, commercial, complex | Full | Yes |

**Note:** Betaflight 2025.12 added altitude hold and position hold — a massive improvement for beginners. Add a GPS module ($12-18) to unlock these safety features. Configure via the new Progressive Web App (no desktop download needed).

---

## Safety Essentials

- **Never arm with props on indoors**
- **Always do a pre-flight check** (props tight, battery secure, antenna attached)
- **Set a failsafe** in Betaflight/iNav (motor stop or RTH on signal loss)
- **Use a smoke stopper** on first power-up (a current-limiting inline fuse that prevents magic smoke)
- **Fly in open areas** away from people until comfortable
- **Set a battery voltage alarm** (3.5V per cell minimum)
- **Carry a LiPo-safe bag** for battery transport and storage
