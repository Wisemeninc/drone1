# Drone Regulations — Outdoor Flying

Rules for flying your DIY drone outdoors. These apply regardless of whether you built or bought the drone.

---

## US FAA Rules

### Registration

| Weight | Registration Required? | Cost | Validity |
|--------|----------------------|------|----------|
| **<250g (0.55 lbs)** | No (recreational) | Free | — |
| **250g–25kg** | **Yes** | $5 | 3 years |
| >25kg | Special waiver | — | — |

**Your 5" quad will weigh 500-700g. You MUST register.**

Register at: https://faadronezone.faa.gov

Your registration number must be visible on the drone (or in the battery compartment if accessible without tools).

### Recreational Flyers (Section 44809)

You must pass **The Recreational UAS Safety Test (TRUST)** before flying. Free, online, takes ~30 minutes.

**Rules:**
- Fly under **400 feet AGL** (above ground level)
- Maintain **visual line of sight** (VLOS) at all times
- **Never** fly over people or moving vehicles
- **Never** fly in controlled airspace without LAANC authorization
- **Never** fly near emergency response operations
- **Never** fly under the influence
- Yield right-of-way to manned aircraft
- Fly at or below 100 mph (not a practical concern for most)
- **Night flying:** allowed with anti-collision lights visible at 3 statute miles

### Controlled Airspace (Near Airports)

- Use **B4UFLY** app (official FAA app) to check if your flying location is restricted
- Use **LAANC** (Low Altitude Authorization and Notification Capability) for instant authorization in controlled airspace via apps like AirMap, Aloft, or DJI Fly
- **Class B (major airports):** Generally prohibited without LAANC
- **Class C/D (regional airports):** LAANC available, altitude caps apply
- **Class E/G (most other areas):** Generally fine, but check B4UFLY

### Part 107 (Commercial Use)

If you fly for any commercial purpose (paid work, business use, YouTube monetization arguably), you need a **Remote Pilot Certificate**:
- Pass an FAA knowledge test ($175)
- Valid for 2 years (recurrent test to renew)
- Same airspace rules apply, but waivers available for night, over people, beyond VLOS

### Remote ID (Effective March 2024)

- All drones 250g+ must broadcast Remote ID
- Options: Built-in module (firmware/hardware) OR fly at FAA-Recognized Identification Areas (FRIAs)
- **Betaflight 2025.12 supports Remote ID broadcast** via serial-connected module or direct ESP32 broadcast
- **iNav supports Remote ID broadcast** natively
- External Remote ID modules available ($30-50) — mounts on frame, broadcasts your registration ID
- **FRIAs:** AMA flying fields and some community areas are exempt — check FAA FRIA map

**Practical advice for your build:**
- Easiest option: buy an external Remote ID module ($30-50, e.g., DroneTag Mini, HolyBro Remote ID) and velcro it to your frame
- Advanced option: configure Betaflight/iNav built-in broadcast (requires ESP32 on FC or external module on UART)
- If you only fly at AMA fields or FRIAs, you're exempt — but having a module gives you freedom to fly anywhere legal

---

## EU Rules (EASA)

### Categories

| Category | Subcategory | Weight | Requirements |
|----------|-------------|--------|--------------|
| **Open** | **A1** | <250g | Fly near (not over) people. No registration if no camera (varies by country). |
| **Open** | **A1** | 250-900g | Register with national authority. Keep distance from uninvolved people. |
| **Open** | **A2** | 900g-4kg | A2 Certificate of Competency (online exam). 30m horizontal from uninvolved people. |
| **Open** | **A3** | 4-25kg | Fly only in areas clear of uninvolved people. 150m from residential/commercial areas. |
| **Specific** | — | Any | Risk assessment required (SORA). Operator authorization. |
| **Certified** | — | Any | Aviation-grade certification. Not relevant for hobby. |

### EU Registration

- Required for any drone with a camera OR weighing 250g+ 
- Register in your country of residence (each country has a civil aviation authority)
- Costs vary by country (free to ~50 EUR)
- EU operator number must be displayed on the drone

### EU Exam

