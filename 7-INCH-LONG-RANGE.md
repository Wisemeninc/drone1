# 7" Long Range Drones — The Distance Machine

Everything you need to know about 7-inch long range FPV builds. The sweet spot between portability and maximum efficiency — routinely achieving 30-60km one-way range and 25-40 minute flight times on Li-Ion packs.

---

## Why 7" for Long Range?

The physics are simple: larger prop disc area = more efficient lift at lower RPMs.

| Factor | 5" | 7" | Advantage |
|--------|----|----|-----------|
| Hover efficiency | ~5-7 g/W | ~8-12 g/W | **7" is 40-70% more efficient** |
| Flight time (LiPo) | 4-8 min | 12-20+ min | 2-3x longer |
| Flight time (Li-Ion) | 12-20 min | 25-40+ min | Nearly 2x |
| Cruising speed sweet spot | 50-70 km/h | 50-80 km/h | Better range per Wh |
| Prop disc area | ~127 cm² | ~249 cm² | ~2x area = less work per revolution |
| Wind handling | Light, blown around | More inertia, stable | Better in wind |
| Practical one-way range | 8-15 km | **30-60 km** | Game-changing difference |

**Bottom line:** 7" is the sweet spot — large enough for real efficiency gains, small enough to remain portable and fly aggressively.

---

## PlatyFPV — Mountain Surfing on 7"

