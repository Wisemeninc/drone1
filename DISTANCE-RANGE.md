# Distance & Range Guide

How far can you fly a drone? It depends on your build, video system, battery, and radio link.

---

> ## ⚠️ Read this before the tables below
>
> **The ranges in this guide are what the hardware can do, not what you may legally transmit in Denmark or the EU.**
>
> 5.8GHz video is capped at **25mW e.i.r.p.** for licence-free use — ERC Recommendation 70-03, Annex 1 (ETSI EN 300 440). At 25mW an analog VTX gives roughly **200–500m** of usable range — not the kilometres quoted below. The allowance applies only inside **5725–5875 MHz** — Raceband R1/R2/R7/R8 and Bands E and L are outside it (channel table in [REGULATIONS.md](./REGULATIONS.md)). An amateur licence is not a reliable workaround — the amateur allocation excludes most FPV channels (see [REGULATIONS.md](./REGULATIONS.md)).
>
> **That cap applies to everyone, DJI included.** The DJI O4 in CE mode is limited to the same 25mW on 5.8GHz (DJI spec: <14 dBm). It still reaches about **6 km in CE mode** (vs 10 km on FCC firmware) because of a far better link budget — OFDM, error correction, receive sensitivity — and because it also operates on **5.1GHz at up to 23 dBm (CE)**, a band a bare analog VTX cannot legally use. Certification is what lets a system be sold to use those bands and modes; it does not buy a power exemption.
>
> **The practical consequence, and it inverts the usual advice:** legal range in the EU comes from a digital system with a strong link budget, not from a high-power analog VTX. A 1.6W analog VTX is 64× over the legal limit here; run at its legal 25mW it is a short-range park system.
>
> Every table below now carries an **EU-legal** column. Read that column, not the hardware column, when planning a build to fly in Denmark. See [REGULATIONS.md](./REGULATIONS.md).

## What Limits Your Range

Range is limited by whichever system fails first. Ranked by what typically kills range:

1. **Video link** — you can't fly what you can't see (biggest limiter for most builds)
2. **Battery capacity** — you need enough juice to get there AND back
3. **Efficiency** — low KV + bi-blade props + light frame = more km per mAh
4. **Firmware** — iNav with GPS gives return-to-home if video drops
5. **Control link** — ELRS 900MHz at 1W basically never runs out of range

---

## Range by Limiting Factor

| Limiting Factor | Range (hardware max) | **EU equipment ceiling** | What Happens |
|----------------|---------------------|--------------------------|--------------|
| Video link (analog 800mW) | 1-3 km | **200-500m** — must run 25mW | Screen goes to static |
| Video link (analog 1.6W) | 2-5 km | **200-500m** — must run 25mW | Fades and breaks up |
| Video link (Walksnail) | 5-8 km | CE-limited — no published CE figure found; well below hardware | Digital feed cuts |
| Video link (DJI O3) | 8-13 km | CE-limited, below the FCC figure | Digital feed drops |
| **Video link (DJI O4)** | **10-13 km (FCC)** | **~6 km (CE)** — same 25mW on 5.8GHz; wins on link budget + 5.1GHz | Best current digital range |
| Video link (HDZero) | 3-5 km | CE-limited — no published CE figure found; well below hardware | Lower power digital |
| Control link (ELRS 2.4GHz 250mW) | 10-15 km | Over the 100mW EIRP EU cap | Rarely the bottleneck |
| Control link (ELRS 2.4GHz 1W) | 20-30 km | Well over the EU cap | Extreme range |
| **Control link (ELRS 900MHz 1W)** | **50-100+ km** | **Not an EU configuration** — see note | Essentially unlimited for quads |
| Control link (TBS Crossfire) | 30-40+ km | 868MHz EU versions are duty-cycle limited | Proven long-range |
| Battery (5" freestyle, 1300mAh 4S) | 2-4 km round trip | n/a — not power-limited | Need to return before voltage sag |
| Battery (5" efficient, 1500mAh 6S) | 5-8 km round trip | n/a — not power-limited | Low KV cruise extends range |
| Battery (5" long-range, 1800mAh 6S) | 8-12 km round trip | n/a — not power-limited | Purpose-built for distance |
| Battery (7" long-range, 2500mAh 6S) | 15-30 km round trip | n/a — not power-limited | Large props, maximum efficiency |

> **On "900MHz":** the 902-928MHz band ELRS uses at 1W is a US allocation. The EU equivalent is **868MHz at 25 mW e.r.p. with a 1 % duty cycle** for the sub-bands ELRS EU868 actually uses (ETSI EN 300 220; the 500 mW allowance exists only in the narrow 869.4–869.65 MHz sub-band), so EU long-range links are materially shorter than the figures above. 2.4GHz is capped at 100mW EIRP (ETSI EN 300 328). None of this usually matters in practice — the video link fails long before the control link does.

---

## Real-World Range by Build Type

| Build Type | Max Distance (hardware) | **EU equipment ceiling** (VLOS still applies) | Primary Limiter | Approx Cost |
|------------|------------------------|------------------------------------------------|-----------------|-------------|
| **Budget 5" (analog video)** | **1-2 km** | **200-500m** | Legal VTX power | $500-600 |
| **Mid-range 5" (Walksnail)** | **4-6 km** | CE-limited — no published CE figure | Legal VTX power | $900-1,100 |
| **Mid-range 5" (DJI O4)** | **5-8 km** | **~6 km** equipment ceiling — but VLOS | VLOS, then battery | $1,000-1,300 |
| **Dedicated 5" long-range** | **10-15 km** | ~6 km with DJI O4 — but VLOS | VLOS | $800-1,200 |
| **7" long-range build** | **20-40 km** | ~6 km with DJI O4 — but VLOS | VLOS | $1,000-1,500 |
| **Extreme long-range (custom)** | **50-100+ km** | Not legally achievable in the Open category | Regulatory | $1,500+ |

> **VLOS binds before any of this.** Denmark's Open category requires unaided visual line of sight at all times. Trafikstyrelsen publishes the formula: **327 × (propeller-tip-to-tip diagonal in metres) + 20 m** — about **134 m for a 5" quad** and ~184 m for a 7", whatever your video link reaches. The column above is the *equipment* ceiling — what the gear may legally emit — not a distance you may fly; VLOS is the *operational* ceiling, and it is stricter. Flying to 6 km on a DJI O4 is legal equipment used illegally unless you hold a Specific-category authorisation. See [REGULATIONS.md](./REGULATIONS.md) and [BVLOS-RELAY-DRONE.md](./BVLOS-RELAY-DRONE.md).

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
- **FPV with an observer:** the *only* way FPV is legal in the Open category — `UAS.OPEN.060(4)` / Art. 4(1)(d) of 2019/947. The observer must stand **alongside** the pilot, keep the aircraft in **unaided** visual line of sight, and be able to warn the pilot. This is law, not "accepted practice", and it does **not** extend VLOS — the ~134 m limit above still applies; the observer merely lets you wear the goggles.

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
