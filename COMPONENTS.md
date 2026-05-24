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

| Spec | F4 (STM32F405) | F7 (STM32F722) | H7 (STM32H743) |
|------|----------------|----------------|-----------------|
| Clock Speed | 168 MHz | 216 MHz | 480 MHz |
| Flash Storage | 1 MB | 512 KB–1 MB | 2 MB |
| Blackbox Logging | Limited | Good | Excellent (high-rate) |
| PID Loop Rate | 8K max | 8K comfortable | 32K capable |
| UART Count | 3-5 | 4-6 | 6-8 |
| Future-proofing | Being phased out | Good for 2-3 years | Best long-term |
| Price Range | $25-40 | $35-60 | $45-80 |
| Betaflight Support | Being deprecated | Full | Full |
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
| **SpeedyBee F405 V4** | F4 | 6 | $30-35 | Bluetooth config from phone, great docs | F4 being phased out |
| **SpeedyBee F7 V3** | F7 | 6 | $40-50 | WiFi blackbox download, solid | Slightly more expensive |
| **Mamba F722 MK4** | F7 | 5 | $35-45 | Proven reliable, Diatone support | No wireless config |
| **GEPRC Span F722-BT-HD** | F7 | 6 | $45-55 | DJI connector built-in, Bluetooth | Proprietary connectors |
| **Foxeer Reaper F7** | F7 | 6 | $40-50 | Good analog/digital support | Newer, less community testing |

### FC+ESC Stacks (Buy Together)

| Stack | FC + ESC | Price | Pros |
|-------|----------|-------|------|
| **SpeedyBee F405 V4 + 50A** | F4 + BL32 50A | $65-80 | Best beginner deal, guaranteed compatibility |
| **Mamba F722 + F50 Pro** | F7 + BL32 50A | $75-95 | Reliable combo |
| **GEPRC Span + 60A** | F7 + BL32 60A | $90-110 | Good for 6S builds |

### Beginner Pick: SpeedyBee F405 V4 Stack

- FC + ESC matched and guaranteed compatible
- Bluetooth configuration from SpeedyBee phone app
- Well-documented, YouTube build guides available
- One purchase, no compatibility issues

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
| **Mamba F50 Pro** | 50A | BL32 | $40-50 | Reliable, good thermals | Nothing special |
| **T-Motor F55A Pro II** | 55A | BL32 | $55-70 | Premium quality, excellent FETs | Expensive |
| **Aikon AK32 Pin 35A** | 35A | BL32 | $50-60 | Ultra-clean power, racing focused | Only 35A |

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

| Feature | ExpressLRS (ELRS) | TBS Crossfire | FrSky ACCESS |
|---------|-------------------|---------------|--------------|
| Frequency | 2.4GHz or 900MHz | 900MHz | 2.4GHz |
| Range (2.4GHz) | 10-30+ km | — | 1-2 km |
| Range (900MHz) | 30-100+ km | 30-40+ km | — |
| Latency | **250us-500us (best)** | ~4ms | ~9-18ms |
| Refresh Rate | Up to 1000Hz | 150Hz | 50-100Hz |
| Open Source | **Yes** | No (proprietary) | No |
| TX Module Price | $25-40 (or built into radio) | $150-200 | Built into radio |
| RX Price | $10-20 | $50-70 | $20-40 |
| Community | Massive, rapidly growing | Established, loyal | Declining |
| Telemetry | Yes (CRSF protocol) | Yes (CRSF) | Yes |
| **2025 Verdict** | **Clear winner — use this** | Still excellent, expensive | Avoid for new builds |

### Why ExpressLRS Wins in 2025

1. **Lowest latency** — 250us at 500Hz vs 4ms for Crossfire
2. **Longest range** — 900MHz ELRS at 1W exceeds Crossfire range
3. **Cheapest** — $12 receivers vs $50-70 for Crossfire
4. **Open source** — community-driven updates, no vendor lock-in
5. **Built into modern radios** — no external module needed
6. **Massive community** — any problem has a solution online

### Radio Transmitters (TX)

| Radio | Style | ELRS Built-in | Gimbals | Price | Pros | Cons |
|-------|-------|---------------|---------|-------|------|------|
| **BetaFPV LiteRadio 3 Pro** | Gamepad | Yes | Potentiometer | $45-55 | Cheapest entry | Budget gimbals, small |
| **RadioMaster Pocket** | Compact | Yes | Hall sensor | $60-80 | Great value, portable, good gimbals | Small for large hands |
| **RadioMaster Zorro** | Gamepad | Yes | Hall sensor | $90-110 | Ergonomic, hall gimbals, EdgeTX | Mid-price |
| **RadioMaster TX16S MKII** | Full-size | Yes (ELRS version) | Hall sensor (AG optional) | $150-200 | Maximum features, big screen, EdgeTX | Large, heavy |
| **RadioMaster MT12** | Pistol grip | Yes | — | $70-90 | Unique form factor | Unusual ergonomics |

### Receivers (RX)

