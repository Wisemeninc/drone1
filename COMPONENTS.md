# Drone Components — Detailed Reference

Complete breakdown of every component category with specific models, pros/cons, and beginner recommendations.

---

## 1. Frame

The frame holds everything together. For outdoor 5" quads, carbon fiber is the only serious option.

### Carbon Fiber vs Alternatives

| Material | Weight | Durability | Vibration | Price | Verdict |
|----------|--------|-----------|-----------|-------|---------|
| **Carbon Fiber** | 80-120g | Shatters on extreme impact, very stiff | Excellent dampening | $25-100 | **Standard — use this** |
| Aluminum | 150-250g | Bends, doesn't shatter | Poor (resonates) | $15-40 | Avoid for quads |
| 3D Printed (TPU/PETG) | Varies | Flexible but weak | Moderate | $5-15 filament | Frame mounts/accessories only |

### Frame Geometry

| Layout | Description | Best For |
|--------|-------------|----------|
| **True-X** | Arms at 90 degrees, symmetric | General purpose, clean builds |
| **Stretched-X** | Front arms spread wider | Freestyle (smoother pitch) |
| **Deadcat** | Rear arms angled in | Keep props out of camera view |
| **H-frame** | Rectangular | Durability, heavy payloads |

### Arm Thickness

- **4mm arms** — lightweight, racing, breaks easier
- **5mm arms** — sweet spot for freestyle
- **6mm arms** — tank mode, heavy but nearly indestructible

### Recommended Frames

| Frame | Weight | Arm Thickness | Price | Pros | Cons |
|-------|--------|---------------|-------|------|------|
| **Source One V5** | ~110g | 4mm | $30-40 | Open-source, cheapest arms ($3 each), huge community, true-X | Basic design, no fancy features |
| **TBS Source Two V0.2** | ~125g | 5mm | $40-50 | Stretched-X, great for freestyle, thick arms | Slightly heavy |
| **ImpulseRC Apex** | ~115g | 5mm | $80-100 | Premium build quality, excellent HD camera mounting | Expensive, arms not universal |
| **Armattan Badger** | ~130g | 5mm | $55-75 | **Lifetime warranty on arms** — they replace free | Heavy, older design |
| **GEPRC Mark5** | ~105g | 4.5mm | $45-60 | Clean design, good DJI O3 mounting, light | Arms can be hard to find |
| **Diatone Roma F5 V2** | ~100g | 4mm | $35-50 | Lightweight, smooth, good value | 4mm arms break faster |

### Beginner Pick: Source One V5

- Arms cost $3-5 to replace (you WILL break arms learning)
- Thousands of build videos available
- Fits any standard 20x20 or 30.5x30.5 stack
- True-X layout is easiest to set up

---

## 2. Flight Controller (FC)

The brain of the drone. Runs Betaflight or iNav firmware, reads gyroscope data, and sends commands to the ESC.

### Processor Comparison

| Spec | F4 (STM32F405) | F7 (STM32F722) | **H7 (STM32H743)** |
|------|----------------|----------------|-----------------|
| Clock Speed | 168 MHz | 216 MHz | **480 MHz** |
| Flash Storage | 1 MB | 512 KB–1 MB | 2 MB |
| Blackbox Logging | Limited | Good | Excellent (high-rate) |
| PID Loop Rate | **4K practical (CPU-bound)** | 8K comfortable | 32K capable |
| UART Count | 3-5 | 4-6 | 6-8 |
| Future-proofing | **Legacy — CPU-limited, still supported** | Good | **Best — buy this in 2026** |
| Price Range | $25-40 | $35-60 | $45-80 |
| Betaflight Support | Supported — no documented cap; 4kHz is the practical CPU ceiling | Full | Full |
| iNav Support | Full | Full | Full |

### Key FC Features to Look For

- **Barometer** — needed for altitude hold in iNav
- **Bluetooth/WiFi** — configure from phone without USB cable (SpeedyBee)
- **SD card slot or onboard flash** — Blackbox logging for PID tuning
- **Current sensor** — tracks battery usage (mAh consumed)
- **Sufficient UARTs** — one for receiver, one for GPS, one for VTX smart audio, one for ESC telemetry

### Recommended Flight Controllers

