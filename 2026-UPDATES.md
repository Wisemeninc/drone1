# 2026 Updates — What Changed

> **Note (May 2026):** All corrections below have been inlined into the base documentation files (COMPONENTS.md, BUILD-GUIDE.md, BUDGET-TIERS.md, SHOPPING-LIST.md, TRADE-OFFS.md, REGULATIONS.md). This file now serves as a changelog explaining *why* things changed. Each base doc is accurate standalone — you don't need to cross-reference this file.

Last updated: **September 2026.**

---

## What Changed Since May 2026

Four months of drift, checked on 2026-09-05 against vendor release notes and authority pages where they exist; sourcing is noted per item, and items that rest on shop listings or buyer-guide roundups say so. The regulatory item is the one that should change what you buy.

### A. Denmark: Remote-ID proposed for all drones of 250 g or more — from 1 Jan 2027

**This supersedes the "no major 2026 changes" line this file used to carry.**

In June 2026 Trafikstyrelsen put an amended drone declaration out to consultation (deadline 21 August 2026, now closed) requiring **Remote-ID or equivalent remote identification on every drone of 250 g or more** (*mindst 250 g*), expected in force **1 January 2027**. Drones under 250 g are caught only when flying in security-critical zones with sensors such as a camera.

A 500–700 g DIY quad is squarely in scope, and the A3 exemption that covers non-C-marked builds today is exactly what the proposal removes. The same draft widens mandatory distances around commercial ports, airports, prisons and certain government facilities, and requires logbooks to be produced **to the police** on demand.

Separately, **the DK-STS-03 droneerklæring expired 1 January 2026** — a *Specific-category* standard scenario used by commercial operators. It never applied to Open-category hobby flying, so it changes nothing for this guide's reader; it is noted because older Danish guidance written for it still circulates. The draft Remote-ID rules also carry an **exemption for model-flying fields, meets and competitions** (§4 stk. 2).

An earlier version of this section also claimed an **EASA "privately built drones framework"** was due in Q3 2026. No such EASA rulemaking could be found; the claim traced to a blog. The governing rule — `UAS.OPEN.040(4)(a)`, privately built under 25 kg in A3 — is permanent, and the Article 22 transition that did expire (31 Dec 2023) applied to commercial legacy drones, not home builds. Removed.

