# Drone Regulations — Denmark & EU

Rules for flying your DIY drone outdoors. These apply regardless of whether you built or bought the drone.

Denmark follows the **EU-wide EASA drone regulations** implemented through the Danish Transport Authority (Trafikstyrelsen). The rules are harmonized across all EU/EEA member states.

---

## EU Rules (EASA) — Applied in Denmark

### Categories

| Category | Subcategory | Weight | Requirements |
|----------|-------------|--------|--------------|
| **Open** | **A1** | <250g | Fly near (not over) people. No exam required if drone has C0 class marking. |
| **Open** | **A1** | 250g–900g (C1) | Register as operator. Pass A1/A3 online exam. Keep distance from uninvolved people. |
| **Open** | **A2** | 900g–4kg (C2) | A2 Certificate of Competency (additional exam). 30m horizontal from uninvolved people (5m in low-speed mode). |
| **Open** | **A3** | 4–25kg (C3/C4) | A1/A3 exam. Fly only in areas clear of uninvolved people. 150m from residential/commercial/industrial areas. |
| **Specific** | — | Any | Risk assessment required (SORA/PDRA). Operator authorization from Trafikstyrelsen. |
| **Certified** | — | Any | Aviation-grade certification. Not relevant for hobby. |

**Your 5" quad will weigh 500–700g. It falls in subcategory A1 (if <900g) or A3 (if no C-class marking, which applies to most DIY builds).**

### Important: Legacy/DIY Drones Without C-Class Marking

Most DIY-built drones and older commercial drones do NOT have a C-class marking. Under the transition rules:

- **<250g without C-class:** Fly in A1 (near but not over people)
- **250g–25kg without C-class:** Fly in **A3 only** (150m from residential/commercial/industrial areas, well away from uninvolved people)

This means your DIY 5" quad (no C-class) must follow A3 rules regardless of its weight.

---

## Danish Registration (Trafikstyrelsen)

### Who Must Register?

- Any drone **250g or heavier**, OR
- Any drone **with a camera** (regardless of weight)

Since virtually all FPV drones have cameras, **you must register**.

### How to Register

1. Go to: https://droneregister.trafikstyrelsen.dk
2. Create an account (NemID/MitID login)
3. Register as **UAS operator**
4. Receive your **operator registration number**
5. Mark the number visibly on all your drones

| Detail | Info |
|--------|------|
| **Cost** | Free |
| **Validity** | Must be renewed (check current period) |
| **Required for** | All drones with camera or 250g+ |
| **Number display** | Must be visible on the drone |

---

## Danish/EU Pilot Competency (Exams)

### A1/A3 Certificate (Required for Open Category)

- **Where:** Online at Trafikstyrelsen's drone portal or via EASA member state mutual recognition
- **Format:** 40 multiple-choice questions
- **Topics:** Air safety, airspace, regulations, human performance, operating procedures
- **Cost:** Free
- **Validity:** 5 years
- **Language:** Danish (English may be available depending on portal)

### A2 Certificate of Competency

Required if you want to fly 900g–4kg drones closer to people (30m, or 5m in low-speed mode):

- Must hold A1/A3 certificate first
- Self-practical training (documented)
- Additional theory exam (30 questions)
- Covers meteorology, UAS flight performance, technical/operational risk mitigation
- **Cost:** Varies (exam fee applies)

---

## Danish Airspace Rules

### Altitude

- **Maximum height:** 120m (400ft) AGL in Open category
- No exceptions without Specific category authorization

### No-Fly Zones (Denmark-Specific)

| Zone | Restriction |
|------|-------------|
| **Airports** | No flying within flight restriction zones (varies per airport, typically 5km+) |
| **Helicopter landing sites** | No-fly radius applies |
| **Military areas** | Prohibited |
| **Prisons** | Prohibited |
| **Police operations** | Prohibited |
| **Royal residences** | Prohibited |
| **Populated areas (A3)** | 150m minimum distance for drones without C-class marking |
| **Nature reserves** | Check local rules — many restrict or ban drones |

### Checking Airspace Before Flying

