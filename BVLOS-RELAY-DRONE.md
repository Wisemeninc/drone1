# BVLOS Relay Drone — Design Reference

How to build a drone that **relays video and control signals** to another drone operating **Beyond Visual Line Of Sight (BVLOS)**.

A relay drone is a flying signal repeater. It loiters at altitude between the operator and the mission drone, bypassing terrain, buildings, and the curvature of the Earth that would otherwise block direct RF.

> **Heads up — legal reality first.** In the EU under EASA, BVLOS flight requires either the **Specific** category with an operational authorisation (or PDRA/STS) or the **Certified** category. You cannot legally fly BVLOS as a hobbyist under the Open category. See [REGULATIONS.md](./REGULATIONS.md) and the [Regulatory](#regulatory) section below before building anything.

---

## Table of Contents

1. [Concept and Physics](#concept-and-physics)
2. [System Architecture](#system-architecture)
3. [Airframe Selection](#airframe-selection)
4. [RF Relay Payload](#rf-relay-payload)
5. [Onboard Compute](#onboard-compute)
6. [Antenna Design](#antenna-design)
7. [Software Stack](#software-stack)
8. [Power and Endurance](#power-and-endurance)
9. [Regulatory](#regulatory)
10. [Build Roadmap](#build-roadmap)
11. [References](#references)

---

## Concept and Physics

### Why a relay is needed

Standard FPV/control links (2.4 GHz, 5.8 GHz, 900 MHz) are **line-of-sight** RF. As soon as terrain, buildings, foliage, or the Earth itself obstructs the path, signal collapses. The radio horizon at ground level is roughly:

```
d_km ≈ 3.57 × (√h1 + √h2)        where h is antenna height in meters
```

| Operator height | Drone height | Horizon distance |
|----------------:|-------------:|-----------------:|
| 2 m | 50 m | ~30 km |
| 2 m | 120 m (EU limit) | ~44 km |
| 2 m | 400 m | ~76 km |
| 2 m | 500 m (relay) | ~85 km |

A relay drone parked at **300–500 m AGL** dramatically extends radio horizon for *both* legs of the link. The mission drone can fly low (terrain following, urban canyons) and still maintain a link via the relay overhead.

### The two legs

```
Operator ────leg A────► Relay ────leg B────► Mission Drone
         (uplink)              (downlink)
```

- **Leg A** (operator ↔ relay): typically longer, optimised with directional/high-gain antennas
- **Leg B** (relay ↔ mission): omnidirectional, the mission drone can move freely

The two legs **must use different frequencies** or be time-division multiplexed; otherwise the relay receiver desensitises against its own transmitter (self-interference).

---

## System Architecture

```
┌──────────────────┐   915 MHz / 2.4 GHz   ┌──────────────────┐
│   Ground Station │ ◄───────────────────► │   Relay Drone    │
│   (operator)     │     MAVLink + video   │   @ 400m AGL     │
│   - Mission      │                       │   - SBC          │
│     Planner      │                       │   - 2× radios    │
│   - QGC          │                       │   - Loiter loop  │
└──────────────────┘                       └────────┬─────────┘
                                                    │
                                            5.8 GHz / 1.2 GHz
                                                    │
                                           ┌────────▼─────────┐
                                           │  Mission Drone   │
                                           │  - Cargo / cam / │
                                           │    survey        │
                                           └──────────────────┘
```

Components:

| Block | Function | Typical Hardware |
|-------|----------|------------------|
| Ground Station | Operator UI, mission planning | Laptop + telemetry radio |
| Long-range uplink | Operator ↔ relay link | Doodle Labs Helix, RFD900x, Microhard |
| Relay airframe | Carry payload, loiter high | Fixed-wing or large multirotor |
| Relay SBC | IP forwarding / MAVLink routing | Raspberry Pi CM4, Jetson Orin Nano |
| Short-range downlink | Relay ↔ mission link | 5.8 GHz mesh or P2P radio |
| Mission drone | Actual payload carrier | Any ArduPilot/PX4 platform |

---

## Airframe Selection

### Why fixed-wing is preferred for the relay

The relay needs to **loiter for hours**, ideally over a single point. Multirotors burn 200–400 W just hovering; fixed-wings need only 80–150 W in slow cruise. A 2 kg fixed-wing on 10 Ah of LiPo can fly 90+ minutes; the same energy in a quad gives 20 minutes.

**Recommended fixed-wing platforms:**

| Platform | Wingspan | Endurance | Why |
|----------|---------:|----------:|-----|
| [Skywalker X8](https://www.banggood.com/Skywalker-X8-2120mm-Wingspan-EPO-FPV-RC-Airplane-Flying-Wing-KIT-p-1104501.html) | 2.12 m | 60–120 min | Cheap, huge payload bay, proven UAV platform. See [RCGroups build thread](https://www.rcgroups.com/forums/showthread.php?1840543-Skywalker-X8-FPV) for tuning. |
| [Reptile S800 V2 / Sky Shadow](https://www.banggood.com/Reptile-S800-SKY-SHADOW-820mm-Wingspan-FPV-EPP-Flying-Wing-Racer-RC-Airplane-KIT-p-1108279.html) | 0.82 m | 30–60 min | Compact, easy hand-launch. See [RCGroups build thread](https://www.rcgroups.com/forums/showthread.php?3426643-Reptile-skyshadow-S800-build). |
| [Foxtech Nimbus VTOL](https://www.foxtechfpv.com/) | 1.8 m | 60–90 min | VTOL — no runway needed (search "Nimbus" on foxtechfpv.com) |
| [Believer 1960mm](https://www.aliexpress.com/wholesale?SearchText=Believer+1960mm+UAV) | 1.96 m | 90+ min | Designed for aerial survey, big payload bay. MakeFlyEasy original airframe — listings rotate often; see [RCGroups build thread](https://www.rcgroups.com/forums/showthread.php?2984973-Believer-Twin-tractor-1960mm-Mapping-FPV-Plane-full-review-mods-owner-s-thread) for setup. |

### When to use a multirotor

- Operator needs the relay to **stay over a fixed point** without orbiting (legal restriction, obstacle, antenna alignment)
- No runway or launch space available and VTOL fixed-wing is out of budget
- Short missions (< 30 min)

Recommended: heavy-lift hex or octo (Tarot T18, Tarot X6) with high-capacity Li-Ion pack for max hover time.

### Tether option

For permanent operations, a **tethered multirotor** with power-over-cable eliminates battery life concerns entirely. Vendors: [Elistair](https://elistair.com/), [Hoverfly](https://hoverflytech.com/).

---

## RF Relay Payload

This is the heart of the system. Two architectural approaches:

### Option A — Mesh Radio (recommended)

A single product family handles both legs of the link via mesh routing. Cleanest, fewest moving parts.

| Vendor / Product | Band | Range per hop | Notes |
|------------------|------|--------------:|-------|
| [Doodle Labs](https://doodlelabs.com/) Helix Mesh Rider | 2.2 / 2.4 / 5.1–5.9 GHz | 5–20 km | Industry standard for UAV mesh, MIMO |
| [Doodle Labs](https://doodlelabs.com/) Mesh Rider Radio | Multiple bands | 5–50 km | Proven on Skydio, Teal, Parrot UAVs |
| [Microhard](https://www.microhardcorp.com/) pDDL series | 2.4 / 900 MHz | 20–80 km | IP mesh, ruggedised |
| [Silvus StreamCaster](https://silvustechnologies.com/products/) | L/S/C-band | 50+ km | Military MANET, expensive |
| [Rajant](https://rajant.com/) Kinetic Mesh (BreadCrumb) | Multiple | Variable | Industrial multi-radio mesh |
| [Persistent Systems Wave Relay MPU5](https://www.persistentsystems.com/mpu5/) | Multiple | 10+ km | Military MANET |

### Option B — Dual-Radio Bridge (DIY-friendly)

Two independent radios on different bands, bridged by an SBC. More wiring, but you can use cheaper consumer-grade radios.

```
[Operator] ── 900 MHz ── [RFD900x #1] ── UART ── [Raspberry Pi] ── UART ── [RFD900x #2] ── 868 MHz ── [Mission]
                                                       │
                                                  IP forwarding
                                                  / MAVLink routing
```

Common radio choices for the legs:

| Radio | Band | Range | Use case |
|-------|------|------:|----------|
| RFD900x / RFD900x-US ([RFDesign](https://store.rfdesign.com.au/)) | 868/915 MHz | 40+ km | Telemetry workhorse, EU 868 variant |
| RFD868x ([RFDesign](https://store.rfdesign.com.au/)) | 868 MHz | 40+ km | EU-legal long-range telemetry |
| [TBS Crossfire](https://www.team-blacksheep.com/products/prod:crossfire_tx) | 868/915 MHz | 40+ km | Control link, low latency |
| [ExpressLRS (ELRS) 868/915](https://www.expresslrs.org/) | 868/915 MHz, 2.4 GHz | 30+ km | Open-source control link |
| Dragon Link Advanced ([RCGroups thread](https://www.rcgroups.com/forums/showthread.php?2557039-Dragon-Link-Advanced-Bi-Directional-Long-Range-UHF)) | 433/915 MHz | 40+ km | Long-range UHF control |
| [Ubiquiti Bullet AC / Rocket M](https://store.ui.com/us/en/category/wireless-airmax-5ghz) | 2.4/5 GHz | Variable | Cheap IP backhaul, repurposed |

For video specifically:

| Product | Use | Notes |
|---------|-----|-------|
| [DJI O4 Air Unit Pro](https://www.dji.com/) | Digital FPV video | 20+ km claimed, EU module limits apply (search "O4 Air Unit" on dji.com) |
| [Walksnail Avatar HD](https://caddxfpv.com/) | Digital FPV video | Open-ish, repeater-friendly (search "Walksnail" on caddxfpv.com) |
| [HDZero](https://www.hd-zero.com/) | Digital FPV video | Low latency, line-of-sight |
| Analog 5.8 GHz VTX + RX | Legacy video | Easy to repeat, very tolerant |

---

## Onboard Compute

The SBC's job: **route packets between the two radios**, optionally do MAVLink rewriting, compress video, log telemetry, and run failsafe logic.

| Board | Power | Use case |
|-------|------:|----------|
| [Raspberry Pi CM4](https://www.raspberrypi.com/products/compute-module-4/) | 3–7 W | Best general-purpose, mature ecosystem |
| [Raspberry Pi Zero 2 W](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/) | 1–2 W | Minimum viable, light builds |
| [NVIDIA Jetson Orin Nano](https://developer.nvidia.com/embedded-computing) | 7–15 W | Video transcoding, onboard AI |
| [Khadas VIM4](https://www.khadas.com/vim4) | 5–10 W | Powerful, good video HW accel |
| [BeagleBone Blue](https://www.beagleboard.org/boards/beaglebone-blue) | 2–4 W | Designed for robotics, has IMU built in |
| [Holybro Pixhawk RPi CM4 Baseboard](https://holybro.com/) | n/a | Integrates CM4 directly with Pixhawk (search "CM4 baseboard" on holybro.com) |
| [ModalAI VOXL 2](https://www.modalai.com/products/voxl-2) | 5–10 W | Purpose-built autonomy SBC |

**OS:** Raspberry Pi OS Lite, Ubuntu Server, or Armbian. Disable everything you don't need (desktop, audio, Bluetooth) to reduce RF noise and power draw.

---

## Antenna Design

This is where most amateur relay projects fail. Two physically-close transceivers on different bands still interfere; antenna design is non-optional.

### Principles

1. **Frequency separation** — minimum 1 GHz between leg-A and leg-B bands if possible
2. **Spatial separation** — antennas ≥ 1 m apart on the airframe, or ≥ 30 cm with shielding
3. **Polarisation separation** — leg A vertical, leg B circular (RHCP) for additional isolation
4. **Filtering** — band-pass filters on each radio to suppress out-of-band noise

### Antenna types

| Antenna | Pattern | Use |
|---------|---------|-----|
| Dipole / monopole | Omnidirectional, 2–3 dBi | Mission-leg downlink (drone roams freely) |
| Circular polarised (cloverleaf / Pagoda) | Omni, 1–2 dBi, multipath resistant | Video links, FPV downlink |
| Patch antenna | Directional, 8–14 dBi | Operator-side high-gain dish |
| Yagi | Highly directional, 12–18 dBi | Long-range operator uplink, point at relay |
| Helical | Directional, circular pol, 10–15 dBi | Long-range with multipath rejection |
| MIMO / sector | Multi-beam | Mesh radios with diversity |

**Vendors:**

- [TrueRC](https://www.truerc.com/) — circular polarised FPV antennas (Singularity, AXII)
- Menace RC — fold-over patch and helical (search "Menace RC" via AliExpress / Banggood)
- [VAS / VideoAerialSystems](https://videoaerialsystems.com/) — IBCrazy designs, long-range
- Maple RF / Maple Wireless — IBCrazy / Andrew Newton designs (often sold via VAS resellers)
- Pulse Larsen — industrial UAV antennas (search "Pulse Larsen UAV" — vendor consolidated under [Yageo Group (Pulse Electronics)](https://yageogroup.com/products/Antennas,%20RF%20&%20Microwave))
- [PCTEL](https://www.pctel.com/) — UAV omnis and patches

### Practical layout for a fixed-wing relay

```
       ╔═══ Fuselage top ════════════════════════════════╗
       ║                                                  ║
       ║   [Uplink yagi/patch]              [Downlink omni]
       ║   pointed back                     vertical, on
       ║   toward operator                  tail boom
       ║                                                  ║
       ╚══════════════════════════════════════════════════╝
                          ≥ 1 m separation
```

---

## Software Stack

### MAVLink routing

The relay needs to forward MAVLink between operator and mission drone, possibly while injecting its own telemetry stream.

**[mavlink-router](https://github.com/mavlink-router/mavlink-router)** — the canonical relay. Example config:

```ini
[General]
TcpServerPort=5760
ReportStats=false

[UartEndpoint to-mission]
Device = /dev/ttyUSB0
Baud = 57600

[UdpEndpoint to-operator]
Mode = Normal
Address = 192.168.1.10
Port = 14550
```

Alternative: **[MAVProxy](https://ardupilot.org/mavproxy/)** with `--out` flags to fan out streams.

### Video pipeline

[**GStreamer**](https://gstreamer.freedesktop.org/) handles low-latency RTP forwarding:

```bash
# On relay: receive video from mission drone, forward to operator
gst-launch-1.0 -v \
  udpsrc port=5600 caps='application/x-rtp,encoding-name=H264' ! \
  udpsink host=192.168.1.10 port=5600
```

For transcoding (e.g. downsize H.265→H.264 for bandwidth):

```bash
gst-launch-1.0 -v \
  udpsrc port=5600 ! rtph265depay ! avdec_h265 ! \
  videoscale ! video/x-raw,width=1280,height=720 ! \
  x264enc tune=zerolatency bitrate=2000 ! \
  rtph264pay ! udpsink host=192.168.1.10 port=5601
```

### Mesh networking

If using IP-based mesh radios, the relay is just an IP router — but you need a mesh routing protocol:

| Protocol | Layer | Notes |
|----------|-------|-------|
| [B.A.T.M.A.N.-adv](https://www.open-mesh.org/projects/batman-adv/wiki/Wiki) | L2 | Transparent Ethernet, simplest |
| [OLSRv2](https://www.olsr.org/) | L3 | Mature, IP-based |
| [Babel](https://www.irif.fr/~jch/software/babel/) | L3 | Robust, good for lossy links |
| [802.11s](https://en.wikipedia.org/wiki/IEEE_802.11s) | MAC | Built into Wi-Fi, limited |

For mesh radios from Doodle Labs, Microhard, etc., the routing is built into the radio firmware — you treat it as a black-box Ethernet bridge.

### Failsafe logic

The SBC should run a watchdog:

- If leg A (operator link) goes down for > 5 s → start orbit around current GPS, hold altitude
- If leg B (mission link) goes down for > 5 s → notify operator via leg A, optionally climb 100 m
- If both legs go down for > 30 s → return to home

Implement with [`systemd` timers](https://systemd.io/) + small Python script monitoring MAVLink heartbeat counters.

### Ground station software

| Software | Use |
|----------|-----|
| [Mission Planner](https://ardupilot.org/planner/) | Windows, the original ArduPilot GCS |
| [QGroundControl](https://qgroundcontrol.com/) | Cross-platform, PX4 default |
| [UgCS](https://www.sphengineering.com/flight-planning/ugcs) | Commercial, advanced mission planning |
| [Auterion Mission Control](https://auterion.com/product/mission-control/) | PX4-enterprise GCS |

---

## Power and Endurance

| Component | Typical draw |
|-----------|-------------:|
| SBC (RPi CM4) | 3–5 W |
| Mesh radio | 5–10 W |
| Dual radios + amp | 10–20 W |
| Propulsion (fixed-wing cruise) | 80–150 W |
| Propulsion (multirotor hover, 2 kg) | 200–350 W |

For a fixed-wing relay carrying ~300 g of payload, a 6S 10 Ah Li-Ion pack (≈ 850 g, 220 Wh) yields ~90 minutes endurance.

**Solar augmentation** is feasible on > 2 m wingspan platforms — see [Skydweller Aero](https://www.skydweller.aero/) (persistent solar UAV) and DIY projects on [DIY Drones](https://diydrones.com/).

**Tethering** (for stationary persistent relay) — pure mains power via a thin conductor cable, weights covered by ground winch. See [Elistair](https://elistair.com/) Safe-T product line.

---

## Regulatory

> **Critical**: BVLOS is regulated. Doing it without authorisation in the EU is a serious offence and uninsurable. The rules below are entry points — talk to your national CAA before flying.

### EU / EASA (covers Denmark, Germany, France, etc.)

| Category | BVLOS allowed? | Notes |
|----------|----------------|-------|
| [Open](https://www.easa.europa.eu/en/domains/civil-drones-rpas/specific-category-civil-drones) | **No** | <120 m AGL, VLOS only, hobby/light commercial |
| [Specific](https://www.easa.europa.eu/en/domains/civil-drones-rpas/specific-category-civil-drones) | **Yes**, with SORA + operational authorisation | The realistic path for serious BVLOS |
| [Certified](https://www.easa.europa.eu/en/domains/civil-drones-rpas/certified-category-civil-drones) | **Yes** | Manned-aviation-like certification, for heavy/passenger |

Key EASA docs:

- [EASA Drone Regulations Hub](https://www.easa.europa.eu/en/domains/civil-drones-rpas)
- [EASA Easy Access Rules (UAS Regulation EU)](https://www.easa.europa.eu/en/document-library/easy-access-rules/easy-access-rules-unmanned-aircraft-systems-regulation-eu) — includes SORA, PDRA, STS guidance
- Predefined Risk Assessments (PDRA) — pre-approved BVLOS scenarios — see Easy Access Rules above
- Standard Scenarios (STS-01, STS-02) — STS-02 covers BVLOS in sparsely populated areas — see Easy Access Rules above

**For Denmark specifically:** apply via [droneregler.dk](https://www.droneregler.dk/) and the [Trafikstyrelsen](https://www.trafikstyrelsen.dk/) for Specific category authorisations.

### USA / FAA

- [FAA UAS hub](https://www.faa.gov/uas) — Part 107, waivers, Remote ID, BVLOS resources
- [Remote ID rule](https://www.faa.gov/uas/getting_started/remote_id) — all drones over 250 g must broadcast ID
- [FAA BVLOS ARC report (2022)](https://www.faa.gov/regulations_policies/rulemaking/committees/documents/index.cfm/document/information/documentID/5424) — the basis for future Part 108 rulemaking

### Frequency / spectrum

| Region | ISM bands you can use license-free |
|--------|-----------------------------------|
| EU | 433 MHz (10 mW), 868 MHz (25–500 mW depending on duty cycle), 2.4 GHz (100 mW EIRP), 5.8 GHz (25–1000 mW depending on sub-band) |
| US | 902–928 MHz (1 W), 2.4 GHz (1 W EIRP DSSS), 5.8 GHz (variable) |

[ETSI EN 300 220](https://www.etsi.org/deliver/etsi_en/300200_300299/30022001/) governs EU 433/868 MHz. [ETSI EN 300 328](https://www.etsi.org/deliver/etsi_en/300300_300399/300328/) governs EU 2.4 GHz. Exceeding these makes the link illegal — and unless you've licensed amateur radio frequencies, you're stuck with ISM.

---

## Build Roadmap

A pragmatic phased build that de-risks as you go:

### Phase 1 — Bench prototype (1–2 weekends)

- Two Doodle Labs Helix radios (or pair of RFD900x) + Raspberry Pi CM4
- Bench-test IP forwarding between two laptops via the radios
- Measure throughput, latency, packet loss with `iperf3`
- Verify MAVLink passes through with a SITL ([ArduPilot SITL](https://ardupilot.org/dev/docs/sitl-simulator-software-in-the-loop.html)) on one side, Mission Planner on the other

### Phase 2 — Static ground relay (1 weekend)

- Put the relay payload on a 10 m mast
- Fly your mission drone normally, route its link through the static relay
- Measure achievable range vs. direct
- This proves the architecture without flying the relay

### Phase 3 — Multirotor relay flight (2–4 weekends)

- Mount the payload on a heavy hex (Tarot 680 or similar)
- Hover-test at 100 m AGL
- Validate antenna isolation in-flight
- Measure achievable range at altitude

### Phase 4 — Fixed-wing migration (4–8 weekends)

- Build/buy a Skywalker X8 or Believer
- Add the relay payload + autopilot loiter mission
- Test long-duration loiter (60+ min)
- Validate failsafe behaviour

### Phase 5 — Operational deployment

- Apply for Specific category authorisation (SORA)
- Buy insurance ([Coverdrone](https://www.coverdrone.com/), [Skywatch.AI](https://skywatch.ai/), national equivalents)
- Train two operators (one flying mission, one minding relay)
- Build go/no-go checklists

---

## References

### Hardware vendors — mesh radios

- [Doodle Labs](https://doodlelabs.com/) — UAV mesh radios (Helix, Mesh Rider)
- [Microhard Systems](https://www.microhardcorp.com/) — pDDL, pMDDL ruggedised IP radios
- [Silvus Technologies](https://silvustechnologies.com/) — MANET StreamCaster, military-grade
- [Persistent Systems](https://www.persistentsystems.com/) — Wave Relay MPU5
- [Rajant Corporation](https://rajant.com/) — Kinetic Mesh
- [Trellisware](https://www.trellisware.com/) — TSM MANET radios
- [DTC, a Codan Company (formerly Domo Tactical)](https://www.dtccodan.com/sectors/unmanned-uxv) — Solo7 IP mesh

### Hardware vendors — P2P long-range radios

- [RFDesign (RFD900x, RFD868x)](https://store.rfdesign.com.au/)
- [Team BlackSheep (Crossfire, Tracer)](https://www.team-blacksheep.com/)
- [ExpressLRS open-source project](https://www.expresslrs.org/)
- Dragon Link — see [RCGroups thread](https://www.rcgroups.com/forums/showthread.php?2557039-Dragon-Link-Advanced-Bi-Directional-Long-Range-UHF) (vendor site intermittent)
- [Ubiquiti airMAX](https://store.ui.com/us/en/category/wireless-airmax-5ghz) — Bullet, Rocket, NanoStation
- [MikroTik](https://mikrotik.com/) — wAP, LHG, SXTsq cheap IP backhaul

### Hardware — flight controllers and SBCs

- [Holybro](https://holybro.com/) — Pixhawk, Durandal, Kakute, RPi CM4 baseboards
- [CubePilot](https://www.cubepilot.com/) — Cube Orange, Cube Black
- [Matek Systems](http://www.mateksys.com/) — H743 series, mini autopilots
- [mRo Robotics](https://store.mrobotics.io/) — Pixracer Pro, Control Zero
- [Auterion Skynode X](https://auterion.com/product/skynode-x/) — integrated autopilot + companion computer
- [ModalAI VOXL 2](https://www.modalai.com/products/voxl-2) — autonomy SBC + flight controller
- [Raspberry Pi](https://www.raspberrypi.com/) — Pi 4, Pi 5, CM4
- [NVIDIA Embedded](https://developer.nvidia.com/embedded-computing) — Jetson Orin Nano, Orin NX
- [Khadas](https://www.khadas.com/) — VIM4, Edge2
- [BeagleBoard](https://www.beagleboard.org/) — BeagleBone Blue

### Hardware — airframes

- [Skywalker X8](https://www.banggood.com/Skywalker-X8-2120mm-Wingspan-EPO-FPV-RC-Airplane-Flying-Wing-KIT-p-1104501.html) — also see [RCGroups build thread](https://www.rcgroups.com/forums/showthread.php?1840543-Skywalker-X8-FPV); many clones on AliExpress
- [Foxtech](https://www.foxtechfpv.com/) — Nimbus VTOL, Hover series
- [Quantum Systems](https://quantum-systems.com/) — Trinity Pro (commercial VTOL)
- [Wingtra](https://wingtra.com/) — WingtraOne (commercial)
- Tarot RC — multirotor frames (vendor site intermittent — buy via [GetFPV](https://www.getfpv.com/) or AliExpress resellers)
- [Holybro X500 V2](https://holybro.com/) — pre-built quad development platform (search "X500" on holybro.com)
- [Reptile S800 V2 / Sky Shadow](https://www.banggood.com/Reptile-S800-SKY-SHADOW-820mm-Wingspan-FPV-EPP-Flying-Wing-Racer-RC-Airplane-KIT-p-1108279.html) and [Believer 1960mm](https://www.aliexpress.com/wholesale?SearchText=Believer+1960mm+UAV) — see [RCGroups Reptile build thread](https://www.rcgroups.com/forums/showthread.php?3426643-Reptile-skyshadow-S800-build) and [Believer build thread](https://www.rcgroups.com/forums/showthread.php?2984973-Believer-Twin-tractor-1960mm-Mapping-FPV-Plane-full-review-mods-owner-s-thread); Believer listings rotate frequently across AliExpress sellers

### Hardware — antennas

- [TrueRC Canada](https://www.truerc.com/) — circular polarised FPV, Singularity, AXII
- Menace RC — search via [AliExpress](https://www.aliexpress.com/wholesale?SearchText=menace+rc+antenna) (direct site intermittent)
- [Video Aerial Systems (IBCrazy)](https://videoaerialsystems.com/)
- Maple Wireless — distributed via [VAS](https://videoaerialsystems.com/) and resellers
- Pulse / Pulse Larsen — now under [Yageo Group (Pulse Electronics)](https://yageogroup.com/products/Antennas,%20RF%20&%20Microwave) — industrial UAV antennas
- [PCTEL](https://www.pctel.com/) — UAV omnis and patches
- [Mobile Mark](https://www.mobilemark.com/) — broadband UAV antennas

### Software — autopilots and middleware

- [ArduPilot project](https://ardupilot.org/) — Copter, Plane, Rover firmware
- [PX4 Autopilot](https://px4.io/) — alternative open-source autopilot
- [DronecodePX4 Foundation](https://dronecode.org/)
- [mavlink-router (Intel)](https://github.com/mavlink-router/mavlink-router)
- [MAVProxy](https://ardupilot.org/mavproxy/)
- [pymavlink](https://github.com/ArduPilot/pymavlink) — Python MAVLink library
- [MAVSDK](https://mavsdk.mavlink.io/) — modern MAVLink SDK
- [MAVLink protocol spec](https://mavlink.io/)
- [ROS 2](https://docs.ros.org/) — robot middleware for advanced autonomy
- [PX4 ROS 2 bridge (uXRCE-DDS)](https://docs.px4.io/main/en/ros2/user_guide)

### Software — video and streaming

- [GStreamer](https://gstreamer.freedesktop.org/)
- [FFmpeg](https://ffmpeg.org/)
- [OpenHD project](https://openhdfpv.org/) — open-source long-range digital FPV
- [OpenHD on GitHub](https://github.com/OpenHD) — full source repos including PixelPilot
- [WFB-NG](https://github.com/svpcom/wfb-ng) — Wi-Fi broadcast for video links (OpenHD predecessor)

### Software — mesh networking

- [B.A.T.M.A.N.-adv](https://www.open-mesh.org/projects/batman-adv/wiki/Wiki)
- [OLSR](https://www.olsr.org/) / [OLSRv2](https://datatracker.ietf.org/doc/html/rfc7181)
- [Babel routing protocol](https://www.irif.fr/~jch/software/babel/)
- [LibreMesh](https://libremesh.org/) — community mesh OS

### Software — ground stations

- [Mission Planner (ArduPilot)](https://ardupilot.org/planner/)
- [QGroundControl](https://qgroundcontrol.com/)
- [UgCS](https://www.sphengineering.com/flight-planning/ugcs)
- [Auterion Mission Control](https://auterion.com/product/mission-control/)
- [DroneDeploy](https://www.dronedeploy.com/) — survey-focused commercial
- [Skydio](https://www.skydio.com/) — enterprise drones + cloud

### Regulatory

- [EASA Civil Drones Hub](https://www.easa.europa.eu/en/domains/civil-drones-rpas)
- [EASA Easy Access Rules (UAS Regulation)](https://www.easa.europa.eu/en/document-library/easy-access-rules/easy-access-rules-unmanned-aircraft-systems-regulation-eu) — full SORA / PDRA / STS guidance
- [EU Drone Regulation 2019/947 (consolidated)](https://eur-lex.europa.eu/eli/reg_impl/2019/947/oj/eng)
- [Danish droneregler.dk](https://www.droneregler.dk/)
- [Trafikstyrelsen (Danish CAA)](https://www.trafikstyrelsen.dk/)
- [German LBA](https://www.lba.de/) — search "UAS" for current drone rules
- [UK CAA drones](https://www.caa.co.uk/drones/)
- [FAA UAS](https://www.faa.gov/uas) — hub for Part 107, Remote ID, BVLOS
- [FAA Remote ID](https://www.faa.gov/uas/getting_started/remote_id)
- [ETSI EN 300 220 (sub-GHz ISM)](https://www.etsi.org/deliver/etsi_en/300200_300299/30022001/)
- [ETSI EN 300 328 (2.4 GHz)](https://www.etsi.org/deliver/etsi_en/300300_300399/300328/)

### Reference designs and academic resources

- [Auterion documentation hub](https://docs.auterion.com/) — Skynode reference architecture
- [PX4 system architecture](https://docs.px4.io/main/en/concept/architecture)
- [ArduPilot developer wiki](https://ardupilot.org/dev/)
- [DARPA OFFSET program](https://www.darpa.mil/research/programs/offensive-swarm-enabled-tactics) — multi-drone swarm research
- [DARPA Subterranean Challenge](https://www.darpa.mil/research/challenges/subterranean) — comms-denied autonomy lessons
- [IEEE Xplore (search "BVLOS UAV relay")](https://ieeexplore.ieee.org/Xplore/home.jsp)
- [Google Scholar (BVLOS UAV relay)](https://scholar.google.com/scholar?q=BVLOS+UAV+relay+drone)
- [arXiv robotics section](https://arxiv.org/list/cs.RO/recent)

### Communities and forums

- [ArduPilot forum (Discourse)](https://discuss.ardupilot.org/)
- [PX4 forum](https://discuss.px4.io/)
- [RC Groups](https://www.rcgroups.com/)
- [DIY Drones](https://diydrones.com/)
- [r/diydrones](https://www.reddit.com/r/diydrones/)
- [r/Multicopter](https://www.reddit.com/r/Multicopter/)
- [r/UAVmapping](https://www.reddit.com/r/UAVmapping/)
- [r/AmateurRadio](https://www.reddit.com/r/amateurradio/) — for licensed-band relay builds

### Insurance and operations

- [Coverdrone (EU)](https://www.coverdrone.com/)
- [Skywatch.AI (US/global)](https://skywatch.ai/)
- [Thimble (US, formerly Verifly)](https://www.thimble.com/) — note: Thimble retired drone-specific coverage in 2023; use SkyWatch.AI for hourly drone policies

### Related documents in this repo

- [BUILD-GUIDE.md](./BUILD-GUIDE.md) — main 5" build guide
- [COMPONENTS.md](./COMPONENTS.md) — component reference
- [REGULATIONS.md](./REGULATIONS.md) — Danish/EU rules baseline
- [DISTANCE-RANGE.md](./DISTANCE-RANGE.md) — range theory for FPV builds
- [7-INCH-LONG-RANGE.md](./7-INCH-LONG-RANGE.md) — long-range FPV (shorter-range cousin of BVLOS)

---

*Last updated: 2026-06-08. This is a design reference, not legal advice. BVLOS without authorisation is illegal in most jurisdictions — see [Regulatory](#regulatory) before building.*

*Link policy: vendor homepages and project sites are preferred over specific SKU/product pages, which rot quickly in the hobby drone space. Where a product page is critical (e.g. EU regulatory documents), it's linked directly. When a vendor goes dark, search RCGroups, AliExpress, or the [Wayback Machine](https://web.archive.org/) for current stock and clones.*
