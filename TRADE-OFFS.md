# Trade-Offs — Distance vs Speed vs Flight Time

The fundamental physics of quadcopter design means you cannot maximize distance, speed, AND flight time simultaneously. This document explains the relationships and helps you choose.

---

## The Iron Triangle

```
            SPEED
           /     \
          /       \
         /   YOU   \
        /   PICK    \
       /    TWO      \
      /               \
   RANGE ──────── FLIGHT TIME
```

- **Optimize for speed** → high KV, small battery, light frame → kills range and time
- **Optimize for range** → low KV, big battery, 900MHz link, high-power VTX → kills speed and agility
- **Optimize for flight time** → low KV, medium battery, light frame → moderate speed, moderate range
- **You cannot max all three.** Every component choice is a trade-off.

---

## How Each Component Affects the Triangle

### Motor KV

| KV Rating | Speed | Efficiency | Flight Time | Range |
|-----------|-------|-----------|-------------|-------|
| 1700-1800 (6S) | Moderate | **Best** | **Longest** | **Best** (efficient cruise) |
| 1900-2100 (6S) | Good | Good | Good | Good |
| 2400-2550 (4S) | Good | Moderate | Moderate | Moderate |
| 2700+ (4S) | **Maximum** | Poor | **Shortest** | **Worst** (power hungry) |

**The physics:** Lower KV = slower RPM = less air resistance on props = less wasted energy. A 1700KV motor at cruise draws 3-5A per motor. A 2700KV motor at cruise draws 6-10A per motor.

**Quantified:** Dropping from 2500KV to 1900KV on the same 5" frame = ~30% more flight time at cruise speed.

### Battery Size (Capacity)

| Battery (6S) | Weight | Flight Time | Agility | Range |
|--------------|--------|-------------|---------|-------|
| 1050mAh | 165g | 3-4 min | Best | Short |
| 1300mAh | 195g | 4-5 min | Great | Medium |
| **1500mAh** | 225g | **5-6 min** | Good | **Good** |
| 1800mAh | 270g | 5.5-6.5 min | Moderate | Longer |
| 2200mAh | 320g | 5.5-6 min | Poor | Diminishing |

**The diminishing returns curve:**
```
Flight time
    |        ___________
    |       /
    |      /    ← Diminishing returns start here (~1500mAh for 5")
    |     /
    |    /
    |   /
    |  /
    | /
    |/__________________ Battery capacity (mAh)
```

**Formula:** Every 100g added to AUW (all-up weight) requires ~10-15% more hover power. At some point, extra battery weight costs more energy to carry than it provides.

**Sweet spots:**
- 5" freestyle: 1300-1500mAh (4S or 6S)
- 5" long range: 1500-1800mAh (6S)
- 7" long range: 1800-2500mAh (6S)

### Propeller Choice

| Prop Type | Speed | Efficiency | Thrust | Noise |
|-----------|-------|-----------|--------|-------|
| Bi-blade, low pitch (5030) | Low | **Best** | Low | Quiet |
| Bi-blade, high pitch (5045) | High | Good | Medium | Moderate |
| **Tri-blade, medium pitch (5043)** | **Good** | **Good** | **Good** | Moderate |
| Tri-blade, high pitch (5051) | High | Poor | High | Loud |
| Quad-blade (5040x4) | Moderate | Worst | Maximum | Loudest |

**For maximum range:** Bi-blade, low pitch (5030 or 5035) — moves most air per watt
**For maximum speed:** Tri-blade, high pitch (5051) — maximum acceleration and top speed
**For best balance:** Tri-blade, medium pitch (5040-5045) — the default choice

### Frame Weight

| Frame Weight Change | Speed Impact | Flight Time Impact | Range Impact |
|--------------------|--------------|--------------------|--------------|
| Save 30g | +2-3% top speed | +3-5% flight time | +3-5% range |
| Save 50g | +4-5% top speed | +5-8% flight time | +5-8% range |

**Reality check:** Frame weight matters LEAST compared to battery and motor choices.
- Budget frame (Source One): ~110g → AUW 650g
- Premium frame (Five33): ~75g → AUW 615g
- Difference: 35g saves ~5% battery = ~15-20 seconds extra flight time

Spending $70 more on a frame for 15 seconds is rarely worth it for beginners. Put that money into better batteries instead.

### Radio System (Maximum Control Range)

| System | Real-World Max Range | Latency | Cost |
|--------|---------------------|---------|------|
| FrSky ACCESS (2.4GHz) | 1-2 km | 9-18ms | Built into radio |
| ELRS 2.4GHz (250mW) | 10-15 km | 2-5ms | $12 RX |
| ELRS 2.4GHz (1W) | 20-30 km | 2-5ms | $30-50 TX module |
| **ELRS 900MHz (1W)** | **30-50+ km** | 5-8ms | $20-30 RX |
| TBS Crossfire (900MHz) | 30-40+ km | 5-7ms | $180 TX + $30 RX |

**Critical insight:** For 99% of pilots, the **video link fails before the control link.** Your usable range is limited by what you can SEE, not what you can control.

### Video System (Maximum Video Range)

| System | Usable Video Range | Notes |
|--------|-------------------|-------|
| Analog 25mW | 200-500m | Indoor/park only |
| Analog 200mW | 500m-1.5km | Short range outdoor |
| Analog 800mW | 1-3 km | Standard outdoor |
| **Analog 1.6W** | **2-5 km** | Maximum analog |
| DJI O3 (standard) | 8-13 km | Best digital range |
| HDZero | 3-5 km | Lower power digital |
| Walksnail | 5-8 km | Mid-range digital |

