# 2026 Updates — What Changed

> **Note (May 2026):** All corrections below have been inlined into the base documentation files (COMPONENTS.md, BUILD-GUIDE.md, BUDGET-TIERS.md, SHOPPING-LIST.md, TRADE-OFFS.md, REGULATIONS.md). This file now serves as a changelog explaining *why* things changed. Each base doc is accurate standalone — you don't need to cross-reference this file.

Last updated: May 2026.

---

## Major Changes

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
- Premium: RadioMaster TX16S MKII ($180) — unchanged

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
| ELRS firmware | ELRS 3.x | **ELRS 4.x** | Major update, not backward compatible |
| Betaflight | 4.5 | **2025.12** | New versioning, altitude/position hold |
| FC processor | F7 recommended | **H7 recommended** | F4 limited, H7 is future |
| GPS module | Optional | **Strongly recommended** | BF 2025.12 altitude/position hold |

---

## What DIDN'T Change

- **Frame recommendations** — same brands, same quality, same prices
- **Motor recommendations** — Emax Eco II, iFlight XING2, T-Motor Velox all still current
- **Battery tech** — standard LiPo, no solid-state yet for FPV, same brands
- **Propeller options** — Gemfan 51466, HQProp, Ethix all still standard
- **Soldering equipment** — Pinecil V2 still best value
- **HDZero/Walksnail** — no major confirmed 2026 products (may have updates I couldn't verify)
- **Budget tier pricing** — still approximately $500-600 all-in for a budget build
- **ExpressLRS dominance** — still the clear winner for radio protocol
- **Regulations** — no major 2026 EASA/Danish changes confirmed (Remote ID requirements evolving, C-class marking transition ongoing)

---

## Action Items for Your Build

If ordering parts NOW (May 2026):

1. **FC:** Buy H7-based if available in your price range (SpeedyBee/Mamba H7 stacks)
2. **ELRS:** All current HappyModel/RadioMaster/BetaFPV receivers are ESP-based — safe to buy, just flash to ELRS 4.x
3. **Video:** DJI O4 for premium, O3 for mid-range (likely discounted), analog unchanged for budget
4. **Radio:** RadioMaster TX15 Max is the new mid-range value pick
5. **Betaflight:** Add a GPS module to your build — altitude/position hold is now in Betaflight (huge for learning!)
6. **GPS:** BN-220 or BN-880 (with compass) — $12-18, enables RTH and position hold

**Biggest impact for beginners:** The addition of altitude hold and position hold in Betaflight 2025.12 makes a GPS module essentially mandatory now. It's $12-18 and gives you a safety net while learning.