- **Dronezoner (droneregler.dk/dronezoner)** — Official Danish drone zone map (https://www.droneregler.dk/dronezoner)
- Shows no-fly zones, restricted areas, altitude caps
- **Always check before every flight**
- General drone rules info: https://www.droneregler.dk

---

## Remote Identification (EU)

Starting January 1, 2024, Remote ID requirements apply:

- Drones in class C1, C2, C3 must have **direct remote identification** (broadcast via Wi-Fi/Bluetooth)
- DIY drones without C-class marking: Remote ID not strictly required in A3 subcategory (but regulations are evolving — check current status)
- External Remote ID modules are available (€30–50) and recommended for future-proofing

**Practical advice for your build:**
- An external Remote ID module (e.g., DroneTag Mini, Aerobits) can be velcroed to your frame
- Some flight controllers support broadcast via ESP32 — check Betaflight/iNav compatibility
- Having Remote ID gives you flexibility if rules tighten

---

## General Rules (EU/Denmark)

1. **Stay below 120m AGL** — hard limit in Open category
2. **Keep visual line of sight (VLOS)** — if you can't see it, bring it back
3. **Don't fly over people** — props at 40,000+ RPM are dangerous
4. **Don't fly near airports** — check droneregler.dk/dronezoner
5. **Don't fly in bad weather** — wind >20 km/h is risky for smaller quads
6. **Don't fly over private property at low altitude** without permission (privacy law applies in Denmark)
7. **Don't fly near power lines** — interference + physical danger
8. **Never fly under the influence**
9. **Yield right-of-way to manned aircraft** — always

---

## Liability and Insurance

| Option | Coverage | Cost | Notes |
|--------|----------|------|-------|
| **Modelflyvning Danmark** | Liability insurance | ~300 DKK/year | Danish model flying association, includes club access |
| **Private ansvarsforsikring** | May cover drones | Check policy | Some Danish home insurance covers drone liability |
| **Dedicated drone insurance** | Varies | €50–150/year | Available from various EU insurers |
| **None** | €0 | Free | You're personally liable — risky in Denmark |

**Recommendation:** Join Modelflyvning Danmark or ensure your private liability insurance (ansvarsforsikring) covers drone flying. Denmark has strict liability rules — if your drone causes damage or injury, you are liable regardless of fault.

**Note:** EU regulations recommend but do not mandate insurance for Open category. However, Danish law may impose liability regardless. Having insurance is strongly recommended.

---

## Practical Advice for Outdoor Flying in Denmark

### Finding Places to Fly

- **Model flying clubs (Modelflyvning Danmark):** Best option — insured, legal, community. Find clubs at modelflyvning.dk
- **Open fields / agricultural land:** Usually fine for A3 if you have permission and maintain 150m from buildings/people
- **Beaches:** Often fine in less populated areas, but check local rules and nature protection zones
- **Forests (state-owned):** Generally prohibited or restricted
- **Nature reserves / Natura 2000 areas:** Drones often banned or require permit
- **Private land:** Best if you have access — fewer issues with people nearby

### Pre-Flight Checklist

- [ ] Check droneregler.dk/dronezoner for your location
- [ ] Verify you're 150m from residential/commercial areas (A3 requirement)
- [ ] Battery charged and not puffed
- [ ] Props tight, correct direction (CW/CCW matched)
- [ ] Antenna attached to VTX (flying without antenna burns VTX)
- [ ] Failsafe configured (test: turn off TX, confirm drone disarms or lands)
- [ ] GPS lock if using iNav (wait for 8+ satellites)
- [ ] No visible damage to frame or motors
- [ ] SD card in goggles DVR (for reviewing crashes)
- [ ] Operator registration number visible on drone
- [ ] A1/A3 certificate obtained and valid

---

## Weight Optimization: Staying Under 250g

If you want fewer restrictions (fly in A1 near people, simpler rules), a sub-250g build IS possible but challenging:

| Component | Ultra-Light Choice | Weight |
|-----------|-------------------|--------|
| Frame | 3" or ultralight 5" (Flywoo Explorer) | 30–60g |
| FC+ESC | 20x20 AIO (all-in-one) | 8–12g |
| Motors | 1404 or 1804 (small) | 28–40g (x4) |
| Props | 3" or light 5" bi-blade | 8–12g (x4) |
| Battery | 450–650mAh 4S | 55–80g |
| VTX + Camera | Ultra-light analog or DJI O3 Lite | 20–35g |
| Receiver | 1g ELRS | 1g |
| **Total** | | **180–240g** |

**Trade-offs:** Less power, shorter flight time (2–4 min), less crash resistant, harder to build (tiny components). Most beginners are better served by a standard 5" build and just registering.

**Note:** Even sub-250g drones with a camera require operator registration in Denmark.

---

## Key Links

| Resource | URL |
|----------|-----|
| Trafikstyrelsen Drone Portal | https://droneregister.trafikstyrelsen.dk |
| Dronezoner (airspace map) | https://www.droneregler.dk/dronezoner |
| Droneregler (rules info) | https://www.droneregler.dk |
| EASA Drone Rules | https://www.easa.europa.eu/en/domains/civil-drones |
| Modelflyvning Danmark | https://www.telemodel.dk |
| EU Drone Regulation 2019/947 | EUR-Lex (search "Commission Implementing Regulation 2019/947") |