**The real range limiter in most builds is the video system, not the radio.**

---

## Build Profiles

### Profile 1: Maximum Speed (Racing)

| Component | Choice | Why |
|-----------|--------|-----|
| Motors | 2207 2700KV (4S) | Highest RPM, lightest |
| Battery | 1050-1300mAh 4S | Minimum weight |
| Props | Tri-blade 5045-5051 | Maximum thrust |
| Frame | <100g, 4mm arms | Minimum weight |
| VTX | Analog (lightest) | Weight savings |

**Result:** 160+ km/h capable, 2-3 min flights, very agile

### Profile 2: Freestyle (Balanced — Most Common)

| Component | Choice | Why |
|-----------|--------|-----|
| Motors | 2306 2400KV (4S) or 1900KV (6S) | Balance of power and efficiency |
| Battery | 1300-1500mAh | Good flight time without sluggishness |
| Props | Tri-blade 5040-5046 | Good grip, responsive |
| Frame | 100-120g, 5mm arms | Durable enough for crashes |
| VTX | Digital or high-power analog | Good range for spots |

**Result:** 120-140 km/h capable, 4-6 min flights, responsive and durable

### Profile 3: Long Range / Cruising

| Component | Choice | Why |
|-----------|--------|-----|
| Motors | 2306 1700-1800KV (6S) | Maximum efficiency |
| Battery | 1500-2000mAh 6S | Extended flight time |
| Props | Bi-blade 5030-5035 | Most efficient |
| Frame | Lightweight, GPS mount | Every gram counts |
| Radio | ELRS 900MHz | Maximum control range |
| VTX | DJI O3 (10km+) or analog 1.6W | Video is the range limit |
| Firmware | iNav | GPS return-to-home safety |

**Result:** 80-100 km/h cruise, 8-15 min flights, 5-15 km usable range

### Profile 4: Cinematic / Camera Drone

| Component | Choice | Why |
|-----------|--------|-----|
| Motors | 2306 1900KV (6S) | Smooth, enough power for payload |
| Battery | 1500-1800mAh 6S | Compensate for extra weight |
| Props | Tri or quad-blade, low pitch | Smooth, stable |
| Frame | Deadcat (props out of camera view) | Clean footage |
| VTX | DJI O3 (4K recording) | Onboard 4K footage |
| Camera | GoPro or naked GoPro (additional) | Better footage than DJI O3 camera |

**Result:** Smooth, stable, 4-6 min with good footage, 5-10 km range

---

## Decision Flowchart

```
What do you primarily want to do?
│
├── Race competitively
│   └── 4S, 2700KV, 1050mAh, tri-blade 5051, analog, light frame
│
├── Freestyle (flips, rolls, proximity flying)
│   └── 4S/6S, 2400/1900KV, 1300mAh, tri-blade 5043, digital or analog
│
├── Long range exploration
│   └── 6S, 1700KV, 1500-2000mAh, bi-blade, ELRS 900MHz, GPS + iNav
│
├── Cinematic filming
│   └── 6S, 1900KV, 1500mAh, tri/quad-blade low pitch, DJI O3, GoPro
│
└── I don't know yet (beginner)
    └── 4S, 2400KV, 1300mAh, tri-blade 5043, analog → upgrade later
```

---

## Quantified Trade-Off Table

| Change | Speed Impact | Flight Time Impact | Range Impact | Cost Impact |
|--------|-------------|-------------------|--------------|-------------|
| 4S → 6S | Same (reKV) | +15-25% | +15-25% | +$10-15/pack |
| 2700KV → 1900KV | -30% top speed | +30% | +30% | Same |
| 1300mAh → 1800mAh | -5% (weight) | +20-30% | +20-30% | +$8-12/pack |
| Tri-blade → Bi-blade | -10% acceleration | +15-20% | +15-20% | Same |
| Analog → DJI O3 | No change | -5% (weight) | +200-400% video range | +$300-400 |
| High-pitch → Low-pitch | -15% top speed | +10-15% | +10-15% | Same |
| Add GPS + iNav | No change | -2% (weight) | Infinite (RTH) | +$12-20 |
| ELRS 2.4 → 900MHz | No change | No change | +100-200% control | +$15-25 |

---

## Summary: What Matters Most

**Ranked by impact on flight time (most to least):**
1. Motor KV selection (30% difference)
2. Battery capacity (20-30% difference)
3. Prop pitch and blade count (15-20%)
4. Battery chemistry (4S vs 6S efficiency: 15-25%)
5. Frame weight (3-8%)
6. VTX system weight (2-5%)

**Ranked by impact on usable range:**
1. Video system (analog 1km vs DJI 10km — 10x difference)
2. Radio protocol (FrSky 2km vs ELRS 900MHz 50km)
3. Battery capacity (more flight time = more distance possible)
4. Motor efficiency (extends cruise distance)
5. Prop efficiency (bi-blade for range)

**Ranked by impact on speed:**
1. Motor KV (direct RPM relationship)
2. Prop pitch (direct thrust angle)
3. AUW / power-to-weight ratio
4. Frame aerodynamics (minimal at hobby speeds)