- **A1/A3 online exam:** Required for subcategories A1 and A3 (free in most countries, ~40 questions)
- **A2 certificate:** Additional exam for flying closer to people (higher weight class)

---

## UK Rules (CAA)

| Weight | Registration | Requirements |
|--------|-------------|--------------|
| <250g | Operator ID only | Fly responsibly |
| 250g+ | Operator ID + Flyer ID | Pass online theory test |
| 250g-25kg (Open) | A2 CofC for closer distances | Additional exam |

- Register at: https://register-drones.caa.co.uk
- **Flyer ID:** Online test, free, valid 5 years
- **Operator ID:** Registration fee, valid 1 year
- 120m (400ft) altitude cap
- VLOS at all times
- No flying near airports (5km exclusion zone for most)

---

## General Rules (Apply Almost Everywhere)

Regardless of country, these are universal best practices:

1. **Stay below 120m / 400ft AGL**
2. **Keep visual line of sight** — if you can't see it, bring it back
3. **Don't fly over people** — props at 40,000+ RPM are dangerous
4. **Don't fly near airports** — check local maps
5. **Don't fly in bad weather** — wind >20mph is risky for 5" quads
6. **Carry liability insurance** — AMA membership includes $2.5M coverage in the US ($75/year)
7. **Don't fly over private property** without permission (debatable legally, but good practice)
8. **Don't fly near power lines** — they cause video interference AND are dangerous

---

## Liability and Insurance

| Option | Coverage | Cost | Notes |
|--------|----------|------|-------|
| **AMA membership** (US) | $2.5M liability | $75/year | Includes access to AMA flying fields |
| **BMFA** (UK) | Public liability | ~£40/year | Similar to AMA |
| **Homeowner's insurance** | Varies | Check policy | May or may not cover drone incidents |
| **None** | $0 | Free | You're personally liable for all damages |

**Recommendation:** Get AMA or equivalent membership. If your drone hits someone's car or injures someone, $75/year is nothing compared to a lawsuit.

---

## Practical Advice for Outdoor Flying

### Finding Places to Fly

- **AMA fields:** Best option — insured, legal, community (find at ama.org)
- **Parks:** Check local ordinances — many prohibit drones, some allow in specific areas
- **Private land:** Best if you have access — full control, no restrictions
- **Open fields / agricultural land:** Usually fine if you have permission and no one is around
- **Beaches:** Often restricted near populated areas
- **National Parks (US):** **BANNED** — do not fly in any National Park

### Pre-Flight Checklist

- [ ] Check B4UFLY / local airspace app
- [ ] Battery charged and not puffed
- [ ] Props tight, correct direction (CW/CCW matched)
- [ ] Antenna attached to VTX (flying without antenna burns VTX)
- [ ] Failsafe configured (test: turn off TX, confirm drone disarms or lands)
- [ ] GPS lock if using iNav (wait for 8+ satellites)
- [ ] No visible damage to frame or motors
- [ ] SD card in goggles DVR (for reviewing crashes)
- [ ] Phone charged (for B4UFLY / SpeedyBee app)
- [ ] Emergency contact info on the quad (name + phone number sticker)

---

## Weight Optimization: Staying Under 250g

If you want to avoid registration (and get fewer restrictions), a sub-250g 5" build IS possible but challenging:

| Component | Ultra-Light Choice | Weight |
|-----------|-------------------|--------|
| Frame | 3" or ultralight 5" (Flywoo Explorer) | 30-60g |
| FC+ESC | 20x20 AIO (all-in-one) | 8-12g |
| Motors | 1404 or 1804 (small) | 28-40g (×4) |
| Props | 3" or light 5" bi-blade | 8-12g (×4) |
| Battery | 450-650mAh 4S | 55-80g |
| VTX + Camera | Ultra-light analog or DJI O3 Lite | 20-35g |
| Receiver | 1g ELRS | 1g |
| **Total** | | **180-240g** |

**Trade-offs:** Less power, shorter flight time (2-4 min), less crash resistant, harder to build (tiny components). Most beginners are better served by a standard 5" build and just registering.