| FC | Processor | UARTs | Price | Pros | Cons |
|----|-----------|-------|-------|------|------|
| **SpeedyBee F405 V4** | F4 | 6 | $30-35 | Bluetooth config from phone, cheapest | F4 legacy — 4kHz practical PID ceiling (CPU headroom, not a firmware cap) |
| **SpeedyBee F7 V3** | F7 | 6 | $40-50 | WiFi blackbox download, solid | Being surpassed by H7 |
| **Mamba F722 MK4** | F7 | 5 | $35-45 | Proven reliable, Diatone support | No wireless config |
| **SpeedyBee F7 H7 stack** | H7 | 7 | $50-65 | Latest gen, full BF 2026.6 features | Newer, fewer build guides |
| **GEPRC Span F722-BT-HD** | F7 | 6 | $45-55 | DJI connector built-in, Bluetooth | Proprietary connectors |

### FC+ESC Stacks (Buy Together)

| Stack | FC + ESC | Price | Pros |
|-------|----------|-------|------|
| **SpeedyBee F405 V4 + 50A** | F4 + BL32 50A | $65-80 | Cheapest beginner deal, guaranteed compatibility |
| ~~**Mamba F722 + F50 Pro**~~ | F7 + BL32 50A | — | ⚠️ F50 Pro has no EU stock — see note below |
| **GEPRC Span H7 + 60A** | H7 + BL32 60A | $90-120 | Best future-proofing, full BF 2026.6 features |

### Beginner Pick: SpeedyBee F405 V4 Stack (budget) or H7 stack (recommended)

- **If budget is tight:** F405 V4 stack ($65-80) — Bluetooth config, great docs, works fine for learning
- **If you can spend $20 more:** Get an H7 or F7 stack — unlocks 8K PID loops, altitude/position hold and the rebuilt GPS Rescue in Betaflight 2026.6, better blackbox logging, and won't need replacing as firmware advances

---

## 3. Motors

Motors convert electrical energy into thrust. The two key specs are **stator size** and **KV rating**.

### Understanding Motor Naming: 2306

- **23** = stator diameter in mm
- **06** = stator height in mm
- Wider stator = more torque
- Taller stator = higher RPM potential

### Stator Size Comparison

| Size | Torque | RPM | Weight | Best For |
|------|--------|-----|--------|----------|
| **2207** | Moderate | Higher (taller stator) | 30-34g | Racing, lighter builds |
| **2306** | Higher (wider stator) | Moderate | 33-36g | **Freestyle, carrying weight, all-around** |
| **2407** | High | High | 36-40g | Heavy rigs, 6S power |

### KV Rating Explained

KV = RPM per volt (unloaded). Higher KV = faster spin = more current draw.

| KV | Battery | Character | Efficiency | Use Case |
|----|---------|-----------|-----------|----------|
| **1700-1800** | 6S | Smooth, efficient, long flights | Best | Long-range, cinematic, cruising |
| **1900-2100** | 6S | Balanced power and efficiency | Good | Freestyle on 6S |
| **2400-2550** | 4S | Balanced, responsive | Good | **Freestyle on 4S (most common beginner)** |
| **2700-2900** | 4S | Aggressive, power-hungry | Poor | Racing |

### The KV Decision

| If you want... | Choose | Why |
|----------------|--------|-----|
| Longest flight time | 1700KV + 6S | Least current draw at cruise speed |
| Best power:efficiency | 1900KV + 6S | Good power, still efficient |
| Easiest beginner setup | 2400KV + 4S | 4S batteries cheaper, lighter crashes |
| Maximum speed | 2700KV + 4S | Highest RPM, racing class |

### Recommended Motors

| Motor | Size | KV | Price (×4) | Pros | Cons |
|-------|------|-----|-----------|------|------|
| **Emax Eco II 2306** | 2306 | 2400 | $40-50 | Best budget, widely available, proven | Basic bearings |
| **iFlight XING2 2306** | 2306 | 2555 | $55-65 | Great all-rounder, good bearings | Mid-price |
| **T-Motor Velox V2 2306** | 2306 | 2400 | $55-70 | Very smooth, durable | Expensive for performance |
| **BrotherHobby Avenger V3 2306** | 2306 | 1900 | $60-75 | Excellent for 6S freestyle | Only makes sense on 6S |
| **Emax Eco II 2207** | 2207 | 1700 | $40-50 | Budget 6S long-range | Lower torque than 2306 |
| **T-Motor F60 Pro V 2207** | 2207 | 1750 | $80-100 | Premium 6S, tight tolerances | Expensive |

### Beginner Pick: Emax Eco II 2306 2400KV

- $10-12 per motor — cheap to replace when you crash
- Pairs with readily available 4S batteries
- Proven in thousands of builds
- Good enough performance for years of flying

---

## 4. ESC (Electronic Speed Controller)

