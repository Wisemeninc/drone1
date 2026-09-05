# Drone Regulations — Denmark & EU

Rules for flying your DIY drone outdoors. These apply regardless of whether you built or bought the drone.

Denmark follows the **EU-wide EASA drone regulations** implemented through the Danish Transport Authority (Trafikstyrelsen). The rules are harmonized across all EU/EEA member states.

> **Checked: September 2026.** Two changes since this guide was first written: the DK-STS-03 declaration expired on 1 January 2026, and Denmark has a proposal in flight to require Remote-ID on **all drones of 250 g or more from 1 January 2027**. Both are covered below. Regulations move faster than this document — always confirm at [droneregler.dk](https://www.droneregler.dk).

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

**Danish change — the DK-STS-03 declaration expired January 1, 2026 — but it does not affect you.** DK-STS-03 was a *Specific-category* standard scenario operated under a declaration, used mainly by commercial operators flying legacy drones in built-up areas. It was never an Open-category privilege, so its expiry changes nothing for a hobby A3 flyer. It is mentioned here only because older Danish guidance written for STS operators still circulates and can read as if it applies to everyone. It does not.

**Privately built drones — the rule is permanent, not transitional.** Regulation 2019/947, `UAS.OPEN.040(4)(a)`, allows a privately built UAS of under 25 kg MTOM to fly in subcategory A3 with an A1/A3 certificate. That provision has no expiry. The transitional period that *did* expire — Article 22, on 31 December 2023 — applied to non-compliant *commercial* drones placed on the market before the class-marking regime, not to home builds. Privately built drones are excluded from class marking altogether (Regulation 2019/945, Article 2(1)(a)), so a home build can never be C4 and never needs to be. The "DIY means A3, no class mark needed" premise of this guide rests on `UAS.OPEN.040(4)(a)`, and it is stable. (An earlier version of this page described a pending EASA "privately built framework" due in 2026; no such EASA rulemaking could be found and the claim has been removed.)

---

## Danish Registration (Trafikstyrelsen)

### Who Must Register?

- Any drone **250g or heavier**, OR
- Any drone **with a camera** (regardless of weight)

Since virtually all FPV drones have cameras, **you must register**.

### How to Register

1. Go to: https://www.droneregler.dk/fritidsdroneflyvning/registrer-dig-som-privat-droneoperatoer
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

## Video Transmitter Power (5.8GHz)

**This catches almost every new FPV builder.** Analog VTXs are sold rated at 400mW, 800mW, 1.6W and higher, but in Denmark and across the EU:

| Setting | Legal licence-free? | Realistic range |
|---------|--------------------|-----------------|
| **25mW** | ✅ **Yes** — the CEPT limit | 200-500m |
| 200mW / 400mW / 800mW / 1.6W | ❌ No — and an amateur licence is not the workaround it sounds like (see below) | 1-5 km |

The cap is **25mW e.i.r.p.** for non-specific short-range devices in 5725–5875 MHz under **ERC Recommendation 70-03, Annex 1**, given binding EU effect by **Decision (EU) 2022/180, Annex entry 61** (harmonised standard ETSI EN 300 440), and e.i.r.p. means transmitter power *plus* antenna gain. This is why every analog VTX sold by an EU shop is listed as "25mW" — the shops are selling you the legal configuration.

**25mW is necessary but not sufficient — the channel matters just as much.** The 25mW allowance exists only inside **5725–5875 MHz**. Standard FPV channel banks spill out of it on both sides, and what lies outside is not "grey": the FPV channels that fall below 5725 MHz (R1/R2, low Band E, Band L) sit in **5470–5725 MHz**, an RLAN band in which UAS operation is **not permitted** — Decision (EU) 2022/179 as amended by 2022/2307, which bars UAS from 5250–5350 and 5470–5725 MHz; above 5875 MHz is the **road-safety ITS band** (Decision (EU) 2020/1426). (The same Decision *does* permit UAS in 5170–5250 MHz at up to 23 dBm — that is the 5.1 GHz carve-out a certified DJI O4 uses, see point 2 below. No analog FPV VTX operates there.) A VTX set to 25mW on Raceband R7 is illegal on two counts.

| Band | ✅ Usable | ⚠️ Avoid — <10 MHz from an edge, or shares spectrum with 33 dBm telematics | ❌ Outside — prohibited |
|------|------------------------------|--------------------------------------|-------------------------|
| **Raceband (R)** | **R4 5769 · R5 5806 · R6 5843** | R3 5732 (7 MHz) | R1 5658 · R2 5695 (RLAN, UAS not permitted) · R7 5880 · R8 5917 (ITS) |
| **Band A** | A2 5845 · A3 5825 · A4 5805 · A5 5785 · A6 5765 · A7 5745 | A8 5725 (0 MHz) · A1 5865 (on the 5855–5875 V2X band) | — |
| **Band B** | B2 5752 · B3 5771 · B4 5790 · B5 5809 · B6 5828 · B7 5847 | B1 5733 (8 MHz) · B8 5866 (9 MHz; on the V2X band) | — |
| **Band E** | — | — | E1–E4 (5645–5705, RLAN) · E5–E8 (5885–5945, ITS) |
| **Band F / Fatshark** | F1 5740 · F2 5760 · F3 5780 · F4 5800 · F5 5820 · F6 5840 | F7 5860 (on the 5855–5875 V2X band) | F8 5880 (ITS) |
| **Band L** | — | — | all — 5362–5469 is radar / Earth-observation / aeronautical radionavigation spectrum with no civil allocation at all; 5470–5621 is RLAN where UAS operation is not permitted |

Two things put a channel in the ⚠️ column. First, analog FPV video occupies roughly 20 MHz (±10 MHz around the centre), so a channel centred less than 10 MHz from a band edge spills over it — each such channel shows its distance. Second, the 25 mW SRD allowance **shares** 5725–5875 MHz with much louder licensed users: **5855–5875 MHz is vehicle-to-vehicle telematics at 33 dBm e.i.r.p.** (Decision 2022/180, entries 88–89), so A1, B8 and F7 are legal but will be flattened by any nearby V2X-equipped vehicle. **Stick to R4–R6, A2–A7, B2–B7 or F1–F6.** One more thing to know rather than avoid: **5795–5815 MHz is road tolling at 2 W** (entry 62), which A4, F4, R5 and B5 straddle — fully legal to use, but expect the picture to break up under motorway gantries and don't blame the VTX. Digital systems (DJI, Walksnail, HDZero) manage this in firmware in CE mode; analog does not — you have to pick the channel yourself.

**Two practical consequences:**

1. **Set your VTX to 25mW on a channel from the ✅ column, and leave it there.** Almost every VTX supports 25mW, usually as the lowest power setting. An amateur radio licence does not help in practice: the amateur 6 cm allocation (5650–5850 MHz) excludes A1, F7/F8, R7/R8 and upper Band E — most of what an FPV VTX offers — and whether a licensed amateur may run commercially made FPV equipment above 25mW on the channels that remain is a national spectrum-use question for the Danish authority, not something this guide can promise. Plan on 25mW.
2. **If you want real range legally, buy a good digital system — but understand why it works.** The DJI O4 is held to the **same 25mW on 5.8GHz as everyone else** (DJI's own spec: <14 dBm in CE mode). It reaches roughly 6 km in CE mode anyway, for two reasons neither of which is a power allowance: a far better link budget (OFDM modulation, error correction, receive sensitivity — the same reason a phone gets data where a walkie-talkie gets static), and access to the **5.1GHz band at up to 23 dBm (CE)**, which a bare analog VTX cannot legally use. RED type-approval is what allows a system to be sold using those bands and modes; it does **not** raise the 5.8GHz power cap for anyone. The practical conclusion still holds — digital is the route to legal range here — but it holds because of engineering, not because certification buys an exemption.

Note that **VLOS still applies** regardless of what your video link can do. See the Open category rules above.

---

## Remote Identification

### In force today (EU)

Since January 1, 2024:

- Drones in class C1, C2, C3 must have **direct remote identification** (broadcast via Wi-Fi/Bluetooth)
- DIY drones without C-class marking: Remote ID **not currently required** in the A3 subcategory

### Proposed for January 1, 2027 (Denmark) — this affects your build

> **Status: a proposal that has been through consultation, not yet law.** Dates and thresholds below are from the draft (Høringsportalen sag 71261) and can still move.

**This is the single most important change for anyone building a 5" quad right now.**

In June 2026 Trafikstyrelsen sent an amended drone declaration to public consultation. It requires **Remote-ID or another form of remote identification on every drone of 250 g or more** (the draft says *mindst 250 g* — at least 250 g, so a 250 g drone is caught) — described by the authority as an "electronic number plate" that lets drone operations be detected and identified.

| Detail | Status |
|--------|--------|
| **Requirement** | Remote-ID or equivalent remote identification |
| **Applies to** | **All drones of 250 g or more** (*mindst 250 g*) — including privately built, no C-class marking |
| **Exemption** | Flying at a **model-flying field, meet or competition** (draft §4 stk. 2) — directly relevant if you fly at a Modelflyvning Danmark club |
| **Under 250 g** | Only when flying in security-critical drone zones with sensors such as a camera |
| **Consultation deadline** | August 21, 2026 (now closed) |
| **Expected in force** | **January 1, 2027** |

**Your 500–700 g DIY quad is over 250 g. It is in scope.** The A3-subcategory exemption that covers you today is what this proposal removes.

The same draft also:

- **Increases mandatory distances** around commercial ports, airports, prisons and certain government facilities
- **Requires logbooks on demand to the police**, not just to Trafikstyrelsen as before (hobby drones under 250 g stay exempt from the logbook requirement)

**Status caveat:** this went through consultation, not yet final law. The date and the exact thresholds can still move. Verify at [droneregler.dk](https://www.droneregler.dk) before relying on it — but plan your build as though it is coming.

### Practical advice for your build

- Budget **€30–50 for an external Remote ID module** (DroneTag Mini, Aerobits and similar) — velcro it to the frame. Given the January 2027 date, treat this as a near-term purchase rather than optional future-proofing.
- Some flight controllers can broadcast via an ESP32 — check current Betaflight/iNav compatibility before counting on it instead of a dedicated module.
- Weight matters: a Remote ID module adds grams to a build that may already be near a category threshold. Account for it now rather than after the fact.

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
| Trafikstyrelsen Drone Registration | https://www.droneregler.dk/fritidsdroneflyvning/registrer-dig-som-privat-droneoperatoer |
| Dronezoner (airspace map) | https://www.droneregler.dk/dronezoner |
| Droneregler (rules info) | https://www.droneregler.dk |
| EASA Drone Rules | https://www.easa.europa.eu/en/domains/civil-drones |
| Modelflyvning Danmark | https://www.modelflyvningdanmark.dk |
| EU Drone Regulation 2019/947 | EUR-Lex (search "Commission Implementing Regulation 2019/947") |