| Receiver | Frequency | Price | Pros | Cons |
|----------|-----------|-------|------|------|
| **HappyModel EP1/EP2** | 2.4GHz | $10-15 | Cheapest ELRS RX, tiny | Basic antenna |
| **BetaFPV SuperD** | 2.4GHz | $12-18 | Diversity antenna, reliable | Slightly bigger |
| **RadioMaster RP1** | 2.4GHz | $15-18 | Ceramic antenna, clean mount | No external antenna |
| **RadioMaster RP3** | 2.4GHz | $18-22 | Diversity, T-antenna | Slightly expensive |
| **HappyModel ES900RX** | 900MHz | $18-25 | Long range (900MHz) | Larger, needs 900MHz TX |
| **BetaFPV Nano 900** | 900MHz | $20-28 | Small 900MHz | Need 900MHz TX module |

### Beginner Pick: RadioMaster Pocket ELRS + HappyModel EP2

- Radio: $65 — hall sensor gimbals, built-in ELRS, EdgeTX firmware
- Receiver: $12 — tiny, reliable, proven
- **Total: $77** for a control link that exceeds 10km range
- Can upgrade to TX16S later if you want a bigger radio (same protocol)

---

## 7. FPV Video System

The video system is what you see through while flying. This is the biggest cost decision in the build.

### System Comparison

| Feature | Analog | DJI O3 | HDZero | Walksnail Avatar |
|---------|--------|--------|--------|-----------------|
| Latency | **~10ms (best)** | 28-40ms | **~15ms** | 22-35ms |
| Resolution | 480-720p (noisy) | 1080p/100fps | 720p/90fps | 1080p/60fps |
| Range | 1-3 km | 10+ km | 3-5 km | 5-8 km |
| VTX Weight | 3-8g | ~36g | ~25g | ~30g |
| VTX Price | $15-30 | $90-110 | $80-100 | $70-90 |
| Goggle Price | $50-150 | $230-350 | $350-530 | $280-400 |
| **Total System** | **$80-180** | **$350-500** | **$450-630** | **$370-490** |
| Onboard Recording | No (external DVR) | **4K onboard** | No (external DVR) | 1080p onboard |
| Ecosystem | Open (any brand) | Closed (DJI only) | Open (multiple VRX) | Semi-open |
| Penetration | Good (analog handles interference) | Moderate | Moderate | Moderate |

### Decision Matrix

| If you want... | Choose | Why |
|----------------|--------|-----|
| Cheapest entry to learn | **Analog** | $80-150 total, upgrade later |
| Best image + recording | **DJI O3** | 4K onboard recording, best range |
| Lowest latency digital | **HDZero** | 15ms, closest to analog feel |
| Best value digital | **Walksnail** | Cheaper than DJI, good image |
| Maximum range | **DJI O3** | 10+ km reliable link |
| Open ecosystem | **HDZero** | No vendor lock-in |

### Analog Components

| Component | Recommended | Price | Notes |
|-----------|-------------|-------|-------|
| VTX | Rush Tank Ultimate Plus | $30-40 | 1.6W output, smart audio |
| VTX (budget) | SpeedyBee TX800 | $18-22 | 800mW, good enough to start |
| Camera | Foxeer Razer Mini | $18-22 | Good low-light, sharp image |
| Camera (upgrade) | Caddx Ratel 2 | $25-35 | Excellent dynamic range |
| Goggles (box) | Eachine EV800D | $60-80 | Diversity receiver, DVR built-in |
| Goggles (compact) | Skyzone Cobra X V2 | $160-200 | OLED, compact, good optics |

### Digital Systems

| System | VTX + Camera | Goggles | Total | Notes |
|--------|-------------|---------|-------|-------|
| **DJI O3 Air Unit** | $90-110 | $230-350 (Goggles 2/3) | $350-500 | Best overall, locked ecosystem |
| **HDZero Freestyle** | $80-100 | $350-530 (Goggles) | $450-630 | Best latency, most expensive |
| **Walksnail Avatar HD** | $70-90 | $280-400 (Goggles X) | $370-490 | Good balance of price/quality |

### Beginner Strategy

**Option A — Budget start:** Buy analog ($80-120), learn to fly, upgrade to digital later. You'll crash a lot learning; analog VTX weighs nothing and costs nothing to replace.

**Option B — Invest once:** Buy DJI Goggles 2 + O3 Air Unit ($400-500). Better experience from day 1, goggles work across all future builds. The premium is worth it if you know you'll stick with the hobby.

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

### Reading Prop Names: 51466

- **51** = 5.1 inch diameter
- **4** = 4.0 inch pitch (some use 46 = 4.6 pitch)
- **6** = number of blades... wait no. Actually:
  - **5** = diameter (5 inches)
  - **14** = pitch (but read as 4.0-4.6 depending on brand notation)
  - **66** = blade design identifier

More commonly: **5x4.3x3** = 5" diameter, 4.3" pitch, 3 blades. This is the clearest notation.

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
| **DAL Cyclone T5040C** | 3 | 4.0" | $15-20 | Budget, very durable | Slightly heavy |
| **Gemfan 5125** | 2 | 2.5" | $15-20 | Long range, maximum efficiency | Low thrust |
| **HQProp 5x4.5** | 2 | 4.5" | $18-22 | Racing bi-blade, fast | Inefficient |

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