The ESC converts the FC's digital commands into the 3-phase AC that spins brushless motors.

### 4-in-1 vs Individual ESCs

| Factor | 4-in-1 (Single Board) | Individual (4 Separate) |
|--------|----------------------|------------------------|
| Weight | Lighter (one PCB) | Heavier (4 PCBs + wiring) |
| Wiring | Clean, minimal | Complex, more solder joints |
| Failure Mode | Whole board dies if one channel blows | Replace just the bad one |
| Price | $30-60 | $60-100 total |
| Build Complexity | Easy | Hard |
| **Verdict** | **Use this for 99% of builds** | Only for redundancy-critical long-range |

### Amp Rating Selection

The ESC must handle the **peak** current your motors pull. Oversizing is cheap insurance.

| Rating | Handles | Use Case |
|--------|---------|----------|
| 30A | ~25A continuous / ~35A burst | Light 4S, racing, 2207 motors |
| **45A** | ~40A continuous / ~55A burst | **Best all-around for 2306 on 4S/6S** |
| **50A** | ~45A continuous / ~60A burst | Recommended sweet spot |
| 60A+ | ~55A continuous / ~75A burst | 6S aggressive, heavy builds |

**Rule:** Your ESC amp rating should be 1.5-2x the motor's max continuous current draw.

### Firmware Comparison

| Feature | BLHeli_S | BLHeli_S + Bluejay | BLHeli_32 |
|---------|----------|-------------------|-----------|
| Price range | $25-35 | Same (free flash) | $40-65 |
| RPM telemetry | No | **Yes (bidirectional DShot)** | Yes (native) |
| RPM filtering | No | **Yes** | Yes |
| Configurability | Basic | Good | Maximum |
| Startup tune | No | Yes | Yes |
| Motor direction | Solder swap | **Software reverse** | Software reverse |
| **Recommendation** | Don't buy stock | **Flash Bluejay for free** | Best if budget allows |

**Bluejay firmware:** Free open-source firmware you flash onto BLHeli_S ESCs. Adds bidirectional DShot (RPM filtering) and software motor direction. Effectively makes cheap ESCs perform like BLHeli_32 for the features that matter most.

### Recommended ESCs

| ESC | Amps | Firmware | Price | Pros | Cons |
|-----|------|----------|-------|------|------|
| **SpeedyBee BLS 50A** | 50A | BLHeli_S (flash Bluejay) | $30-35 | Cheapest good ESC, flash Bluejay day 1 | Need to flash firmware |
| **SpeedyBee F405 V4 Stack** | 50A | BL32 | $65-80 | FC+ESC combo, plug and play | More expensive than ESC alone |
| ~~**Mamba F50 Pro**~~ | 50A | BL32 | — | Was reliable, good thermals | ⚠️ **No EU stock (Sept 2026)** — AliExpress only |
| **T-Motor F55A Pro II** | 55A | BL32 | $70-80 (€69.95 incl. VAT at FlyingMachines) | Premium quality, excellent FETs | Expensive; EU stock intermittent |
| **Aikon AK32 Pin 35A** | 35A | BL32 | $50-60 | Ultra-clean power, racing focused | Only 35A |

> **⚠️ Availability note (September 2026):** the Mamba F50 Pro is no longer stocked by any EU FPV shop checked — mostly US/UK stock, often backordered, still on AliExpress. **The substitute is the T-Motor F55A Pro II** (30.5×30.5 base variant, **$70-80** — €69.95 incl. VAT at FlyingMachines): BL32 preloaded, nothing to flash. Be clear-eyed about what this swap buys you: the Mamba F50 Pro was dropped because no EU shop stocks it, and every F55A variant was **also out of stock when checked in September 2026**. So the honest position is that **neither ESC is on an EU shelf right now** — the F55A is the better part and is at least *listed* by an EU shop for backorder, but your realistic options today are backorder from FlyingMachines or AliExpress. Do **not** buy the *ULTRA F55A PROII* variant for this build: it is **20×20 mm** and will not fit the 30.5 mm stack.
>
> The **SpeedyBee BLS 50A** below is still an excellent ESC and the cheapest route if you are happy to flash Bluejay — but source it carefully. EU specialty shops do not carry it standalone, and an Amazon search for it mostly returns third-party "kompatibel mit Speedybee" clone stacks rather than the genuine part.

### Beginner Pick: SpeedyBee Stack (FC+ESC combo)

- Guaranteed compatibility between FC and ESC
- One purchase decision instead of two
- BL32 firmware out of the box — no flashing needed
- 50A handles any 5" motor comfortably

