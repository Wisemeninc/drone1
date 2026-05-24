# Soldering Guide for Drone Builds

Everything you need to know about soldering your own FPV drone — tools, materials, techniques, and joint-specific tips.

---

## Essential Soldering Kit

### Soldering Iron

| Iron | Type | Wattage | Heat-up | Price | Pros | Cons |
|------|------|---------|---------|-------|------|------|
| **Pinecil V2** | Portable | 65-100W (with PD) | 6 seconds | $26 + $25 PD adapter | USB-C powered, portable, open firmware, field repairs | Needs 65W+ power supply, small tip selection |
| **FNIRSI HS-02** | Portable | 90W | 8 seconds | $35-45 | Good alternative to Pinecil, built-in display | Newer brand |
| **TS100/TS101** | Portable | 65W | 10 seconds | $50-70 | Well-established, huge tip library, barrel jack | No USB-C native (TS100), pricier |
| **Hakko FX-888D** | Station | 70W | 15 seconds | $105-120 | Rock-solid temp control, massive tip library, lasts forever | Not portable, overkill for occasional use |

**Recommendation:** [Pinecil V2](https://eleshop.eu/pinecil-smart-mini-portable-soldering-iron.html) — best value, portable for field repairs, heats in 6 seconds.

**Recommended tip upgrade:** [Pinecil Short Tip Set (fine)](https://eleshop.eu/pinecil-short-soldering-tip-set-fine.html) — includes ST-BC2 (2.1mm bevel, ideal for FC pads), ST-C1 (1mm conical for detail), ST-ILS (ultra-fine), and ST-KU (knife for drag soldering). Shorter tips = more precise + faster heat-up than stock.

### Soldering Iron Tips

| Tip Type | When to Use | Drone Application |
|----------|-------------|-------------------|
| **Chisel (D24, 2-3mm)** | General purpose, most drone pads | ESC pads, motor wires, battery XT60 |
| **Conical/Fine** | Tiny pads, precision work | VTX pads, receiver pads, signal wires |
| **Knife/Hoof** | Drag soldering | Not common in drone builds |

**Buy at minimum:** One 2mm chisel tip (primary) and one fine conical tip (for receiver/VTX work).

### Solder Wire

| Type | Melting Point | Behavior | Recommendation |
|------|-------------|----------|----------------|
| **63/37 Leaded (Eutectic)** | 183°C (single point) | Transitions instantly from liquid to solid — **fewest cold joints** | **Best for beginners** |
| **60/40 Leaded** | 183-190°C (range) | Slightly pasty stage, marginally more forgiving | Also fine |
| **Lead-free (SAC305)** | 217°C+ | Higher temps, worse wetting, more cold joints | Avoid for hobby |

**Wire gauge:**
- **0.8mm (0.031")** — Standard for most drone pads (ESC, motor, battery)
- **0.5mm (0.020")** — Fine work (VTX pads, receiver, camera)
- **1.0mm (0.040")** — Large joints only (XT60 connector cups)

**Brand recommendations:** Kester 44 (63/37, rosin core) or MG Chemicals 4900 (63/37, 0.8mm)

### Flux

| Type | When to Use | Recommended Product |
|------|-------------|---------------------|
| **Rosin paste (no-clean)** | Pre-tinning pads, reflowing old joints | Amtech NC-559-V2 ($8-12) |
| **Flux pen** | Quick touch-up, convenient | Kester 951 or MG Chemicals 835 ($8-10) |
| **Rosin core (in solder)** | Built into the solder wire | Already there if you buy rosin-core |

**Key insight:** Flux is the single biggest difference between frustrating soldering and easy soldering. Use it liberally.

### Essential Accessories

| Item | Purpose | Price | Notes |
|------|---------|-------|-------|
| **Solder wick (2.5mm)** | Remove excess solder, fix bridges | $4-6 | Chemtronics brand recommended |
| **Brass wool tip cleaner** | Clean tip without cooling it | $5-8 | Better than wet sponge |
| **Helping hands / PCB holder** | Hold boards and wires steady | $15-30 | Get one with heavy base or magnetic |
| **Silicone soldering mat** | Protect desk, heat-resistant, organize parts | $10-15 | Get one with compartments |
| **Kapton tape** | Mask adjacent pads, insulate | $5 | Essential for tight PCB work |
| **Isopropyl alcohol 99%** | Clean flux residue after soldering | $5 | Use with brush or cotton swab |
| **Wire strippers (30-20 AWG)** | Strip silicone motor/signal wires | $8-15 | Adjustable type recommended |
| **Flush cutters** | Trim wire ends, cut zip ties | $5-10 | Get a pair just for electronics |
| **Multimeter** | Verify connections, check shorts | $15-30 | Essential for debugging |
| **Smoke stopper** | Limit current on first power-up | $10-15 (or DIY with bulb) | Prevents magic smoke |

### Total Soldering Kit Cost

| Tier | Contents | Total |
|------|----------|-------|
| **Minimum** | Pinecil + solder + flux + wick + brass cleaner | ~$55 |
| **Comfortable** | Above + helping hands + mat + kapton + IPA + strippers | ~$95 |
| **Full setup** | Above + multimeter + smoke stopper + extra tips | ~$130 |

---

## Soldering Temperature Guide

| Joint Type | Temperature | Time Limit | Notes |
|------------|-------------|-----------|-------|
| Pre-tinning wire tips | 350°C | No limit | Tin all wires before assembly |
| Pre-tinning PCB pads | 360°C | 2-3 sec | Add small dome of solder to each pad |
| Motor wires to ESC | 370°C | 3-4 sec | Thick wire needs heat, but ESC pads are fragile |
| Signal wires (RX, VTX) | 340-350°C | 2 sec max | Tiny pads lift easily — be quick |
| XT60 battery connector | 380-400°C | 4-5 sec | Large thermal mass, needs patience |
| Capacitor (low ESR) | 350°C | 2-3 sec | Solder across battery pads |

**General rule:** Higher temp = shorter time. It's better to use 380°C for 2 seconds than 320°C for 8 seconds (the long dwell time lifts pads).

---

## Drone-Specific Soldering Joints

### Build Order for Soldering

Solder in this order (easiest to hardest, biggest pads first):

1. **Battery XT60 connector** → ESC battery pads (biggest pads, most forgiving)
2. **Low-ESR capacitor** → across battery pads (prevents voltage spikes)
3. **Motor wires** → ESC motor pads (4 motors × 3 wires = 12 joints)
4. **ESC signal ribbon** → FC (if not a stack with pin headers)
5. **Receiver** → FC UART pads (small pads, 4-5 wires)
6. **VTX** → FC video/power pads (small pads, 4-5 wires)
7. **Camera** → VTX or FC (easiest last joints — low current, forgiving)

### Joint-by-Joint Guide

#### Battery Lead (XT60 to ESC)

```
Difficulty: ★★★☆☆ (hard due to thermal mass, but pads are large)
Wire gauge: 12-14 AWG (thick!)
Temp: 380-400°C
Tip: Large chisel (3mm+)
```

**Steps:**
1. Tin the XT60 connector cups — fill each cup ~60% with solder
2. Tin the ESC battery pads — add generous dome
3. Tin wire ends (~5mm of exposed wire)
4. Hold wire against pad, press iron on wire AND pad simultaneously
5. Wait for solder to flow together (3-4 seconds)
6. Remove iron, hold still until solid

**Common mistakes:**
- Not enough heat (cold joint — wire pulls free)
- Heating too long (PCB delaminates)
- Insufficient tinning (solder won't bridge the gap)

#### Motor Wires (to ESC)

```
Difficulty: ★★☆☆☆ (medium — multiple joints but pads are decent size)
Wire gauge: 18-20 AWG
Temp: 360-370°C
Tip: Chisel (2mm)
```

**Steps:**
1. Strip 3-4mm of silicone insulation from each motor wire
2. Tin each wire end
3. Tin each ESC motor pad
4. Place wire on pad, touch iron to junction, solder flows
5. 2-3 seconds per joint

**Notes:**
- Motor direction is set by any two wires being swapped (or in software with BLHeli_32/Bluejay)
- Label which motor is which before connecting
- Consistent wire routing prevents confusion

#### Receiver (ELRS/Crossfire to FC)

```
Difficulty: ★★★★☆ (small pads, thin wires, easily damaged)
Wire gauge: 26-30 AWG (very thin)
Temp: 340-350°C
Tip: Fine conical or small chisel (1-1.5mm)
```

**Steps:**
1. Identify FC pads: TX, RX, 5V, GND (check FC pinout diagram!)
2. Pre-tin EACH pad with a tiny amount of solder
3. Strip 2mm of insulation from each RX wire
4. Tin wire ends
5. Hold wire to pad with tweezers, touch iron briefly (1-2 sec), solder reflows
6. Wire adheres to pad

**Critical:** 
- Use flux on pre-tinned pads before reflowing
- Do NOT apply pressure — just let heat do the work
- If pad lifts, you can sometimes scrape the trace and solder to it

#### VTX (Video Transmitter to FC)

```
Difficulty: ★★★★☆ (same as receiver — tiny pads)
Wire gauge: 26-28 AWG
Temp: 340-350°C
Tip: Fine conical
```

**Connections needed:**
- 5V or 9V power (check VTX requirements)
- GND
- Video signal (from FC video out pad)
- Smart Audio / IRC Tramp (for OSD power control) — optional but recommended

#### Camera

```
Difficulty: ★☆☆☆☆ (easy — only 3 wires, forgiving)
Wire gauge: 26-28 AWG
Temp: 340°C
Tip: Any
```

**Connections:** 5V, GND, Video Signal. Hardest to mess up.

---

## Technique Reference

### The Perfect Solder Joint

```
GOOD joint:              BAD joint (cold):       BAD joint (too much):
   _____                    _____                    _____ 
  / wire \                 / wire \                 / wire \
 /________\               |________|               (________) 
 |  pad   |               |  pad   |               |  pad   |
 
 - Shiny                  - Dull/grainy            - Blobby
 - Concave fillet         - Round/balled           - Overflow to adjacent
 - Wets both surfaces     - Sits on top            - Risk of bridges
```

### Pre-Tinning (Do This for Every Joint)

**Why:** Pre-tinning both surfaces means when you join them, you only need to reflow — not feed new solder. This cuts joint time from 5 seconds to 2 seconds, dramatically reducing pad-lift risk.

**How to pre-tin a pad:**
1. Apply flux to the bare pad
2. Touch iron to pad (1 second to heat)
3. Feed solder into the junction of iron tip and pad
4. Remove iron — pad now has a dome of solder
5. Repeat for all pads

**How to pre-tin a wire:**
1. Strip insulation (3-5mm depending on joint)
2. Hold iron against bare wire
3. Feed solder until wire absorbs it (wicks into strands)
4. Wire is now silver/shiny instead of copper

### The Reflow Technique (Joining Pre-Tinned Surfaces)

1. Both surfaces already have solder on them
2. Apply a touch of flux to the pad (helps old solder reflow)
3. Hold wire against pad (use tweezers or helping hands)
4. Touch iron to the wire (on top of the joint)
5. Solder melts on both surfaces and flows together (1-2 seconds)
6. Remove iron, hold steady until solid

### Fixing Mistakes

| Problem | Fix |
|---------|-----|
| **Solder bridge** (two pads connected) | Drag solder wick across bridge with flux + heat |
| **Cold joint** (dull, grainy) | Add flux, reflow with iron for 2 seconds |
| **Too much solder** (blob) | Solder wick to remove excess, then reflow |
| **Lifted pad** (copper peeled from PCB) | Scrape trace, solder directly to trace. Or use bodge wire to next via. |
| **Wire won't tin** (solder rolls off) | Apply flux, try again. Wire may have enamel coating — sand lightly first. |

---

## Common Beginner Mistakes

1. **Not using flux** — This is the #1 cause of bad joints. Flux cleans oxidation and helps solder flow. Use it on every joint.

2. **Heating too long** — PCB pads are glued to the board with thin adhesive. More than 3-4 seconds of heat and the pad lifts off permanently. Use higher temperature for shorter time.

3. **Heating the solder instead of the pad** — The iron must touch the PAD (and wire), then solder flows into the hot junction. Never melt solder onto the iron tip and try to transfer it.

4. **Oxidized tip** — A black/crusty tip transfers no heat. Keep it tinned (coated in fresh solder) at all times. Clean with brass wool, re-tin immediately.

5. **Moving the joint while cooling** — Causes a "cold joint" (dull crystalline appearance). Hold perfectly still for 2 seconds after removing iron.

6. **Wrong tip size** — Too small a tip on a battery pad means you hold longer (bad). Too large on a signal pad means you bridge adjacent pads (bad). Match tip to joint size.

7. **Insufficient stripping** — Not enough exposed wire means weak mechanical bond. Strip 3-5mm for most joints.

8. **No practice** — Buy a $5-10 practice PCB from Amazon before touching your $70 flight controller. Practice pre-tinning, reflowing, and desoldering.

---

## Safety

- **Work in ventilated area** — Rosin flux fumes irritate lungs. Use a fume extractor fan or work near open window.
- **Wash hands after handling leaded solder** — Don't eat/drink while soldering.
- **Iron is 350°C+** — Will burn instantly. Always return to holder when not in active use.
- **Never leave iron on unattended** — Pinecil/TS100 have auto-sleep; station irons may not.
- **LiPo batteries** — Never solder directly to LiPo cells. Use XT60/XT30 connectors with pre-made pigtails.

---

## Practice Progression

| Stage | Exercise | What You Learn |
|-------|----------|----------------|
| 1 | Tin 20 wire ends | Basic technique |
| 2 | Tin pads on practice PCB | Pad heating, solder flow |
| 3 | Solder wires to practice PCB pads | Reflow joining |
| 4 | Desolder and resolder same joints | Wick technique |
| 5 | Solder XT60 connector (practice lead) | High-thermal-mass joints |
| 6 | **Build your drone** | All skills combined |

**Time to proficiency:** 2-3 hours of practice before your first real build. Watch 2-3 YouTube drone soldering tutorials (Joshua Bardwell, Oscar Liang).