[PlatyFPV](https://www.youtube.com/channel/UCqOLDBE34WiqytAgCRManAg) (@platy_fpv on Instagram) is a European FPV pilot specializing in high-speed mountain surfing through the Alps, Dolomites, and Slovenia. He defines "Platy Style" — analog video, no stabilization, 7-inch long range quads flown aggressively through mountain terrain at multi-kilometer distances.

### What Makes Platy's Approach Notable

- **Analog video** — no DJI digital, pure analog for lowest latency and lighter weight
- **No stabilization** — raw acro/nostab for full control at speed
- **7-inch props** — efficiency for sustained mountain runs covering 5-15+ km per flight
- **ELRS 868MHz** — European 868MHz band for maximum penetration through mountain valleys
- **Aggressive flying at range** — not slow cruising; full-speed proximity through ridgelines

### Platy's Gear (Known Components)

#### Ground Station

| Component | Specific Gear |
|-----------|--------------|
| Radio | **Radiomaster Boxer Crush** |
| ELRS Module | **Bandit Micro ELRS 868MHz** |
| Goggles | **Orqa FPV One.Pilot** |
| Receiver Module | **IRC Rapidfire** |
| Antenna | **TrueRC X2 Air Patch** (directional) |

#### Long Range Quad

| Component | Specific Part |
|-----------|--------------|
| Frame | **Kayouloin 7"** |
| Props | 7-inch (bi-blade for efficiency) |
| Video | Analog VTX (high power, 1W+) |
| Control Link | ELRS 868MHz |
| Firmware | iNav (GPS + RTH safety) |

> **Full gear breakdown:** Watch [PLATY LONG RANGE SETUP TOUR](https://www.youtube.com/watch?v=IkLi6TvG_Ac) for the complete walkthrough of every component, tips for safe long-range flying, and his reasoning behind each choice.

### PlatyFPV Videos — Best Picks

| # | Title | Why Watch |
|---|-------|-----------|
| 1 | [PLATY LONG RANGE SETUP TOUR](https://www.youtube.com/watch?v=IkLi6TvG_Ac) | **Start here** — complete gear and setup breakdown for LR mountain surfing |
| 2 | [EPIC FPV Long Range Rescue Mission](https://www.youtube.com/watch?v=beGM6D8SqNc) | Full gear list in description, demonstrates range capability |
| 3 | [Platy Style / FPV Mountain Surfing](https://www.youtube.com/watch?v=GsZHVOmzoYQ) | Defines "Platy Style" — analog, nostab, 7-inch through the French Alps |
| 4 | [DOLOMITES FPV DRONE HIGH SPEED MOUNTAIN SURFING (UNCUT)](https://www.youtube.com/watch?v=ubFStwMYCOM) | Full uncut mountain run — see what 7" LR flying actually looks like |
| 5 | [3 EPIC DIVES ACROSS THE ALPS](https://www.youtube.com/watch?v=-yfnZ17V8QM) | France, Italy, Slovenia — commented flights explaining decisions |
| 6 | [Flowing with the Mountains](https://www.youtube.com/watch?v=0pvl8mfTkyk) | Cinematic mountain surfing, Feb 2026 |
| 7 | [CRAZY FPV DRONE HIGH SPEED MOUNTAIN RUN (4K)](https://www.youtube.com/watch?v=YPNtouPtkJY) | 4K quality, shows what aggressive LR looks like |

---

## Components for a 7" Long Range Build

### Frames

| Frame | Weight | Price | Geometry | Notes |
|-------|--------|-------|----------|-------|
| **Kayouloin 7"** | ~140-160g | $50-70 | True-X | Platy's choice — proven for mountain LR |
| **iFlight Chimera7** | ~150-170g | $60-80 | Deadcat | Popular, good HD camera mounting |
| **GEPRC Crocodile7 / Mark4-7** | ~160-180g | $50-70 | True-X | Proven LR frame, thick 5mm arms |
| **AOS 7 V2** | ~130-140g | $80-100 | True-X | Premium, extremely rigid, lightest option |
| **Flywoo Explorer LR7** | ~140g | $55-65 | Deadcat | Designed for Li-Ion mounting |
| **TBS Source One 7"** | ~145g | $25-35 | True-X | Open source, cheapest, replaceable arms |
| **Diatone Roma L7** | ~155g | $55-70 | True-X | Good arm stiffness, clean design |
| **Mode 2 Shredder 7"** | ~112g | $70-90 | True-X | Ultra-light with replaceable arms |

**Typical specs:** ~280-310mm wheelbase, 4-5mm thick arms, 3mm top/bottom plates.

### Motors

For 7" long range on 6S, you want 2806.5 or 2807 stators at 1300-1500KV.

| Motor | Size | KV (6S) | Price (x4) | Notes |
|-------|------|---------|-----------|-------|
| **T-Motor F60 Pro IV 2806.5** | 2806.5 | 1300KV | $100-120 | Premium, tight tolerances |
| **BrotherHobby Avenger V3 2806.5** | 2806.5 | 1300KV | $88-112 | Excellent efficiency |
| **iFlight XING2 2806.5** | 2806.5 | 1300KV | $72-88 | Great value all-rounder |
| **Emax ECO II 2807** | 2807 | 1300KV | $60-72 | Budget king, proven |
| **FlyFishRC Flash 2806.5** | 2806.5 | 1350KV | $72-88 | Good balance of price/performance |
| **T-Motor Velox V2 2806.5** | 2806.5 | 1350KV | $80-100 | Smooth, durable |

**Stator sizing explained:**
- **2806.5** — sweet spot for 7" LR (wide stator = torque for big props)
- **2807** — slightly taller, more RPM potential
- **2808** — maximum efficiency, heavier builds, 1150-1400KV

**Rule:** Lower KV = more efficient cruising. 1300KV on 6S is the long-range sweet spot.

### Propellers

| Prop | Blades | Pitch | Best For |
|------|--------|-------|----------|
| **HQProp 7x3 (bi-blade)** | 2 | 3.0" | **Maximum efficiency — LR king** |
| **Gemfan 7035 (bi-blade)** | 2 | 3.5" | Efficient with slightly more thrust |
| **HQProp 7x3.5x3** | 3 | 3.5" | Balance of efficiency and handling |
| **Gemfan 7040 (bi-blade)** | 2 | 4.0" | More thrust, slightly less efficient |
| **HQProp 7x4x3** | 3 | 4.0" | Aggressive, freestyle-capable |

**For pure long range:** Bi-blade 7x3 or 7x3.5. Less thrust, but 15-25% more efficient than tri-blade equivalents.

**For mixed flying (like Platy's aggressive mountain surfing):** Tri-blade 7x3.5 — responsive enough for proximity flying while maintaining good efficiency.

### Batteries — Li-Ion vs LiPo

The biggest decision for 7" LR. Li-Ion wins for range; LiPo wins for aggressive flying.

#### Li-Ion 21700 Cells (Recommended for LR)

| Cell | Capacity | Max Continuous | Weight | Best For |
|------|----------|---------------|--------|----------|
| **Molicel P42A** | 4200mAh | 30A | 70g | **Best all-rounder — recommended** |
| **Samsung 40T** | 4000mAh | 35A | 67g | Highest discharge, punchier flying |
| **Molicel P45B** | 4500mAh | 45A | 70g | Newest, excellent discharge + capacity |
| **Samsung 50E** | 5000mAh | 10A | 69g | Maximum endurance, very gentle cruise only |

**6S pack (6x 21700 P42A):** ~420g, 4200mAh, ~93Wh = **25-40 min flight time**

#### Li-Ion 18650 Cells (Lighter, Less Capacity)

| Cell | Capacity | Max Continuous | Weight | Best For |
|------|----------|---------------|--------|----------|
| **Sony/Murata VTC6** | 3000mAh | 15A | 46g | Balanced capacity/current |
| **Samsung 30Q** | 3000mAh | 15A | 46g | Budget alternative to VTC6 |
| **Samsung 35E** | 3500mAh | 8A | 50g | Max range, very gentle flying |

**6S pack (6x 18650 VTC6):** ~276g, 3000mAh, ~66Wh = **20-30 min flight time**

#### LiPo (For Aggressive LR Flying)

| Battery | Config | Weight | Flight Time | Best For |
|---------|--------|--------|-------------|----------|
| 1800mAh 6S | 6S/100C | ~270g | 12-16 min | Mixed LR + freestyle (Platy style) |
| 2200mAh 6S | 6S/100C | ~320g | 15-20 min | Moderate range, punchy |
| 1500mAh 6S | 6S/100C | ~225g | 10-14 min | Lighter, more agile |

**Decision guide:**
- Want maximum distance (30-60km)? → **Li-Ion 21700 (P42A or P45B)**
- Want aggressive mountain flying (Platy style, 5-15km runs)? → **LiPo 1800-2200mAh 6S**
- Budget / lighter build? → **Li-Ion 18650 (VTC6)**

### Flight Controller & ESC

Same principles as 5" builds, but ensure your FC supports iNav well.

| Stack | FC + ESC | Price | Notes |
|-------|----------|-------|-------|
| **SpeedyBee F405 V4 + 50A** | F4 + BL32 50A | $65-80 | Budget iNav, proven |
| ~~**Mamba F722 + F50 Pro**~~ | F7 + BL32 50A | — | ⚠️ F50 Pro no longer stocked in EU (Sept 2026) — AliExpress only |
| **GEPRC Span H7 + 60A** | H7 + BL32 60A | $90-120 | Best future-proofing, barometer included |
| **Matek F722-SE** | F7 (standalone) | $40-50 | iNav community favourite, dual BEC |

**Key requirements for LR:**
- Barometer (altitude hold)
- Sufficient UARTs (RX, GPS, VTX smart audio minimum)
- Current sensor (track mAh consumed in real-time)
- SD card slot (blackbox for tuning efficiency)

### GPS Module

Essential for 7" LR — enables return-to-home and position tracking.

| GPS Module | Price | Notes |
|-----------|-------|-------|
| **BN-880** | $12-18 | GPS + compass, iNav standard |
| **Beitian BN-220** | $10-15 | GPS only, no compass (lighter) |
| **Matek M10-5883** | $20-30 | M10 chipset, faster lock, compass |
| **SpeedyBee SP-F10** | $15-20 | Quick lock, good for iNav |

### Radio System

For LR, 900MHz ELRS is the standard. Control link will never be your limiting factor.

| Component | Recommendation | Price | Range |
|-----------|---------------|-------|-------|
| TX Module | **Bandit Micro ELRS 868/915MHz** | $30-45 | 50-100+ km |
| RX | **HappyModel ES900RX** | $18-25 | Matches TX range |
| Alternative TX | **BetaFPV Micro 900MHz** | $25-35 | 50+ km |
| Radio | **Radiomaster Boxer** or **TX16S** | $90-200 | — |

**Platy's choice:** Radiomaster Boxer Crush + Bandit Micro ELRS 868MHz module.

### Video System

| System | Range | Latency | Weight | Notes |
|--------|-------|---------|--------|-------|
| **Analog 1.6W** (Platy's choice) | 5-10 km | ~10ms | 5-10g | ⚠️ Lightest and cheapest, but **illegal to transmit at that power in the EU** — 25mW is the cap, giving 200-500m, and an amateur licence is not a reliable workaround. Legal EU range comes from a digital system's link budget, and VLOS binds first anyway. |
| **DJI O4** | 10-13 km | 25-38ms | ~35g | Best range + recording, heaviest |
| **DJI O3** | 8-13 km | 28-40ms | ~36g | Good value (discounted now) |
| **Walksnail Avatar** | 5-8 km | 22-35ms | ~30g | Middle ground |

**For pure LR distance:** Analog wins on weight and latency. Add a directional patch antenna on your goggles (like Platy's TrueRC X2 Air Patch) for extended video range.

**For recording:** DJI O4 gives you 4K onboard without carrying a GoPro.

---

## Distance & Flight Time Reference

### Flight Time by Battery (7" build, ~700-900g AUW without battery)

| Battery | AUW | Cruise Time | Aggressive Time |
|---------|-----|-------------|-----------------|
| 6S 1300mAh LiPo | ~900g | 8-12 min | 6-8 min |
| 6S 1800mAh LiPo | ~1000g | 12-16 min | 8-12 min |
| 6S 2200mAh LiPo | ~1100g | 15-20 min | 10-14 min |
| 6S 18650 Li-Ion (VTC6) | ~1000g | 20-30 min | 14-20 min |
| **6S 21700 Li-Ion (P42A)** | **~1150g** | **25-40 min** | **18-25 min** |

### Range by Setup

| Setup | One-Way Range | Round Trip | Limiting Factor |
|-------|---------------|------------|-----------------|
| 7" + 1800mAh LiPo + Analog | 5-10 km | 10-20 km | Battery / video |
| 7" + Li-Ion 18650 + Analog | 15-25 km | 30-50 km | Video range |
| 7" + Li-Ion 21700 + DJI O4 | **30-50 km** | **60-100 km** | Battery |
| 7" + Li-Ion 21700 + Analog + Patch | 20-40 km | 40-80 km | Video range |
| **Extreme (optimized)** | **50-75 km** | **100-150 km** | Battery + regulatory |

### The Distance Formula

```
Max one-way distance = (flight time x cruise speed) / 2.5
```

The 2.5 safety factor accounts for: return trip, safety margin (land at 3.5V/cell), wind on return, non-straight path.

| Flight Time | Cruise Speed | Max One-Way | Round Trip |
|-------------|-------------|-------------|------------|
| 12 min | 70 km/h | 5.6 km | 11.2 km |
| 20 min | 70 km/h | 9.3 km | 18.7 km |
| 25 min | 75 km/h | 12.5 km | 25.0 km |
| 30 min | 80 km/h | 16.0 km | 32.0 km |
| 40 min | 80 km/h | 21.3 km | 42.7 km |

---

## Firmware for 7" Long Range

### iNav (Recommended for Most LR Builds)

- GPS waypoint missions
- Return-to-home on failsafe (RTH)
- Position hold, altitude hold
- Cruise mode (set heading + speed, drone holds it)
- Efficient power management
- Mission planner for pre-planned routes

### Ardupilot (For Extreme Range / Full Autonomy)

- Complex waypoint missions with actions
- Geofencing
- Advanced failsafes (multiple layers)
- Terrain following
- Companion computer integration
- Overkill for most LR FPV, but necessary for 50+ km automated missions

### Which to Choose

| Use Case | Firmware |
|----------|----------|
| Mountain surfing (Platy style) | **iNav** — RTH safety, position hold for recovery |
| Pure distance flying (30-50km) | **iNav** — cruise mode + efficient RTH |
| Waypoint mapping missions | **Ardupilot** — full mission planning |
| Mixed freestyle + LR safety | **Betaflight with GPS Rescue** — basic RTH only |

---

## Safety for Long Range Flying

Flying 7" at 20-50km requires additional precautions beyond standard 5" builds.

### Mandatory

| Feature | Why |
|---------|-----|
| GPS + iNav with RTH | Drone flies home if link drops |
| Failsafe set to RTH | Automatic on signal loss |
| Battery telemetry on OSD | Know remaining mAh at all times |
| Low-voltage alarm | Warning before critical battery |
| RSSI + link quality on OSD | Monitor both video and control links |

### Strongly Recommended

| Feature | Why |
|---------|-----|
| Directional patch antenna (goggles) | +30-50% video range |
| Buzzer + GPS coordinates on OSD | Find the drone if you crash at 10km |
| Pre-planned route (iNav mission) | Know the path, avoid obstacles |
| Second battery for goggles | Goggles dying = lost drone |
| Spotter | Legal requirement + extra eyes |

---

## Sample Builds

### Platy-Style Mountain Surfer (Aggressive LR)

Designed for high-speed multi-km mountain runs. LiPo for punch, analog for latency.

| Component | Choice | Price |
|-----------|--------|-------|
| Frame | Kayouloin 7" | ~$60 |
| Motors | 2806.5 1300KV (x4) | ~$80 |
| FC + ESC | F7 stack + 50A BL32 | ~$85 |
| Props | Tri-blade 7x3.5 | ~$5/set |
| Battery | 6S 1800mAh LiPo | ~$35 |
| GPS | BN-880 | ~$15 |
| VTX | Analog 1.6W — ⚠️ **run at 25mW on a legal channel in the EU**; see REGULATIONS.md | ~$35 |
| RX | ELRS 868/900MHz | ~$20 |
| Firmware | iNav | Free |
| **Total (quad only)** | | **~$335** |

*Flight time: 12-16 min cruise | Range: 5-10km aggressive mountain runs*

### Maximum Distance Explorer (Li-Ion LR)

Pure distance build. Li-Ion for maximum flight time, DJI for video range.

| Component | Choice | Price |
|-----------|--------|-------|
| Frame | Flywoo Explorer LR7 or AOS 7 V2 | ~$70 |
| Motors | 2806.5 1300KV (x4) | ~$80 |
| FC + ESC | H7 stack + 60A BL32 | ~$100 |
| Props | Bi-blade 7x3 | ~$5/set |
| Battery | 6S 21700 Li-Ion (P42A) | ~$60 |
| GPS | Matek M10-5883 | ~$25 |
| VTX | DJI O4 Air Unit | ~$120 |
| RX | ELRS 900MHz | ~$20 |
| Firmware | iNav | Free |
| **Total (quad only)** | | **~$480** |

*Flight time: 25-40 min cruise | Range: 30-50km one-way*

### Budget Distance Flyer

Cheapest path to real long range capability.

| Component | Choice | Price |
|-----------|--------|-------|
| Frame | TBS Source One 7" | ~$30 |
| Motors | Emax ECO II 2807 1300KV (x4) | ~$65 |
| FC + ESC | SpeedyBee F405 V4 + 50A | ~$70 |
| Props | Bi-blade 7x3.5 | ~$5/set |
| Battery | 6S 18650 Li-Ion (VTC6) | ~$35 |
| GPS | BN-880 | ~$15 |
| VTX | Analog 1.6W — ⚠️ **run at 25mW on a legal channel in the EU**; see REGULATIONS.md | ~$35 |
| RX | ELRS 900MHz (HappyModel ES900RX) | ~$20 |
| Firmware | iNav | Free |
| **Total (quad only)** | | **~$275** |

*Flight time: 20-30 min cruise | Range: 15-25km one-way*

---

## YouTube Resources — 7" Long Range

### PlatyFPV (Mountain Surfing Specialist)

| # | Title | Why Watch |
|---|-------|-----------|
| 1 | [PLATY LONG RANGE SETUP TOUR](https://www.youtube.com/watch?v=IkLi6TvG_Ac) | **Complete gear breakdown** — every component explained |
| 2 | [EPIC FPV Long Range Rescue Mission](https://www.youtube.com/watch?v=beGM6D8SqNc) | Full gear in description, demonstrates range capability |
| 3 | [Platy Style / FPV Mountain Surfing](https://www.youtube.com/watch?v=GsZHVOmzoYQ) | Defines "Platy Style" — analog, nostab, 7-inch, French Alps |
| 4 | [DOLOMITES HIGH SPEED MOUNTAIN SURFING (UNCUT)](https://www.youtube.com/watch?v=ubFStwMYCOM) | Full uncut run — real 7" LR flying |
| 5 | [3 EPIC DIVES ACROSS THE ALPS](https://www.youtube.com/watch?v=-yfnZ17V8QM) | Commented flights with decisions explained |
| 6 | [Flowing with the Mountains](https://www.youtube.com/watch?v=0pvl8mfTkyk) | Cinematic mountain surfing (Feb 2026) |
| 7 | [CRAZY FPV DRONE HIGH SPEED MOUNTAIN RUN (4K)](https://www.youtube.com/watch?v=YPNtouPtkJY) | 4K quality aggressive LR |

### Other 7" Long Range Channels

| Channel | Focus |
|---------|-------|
| **Painless360** | iNav setup for LR builds |
| **Pawel Spychalski** | iNav developer, deep technical LR content |
| **Mads Tech** | Long range builds with detailed component selection |
| **Oscar Liang** (written) | Best written guides at oscarliang.com |
| **Gal Kremer** | Long range FPV flying, distance records |

---

## Notes

- All PlatyFPV URLs verified as of May 2026.
- Li-Ion cells require spot welding or pre-built packs — you cannot solder directly to cells safely.
- 7" builds need iNav or Ardupilot — flying 20+ km without GPS RTH is irresponsible.
- Legal VLOS limit is ~500m-1km. Long range flying in remote areas is common in the hobby but technically requires BVLOS authorization in most jurisdictions.
- Start with a LiPo build if you're coming from 5" — learn the handling before committing to Li-Ion distance flights.