---

## 5. Battery (LiPo)

The battery is the heaviest single component and most impacts flight time, weight, and performance.

### LiPo Basics

- **Cell count (S):** 1S = 3.7V nominal, 4S = 14.8V, 6S = 22.2V
- **Capacity (mAh):** How much energy it stores
- **C rating:** Maximum safe discharge rate (multiply by capacity for max amps)
- **Example:** 1300mAh 100C = 1.3A × 100 = 130A max discharge

### 4S vs 6S for 5" Outdoor Quad

| Spec | 4S (14.8V nominal) | 6S (22.2V nominal) |
|------|--------------------|--------------------|
| Current Draw | Higher (compensates for lower voltage) | Lower for same power output |
| Heat Generation | More (I²R losses) | Less |
| Weight (same mAh) | Lighter (~185g for 1300mAh) | Heavier (~195g for 1100mAh) |
| Motor KV Needed | 2400-2700 KV | 1700-1900 KV |
| Cost per Pack | $20-35 | $25-45 |
| Wire Gauge | Thicker (higher current) | Can be thinner |
| Efficiency | Good | **Better** (lower I²R losses) |
| Crash Damage | Less energy = less damage | More voltage = more potential damage |
| **Beginner?** | **Recommended — cheaper, lighter, more forgiving** | Better long-term, steeper learning curve |

### Capacity vs Flight Time (5" quad, ~600-700g AUW)

| Battery | Weight | Freestyle Time | Cruise Time | Sweet Spot? |
|---------|--------|---------------|-------------|-------------|
| 1050mAh 6S | ~165g | 3-4 min | 5-7 min | Racing only |
| 1300mAh 4S | ~185g | 3-5 min | 6-8 min | Good beginner 4S |
| **1300mAh 6S** | ~195g | 4-5 min | 7-9 min | **Freestyle sweet spot** |
| **1500mAh 4S** | ~210g | 4-6 min | 7-9 min | **Best all-around 4S** |
| 1500mAh 6S | ~225g | 5-6 min | 8-10 min | Good all-around 6S |
| 1800mAh 6S | ~270g | 5.5-6.5 min | 9-11 min | Diminishing returns |
| 2200mAh 6S | ~320g | 5.5-6 min | 9-10 min | Too heavy — kills handling |

**The diminishing returns curve:** Every 100g added to AUW requires ~10-15% more hover power. After ~1500mAh on 5", extra capacity adds weight faster than it adds flight time.

### C Rating Reality Check

Advertised C ratings are often exaggerated. Real-world guidance:
- **Budget brands (CNHL, GNB):** Advertise 100C, realistically 40-60C sustained
- **Premium brands (Tattu R-Line):** Advertise 130C, realistically 60-80C sustained
- **For a 5" quad:** You need ~80-120A burst. A 1300mAh pack at "100C" (real 50C) = 65A sustained. This is fine for freestyle; racing might sag.

### Recommended Batteries

| Battery | Config | Weight | Price | Pros | Cons |
|---------|--------|--------|-------|------|------|
| **CNHL Black Series 1300mAh 4S** | 4S/100C | ~185g | $20-25 | Budget workhorse, good punch | Degrades after ~100 cycles |
| **CNHL Black Series 1100mAh 6S** | 6S/100C | ~195g | $25-30 | Cheap 6S entry | Lower capacity |
| **GNB 1500mAh 4S** | 4S/120C | ~210g | $22-28 | Good flight time, decent price | Heavier |
| **CNHL 1500mAh 6S** | 6S/100C | ~240g | $30-38 | Longer flights | Heavy for aggressive flying |
| **Tattu R-Line V4 1300mAh 4S** | 4S/130C | ~175g | $30-35 | Premium cells, better voltage under load | 50% more expensive |
| **Tattu R-Line V4 1050mAh 6S** | 6S/130C | ~180g | $35-40 | Light, punchy, premium | Short flight times |

### Battery Care (Critical for Safety)

- **Storage voltage:** 3.80-3.85V per cell when not flying for >2 days
- **Never discharge below:** 3.5V per cell under load (3.3V absolute minimum)
- **Never charge above:** 4.20V per cell (4.35V for HV packs only)
- **Charge rate:** 1C is safest (1300mAh = 1.3A charge). 2C for speed.
- **Never charge unattended** — LiPo fires are real
- **Use a LiPo bag** for charging and transport
- **Puffed battery = retired battery** — dispose properly at battery recycling