**Impact on builds:** budget €30–50 for an external Remote ID module (DroneTag Mini, Aerobits) and account for its weight now. See [REGULATIONS.md](./REGULATIONS.md) for the full picture. Still a proposal, not final law — verify at [droneregler.dk](https://www.droneregler.dk).

### B. Betaflight 2026.6 / 2026.6.1 (June 2026)

Supersedes 2025.12 throughout this guide.

- **GPS Rescue rebuilt** on a new 3D position estimator — noticeably more precise
- **Optical flow position hold** — holds position without GPS lock (needs a supported flow sensor)
- **Switchable battery profiles** with independent voltage and capacity settings
- **CAN bus support** and the first DroneCAN GPS implementation
- **Modernised app**, in-app Blackbox log viewer, native Android firmware flashing over USB, a dedicated iOS app, and the Betaflight Bridge companion
- **New platforms:** ESP32, STM32H5 / N6 / C5, STM32H757 dual-core, X32M7, RP2350 pixel OSD
- **Expanded MAVLink** telemetry for QGroundControl
- **Autopilot and waypoint missions — simulation only, not flight-ready.** Do not plan a build around them.

**Impact on builds:** GPS modules are more worth having than ever. The old "4kHz cap in BF 2025.12" framing in this guide asserted a firmware cap; the 2026.6 release notes contain no such cap, so the claim has been reworded to what the evidence supports — no documented cap, with 4kHz as the practical ceiling F4 CPU headroom allows. Absence from the release notes is not positive evidence of full support, and the guide no longer says "Full".

### C. ExpressLRS 4.1.0 (July 2026)

The current stable release, and **compatible with all hardware already on any 4.x version** — no repeat of the 3.x → 4.x break.

- Smarter dynamic power (power-down threshold lowered from +1.5 SD to +0.5 SD, so it drops power more readily on a good link)
- Substantially fewer false "telemetry lost" callouts, via a linearly-scaled grace period
- **Bind phrases settable from the handset Lua script** — no WiFi needed
- **GPS time sync to the flight controller** over a new CRSF sensor type — pairs with Betaflight 2026.6
- WebUI VBAT calibration, millivolt-precision voltage telemetry
- Groundwork for Semtech's **LR2021** 4th-gen LoRa chip — the first to do LoRa, FLRC and FSK on both 2.4GHz and 900MHz

**Impact on builds:** none to your shopping list. Flash to 4.1 and keep TX and RX on the same major version.

### D. RadioMaster TX16S MK3 (January 2026)

The premium radio pick in this guide was the previous generation.

| Radio | Notes |
|-------|-------|
| **TX16S MK3** | **Current flagship** — STM32 H7 processor, larger 5" screen, dual-band Gemini ELRS, same form factor and same price as the MKII |
| TX16S MKII | Previous gen, still excellent, may be discounted |

Gemini Xrossband transmits on 2.4GHz and 900MHz simultaneously — but only with a Gemini-capable receiver on the aircraft.

### E. Digital video: the field widened

The old "no major confirmed 2026 products" line for HDZero/Walksnail no longer holds.

- **Walksnail Avatar HD Pro** — 1080p/100fps feed, onboard 4K/60 recording, 22-28ms depending on mode. Walksnail also has the widest VTX range of any system now (7g 1S Lite kits up to 35g dual-antenna Pro kits), and spent 2025-26 fixing its firmware-stability reputation.
- **OpenIPC and Ascent** now appear routinely in 2026 system comparisons alongside DJI, HDZero and Walksnail. OpenIPC is the open-source, no-lock-in option.

**Sourcing caveat:** the OpenIPC/Ascent entries come from 2026 buyer-guide roundups rather than hands-on testing — research before buying.

**No change:** DJI O4 is still current-generation. **There is no O5.** DJI's own O4 Air Unit release notes were still being updated in March 2026.

---

## Earlier in 2026 (May) — Major Changes

### 1. DJI O4 Replaces O3 as Current-Gen

The DJI O3 Air Unit is now previous-generation. **DJI O4** is the current system:

| System | Status | Notes |
|--------|--------|-------|
| DJI O3 | Previous gen | Still works, still sold, still good. Cheaper now. |
| **DJI O4** | **Current gen** | Latest air unit, improved link |
| **DJI O4 Pro** | **Current gen** | Higher-end variant |
| **DJI Remote Controller 3 (RC3)** | **New** | Compact radio that talks directly to O4 air units — no separate receiver needed |

**Impact on builds:**
- Premium tier: Consider DJI O4 Air Unit instead of O3
- DJI RC3 is an alternative to RadioMaster + ELRS if you commit fully to DJI ecosystem
- O3 is now a mid-range option (likely discounted)

### 2. ExpressLRS 4.0 (Major Release — Feb 2025)

**ELRS 4.0 is a breaking change. Not backward-compatible with ELRS 3.x/2.x/1.x.**

Key new features:
- **1000Hz FSK mode (K1000)** on 2.4GHz — even lower latency
- **Automatic Antenna Diversity** — switches between True Diversity and Gemini modes automatically
- **Statistical Adaptive Dynamic Power** — smarter power management replaces fixed thresholds
- **Double telemetry bandwidth** in Gemini mode
- **Direct GPS input on receiver** — RX can read GPS directly (NMEA, 115200 baud)
- **New WebUI** — complete rewrite, much cleaner

**Breaking changes:**
- **STM32-based hardware dropped** — R9M, ExpressLRS PP, Ghost hardware no longer supported
- **Flash filesystem changed** from SPIFFS to LittleFS — settings lost on upgrade
- All transmitters and receivers must be on ELRS 4.x to communicate

**Impact on builds:**
- Only buy ESP-based ELRS hardware (all current RadioMaster/HappyModel/BetaFPV stuff is ESP-based — you're fine)
- Make sure TX and RX are both running ELRS 4.x after flashing
- The K1000 mode at 1000Hz is the new performance target

### 3. Betaflight 2025.12 (New Versioning + Major Features)

Betaflight switched to **calendar-based versioning** (YYYY.M.PATCH) with releases every 6 months.

**New autonomous flight features:**
- **Altitude Hold** — maintains altitude via barometer/GPS
- **Position Hold** — holds GPS position (needs GPS + magnetometer)
- **Collision Detection** — experimental
- **Auto-disarm on landing impact** — safety feature

**New hardware support:**
- H725 CPU (next-gen FC processor)
- Raspberry Pi RP2350 MCU
- APM32F40X series (Chinese STM32 alternative)
- New gyros: IIM42653, ICM456xx, ICM-42688-P, LSM6DSV16X

**Other additions:**
- ELRS FLRC F-modes support
- Progressive Web App configurator (auto-updates, no desktop app needed)
- Board alignment simplified (separate gyro alignment removed)
- MAVLink improvements
- Caddx camera gimbal support

**Impact on builds:**
- GPS module even more useful now (altitude hold, position hold — great for beginners!)
- H7 FCs are now the clear standard (F4 limited to 4kHz PID loop)
- Consider adding a magnetometer/compass if your FC has one (enables position hold)

### 4. RadioMaster TX15 / TX15 Max (New Radio)

| Radio | Price | Notes |
|-------|-------|-------|
| **RadioMaster TX15** | ~$120 | Color touchscreen, full-size gimbals, ELRS built-in |
| **RadioMaster TX15 Max** | ~$139 | Premium version, hall sensors, same form factor |

**Where it fits:** Between the Zorro ($100) and TX16S ($180). Boxer-style form factor with a color touchscreen. If you want full-size without TX16S bulk, this is the new pick.

**Updated radio recommendations:**
- Budget: RadioMaster Pocket ($65) — unchanged
- **Mid-range: RadioMaster TX15 Max ($139) — NEW PICK**
- Premium: RadioMaster TX16S MKII ($180) — unchanged *(superseded September 2026 — see section D: the TX16S MK3 replaced it in January 2026)*

### 5. ESC Firmware: AM32 Growing

**AM32** is the open-source successor to BLHeli_32 (which is closed-source and effectively abandoned):
- Active development
- Growing hardware support
- Free (vs BLHeli_32 license fees baked into ESC price)
- Not yet universal — check if your ESC supports it before flashing

**Current status:** BLHeli_32 ESCs still work fine. AM32 is the future direction. No action needed for new builds unless you specifically want cutting-edge firmware.

---

## Updated Recommendations Table

| Category | Old (2025) Pick | 2026 Pick | Change Reason |
|----------|----------------|-----------|---------------|
| DJI Video (premium) | DJI O3 + Goggles 2 | **DJI O4 + Goggles 2** (or RC3) | O4 is current gen |
| DJI Video (mid) | — | **DJI O3 (discounted)** | Previous gen = cheaper |
| Mid-range radio | RadioMaster Zorro ($100) | **RadioMaster TX15 Max ($139)** | Better screen, same form factor |
| Premium radio | RadioMaster TX16S MKII | **RadioMaster TX16S MK3** | H7 CPU, 5" screen, dual-band Gemini, same price |
| Remote ID (DK) | Not required for DIY in A3 | **Plan for a module (€30-50)** | Proposed mandatory for 250g+ from 1 Jan 2027 |
| ELRS firmware | ELRS 3.x | **ELRS 4.1** | 4.x broke from 3.x; 4.1 is a safe in-place upgrade |
| Betaflight | 4.5 | **2026.6** | Rebuilt GPS Rescue, optical flow hold, modernised app |
| FC processor | F7 recommended | **H7 recommended** | F4 limited, H7 is future |
| GPS module | Optional | **Strongly recommended** | BF 2026.6 altitude/position hold, rebuilt GPS Rescue |

---

## What DIDN'T Change

- **Frame recommendations** — same brands, same quality, same prices
- **Motor recommendations** — Emax Eco II, iFlight XING2, T-Motor Velox all still current
- **Battery tech** — standard LiPo, no solid-state yet for FPV, same brands
- **Propeller options** — Gemfan 51466, HQProp, Ethix all still standard
- **Soldering equipment** — Pinecil V2 still best value
- **Budget tier pricing** — still approximately $500-600 all-in for a budget build
- **ExpressLRS dominance** — still the clear winner for radio protocol
- ~~**Regulations** — no major 2026 EASA/Danish changes confirmed~~ — **superseded, see section A above.** Denmark has a Remote-ID mandate for 250 g+ proposed for 1 Jan 2027, DK-STS-03 expired 1 Jan 2026, and EASA's privately-built framework was due Q3 2026.

---

## Action Items for Your Build

If ordering parts NOW (September 2026):

1. **FC:** Buy H7-based if available in your price range (SpeedyBee/Mamba H7 stacks)
2. **ELRS:** All current HappyModel/RadioMaster/BetaFPV receivers are ESP-based — safe to buy, just flash to ELRS 4.1
3. **Video:** DJI O4 for premium, O3 for mid-range (likely discounted), analog unchanged for budget
4. **Radio:** RadioMaster TX15 Max is the mid-range value pick; **TX16S MK3** is the premium pick (the MKII it replaced is previous-gen)
5. **Betaflight:** Add a GPS module to your build — altitude/position hold is in Betaflight, and 2026.6 rebuilt GPS Rescue (huge for learning!)
6. **GPS:** BN-220 or BN-880 (with compass) — $12-18, enables RTH and position hold

7. **Remote ID:** budget €30-50 for an external module and account for its weight — Denmark looks set to require it on 250g+ drones from 1 Jan 2027

**Biggest impact for beginners:** altitude hold and position hold (Betaflight 2025.12, refined through 2026.6) make a GPS module essentially mandatory. It's $12-18 and gives you a safety net while learning.

**Biggest impact overall:** the proposed Danish Remote-ID mandate. Everything else here is a firmware flash or a nicer radio; that one changes what has to be bolted to your airframe.
