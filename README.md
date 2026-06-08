# DIY FPV Drone Build Guide

Complete reference for building a 5" FPV quadcopter from scratch, focused on outdoor flying under Danish and EU regulations.

Covers everything from component selection to soldering, budget planning, range optimization, and legal requirements — all in one place.

## Documentation

| Document | Description |
|----------|-------------|
| [BUILD-GUIDE.md](./BUILD-GUIDE.md) | Main guide — assembly sequence, simulator advice, build order |
| [COMPONENTS.md](./COMPONENTS.md) | Every component category with specific models, pros/cons, and recommendations |
| [BUDGET-TIERS.md](./BUDGET-TIERS.md) | Budget / Mid-Range / Premium complete builds ($500–$1500+) |
| [SHOPPING-LIST.md](./SHOPPING-LIST.md) | Copy-paste shopping lists for each budget tier |
| [SHOPPING-LIST-ALIEXPRESS-QUAD.md](./SHOPPING-LIST-ALIEXPRESS-QUAD.md) | Quad-only (no batteries/support/soldering), direct AliExpress links per tier |
| [SHOPPING-LINKS-EU.md](./SHOPPING-LINKS-EU.md) | EU-based FPV shops, Amazon.de, and AliExpress links |
| [SOLDERING-GUIDE.md](./SOLDERING-GUIDE.md) | Tools, techniques, joint types, and beginner tips |
| [TRADE-OFFS.md](./TRADE-OFFS.md) | Distance vs Speed vs Flight Time decision matrix |
| [DISTANCE-RANGE.md](./DISTANCE-RANGE.md) | Range limits by build type, video system, and battery |
| [7-INCH-LONG-RANGE.md](./7-INCH-LONG-RANGE.md) | 7" long range builds — 30–60km range, Li-Ion packs, efficiency |
| [BVLOS-RELAY-DRONE.md](./BVLOS-RELAY-DRONE.md) | Relay drone design — BVLOS via aerial signal repeater, mesh radios, regulatory |
| [REGULATIONS.md](./REGULATIONS.md) | Danish and EU EASA drone rules, registration, airspace |
| [VIDEOS.md](./VIDEOS.md) | Curated YouTube tutorials — soldering, building, flying, iNav |
| [2026-UPDATES.md](./2026-UPDATES.md) | Latest 2026 changes — DJI O4, ELRS 4.0, Betaflight 2025.12 |

## Quick Start

1. **Buy a radio** (RadioMaster Pocket or Zorro with ELRS)
2. **Fly a simulator** for 2–4 weeks (Velocidrone, Liftoff, or TRYP FPV)
3. **Pick a budget tier** from [BUDGET-TIERS.md](./BUDGET-TIERS.md)
4. **Order parts** using [SHOPPING-LINKS-EU.md](./SHOPPING-LINKS-EU.md)
5. **Build** following [BUILD-GUIDE.md](./BUILD-GUIDE.md) and [SOLDERING-GUIDE.md](./SOLDERING-GUIDE.md)
6. **Register** at [droneregler.dk](https://www.droneregler.dk/fritidsdroneflyvning/registrer-dig-som-privat-droneoperatoer) and check [droneregler.dk/dronezoner](https://www.droneregler.dk/dronezoner) before flying

## Key Specs (Standard 5" Build)

| Spec | Value |
|------|-------|
| Prop size | 5 inch |
| Weight | 500–700g (requires registration) |
| Flight time | 3–8 min (LiPo) |
| Range | 1–10+ km (depends on video/radio setup) |
| Flight controller | Betaflight or iNav |
| Radio protocol | ExpressLRS (ELRS) |
| EU category | Open A3 (no C-class marking) or A1 (if <900g with C1) |

## Regulations (Denmark / EU)

This guide follows Danish and EU EASA regulations:

- **Registration required** for drones 250g+ or with camera
- **A1/A3 online exam** required (free, ~40 questions)
- **120m max altitude** in Open category
- **VLOS (visual line of sight)** at all times
- **150m from buildings/people** for DIY drones without C-class marking (A3 subcategory)
- Check airspace: [droneregler.dk/dronezoner](https://www.droneregler.dk/dronezoner)

See [REGULATIONS.md](./REGULATIONS.md) for full details.

## License

Personal reference. Use at your own risk — always verify current regulations with official sources.