### Beginner Pick: CNHL Black Series 1300mAh 4S (buy 4-6 packs)

- Cheap enough to buy a full rotation set
- Good performance for learning
- When you crash and dent one, you're out $22 not $35
- Upgrade to Tattu or 6S once you're comfortable

---

## 6. Radio System (Transmitter + Receiver)

The radio link is your control connection to the drone. Range, latency, and reliability are critical.

### Protocol Comparison

| Feature | ExpressLRS (ELRS 4.x) | TBS Crossfire | FrSky ACCESS |
|---------|-------------------|---------------|--------------|
| Frequency | 2.4GHz or 900MHz | 900MHz | 2.4GHz |
| Range (2.4GHz) | 10-30+ km | — | 1-2 km |
| EU power cap | 100mW EIRP (2.4GHz) / 868MHz duty-cycled | Same | Same |
| Range (900MHz) | 30-100+ km | 30-40+ km | — |
| Latency | **250us at 1000Hz (best)** | ~4ms | ~9-18ms |
| Refresh Rate | Up to **1000Hz (K1000 mode)** | 150Hz | 50-100Hz |
| Open Source | **Yes** | No (proprietary) | No |
| TX Module Price | $25-40 (or built into radio) | $150-200 | Built into radio |
| RX Price | $10-20 | $50-70 | $20-40 |
| Community | Massive, rapidly growing | Established, loyal | Declining |
| Telemetry | Yes (CRSF protocol) | Yes (CRSF) | Yes |
| **2026 Verdict** | **Clear winner — use this** | Still excellent, expensive | Avoid for new builds |

### Why ExpressLRS Wins in 2026

1. **Lowest latency** — 250us at 1000Hz (K1000 mode, ELRS 4.0+) vs 4ms for Crossfire
2. **Longest range** — 900MHz ELRS at 1W exceeds Crossfire range
3. **Cheapest** — $12 receivers vs $50-70 for Crossfire
4. **Open source** — community-driven updates, no vendor lock-in
5. **Built into modern radios** — no external module needed
6. **ELRS 4.x features** — automatic antenna diversity, adaptive power, direct GPS input on RX; **4.1** adds smarter dynamic power, far fewer false "telemetry lost" callouts, bind phrases settable from the handset Lua script (no WiFi), and GPS time sync to the FC
7. **Massive community** — any problem has a solution online

**Note:** **ELRS 4.1.0 (July 2026) is the current stable release.** It is compatible with all hardware already running any 4.x version — upgrading 4.0 → 4.1 is routine, with no repeat of the 3.x → 4.x break. ELRS 4.0 remains NOT backward-compatible with 3.x: both TX and RX must be on 4.x to talk to each other. All current RadioMaster/HappyModel/BetaFPV hardware is ESP-based and fully supported.

**On the horizon:** ELRS 4.1 lays the groundwork for Semtech's LR2021 (4th-gen LoRa) — the first chip to handle LoRa, FLRC and FSK on both 2.4GHz and 900MHz. Full support is still landing, so there is nothing to buy yet, but expect dual-band receivers to get simpler over the next year.

### Radio Transmitters (TX)

| Radio | Style | ELRS Built-in | Gimbals | Price | Pros | Cons |
|-------|-------|---------------|---------|-------|------|------|
| **BetaFPV LiteRadio 3 Pro** | Gamepad | Yes | Potentiometer | $45-55 | Cheapest entry | Budget gimbals, small |
| **RadioMaster Pocket** | Compact | Yes | Hall sensor | $60-80 | Great value, portable, good gimbals | Small for large hands |
| **RadioMaster Zorro** | Gamepad | Yes | Hall sensor | $90-110 | Ergonomic, hall gimbals, EdgeTX | Mid-price |
| **RadioMaster TX16S MK3** | Full-size | Yes (Gemini dual-band) | Hall sensor (AG optional) | $150-200 | **Current flagship** — H7 CPU, 5" screen, dual-band Gemini ELRS, same price as MKII | Large, heavy |
| **RadioMaster TX16S MKII** | Full-size | Yes (ELRS version) | Hall sensor (AG optional) | $150-200 | Previous gen — still excellent, often discounted | Superseded by MK3 |
| **RadioMaster MT12** | Pistol grip | Yes | — | $70-90 | Unique form factor | Unusual ergonomics |

### Receivers (RX)

