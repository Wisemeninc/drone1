# YouTube Video Resources — FPV Drone Build Learning Path

Curated videos covering every phase of your first 5" quad build — plus tiny whoops, 7" long range, fixed-wing, BVLOS concepts, repair, batteries, GPS rescue, antennas, goggles, EU regs, and cinematography. Organized by skill progression — work through top to bottom.

> **Channels to subscribe to:** Joshua Bardwell, Mr Steele, Le Drib, Rotor Riot, BotGrinder, Painless360, Mads Tech, Chris Rosser, Oscar Liang, UAVfutures, Drone Camps, CurryKitten, Mr.D - Falling with style, rctestflight, FliteTest, Pawel Spychalski (iNav developer)

---

## Contents

1. [Soldering Skills](#1-soldering-skills)
2. [Simulator Practice](#2-simulator-practice-buy-radio-first-fly-this)
3. [The Build (Assembly & Wiring)](#3-the-build-assembly--wiring)
4. [ExpressLRS Setup](#4-expresslrs-setup)
5. [FPV Video System Setup](#5-fpv-video-system-setup)
6. [Betaflight & Firmware Configuration](#6-betaflight--firmware-configuration)
7. [First Real Flight](#7-first-real-flight-after-sim--build)
8. [Inspiration — What You're Working Toward](#8-inspiration--what-youre-working-toward)
9. [iNav — GPS Navigation & Autonomous Flight](#9-inav--gps-navigation--autonomous-flight)
10. [Ardupilot — Advanced Autonomous & Commercial](#10-ardupilot--advanced-autonomous--commercial)
11. [Tiny Whoop & Indoor Practice](#11-tiny-whoop--indoor-practice)
12. [7-Inch & Long Range Builds](#12-7-inch--long-range-builds)
13. [Fixed-Wing FPV & VTOL](#13-fixed-wing-fpv--vtol)
14. [BVLOS, Mesh Radio & Relay Concepts](#14-bvlos-mesh-radio--relay-concepts)
15. [EU / Denmark Drone Regulations](#15-eu--denmark-drone-regulations)
16. [Crash Recovery, Repair & Motor Swap](#16-crash-recovery-repair--motor-swap)
17. [LiPo Battery Safety & Charging](#17-lipo-battery-safety--charging)
18. [GPS Rescue & Failsafe](#18-gps-rescue--failsafe)
19. [Antennas — Theory, Repair & Placement](#19-antennas--theory-repair--placement)
20. [Goggles Deep Dive](#20-goggles-deep-dive)
21. [Cinematography Techniques](#21-cinematography-techniques)
22. [Suggested Learning Order](#suggested-learning-order)

---

## 1. Soldering Skills

Master soldering BEFORE your parts arrive. Practice on old electronics or a $5 practice board from Amazon.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Most FPV pilots need to watch this soldering tutorial](https://www.youtube.com/watch?v=GoPT69y98pY) | Joshua Bardwell | **The definitive FPV soldering reference** — iron selection, solder choice, flux, tip styles, and technique in one video |
| 2 | [How to solder a flight controller for beginners](https://www.youtube.com/watch?v=F-22UZ2zD10) | Painless360 | Step-by-step FC pad soldering — exactly what you'll do on your first build |
| 3 | [How TO Perfect Solder Joint — FPV Drone Pro Tips & Tricks](https://www.youtube.com/watch?v=HTy9Z9LpA2U) | Mr Steele | Quick pro-level tips from a top pilot — great after you've practiced basics |
| 4 | [LEARN HOW TO SOLDER IN 10 MINUTES! EASY BEGINNERS GUIDE for drones](https://www.youtube.com/watch?v=XPV3aIoGNsk) | UAVfutures | Stew's energetic 10-min primer — perfect "zero to confident" companion to Bardwell |
| 5 | [Beginners guide to quadcopter soldering. What you need to know.](https://www.youtube.com/watch?v=lseZwkkQ070) | UAVfutures | Quad-specific soldering (XT60, motors, capacitors) — fills the gap between general technique and FC pads |

**Start with #1 (Bardwell) — it's comprehensive.** Then #4 for a quick refresher, #2 right before you solder your FC.

---

## 2. Simulator Practice (Buy Radio First, Fly This)

Buy your radio and fly a simulator 10-20 hours BEFORE building. This saves hundreds in crash damage.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Best PC FPV Simulator — WE TRIED THEM ALL](https://www.youtube.com/watch?v=I7lUTEJM62g) | Joshua Bardwell | Comparison of all major sims — helps you pick between Velocidrone, Liftoff, etc. |
| 2 | [How To FPV? (Part 2) Controller and Sim Setup — START Flying!](https://www.youtube.com/watch?v=dOwW6PFZU3Y) | Mr Steele | Connect your RadioMaster to PC and configure the sim — practical setup guide |
| 3 | [Learn To Fly FPV In Under 24 Hours!](https://www.youtube.com/watch?v=Ou5i9zdyqn0) | Rotor Riot | Structured progression plan — what to learn first and time goals |
| 4 | [Learn to fly an FPV drone TODAY (for total beginners)](https://www.youtube.com/watch?v=SpuXqNakP2A) | Joshua Bardwell | Complete beginner roadmap from purchase to flight |
| 5 | [How To Fly ACRO Mode! Beginner Tutorial](https://www.youtube.com/watch?v=bAkfiphJFrU) | Magic FPV | Dedicated acro tutorial — stick inputs, orientation, practice drills |

**Learning order:** Watch #1 to pick your sim, #2 to connect your radio, then #3 or #4 for learning structure. When you're comfortable hovering, watch #5 for acro.

---

## 3. The Build (Assembly & Wiring)

Watch these BEFORE you build. Then re-watch each section as you do it.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [How to Build a 5-Inch FPV Drone — Step-by-Step (For Beginners)](https://www.youtube.com/watch?v=S9dvDU5RmQU) | Joshua Bardwell | **Full build start-to-finish** with modern 2024 components (ELRS, DJI O3, F7 FC) — the single best build video |
| 2 | [My Perfect AOS 5.5 Build](https://www.youtube.com/watch?v=pKWRXOFKLmE) | Chris Rosser | Premium build with component selection reasoning — watch for "why" behind choices |
| 3 | [Build a FPV Drone with NO SOLDERING! (Plug & Play DIY Kwad)](https://www.youtube.com/watch?v=9_m5FVllnVg) | Rotor Riot | Frame assembly and mechanical layout — great for understanding component placement |
| 4 | [2022 Freestyle FPV Drone Build - Configuration and Setup](https://www.youtube.com/watch?v=5ke6LabvtGM) | Joshua Bardwell | Post-build software configuration — ports, receiver, motor direction, PID, OSD |
| 5 | [Build a PRO FPV Racing Drone for ONLY $99 Full guide - 2018 UAVFUTURES $99 Build](https://www.youtube.com/watch?v=3YyNut36HO0) | UAVfutures | The legendary budget build that got thousands into the hobby — proves you don't need premium parts |
| 6 | [Build: CL1 Build (with Le Drib)](https://www.youtube.com/watch?v=MPAoH3ukLWU) | Rotor Riot | Watch a top pilot's premium build choices alongside Rotor Riot pros |

**Watch #1 all the way through before starting.** Keep it open on your phone/laptop as you build.

---

## 4. ExpressLRS Setup

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [ExpressLRS definitive getting started guide](https://www.youtube.com/watch?v=J3Hg2f7RL1A) | Joshua Bardwell | Complete ELRS concepts, flashing TX/RX, binding, and Betaflight integration |
| 2 | [ExpressLRS Setup & Programming — Radiomaster USB UART](https://www.youtube.com/watch?v=1j8KprJAttQ) | Mads Tech | Hands-on flashing and programming ELRS receivers with USB UART |
| 3 | [ELRS Complete Beginner Guide 2025](https://www.youtube.com/watch?v=N0ajKoef3qs) | Joshua Bardwell | The updated 2025 ELRS walkthrough — supersedes older versions |
| 4 | [ExpressLRS 4.0 \| WHAT'S NEW / WHAT'S DIFFERENT](https://www.youtube.com/watch?v=za-_4OX8QJY) | Joshua Bardwell | Required if your TX/RX is on ELRS 4.0 — covers new features and migration |

**Written guide (better for step-by-step):** [Oscar Liang — How to Bind ExpressLRS Receivers](https://oscarliang.com/bind-expresslrs-receivers/) — covers all 6 binding methods.

---

## 5. FPV Video System Setup

### Choosing your video system

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Best FPV Goggle 2023 Buyer's Guide // DJI v. HDZERO v. WALKSNAIL v. ANALOG](https://www.youtube.com/watch?v=TMOeIQ4VRX4) | Joshua Bardwell | The canonical framework for picking your FPV system — saves hundreds in wrong purchases |

### DJI Digital

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Build an FPV Drone — Part 5 — DJI O3 Video Transmitter](https://www.youtube.com/watch?v=kinmxuOnoUM) | Joshua Bardwell | DJI O3 Air Unit wiring, OSD config, and activation (process similar for O4) |
| 2 | [DJI O4 Air Unit — The Dawn of a New Era?](https://www.youtube.com/watch?v=1SlN-tFDnN4) | Albert Kim | DJI O4 unboxing, setup, and performance comparison to O3 |
| 3 | [DJI FPV Remote V3 & DJI O4 & O4 Pro — A Complete Overview & Setup Guide](https://www.youtube.com/watch?v=lG5Gz4M2cog) | Mads Tech | The most thorough O4/O4 Pro deep dive — remote, air unit, ecosystem integration |
| 4 | [Sub250g FPV Drone Build - 04 - DJI O4 Lite Install and Setup](https://www.youtube.com/watch?v=1jtcI5UXcAU) | Joshua Bardwell | DJI O4 Lite installation on a sub-250g build — current Bardwell O4 reference |
| 5 | [DJI N3 FPV Goggle Setup: Unboxing to binding](https://www.youtube.com/watch?v=1xluwfcn9B0) | Painless360 | Complete DJI goggles activation, firmware updates, binding, DVR settings |

### HDZero

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Build an FPV drone in 2023 - HDzero Video Transmitter](https://www.youtube.com/watch?v=Rx0Eh42ztdc) | Joshua Bardwell | HDZero VTX install in a complete build — the go-to setup walkthrough |
| 2 | [Switch to HDZero in 2025? V2 Goggles Mega-Review!](https://www.youtube.com/watch?v=Ig4-c6SgmQY) | Joshua Bardwell | Current state of HDZero in 2025 — HDZero Goggle 2 deep dive |

### Walksnail Avatar

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [The WalkSnail Avatar digital system — Setting up on a Betaflight-based quad](https://www.youtube.com/watch?v=M7laAHNusU8) | CurryKitten | Walksnail Avatar VTX/camera install + OSD setup, end-to-end |

### Analog

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [How to get Max Range with Analog FPV?](https://www.youtube.com/watch?v=3rsap8HdKKw) | FPV Channel | Power levels, channel selection, antenna choice, and range optimization |
| 2 | [Betaflight SmartAudio VTX Table Troubleshooting](https://www.youtube.com/watch?v=thR2XA_0PLM) | Joshua Bardwell | VTX tables, SmartAudio protocol, OSD power/channel control |

---

## 6. Betaflight & Firmware Configuration

### YouTube — Basics

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [How to Build a 5-Inch FPV Drone (config section)](https://www.youtube.com/watch?v=S9dvDU5RmQU) | Joshua Bardwell | Betaflight setup as part of the build — covers all basics |
| 2 | [2022 Freestyle FPV Drone Build - Configuration and Setup](https://www.youtube.com/watch?v=5ke6LabvtGM) | Joshua Bardwell | Dedicated config walkthrough — ports, receiver protocol, motors, PID profiles, OSD |

### YouTube — Tuning Deep Dive

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Betaflight PID Tuning Masterclass w/ PIDToolbox Inventor Brian White](https://www.youtube.com/watch?v=FsJNHI2HWlg) | Joshua Bardwell | Two PID experts in one video — deepest PID/filter tuning content on YouTube |
| 2 | [PID Tuning Masterclass - Part 1 - P Term From Low To High](https://www.youtube.com/watch?v=27lMKi2inpk) | Joshua Bardwell | First episode of Bardwell's PID-by-feel series — what each term actually changes in the air |
| 3 | [Find YOUR perfect rates! With science!](https://www.youtube.com/watch?v=Ql62iRkLX3s) | Joshua Bardwell | Methodical rates tuning — adjusts your stick response to fit your flying style |
| 4 | [I turned BF rates to max and learned something profound](https://www.youtube.com/watch?v=nJ-V7EAnpig) | Joshua Bardwell | Why super-high rates are NOT the answer — Bardwell's surprise finding |

### Written Guides (More Current Than Videos — Updated 2025)

These Oscar Liang guides are the **gold standard** reference — more detailed and up-to-date than any single video:

| # | Title | What It Covers |
|---|-------|---------------|
| 1 | [Betaflight Setup Masterclass](https://oscarliang.com/betaflight-firmware-setup/) | Complete walkthrough of every Betaflight tab — last verified as updated Nov 2025 for BF 2025.12; tab layout changed in the modernised 2026.6 app, so expect cosmetic differences |
| 2 | [How to Flash Betaflight Firmware](https://oscarliang.com/flash-update-betaflight/) | Firmware flashing, Cloud Build, DFU mode, driver troubleshooting |
| 3 | [Betaflight Tuning In 10 Simple Steps](https://oscarliang.com/fpv-drone-tuning/) | No-blackbox tuning — P/D balance, feedforward, filters, dynamic idle |
| 4 | [GPS Rescue Setup (Return to Home)](https://oscarliang.com/setup-gps-rescue-mode-betaflight/) | Hardware selection, wiring, config, failsafe, field testing |
| 5 | [ExpressLRS Setup Guide](https://oscarliang.com/setup-expresslrs-2-4ghz/) | Complete ELRS 2.4GHz setup — hardware, flashing, binding, Betaflight config |

---

## 7. First Real Flight (After Sim + Build)

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [How Long Should You Practice In Sim Before Flying 5" For the First Time?](https://www.youtube.com/watch?v=cIzrdlMhaOM) | Joshua Bardwell | How many sim hours you need — sets realistic expectations |
| 2 | [How To FPV — FASTEST WAY — First Purchase? (Part 1)](https://www.youtube.com/watch?v=HKhzd--jVbQ) | Mr Steele | Mr Steele's recommended path into FPV — buying order and learning structure |
| 3 | [How To FPV — The KEY to becoming a BETTER PILOT (Part 3)](https://www.youtube.com/watch?v=wcCk9VMq2AY) | Mr Steele | Improving stick control and developing flow |
| 4 | [Betaflight 4.3 Failsafe Tab \| COMPLETE WALKTHROUGH PART 8](https://www.youtube.com/watch?v=Il965t3Yp8g) | Joshua Bardwell | Every failsafe setting explained — must-watch before any maiden |

> Also set up GPS Rescue (Section 18) before your first long-range flight.

---

## 8. Inspiration — What You're Working Toward

Watch these when you need motivation. This is what the hobby looks like once you've put in the hours.

### Freestyle (Proximity, Flow, Raw Skill)

| # | Title | Channel | Why It's Special |
|---|-------|---------|-----------------|
| 1 | [GOD MODE Activated — FPV Freestyle](https://www.youtube.com/watch?v=wat4SlyJSHs) | Mr Steele | Peak freestyle mastery — smooth, aggressive lines that define the art |
| 2 | [Passage — FPV Drone Freestyle](https://www.youtube.com/watch?v=iR2EE1ECP-0) | Le Drib | Signature "flow" style — smooth, artistic, musical. Makes flying look like dancing |
| 3 | [eMotion — FPV Drone Freestyle](https://www.youtube.com/watch?v=LaJ5VaxEXsk) | Le Drib | Pure cinematic freestyle — demonstrates FPV as artistic expression |
| 4 | [UNDERGROUND – FPV Freestyle Flow](https://www.youtube.com/watch?v=YaNxnuH4xHk) | Le Drib | Subterranean line work — one of Le Drib's most technical recent reels |
| 5 | [decency](https://www.youtube.com/watch?v=Z4EMHZrXJK4) | Le Drib | Le Drib at his most experimental — minimalist edit, raw flow |
| 6 | [I decided that I don't hate FPV now.](https://www.youtube.com/watch?v=T3eDJ54y5AQ) | BotGrinder | Raw, gritty urban freestyle — the pure fun of ripping with friends |

### Cinematic (Professional, Film-Quality)

| # | Title | Channel | Why It's Special |
|---|-------|---------|-----------------|
| 1 | [GoPro HERO7 X Johnny FPV — DRIFT](https://www.youtube.com/watch?v=SldJIisWFmE) | Johnny FPV | **The video that proved FPV belongs in Hollywood** — a landmark moment for the hobby |
| 2 | [The sky is not the limit](https://www.youtube.com/watch?v=DYHUuJAle8A) | Johnny FPV | Breathtaking cinematic reel across diverse environments |

### Culture & Community

| # | Title | Channel | Why It's Special |
|---|-------|---------|-----------------|
| 1 | [How FPV Changed (And Why I'm Still Here)](https://www.youtube.com/watch?v=FNdzbWEWTjo) | BotGrinder | 10-year veteran reflects on the hobby — perfect for understanding the community |
| 2 | [Flying Drones in the middle of New York City](https://www.youtube.com/watch?v=IMc1n2oADJ0) | BotGrinder | Urban guerilla whooping — shows FPV isn't just open fields |
| 3 | [Legends of FPV - Skitzo FPV](https://www.youtube.com/watch?v=MBsGmVFqCvg) | GetFPV | Mini-doc on Skitzo, one of FPV's original freestyle legends — essential culture |

---

## 9. iNav — GPS Navigation & Autonomous Flight

iNav is for when you want your quad to fly itself — waypoints, return-to-home, position hold, and long-range cruising. Use iNav instead of Betaflight when GPS autonomy is the priority.

### When to Use iNav vs Betaflight

| Use Case | Firmware |
|----------|----------|
| Freestyle, racing, acro | Betaflight |
| Long-range with reliable RTH | **iNav** |
| Waypoint missions (simple) | **iNav** |
| Position hold + cruising | **iNav** |
| Complex autonomous missions | Ardupilot |

### Videos

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [What is INAV and why would I use it?](https://www.youtube.com/watch?v=BXEPO361ghU) | Painless360 | Introduction to iNav — what it is, its capabilities, why choose it over Betaflight |
| 2 | [INAV Flight Modes explained for beginners (2026)](https://www.youtube.com/watch?v=n3zHCPcjaAg) | Painless360 | All flight modes including GPS NAV (RTH, waypoints), arming, VTOL, OSD |
| 3 | [My Top INAV Pro Tips for 2026](https://www.youtube.com/watch?v=nnTmosaMMFs) | Painless360 | Practical tips — GPS setup, RTH "oh dear" switch, failsafe verification, auto-launch, buzzer |
| 4 | [Building an AtomRC Dolphin with FC, GPS and Rx (2026)](https://www.youtube.com/watch?v=9tBNxs3MLgo) | Painless360 | Full hardware build with FC, GPS and receiver wiring, power connections, calibration |
| 5 | [How I Maiden an INAV Model (2026)](https://www.youtube.com/watch?v=92ZveiEaSxk) | Painless360 | Maiden flight process — pre-flight checks, flight mode progression, first flight verification |

### Playlist

| Title | Channel | URL |
|-------|---------|-----|
| [INAV for Beginners 2026 (iNav V9) — Full Series](https://www.youtube.com/playlist?list=PLYsWjANuAm4qmQ9uAZOuU9C1TR9gtxU04) | Painless360 | Complete multi-part series from scratch — hardware, configurator, GPS, flight modes, FPV, maiden |

### Key Channels for iNav

- **Painless360** — Best structured iNav tutorials (beginner series updated yearly)
- **Pawel Spychalski** — iNav lead developer, deep technical content (search his channel directly on YouTube)
- **Oscar Liang** — Written guides at oscarliang.com/inav-setup/

---

## 10. Ardupilot — Advanced Autonomous & Commercial

Ardupilot is the most capable flight controller firmware — used for mapping, surveying, research, and commercial applications. It's more complex than Betaflight/iNav but offers full autonomous mission planning, obstacle avoidance, and advanced failsafes.

### When to Use Ardupilot

| Use Case | Firmware |
|----------|----------|
| Simple freestyle/racing | Betaflight |
| GPS RTH + basic waypoints | iNav |
| **Complex autonomous missions** | **Ardupilot** |
| **Mapping / surveying** | **Ardupilot** |
| **Research / commercial** | **Ardupilot** |
| **Multi-vehicle coordination** | **Ardupilot** |

### Beginner Setup (Start Here)

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [PixHawk/ArduCopter for Beginners: 1. Flashing the PixHawk 6C](https://www.youtube.com/watch?v=_ketmb8u2UI) | Painless360 | Firmware flashing and initial configuration for ArduCopter beginners |
| 2 | [PixHawk/ArduCopter for Beginners: 2. Installing and full setup](https://www.youtube.com/watch?v=WzM4J_qlEso) | Painless360 | Physical Pixhawk installation, complete setup walkthrough, calibration |
| 3 | [PixHawk/ArduCopter for Beginners: 3. Final checks and maiden](https://www.youtube.com/watch?v=gqbwSt6Ds3s) | Painless360 | Pre-flight checks and maiden flight guidance |

### Mission Planner & Ecosystem

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [All the confusing names in 'Pixhawk' explained](https://www.youtube.com/watch?v=0vBXFjhw-5M) | Painless360 | Demystifies the ecosystem — Mission Planner vs QGC, ArduPilot vs PX4, Pixhawk hardware |
| 2 | [Beginner's Tutorial — Simulation using Mission Planner](https://www.youtube.com/watch?v=GFxwRgntGlQ) | Karthik's Tech Time | Practice autonomous flight in SITL simulation without risking hardware |
| 3 | [Beginner's Tutorial: Episode-04 - Overview of Mission Planner](https://www.youtube.com/watch?v=ODf-KYBuBWw) | Karthik's Tech Time | Karthik's dedicated Mission Planner deep dive — every panel and menu walked through |
| 4 | [Ardupilot flight modes explained simply](https://www.youtube.com/watch?v=BzSjAGQy1kM) | Painless360 | All ArduPilot flight modes — shows what ArduPilot can do that simpler FCs cannot |

### Tuning

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Complete ArduPilot Tuning Guide Part 1 — Hardware and Setup](https://www.youtube.com/watch?v=4pkSnBqA_m4) | Chris Rosser | Hardware preparation and initial parameter setup for ArduCopter tuning |
| 2 | [Complete ArduPilot Tuning Guide Part 3 — PIDs](https://www.youtube.com/watch?v=9laDDE3tv-g) | Chris Rosser | Deep PID tuning methodology for multirotors |
| 3 | [Arducopter Tuning — AUTOTUNE, PIDs & FILTERS](https://www.youtube.com/watch?v=AF6aA2z6rhw) | TMac | Full autotune process + manual PID and filter adjustments with flight tests |

### Autonomous Missions

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Beginner's Tutorial: Autonomous Flight with Pixhawk](https://www.youtube.com/watch?v=MNyBaM2pgns) | Karthik's Tech Time | Step-by-step waypoint mission creation and execution |
| 2 | [Building an Autonomous Waypoint Drone](https://www.youtube.com/watch?v=Idnx69G4E20) | ieatgrass R/C | Full build and configuration of a waypoint-capable autonomous drone |

### Custom Builds with Ardupilot

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Ardupilot Drone Build — Part 2 — GPS Setup](https://www.youtube.com/watch?v=9mvh17QiUTw) | Mads Tech | GPS module selection, wiring, and configuration on a custom build |
| 2 | [Ardupilot Compass Configuration — Build Series Part 3](https://www.youtube.com/watch?v=8lFHRlp3i1o) | Mads Tech | Compass setup — CAN vs serial, calibration, interference mitigation |
| 3 | [I Built A BETTER Drone Than DJI — Holybro x650](https://www.youtube.com/watch?v=5oEcA4S9I28) | Dylan Gorman | Full custom build rivaling DJI for autonomous mapping |
| 4 | [HolyBro X500 V2 Development Frame](https://www.youtube.com/watch?v=cTVtFYONHiY) | Painless360 | Ideal starting platform for custom autonomous quad projects |

### Firmware Comparison

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [INAV vs Betaflight vs Ardupilot — Which Is Better?](https://www.youtube.com/watch?v=-NWmJpfxI0A) | Stones RC Channel | Direct three-way comparison — when each firmware is the right choice |

---

## 11. Tiny Whoop & Indoor Practice

A tiny whoop (sub-25g brushless micro) is the cheapest, fastest way to practice acro indoors and develop muscle memory. Many pilots fly more whoop than 5" once they discover them.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [2023 Ultimate Guide to Tiny Whoops: Are you using the right stuff?](https://www.youtube.com/watch?v=lgeeR8TiuP0) | Joshua Bardwell | The current whoop ecosystem — frames, motors, batteries, props that actually work |
| 2 | [The best Tiny Whoop parts and accessories are here!](https://www.youtube.com/watch?v=jRip8Hl-m4Y) | Joshua Bardwell | Curated parts list — what to actually buy for indoor whoop flying |
| 3 | [The Best Whoop you can under $100.](https://www.youtube.com/watch?v=ccg55xebHio) | Drone Camps | Affordable BNF whoop comparison — direct buying advice for your first indoor quad |
| 4 | [How to FPV (Part 4) Do I get a Mini Drone?](https://www.youtube.com/watch?v=V762b-7Omj0) | Mr Steele | Mr Steele's case for starting on a whoop — why it's the most underrated path |
| 5 | [Digital Tiny Whoop under 20 grams! HDZero AIO5 FC makes it possible!](https://www.youtube.com/watch?v=eG3xOCpSVZE) | Joshua Bardwell | If you want HD video on a whoop — HDZero AIO5 build walkthrough |
| 6 | [BetaFPV Meteor65 Pro Setup Guide](https://www.youtube.com/watch?v=jf7y-mIVByI) | Joshua Bardwell | Setup of the most popular BNF whoop — radio binding, props, batteries |
| 7 | [The BEST DJI Whoop for 2025 - Showdown Video](https://www.youtube.com/watch?v=FSyyBAMdB7Y) | Drone Camps | If going DJI O3/O4 whoop, this picks the winner for indoor HD flying |

---

## 12. 7-Inch & Long Range Builds

7-inch quads with Li-Ion packs are the standard for true long range (20-60+ km) — efficient cruise, big payload bay, room for full-power VTX. See [`7-INCH-LONG-RANGE.md`](./7-INCH-LONG-RANGE.md) for the matching build doc.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [What are seven inches good for? // IFLIGHT CHIMERA 7 PRO](https://www.youtube.com/watch?v=LWhPYMqu9gI) | Joshua Bardwell | Why fly 7" at all — Bardwell's take on the strengths and trade-offs |
| 2 | [Taking 7" FPV to the next level: Fly further, fly faster! // AOS UL7](https://www.youtube.com/watch?v=axKOainoNNo) | Chris Rosser | Modern long-range 7" platform reasoning — AOS UL7 design and use cases |
| 3 | [AOS UL7, 8 and 10 inch Ultra Long Range Frames: Fly further, faster!](https://www.youtube.com/watch?v=YJYtmcCaSn4) | Chris Rosser | Comparison across the AOS Ultra Long Range frame family — picking the right size |
| 4 | [7inch paradise / fpv long range](https://www.youtube.com/watch?v=rrfAgipiWpA) | PlatyFPV | Cinematic 7" long-range flight — what's possible once tuned and dialed |

---

## 13. Fixed-Wing FPV & VTOL

When you want hours of flight time, hundreds of km of range, or aerial survey, a fixed-wing platform is the answer. Skywalker X8 and similar wings are the standard. See [`BVLOS-RELAY-DRONE.md`](./BVLOS-RELAY-DRONE.md) for airframe selection.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Making learning to fly fixed wing easier - links to help](https://www.youtube.com/watch?v=OaKqAng-BVE) | Painless360 | Painless360's curated entry path into fixed-wing FPV — the right place to start |
| 2 | [Tips for learning to land a 'plane or wing FPV (viewer request)](https://www.youtube.com/watch?v=kb6di_eVdH0) | Painless360 | Landing is the hardest part of wing flying — practical advice from a fixed-wing pilot |
| 3 | [Flite Test - Skywalker X8 - REVIEW](https://www.youtube.com/watch?v=PoJLgAlkABE) | FliteTest | Classic FliteTest review of the Skywalker X8 — the canonical wing platform |
| 4 | [Radiomaster Nexus X flight controller can now be used for fixed-wing](https://www.youtube.com/watch?v=crWHiuEk72o) | Painless360 | Modern FC options for fixed-wing builds — Nexus X is a major 2026 addition |
| 5 | [AtomRC Flying Fish: Setup tips and maiden flight!!](https://www.youtube.com/watch?v=2Fy8jQusda8) | Painless360 | Affordable beginner FPV plane — setup and maiden walkthrough |

---

## 14. BVLOS, Mesh Radio & Relay Concepts

These videos cover the *technical and regulatory* side of flying beyond visual line of sight — the foundations behind [`BVLOS-RELAY-DRONE.md`](./BVLOS-RELAY-DRONE.md). BVLOS is legally restricted; videos here are educational, not authorization to fly.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Can I Fly My Drone Beyond Visual Line of Sight?](https://www.youtube.com/watch?v=IQfpD9ky9yc) | UAV Coach | Plain-English BVLOS explainer — what it is, why it's regulated, how authorization works |
| 2 | [Introduction to Doodle Labs' Mesh Rider Radios](https://www.youtube.com/watch?v=m-Nk8DHDpAE) | Doodle Labs | Vendor intro to the dominant mesh radio family for UAV — the core hardware concept |

> **Coverage gap acknowledged:** Quality independent BVLOS / mesh-radio tutorials on YouTube are thin. Most authoritative content is vendor talks (Doodle Labs, Silvus, Microhard) or academic conference recordings. Search the channels listed in [`BVLOS-RELAY-DRONE.md`](./BVLOS-RELAY-DRONE.md) References section.

---

## 15. EU / Denmark Drone Regulations

Read [`REGULATIONS.md`](./REGULATIONS.md) first — that's the authoritative reference for what you're allowed to fly in Denmark and the EU. These videos are supplemental.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Everything about Drones in Open Category: A1, A2 & A3](https://www.youtube.com/watch?v=Dsa1ceFPhn8) | EU Drone Port™ | Explains the EASA Open category subcategories — what each lets you do |

> **Coverage gap acknowledged:** Most YouTube drone-law content is US/FAA focused (Pilot Institute is excellent but Part 107 only). For EU/Denmark specifics, [`REGULATIONS.md`](./REGULATIONS.md) plus [droneregler.dk](https://www.droneregler.dk/) and [easa.europa.eu](https://www.easa.europa.eu/en/domains/civil-drones) are the authoritative sources.

---

## 16. Crash Recovery, Repair & Motor Swap

Your first crash is inevitable. These videos cover what to do when something breaks.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Quadcopter motor twitching. What next? \| BAD MOTOR OR ESC TROUBLESHOOTING GUIDE](https://www.youtube.com/watch?v=qtvrG4ilWgk) | Joshua Bardwell | Decision tree for "is it the motor or the ESC?" — covers swap procedure and bench tests |
| 2 | [Is Your ESC Broken \| HOW TO FIND OUT](https://www.youtube.com/watch?v=NW4a3AnraVk) | Joshua Bardwell | Diagnosing a dead ESC after a crash — proper test methodology before you replace |
| 3 | [How To Clean Quadcopter Motors](https://www.youtube.com/watch?v=CTa1S4G_0GA) | Joshua Bardwell | Dirt and dust kill motors — the maintenance no one tells you to do |

---

## 17. LiPo Battery Safety & Charging

LiPos can catch fire if mishandled. This section is mandatory before you charge your first pack.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [How to keep LiPos from burning down your house (safe lipo charging)](https://www.youtube.com/watch?v=n3urBpFIBgY) | Joshua Bardwell | **The definitive LiPo safety video** — charging current, bags, fire risk, must-watch |
| 2 | [RC Basics: Introduction to LIPO Batteries](https://www.youtube.com/watch?v=QdHjyk7fgc8) | Painless360 | Calm, structured intro — voltages, cells, S-counts, when to retire a pack |
| 3 | [Ultimate LiPo battery charging guide! 2023. How to charge lipo battery](https://www.youtube.com/watch?v=4N4tlSfITqA) | UAVfutures | Stew's beginner-focused complement to Bardwell — storage charging, balance mode, C-rate basics |
| 4 | [Parallel Charging \| CAN YOU MIX DIFFERENT mAh OF BATTERY](https://www.youtube.com/watch?v=AwqJOLzo59M) | Joshua Bardwell | Parallel charging done correctly — rules and pitfalls when you own 6+ packs |
| 5 | [New ultimate parallel charge board does it all (XT30 and XT60, 2S-6S)](https://www.youtube.com/watch?v=HwUkkyUIOOk) | Joshua Bardwell | Modern parallel charge board hardware recommendation |

---

## 18. GPS Rescue & Failsafe

GPS Rescue brings your quad home if your radio link drops. Set this up BEFORE flying out of range. Pair with Oscar Liang's written guide ([Section 6 written guide #4](#written-guides-more-current-than-videos--updated-2025)).

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Betaflight 4.5 GPS Rescue Setup Guide](https://www.youtube.com/watch?v=Zytp-J14evo) | Joshua Bardwell | The current Bardwell GPS Rescue walkthrough — pairs with Oscar Liang's written guide |
| 2 | [Betaflight 4.4 GPS Rescue - Can You Now Trust It ?](https://www.youtube.com/watch?v=puN6glQ8GsQ) | Mads Tech | Honest field test — when GPS Rescue works and when it doesn't |
| 3 | [Betaflight 4.3 Failsafe Tab \| COMPLETE WALKTHROUGH PART 8](https://www.youtube.com/watch?v=Il965t3Yp8g) | Joshua Bardwell | Every failsafe setting tab-by-tab — the most thorough failsafe reference |

---

## 19. Antennas — Theory, Repair & Placement

Antennas matter more than power for range. Polarization, placement, and clean coax connections are 80% of the link.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Antenna Basics For RC Flight: Polarization](https://www.youtube.com/watch?v=JlaBpd0Rs-k) | Joshua Bardwell | **Antenna 101** — circular vs linear, why polarization matters |
| 2 | [Left vs Right Circular Polarization \| WHICH IS BETTER (LHCP vs. RHCP)](https://www.youtube.com/watch?v=mbHl3DgnN4k) | Joshua Bardwell | The LHCP/RHCP debate settled — and what to actually do about it |
| 3 | [How To Reinforce Your Flimsy FPV Antenna](https://www.youtube.com/watch?v=OJhMgXhz2eA) | Joshua Bardwell | Strain relief that saves your antenna from snapping in a crash |
| 4 | [How To Reinforce TBS Unify Antenna Connector \| NO DIRECT-SOLDERING COAX](https://www.youtube.com/watch?v=2afwhOXVb8c) | Joshua Bardwell | U.FL connector reinforcement — the #1 antenna failure on FPV quads |

---

## 20. Goggles Deep Dive

The goggle is the most expensive and most personal piece of FPV gear. Don't buy blind.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [Best FPV Goggle 2023 Buyer's Guide // DJI v. HDZERO v. WALKSNAIL v. ANALOG](https://www.youtube.com/watch?v=TMOeIQ4VRX4) | Joshua Bardwell | The canonical "which goggle should I buy" video — still the framework everyone uses |
| 2 | [Switch to HDZero in 2025? V2 Goggles Mega-Review!](https://www.youtube.com/watch?v=Ig4-c6SgmQY) | Joshua Bardwell | Most current Bardwell take — HDZero Goggle 2 deep dive in 2025 landscape |
| 3 | [The BEST Fpv Goggles for 2026... But can you find them?](https://www.youtube.com/watch?v=YCN7q7zMbhk) | Drone Camps | 2026 picks — availability-aware recommendations |
| 4 | [What Is Required To Use Headtracking With The DJI O4 Air Unit? DIY Head Tracking? - FPV Questions](https://www.youtube.com/watch?v=jp4DM6LWI8A) | Joshua Bardwell Livestream Clips | Head tracking on the current DJI stack — practical setup answer most pilots want |
| 5 | [DJI N3 FPV Goggle Setup: Unboxing to binding](https://www.youtube.com/watch?v=1xluwfcn9B0) | Painless360 | Complete DJI goggles activation, firmware updates, binding, DVR settings |

---

## 21. Cinematography Techniques

These videos teach you HOW to film, not just show you what's possible. Studying composition + flight technique is the difference between freestyle and cinematic.

| # | Title | Channel | Why Watch |
|---|-------|---------|-----------|
| 1 | [How I Chase Drift Cars \| Shot Dissection \| FPV Drone](https://www.youtube.com/watch?v=BxZ3lU98i-E) | Mr Steele | Mr Steele breaks down a chase shot frame-by-frame — what to think about while flying |
| 2 | [GoPro HERO7 X Johnny FPV — DRIFT](https://www.youtube.com/watch?v=SldJIisWFmE) | Johnny FPV | Watch this with the sound off and study composition — most influential cinematic reel ever |

> **Channels to study for cinematic technique:** Johnny FPV, Quad Mike, Skitzo, Project Mockingbird, Tom Strojnik, Le Drib (cinematic reels). Most teach by example rather than tutorial — re-watch their reels with intent.

---

## Suggested Learning Order

```
Week 1-2:   Soldering (#1) + radio arrives → Sim setup (Section 2)
Week 1-2:   Optional: Buy a Tiny Whoop (Section 11) for indoor practice
Week 1-2:   READ: LiPo safety (Section 17) before charging anything
Week 2-4:   Fly simulator daily (10-20 hours total) + whoop indoors
Week 3-4:   Parts arrive → Watch build videos (Section 3) before starting
Week 4-5:   Build the quad (re-watch Section 3 as you go)
Week 5:     ELRS binding (Section 4) → Betaflight config (Section 6)
Week 5:     FPV system setup (Section 5) → Goggles setup (Section 20)
Week 5:     Failsafe + GPS Rescue (Section 18) — DO NOT FLY without this
Week 5-6:   First real flights (Section 7)
Ongoing:    Watch inspiration (Section 8) and study cinematography (Section 21)
After 1st crash: Repair & motor swap (Section 16)
Later:      GPS autonomy → iNav (Section 9) or Ardupilot (Section 10)
Later:      Long range → 7" builds (Section 12), fixed-wing (Section 13)
Advanced:   BVLOS / mesh / relay concepts (Section 14, plus BVLOS-RELAY-DRONE.md)
```

---

## Notes

- **Videos age, written guides stay current.** Oscar Liang's guides (oscarliang.com) are updated regularly and should be your primary reference for Betaflight/ELRS configuration.
- **Joshua Bardwell** is the single most useful channel for FPV education. Subscribe.
- **Mr Steele's "How To FPV" series** (Parts 1-4) is the best intro to the hobby if you watch nothing else.
- **Painless360** is the go-to for iNav, Ardupilot, and fixed-wing — his beginner series are updated yearly.
- **Chris Rosser** covers both 5"/7" builds and Ardupilot tuning at a high level.
- **UAVfutures** is the canonical channel for beginner soldering, batteries, and budget builds.
- **Drone Camps** is excellent for current "what should I buy in 2025/2026" buyer's guides.
- Some videos reference DJI O3 — the setup process for O4 is nearly identical.
- iNav and Ardupilot are "next level" — learn Betaflight first, then explore autonomy when ready.
- All URLs verified June 2026. If a link dies, search the exact title on YouTube.
