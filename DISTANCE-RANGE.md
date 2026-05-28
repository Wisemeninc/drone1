# Distance & Range Guide

How far can you fly a drone? It depends on your build, video system, battery, and radio link.

---

## What Limits Your Range

Range is limited by whichever system fails first. Ranked by what typically kills range:

1. **Video link** — you can't fly what you can't see (biggest limiter for most builds)
2. **Battery capacity** — you need enough juice to get there AND back
3. **Efficiency** — low KV + bi-blade props + light frame = more km per mAh
4. **Firmware** — iNav with GPS gives return-to-home if video drops
5. **Control link** — ELRS 900MHz at 1W basically never runs out of range

---

## Range by Limiting Factor

| Limiting Factor | Range | What Happens |
|----------------|-------|--------------|
| Video link (analog 800mW) | 1-3 km | Screen goes to static |
| Video link (analog 1.6W) | 2-5 km | Fades and breaks up |
| Video link (Walksnail) | 5-8 km | Digital feed cuts |
| Video link (DJI O3) | 8-13 km | Digital feed drops |
| **Video link (DJI O4)** | **10-13 km** | Best current digital range |
| Video link (HDZero) | 3-5 km | Lower power digital |
| Control link (ELRS 2.4GHz 250mW) | 10-15 km | Rarely the bottleneck |
| Control link (ELRS 2.4GHz 1W) | 20-30 km | Extreme range |
| **Control link (ELRS 900MHz 1W)** | **50-100+ km** | Essentially unlimited for quads |
| Control link (TBS Crossfire) | 30-40+ km | Proven long-range |
| Battery (5" freestyle, 1300mAh 4S) | 2-4 km round trip | Need to return before voltage sag |
| Battery (5" efficient, 1500mAh 6S) | 5-8 km round trip | Low KV cruise extends range |
| Battery (5" long-range, 1800mAh 6S) | 8-12 km round trip | Purpose-built for distance |
| Battery (7" long-range, 2500mAh 6S) | 15-30 km round trip | Large props, maximum efficiency |

---

## Real-World Range by Build Type

| Build Type | Realistic Max Distance | Primary Limiter | Approx Cost |
|------------|----------------------|-----------------|-------------|
| **Budget 5" (analog video)** | **1-2 km** | Video dies first | $500-600 |
| **Mid-range 5" (Walksnail)** | **4-6 km** | Battery / video | $900-1,100 |
| **Mid-range 5" (DJI O4)** | **5-8 km** | Battery is the limit | $1,000-1,300 |
| **Dedicated 5" long-range** | **10-15 km** | Battery at limits | $800-1,200 |
| **7" long-range build** | **20-40 km** | Battery / safety margins | $1,000-1,500 |
| **Extreme long-range (custom)** | **50-100+ km** | Regulatory / battery | $1,500+ |

---

## How to Build for Maximum Distance

### The Long-Range Recipe

| Component | Choice | Why |
|-----------|--------|-----|
| Motors | 2306 1700-1800KV (6S) | Maximum efficiency at cruise |
| Battery | 1800-2200mAh 6S | Extended flight time without excessive weight |
| Props | Bi-blade 5030 or 5035 | Most efficient, least current draw |
| Frame | Lightweight 5" (<100g) or 7" | Every gram costs range |
| Radio | ELRS 900MHz (1W) | 50+ km control link |
| Video | DJI O4 (10+ km) | Longest digital video range |
| Firmware | **iNav** (not Betaflight) | GPS waypoints, return-to-home, cruise mode |
| GPS | BN-880 (with compass) | Required for iNav navigation |
| Antenna | Directional patch (goggles) + omni (drone) | Focused signal = more range |

### Range Gains by Change

| Modification | Range Improvement | Cost |
|--------------|------------------|------|
| Analog → DJI O4 video | +5-10 km video range | +$400 |
| 2400KV → 1700KV motors | +30% flight distance | Same cost |
| Tri-blade → Bi-blade props | +15-20% flight distance | Same cost |
| 1300mAh → 1800mAh battery | +25-35% flight distance | +$10/pack |
| ELRS 2.4GHz → 900MHz | +30-70 km control range | +$15-25 |
| Betaflight → iNav | Return-to-home safety, cruise mode | Free |
| Add GPS module | Enables RTH if video lost | +$12-18 |
| Directional antenna on goggles | +30-50% video range | +$20-40 |

---

## Flight Time vs Distance Relationship

Your maximum one-way distance is roughly:

```
Max one-way distance = (flight time × cruise speed) ÷ 2.5
```

The 2.5 factor accounts for:
- Return trip
- Safety margin (land at 3.5V/cell, not 3.0V)
- Wind resistance on return
- Non-straight flight path

### Example Calculations

| Flight Time | Cruise Speed | Max One-Way | Round Trip |
|-------------|-------------|-------------|------------|
| 4 min | 60 km/h | 1.6 km | 3.2 km |
| 6 min | 60 km/h | 2.4 km | 4.8 km |
| 8 min | 70 km/h | 3.7 km | 7.5 km |
| 12 min | 80 km/h | 6.4 km | 12.8 km |
| 15 min | 80 km/h | 8.0 km | 16.0 km |
| 20 min | 80 km/h | 10.7 km | 21.3 km |

---

## Long-Range Safety Requirements

Flying beyond visual line of sight (BVLOS) requires additional precautions:

### Mandatory for Long-Range

| Feature | Why | Cost |
|---------|-----|------|
| **GPS + iNav** | Return-to-home on signal loss | $12-18 (GPS module) |
| **Failsafe: RTH** | Drone flies home automatically if link drops | Free (firmware setting) |
| **Battery telemetry** | Know remaining mAh in real-time on OSD | Free (ESC telemetry) |
| **Low-voltage alarm** | Warning before battery dies | Free (OSD setting) |
| **RSSI on OSD** | Monitor signal strength in real-time | Free (OSD setting) |

### Strongly Recommended

| Feature | Why | Cost |
|---------|-----|------|
| Buzzer | Find drone after crash in tall grass/trees | $3 |
| GPS coordinates on OSD | Know exact position if you need to walk to it | Free (iNav) |
| Directional antenna (goggle side) | Extends video range 30-50% | $20-40 |
| Crossfire/ELRS 900MHz | Longer wavelength penetrates obstacles better | $15-25 |
| Pre-planned route (iNav waypoints) | Automated efficient flight path | Free (iNav mission planner) |

---

## Legal Considerations for Distance Flying (Denmark / EU)

| Jurisdiction | VLOS Rule | Max Legal Distance (without waiver) |
|--------------|-----------|-------------------------------------|
| **EU (EASA) / Denmark** | VLOS required in Open category | ~500m–1km (practical eye limit) |

**Reality:** Visual line of sight for a 5" quad is approximately 500m–1km depending on conditions. Beyond that, you cannot see orientation or obstacles.

**Legal long-range options:**
- **EU Specific category:** Authorization via SORA risk assessment (apply to Trafikstyrelsen in Denmark)
- **PDRA (Pre-Defined Risk Assessment):** Standardized scenarios that simplify Specific category approval
- **Spotter:** A second person watching the drone extends legal VLOS
- **FPV with spotter:** One person flies FPV, another maintains VLOS (accepted practice in EU Open category)

**Practical note:** Most long-range FPV pilots fly in remote, unpopulated areas and accept regulatory risk. This is common in the hobby but technically non-compliant without Specific category authorization. In Denmark, enforcement exists — Trafikstyrelsen can issue fines.

---

## Quick Reference: Range by Budget

| Budget | Realistic Range | How |
|--------|----------------|-----|
| **$500-600** | 1-2 km | Budget 5", analog video |
| **$800-1,000** | 5-8 km | 5" with DJI O4, efficient setup |
| **$1,000-1,300** | 10-15 km | Dedicated 5" long-range, iNav, ELRS 900 |
| **$1,200-1,500** | 20-40 km | 7" long-range, large battery, full GPS nav |
| **$1,500+** | 50+ km | Extreme builds, multiple redundancies |