| Receiver | Frequency | Price | Pros | Cons |
|----------|-----------|-------|------|------|
| **HappyModel EP1** | 2.4GHz | $12-16 | Cheap ELRS RX, external dipole antenna | Tiny, basic build quality |
| **HappyModel EP2** | 2.4GHz | $10-15 | Cheapest, ultra-light (0.44g) | **Onboard antenna only — short range** |
| **BetaFPV SuperD** | 2.4GHz | $12-18 | Diversity antenna, reliable | Slightly bigger |
| **RadioMaster RP1 V2** | 2.4GHz | $15-18 | External dipole antenna, clean mount | Single antenna |
| **RadioMaster RP3 V2** | 2.4GHz | $18-22 | True antenna diversity, T-antenna | Slightly more expensive |
| **HappyModel ES900RX** | 900MHz | $18-25 | Long range (900MHz) | Larger, needs 900MHz TX |
| **BetaFPV Nano 900** | 900MHz | $20-28 | Small 900MHz | Need 900MHz TX module |

### Beginner Pick: RadioMaster Pocket ELRS + RadioMaster RP3 V2

- Radio: $65 — hall sensor gimbals, built-in ELRS, EdgeTX firmware
- Receiver: $20 — true antenna diversity (2x external T-antennas) for reliable link in any orientation
- **Total: $85** for a control link that exceeds 10km range and resists signal dropouts on a 5" quad
- Can upgrade to the TX16S MK3 later if you want a bigger radio (same protocol). The MK3 (Jan 2026) is the current flagship: H7 processor, 5" screen and dual-band Gemini ELRS at the MKII's old price. Gemini Xrossband transmits on 2.4GHz and 900MHz simultaneously, but only if you also fit a Gemini-capable receiver
- Avoid the EP2 on a 5" build — its onboard ceramic antenna sacrifices ~30-50% of range vs. RXs with external antennas, and the size/weight savings don't matter on a 5"

---

## 7. FPV Video System

The video system is what you see through while flying. This is the biggest cost decision in the build.

### System Comparison

| Feature | Analog | **DJI O4** | DJI O3 (prev gen) | HDZero | Walksnail Avatar |
|---------|--------|-----------|-------------------|--------|-----------------|
| Latency | **~10ms (best)** | 25-38ms | 28-40ms | **~15ms** | 22-35ms |
| Resolution | 480-720p (noisy) | 1080p/100fps | 1080p/100fps | 720p/90fps | 1080p/60fps |
| Range (hardware) | 1-3 km | **10-13 km** | 8-13 km | 3-5 km | 5-8 km |
| **Range (EU, CE mode)** | **200-500m** at 25mW | **~6 km** — same 25mW on 5.8GHz; wins on link budget + 5.1GHz | CE-limited | CE-limited, no published figure | CE-limited, no published figure |
| VTX Weight | 3-8g | ~35g | ~36g | ~25g | ~30g |
| VTX Price | $15-30 | $100-130 | $80-100 (discounted) | $80-100 | $70-90 |
| Goggle Price | $50-150 | $250-350 (Goggles 2/3) | $230-300 (Goggles 2) | $350-530 | $280-400 |
| **Total System** | **$80-180** | **$380-500** | **$320-420** | **$450-630** | **$370-490** |
| Onboard Recording | No (external DVR) | **4K onboard** | 4K onboard | No (external DVR) | 1080p onboard |
| Ecosystem | Open (any brand) | Closed (DJI only) | Closed (DJI only) | Open (multiple VRX) | Semi-open |

### Decision Matrix

| If you want... | Choose | Why |
|----------------|--------|-----|
| Cheapest entry to learn | **Analog** | $80-150 total, upgrade later |
| Best image + recording | **DJI O4** | 4K onboard recording, best range, current gen |
| Good digital on a budget | **DJI O3 (discounted)** | Previous gen, still excellent, cheaper now |
| Lowest latency digital | **HDZero** | 15ms, closest to analog feel |
| Best value digital | **Walksnail** | Cheaper than DJI, good image |
| Widest VTX choice | **Walksnail** | 1S Lite (7g) through full Pro kit (35g, dual antenna) — fits any airframe |
| Maximum range | **DJI O4** | 10-13 km hardware; ~6 km in CE mode at the same 25mW everyone gets on 5.8GHz — its link budget and 5.1GHz band do the work |
| Open ecosystem | **HDZero** | No vendor lock-in |

### Analog Components

| Component | Recommended | Price | Notes |
|-----------|-------------|-------|-------|
| VTX | TBS Unify Pro32 Nano V1.1 | $35-38 | Switchable — run at 25mW on a legal channel; SmartAudio; 20x20; **u.FL antenna**; **5V input only (4.5–5.5V)** — power from the FC's 5V pad, never VBAT or 9V |
| VTX (budget) | SpeedyBee TX800 | $18-22 | 800mW rated — see the power note below |
| ~~VTX~~ | ~~Rush Tank Ultimate Plus (1.6W)~~ | — | ⚠️ **No EU stock (Sept 2026)** — AliExpress only |
| Camera | Foxeer Razer Mini | $18-22 | Good low-light, sharp image |
| Camera (upgrade) | Caddx Ratel 2 | $25-35 | Excellent dynamic range |
| Goggles (box) | Eachine EV800D | $60-80 | Diversity receiver, DVR built-in |
| Goggles (compact) | Skyzone Cobra X V2 | $160-200 | OLED, compact, good optics |

> **⚠️ 5.8GHz power is capped at 25mW e.i.r.p. in the EU — including Denmark — and only inside 5725–5875 MHz.** That is the licence-free limit (ERC Rec 70-03 Annex 1), and it is why every analog VTX sold by an EU shop is listed as 25mW. An amateur licence is not the workaround it sounds like — the amateur 6 cm allocation (5650–5850 MHz) excludes most FPV channels, and running bought FPV gear above 25mW on the rest is a question for the Danish authority, not a given. The 800mW and 1.6W figures elsewhere in this guide describe what the hardware *can* emit, not what you may legally transmit here. Select 25mW **and** a channel inside the band — R3–R6, A2–A7, B1–B7 or F1–F6; Raceband R1/R2/R7/R8 and Bands E and L are outside it. Full table in [REGULATIONS.md](./REGULATIONS.md).
>
> This also caps realistic analog video range well below the figures in [DISTANCE-RANGE.md](./DISTANCE-RANGE.md) and [TRADE-OFFS.md](./TRADE-OFFS.md), which are written for the hardware's maximum output.

### Digital Systems

| System | VTX + Camera | Goggles | Total | Notes |
|--------|-------------|---------|-------|-------|
| **DJI O4 Air Unit** | $100-130 | $250-350 (Goggles 2/3) | $380-500 | Current gen, best overall, locked ecosystem |
| **DJI O3 Air Unit** | $80-100 | $230-300 (Goggles 2) | $320-420 | Previous gen, discounted, still excellent |
| **HDZero Freestyle** | $80-100 | $350-530 (Goggles) | $450-630 | Best latency, most expensive |
| **Walksnail Avatar HD** | $70-90 | $280-400 (Goggles X) | $370-490 | Good balance of price/quality |
| **Walksnail Avatar HD Pro** | $90-120 | $280-400 (Goggles X) | $390-520 | **New** — 1080p/100fps feed, onboard 4K/60 recording, 22-28ms |

### The Field Widened in 2026

The three-way DJI / HDZero / Walksnail split is now a five-way one. Two additions worth knowing about before you commit:

- **Walksnail Avatar HD Pro** — the meaningful spec bump: 1080p/100fps to the goggles with 4K/60 recorded onboard, 22-28ms depending on mode. Walksnail also spent 2025-26 fixing its weak spot, firmware stability, and now has the widest VTX range of any system (7g 1S kits up to 35g dual-antenna Pro kits).
- **OpenIPC and Ascent** — both now appear routinely in 2026 system comparisons alongside the big three. OpenIPC in particular is the open-source option for people who dislike every vendor's lock-in.

**Caveat:** the OpenIPC and Ascent entries here come from 2026 buyer-guide roundups, not from hands-on testing or primary vendor documentation. Treat them as "worth researching", not as a recommendation. Everything else in this section is unchanged and still accurate.

**Unchanged:** DJI O4 remains current-generation — there is no O5. DJI's own O4 Air Unit release notes were still being updated in March 2026. The O4/O3 guidance below stands.

### Beginner Strategy

**Option A — Budget start:** Buy analog ($80-120), learn to fly, upgrade to digital later. You'll crash a lot learning; analog VTX weighs nothing and costs nothing to replace.

**Option B — Invest once:** Buy DJI Goggles 2 + O4 Air Unit ($380-500). Better experience from day 1, goggles work across all future builds. The premium is worth it if you know you'll stick with the hobby.

**Option C — Value digital:** Buy DJI O3 (now discounted as previous gen) + Goggles 2 ($320-420). Nearly as good as O4 for less money.

---

## 8. Propellers

Props are the cheapest, most frequently replaced component. They directly control thrust, efficiency, and noise.

### Blade Count

| Blades | Thrust | Efficiency | Noise | Responsiveness | Best For |
|--------|--------|-----------|-------|----------------|----------|
| **Bi-blade (2)** | Lower | **Best** | Quietest | Moderate | Long range, efficiency |
| **Tri-blade (3)** | **Good** | Good | Moderate | **Best** | **Freestyle (90% of pilots)** |
| **Quad-blade (4)** | Maximum | Poor | Loud | Very high | Cinematic, heavy rigs |

### Pitch Explained

Pitch = how far forward the prop moves in one revolution (in inches). Higher pitch = more aggressive.

| Pitch | Character | Example Prop | Use Case |
|-------|-----------|-------------|----------|
| 3.0-3.8" | Mild, smooth, efficient | 5030, 5035 | Long range, cruising |
| **4.0-4.5"** | Balanced, responsive | **5040, 5043** | **All-around** |
| 4.5-5.1" | Aggressive, fast, current-hungry | 5045, 5051 | Racing, punch-outs |

### Reading Prop Names

There are two common naming conventions:

**Convention 1 — Combined number (e.g., "51466"):**
- **5** = 5 inch diameter
- **14** = design series identifier
- **66** = variant/revision number
- The pitch is NOT directly encoded — check the spec sheet

**Convention 2 — Explicit notation (e.g., "5x4.3x3"):**
- **5** = diameter in inches
- **4.3** = pitch in inches
- **3** = number of blades
- This is the clearest notation — always check this when comparing

**Example:** Gemfan 51466 V2 = a 5.1" diameter, 4.6" pitch, 3-blade prop. The "51466" is Gemfan's product code; the actual specs are on the packaging.

### Material

| Material | Stiffness | Durability | Efficiency | Price |
|----------|-----------|-----------|-----------|-------|
| Polycarbonate (PC) | Flexible | **Best** (bends, doesn't break) | Lower | Cheapest |
| **PC + Glass Fiber** | Good | Good | **Good** | Standard |
| PC + Carbon Fiber | High | Moderate (shatters) | Best | Expensive |

### Recommended Props

| Prop | Blades | Pitch | Price (10 sets) | Pros | Cons |
|------|--------|-------|-----------------|------|------|
| **Gemfan 51466 V2** | 3 | 4.6" | $20-25 | Gold standard freestyle, great grip | Slightly power-hungry |
| **HQProp 5x4.3x3 V2S** | 3 | 4.3" | $20-25 | Smooth, efficient, great all-around | Less aggressive |
| **Ethix S5 (5x4x3)** | 3 | 4.0" | $25-30 | Smooth, great for freestyle | Premium price |
| **Gemfan Hurricane 5136** | 3 | 3.6" | $18-22 | Light, efficient, smooth | Less punch |
| ~~**DAL Cyclone T5040C**~~ | 3 | 4.0" | — | Was the budget pick | ⚠️ **No EU stock (Sept 2026)** — AliExpress only |
| **Gemfan 5125** | 2 | 2.5" | $15-20 | Long range, maximum efficiency | Low thrust |
| **HQProp 5x4.5** | 2 | 4.5" | $18-22 | Racing bi-blade, fast | Inefficient |

> **⚠️ Availability note (September 2026):** the DAL Cyclone T5040C is no longer stocked by any EU FPV shop checked (Rotorama, FlyingMachines, CopterFarm, FPV24) — it remains available on AliExpress. **Gemfan 51466 V2 is the substitute** used throughout this guide: verified in stock at FPV24 (sold as *Gemfan Hurricane MCK 51466-3*) and on Amazon.de shipping to Denmark.

### Beginner Pick: Gemfan 51466 V2

- Buy 20+ sets (you'll go through them)
- Great all-around performance
- Available everywhere
- ~$2 per set — truly disposable

### Prop Direction (Critical!)

- Motors spin in alternating directions (CW and CCW)
- Props must match their motor direction
- Incorrect prop direction = instant flip on takeoff
- Mark your CW and CCW motors before mounting props

---

## Component Interaction Summary

| Component | Affects |
|-----------|---------|
| Frame weight | Flight time, handling, crash resistance |
| Motor KV | Speed, efficiency, battery compatibility |
| Battery voltage (S) | Motor KV choice, weight, efficiency |
| Battery capacity (mAh) | Flight time, weight, handling |
| ESC amps | Motor compatibility, reliability headroom |
| Prop pitch | Thrust, current draw, noise, response |
| Prop blades | Thrust vs efficiency trade-off |
| Radio system | Maximum safe range |
| VTX power | Video range (usually the limiting factor) |
