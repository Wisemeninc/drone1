# Shopping Links — EU / Europe

Quick-access shopping links for all components across both budget tiers. Includes EU-based FPV specialty shops, Amazon.de, and AliExpress search links.

> **Tip:** EU FPV shops often have better prices than Amazon.de for drone-specific parts, plus expert product descriptions and compatibility notes. AliExpress is cheapest but ships 2-4 weeks from China.

---

> **Note on prices:** EU shop prices quoted in this guide are in EUR and **include VAT** (19 % at the German shops). The USD figures in the build tables are AliExpress/US-style ex-VAT prices, converted where needed at roughly **1.1 USD/EUR** (September 2026). The two are not directly comparable — an EU price that looks 20 % higher may be identical once VAT is stripped.

> **Note on the EU Shop column:** n-Factory's on-site search is JavaScript-driven and has no linkable URL — a search link silently lands on an unrelated product, so those entries point at the shop front page. Search there using the component name in column 2. Rotorama, CopterFarm and FPV24 search links load, but **read the product titles before you trust any of them** — FPV24 shows related items when it has no exact match, CopterFarm matches "BN-220" to 2207 motors, and Rotorama silently rewrites queries (see below).

> **⚠️ Two components were substituted in September 2026** because no EU FPV shop checked (Rotorama, FlyingMachines, CopterFarm, FPV24) still stocks them. Both remain available on AliExpress if you specifically want them.
>
> | Was | Now | Why |
> |-----|-----|-----|
> | DAL Cyclone T5040C props | **Gemfan 51466 V2** | DAL props still sold (e.g. DAL 4045) but not this model. Gemfan 51466 verified in stock at FPV24 (as *Gemfan Hurricane MCK 51466-3*) and on Amazon.de to Denmark. Budget tier rises ~$5-7. |
> | Mamba F50 Pro 4-in-1 ESC | **T-Motor F55A Pro II** (30.5×30.5 base variant only) | Mamba F50 Pro is aging out of the EU market. FlyingMachines *lists* the F55A Pro II (**€69.95 incl. VAT ≈ $75**) but all variants were **out of stock when checked** — so neither the old part nor the new one is on an EU shelf; the F55A is the better part and is at least backorderable from an EU shop. BL32 preloaded, no flashing. The *ULTRA* variant is 20×20 and does not fit this stack. Mid-range FC+ESC rises to $110-130. |
> | Rush Tank Ultimate Plus VTX | **TBS Unify Pro32 Nano V1.1** | No EU shop checked stocks RushFPV — FlyingMachines returns zero for "Rush". Priced from two shops: **€31,90** (FlyingMachines — listed but **out of stock** when checked) and **€33,80** (FPV24 — **in stock**), so about $35-38 at ~1.1 USD/EUR — near-identical to the Rush Tank's $35-40, though see the pricing note below on VAT. Two things the Rush Tank did not make you think about: it is a **20×20** board, not 30×30; and it is **5V input only (4.5–5.5V)** — power from the FC's 5V pad, never VBAT or 9V — the Rush Tank ran happily on VBAT, this will not. Its antenna connector is **u.FL**, so the MMCX Lollipop in the old list needs a u.FL→SMA pigtail (row 9a). Like every VTX it is switchable — the swap reason is stock, not power; set 25mW on a legal channel as you would on any part. AliExpress still has the Rush Tank. |
>
> The AliExpress-only build in [SHOPPING-LIST-ALIEXPRESS-QUAD.md](./SHOPPING-LIST-ALIEXPRESS-QUAD.md) still lists the Mamba F50 Pro, which is correct — AliExpress stocks it.

> **‡ No EU specialty shop checked stocks the BN-220 by name** — Rotorama, FlyingMachines and FPV24 return nothing relevant, and CopterFarm's "3 results" are 2207 brushless motors. Buy it from Amazon.de (verified to return BN-220 GPS modules) or AliExpress.

> **† Amazon.de does not carry the T-Motor F55A Pro II.** Searching for it there returns brushed car ESCs and unrelated motors, so that cell is blank rather than pointing at a search that would mislead you. Buy it from FlyingMachines or AliExpress.

> **Search-relevance caveats (checked September 2026), for the two rows where the shop's own search fights you:**
>
> - **Leaded solder (row 21)** — Amazon.de's solder results skew heavily *bleifrei* (lead-free) whatever you search. The query is now `Lötzinn verbleit Sn63Pb37 0,8mm`, which does surface the right product (Rosfix Sn63Pb37), but check the listing actually says **Sn63Pb37** before ordering — several top results are still lead-free.
> - **Rotorama rewrites queries.** Searching "Rush Tank" there silently becomes "Rush" and returns Emax Avan Rush props and Radiomaster *Crush* radios. If you use Rotorama, check the page hasn't changed your search term — it says so in small print above the results.

---

## EU FPV Specialty Shops (Recommended)

These are dedicated FPV shops based in Europe — fast EU shipping, correct stock, knowledgeable support.

| Shop | Country | Free Shipping | Strengths | URL |
|------|---------|--------------|-----------|-----|
| **n-Factory.de** | Germany | Over €100 | Huge selection, daily shipping before 14:00, 1-3 day delivery in DE | [n-factory.de](https://n-factory.de) |
| **Rotorama** | Czech Republic (ships EU) | Varies | Frames, stacks, motors, batteries — loyalty program, beginner tutorials | [rotorama.de](https://www.rotorama.de) |
| **FlyingMachines.de** | Germany | Over €100 | Large catalog (FPV + DJI), LiPo specialist, fast DE shipping | [flyingmachines.de](https://www.flyingmachines.de) |
| **CopterFarm** | Germany | Over €120 | Small, curated catalogue (one GPS SKU). Search tokenises model numbers loosely — "BN-220" returns 2207 motors — so read the product titles | [copterfarm.de](https://www.copterfarm.de) |
| **FPV24** | Germany | Varies | Huge catalog, DJI dealer, ships fast — search is fuzzy, check the model number | [fpv24.com](https://www.fpv24.com) |
| **Team BlackSheep** | Global (EU warehouse) | Varies | TBS products (Crossfire, frames, VTX), Source One frames | [team-blacksheep.com](https://www.team-blacksheep.com) |
| **Eleshop.eu** | Netherlands | Varies | Pinecil, Pine64 products, soldering tools | [eleshop.eu](https://eleshop.eu) |
| **SpeedyBee Official** | China (EU stock on Amazon) | Varies | Direct SpeedyBee FC/ESC, best prices on their products | [speedybee.com](https://www.speedybee.com) |
| **RadioMaster Official** | China (EU distributors) | Varies | Direct RadioMaster radios, receivers, TX modules | [radiomasterrc.com](https://www.radiomasterrc.com) |

> **Note:** drone-fpv-racer.com (France) is a popular EU shop but currently has sales suspended due to a warehouse fire. Check back periodically — the site is open for browsing/research.

---

## Budget Build (~€500-630) — Search Links

### The Quad

| # | Component | AliExpress Search | Amazon.de Search | EU Shop Search |
|---|-----------|------------------|-----------------|----------------|
| 1 | Source One V5 Frame (5") | [AliExpress](https://www.aliexpress.com/w/wholesale-Source-One-V5-frame-5-inch.html) | [Amazon.de](https://www.amazon.de/s?k=Source+One+V5+Frame+5+Zoll) | [TBS direct](https://www.team-blacksheep.com/shop/cat:sourceone) |
| 2 | SpeedyBee F405 V4 Stack (FC + ESC) | [AliExpress](https://www.aliexpress.com/w/wholesale-SpeedyBee-F405-V4-stack.html) | [Amazon.de](https://www.amazon.de/s?k=SpeedyBee+F405+V4) | [n-Factory — search on site](https://n-factory.de/) |
| 3 | Emax Eco II 2306 2400KV motors | [AliExpress](https://www.aliexpress.com/w/wholesale-Emax-Eco-II-2306-2400KV.html) | [Amazon.de](https://www.amazon.de/s?k=Emax+Eco+II+2306+2400KV) | [n-Factory — search on site](https://n-factory.de/) |
| 4 | Gemfan 51466 V2 props | [AliExpress](https://www.aliexpress.com/w/wholesale-Gemfan-51466-V2-propeller.html) | [Amazon.de](https://www.amazon.de/s?k=Gemfan+51466+Propeller) | [FPV24](https://www.fpv24.com/de/search?search=Gemfan+51466) |
| 5 | SpeedyBee TX800 VTX | [AliExpress](https://www.aliexpress.com/w/wholesale-SpeedyBee-TX800-VTX.html) | [Amazon.de](https://www.amazon.de/s?k=SpeedyBee+TX800+VTX) | [n-Factory — search on site](https://n-factory.de/) |
| 6 | Foxeer Razer Mini camera | [AliExpress](https://www.aliexpress.com/w/wholesale-Foxeer-Razer-Mini-FPV-camera.html) | [Amazon.de](https://www.amazon.de/s?k=Foxeer+Razer+Mini+FPV+Kamera) | [n-Factory — search on site](https://n-factory.de/) |
| 7 | RadioMaster RP3 V2 ELRS receiver (antenna diversity) | [AliExpress](https://www.aliexpress.com/w/wholesale-RadioMaster-RP3-V2-ELRS-2.4GHz-receiver.html) | [Amazon.de](https://www.amazon.de/s?k=RadioMaster+RP3+V2+ELRS) | [Rotorama](https://www.rotorama.de/hledani?q=RadioMaster+RP3) |
| 8 | TBS Triumph antenna (RHCP SMA) | [AliExpress](https://www.aliexpress.com/w/wholesale-TBS-Triumph-antenna-RHCP-SMA.html) | [Amazon.de](https://www.amazon.de/s?k=TBS+Triumph+Antenne+RHCP+SMA) | [TBS direct](https://www.team-blacksheep.com/shop/cat:antennas) |
| 9 | CNHL 1300mAh 4S 100C LiPo (x3) | [AliExpress](https://www.aliexpress.com/w/wholesale-CNHL-1300mAh-4S-100C.html) | [Amazon.de](https://www.amazon.de/s?k=CNHL+1300mAh+4S+100C+XT60) | [n-Factory — search on site](https://n-factory.de/) |
| 10 | BN-220 GPS module | [AliExpress](https://www.aliexpress.com/w/wholesale-BN-220-GPS-module.html) | [Amazon.de](https://www.amazon.de/s?k=BN-220+GPS+Modul) | — ‡ |
| 11 | Low ESR capacitor 35V 1000uF | [AliExpress](https://www.aliexpress.com/w/wholesale-low-ESR-capacitor-35V-1000uF.html) | [Amazon.de](https://www.amazon.de/s?k=Low+ESR+Kondensator+35V+1000uF) | — |
| 12 | Buzzer 5V with wire | [AliExpress](https://www.aliexpress.com/w/wholesale-FPV-buzzer-5V-drone.html) | [Amazon.de](https://www.amazon.de/s?k=FPV+Buzzer+5V+Drohne) | — |

### Support Equipment

| # | Component | AliExpress Search | Amazon.de Search | EU Shop Search |
|---|-----------|------------------|-----------------|----------------|
| 13 | RadioMaster Pocket (ELRS) | [AliExpress](https://www.aliexpress.com/w/wholesale-RadioMaster-Pocket-ELRS.html) | [Amazon.de](https://www.amazon.de/s?k=RadioMaster+Pocket+ELRS) | [n-Factory — search on site](https://n-factory.de/) |
| 14 | Eachine EV800D goggles | [AliExpress](https://www.aliexpress.com/w/wholesale-Eachine-EV800D-FPV-goggles.html) | [Amazon.de](https://www.amazon.de/s?k=Eachine+EV800D+FPV+Brille) | [FlyingMachines](https://www.flyingmachines.de/search?q=EV800D) |
| 15 | ToolkitRC M6 charger | [AliExpress](https://www.aliexpress.com/w/wholesale-ToolkitRC-M6-charger.html) | [Amazon.de](https://www.amazon.de/s?k=ToolkitRC+M6+Ladeger%C3%A4t) | [n-Factory — search on site](https://n-factory.de/) |
| 16 | 12V/10A DC power supply | — | [Amazon.de](https://www.amazon.de/s?k=12V+10A+Netzteil+DC) | — |
| 17 | LiPo safe bag | [AliExpress](https://www.aliexpress.com/w/wholesale-LiPo-safe-bag-large.html) | [Amazon.de](https://www.amazon.de/s?k=LiPo+Sicherheitstasche) | — |

### Soldering Kit

| # | Component | AliExpress Search | Amazon.de Search | EU Shop |
|---|-----------|------------------|-----------------|---------|
| 18 | Pinecil V2 soldering iron | [AliExpress](https://www.aliexpress.com/w/wholesale-Pinecil-V2-soldering-iron.html) | [Amazon.de](https://www.amazon.de/s?k=Pinecil+V2+L%C3%B6tkolben) | [Eleshop.eu (direct)](https://eleshop.eu/pinecil-smart-mini-portable-soldering-iron.html) |
| 19 | Pinecil Fine Tip Set | — | — | [Eleshop.eu (direct)](https://eleshop.eu/pinecil-short-soldering-tip-set-fine.html) |
| 20 | USB-C PD 65W+ power supply | — | [Amazon.de](https://www.amazon.de/s?k=USB-C+PD+65W+Netzteil) | — |
| 21 | Solder 63/37 0.8mm (leaded) | [AliExpress](https://www.aliexpress.com/w/wholesale-solder-wire-63-37-0.8mm-rosin.html) | [Amazon.de](https://www.amazon.de/s?k=L%C3%B6tzinn+verbleit+Sn63Pb37+0%2C8mm) | — |
| 22 | No-clean flux paste | [AliExpress](https://www.aliexpress.com/w/wholesale-no-clean-flux-paste-syringe.html) | [Amazon.de](https://www.amazon.de/s?k=Flussmittel+Paste+no+clean) | — |
| 23 | Solder wick 2.5mm | [AliExpress](https://www.aliexpress.com/w/wholesale-solder-wick-2.5mm-desoldering.html) | [Amazon.de](https://www.amazon.de/s?k=Entl%C3%B6tlitze+2%2C5mm) | — |
| 24 | Brass wool tip cleaner | — | [Amazon.de](https://www.amazon.de/s?k=Messing+Wolle+L%C3%B6tspitze+Reiniger) | — |
| 25 | Smoke stopper (XT60) | [AliExpress](https://www.aliexpress.com/w/wholesale-smoke-stopper-XT60-drone.html) | [Amazon.de](https://www.amazon.de/s?k=Smoke+Stopper+XT60+FPV) | [n-Factory — search on site](https://n-factory.de/) |

---

## Mid-Range Build (~€800-1160) — Search Links

### The Quad

| # | Component | AliExpress Search | Amazon.de Search | EU Shop Search |
|---|-----------|------------------|-----------------|----------------|
| 1 | GEPRC Mark5 Frame (5", HD) | [AliExpress](https://www.aliexpress.com/w/wholesale-GEPRC-Mark5-frame-5-inch.html) | [Amazon.de](https://www.amazon.de/s?k=GEPRC+Mark5+Frame+5+Zoll) | [n-Factory — search on site](https://n-factory.de/) |
| 2 | SpeedyBee F7 V3 Flight Controller | [AliExpress](https://www.aliexpress.com/w/wholesale-SpeedyBee-F7-V3-flight-controller.html) | [Amazon.de](https://www.amazon.de/s?k=SpeedyBee+F7+V3+Flight+Controller) | [n-Factory — search on site](https://n-factory.de/) |
| 3 | T-Motor F55A Pro II 4-in-1 ESC (55A BL32) | [AliExpress](https://www.aliexpress.com/w/wholesale-T-Motor-F55A-Pro-II-ESC.html) | — † | [FlyingMachines](https://www.flyingmachines.de/search?q=F55A) |
| 4 | iFlight XING2 2306 1900KV (6S) x4 | [AliExpress](https://www.aliexpress.com/w/wholesale-iFlight-XING2-2306-1900KV.html) | [Amazon.de](https://www.amazon.de/s?k=iFlight+XING2+2306+1900KV) | [n-Factory — search on site](https://n-factory.de/) |
| 5 | Gemfan 51466 V2 props | [AliExpress](https://www.aliexpress.com/w/wholesale-Gemfan-51466-V2-propeller.html) | [Amazon.de](https://www.amazon.de/s?k=Gemfan+51466+V2+Propeller) | [n-Factory — search on site](https://n-factory.de/) |
| 6 | TBS Unify Pro32 Nano V1.1 VTX (run at 25mW on a legal channel; **5V input only (4.5–5.5V)** — power from the FC's 5V pad, never VBAT or 9V; u.FL) | [AliExpress](https://www.aliexpress.com/w/wholesale-TBS-Unify-Pro32-Nano-VTX.html) | [Amazon.de](https://www.amazon.de/s?k=TBS+Unify+Pro32+Nano+VTX) | [FlyingMachines](https://www.flyingmachines.de/search?q=Unify) |
| 7 | Caddx Ratel 2 camera | [AliExpress](https://www.aliexpress.com/w/wholesale-Caddx-Ratel-2-FPV-camera.html) | [Amazon.de](https://www.amazon.de/s?k=Caddx+Ratel+2+FPV+Kamera) | [n-Factory — search on site](https://n-factory.de/) |
| 8 | RadioMaster RP1 ELRS receiver | [AliExpress](https://www.aliexpress.com/w/wholesale-RadioMaster-RP1-ELRS-receiver.html) | [Amazon.de](https://www.amazon.de/s?k=RadioMaster+RP1+ELRS+2.4GHz) | [n-Factory — search on site](https://n-factory.de/) |
| 9 | Foxeer Lollipop V4 antenna (RHCP **SMA**) | [AliExpress](https://www.aliexpress.com/w/wholesale-Foxeer-Lollipop-V4-SMA-RHCP.html) | [Amazon.de](https://www.amazon.de/s?k=Foxeer+Lollipop+V4+SMA+RHCP) | [n-Factory — search on site](https://n-factory.de/) |
| 9a | TBS u.FL → SMA pigtail (for the Unify Nano) | — | — | [FPV24](https://www.fpv24.com/de/search?search=Unify+Pigtail) |
| 10 | GNB 1500mAh 6S 120C LiPo (x4) | [AliExpress](https://www.aliexpress.com/w/wholesale-GNB-1500mAh-6S-120C-XT60.html) | [Amazon.de](https://www.amazon.de/s?k=GNB+1500mAh+6S+120C+XT60) | [n-Factory — search on site](https://n-factory.de/) |
| 11 | BN-220 GPS module | [AliExpress](https://www.aliexpress.com/w/wholesale-BN-220-GPS-module.html) | [Amazon.de](https://www.amazon.de/s?k=BN-220+GPS+Modul) | — ‡ |
| 12 | Low ESR capacitor 35V 1000uF | [AliExpress](https://www.aliexpress.com/w/wholesale-low-ESR-capacitor-35V-1000uF.html) | [Amazon.de](https://www.amazon.de/s?k=Low+ESR+Kondensator+35V+1000uF) | — |

### Support Equipment

| # | Component | AliExpress Search | Amazon.de Search | EU Shop Search |
|---|-----------|------------------|-----------------|----------------|
| 13 | RadioMaster TX15 Max (ELRS) | [AliExpress](https://www.aliexpress.com/w/wholesale-RadioMaster-TX15-Max-ELRS.html) | [Amazon.de](https://www.amazon.de/s?k=RadioMaster+TX15+Max+ELRS) | [n-Factory — search on site](https://n-factory.de/) |
| 14 | Skyzone Cobra X V2 goggles | [AliExpress](https://www.aliexpress.com/w/wholesale-Skyzone-Cobra-X-V2-goggles.html) | [Amazon.de](https://www.amazon.de/s?k=Skyzone+Cobra+X+V2+FPV+Brille) | [FlyingMachines](https://www.flyingmachines.de/search?q=Skyzone+Cobra) |
| 15 | ToolkitRC M7 charger (200W) | [AliExpress](https://www.aliexpress.com/w/wholesale-ToolkitRC-M7-charger-200W.html) | [Amazon.de](https://www.amazon.de/s?k=ToolkitRC+M7+Ladeger%C3%A4t+200W) | [n-Factory — search on site](https://n-factory.de/) |
| 16 | 24V/10A DC power supply | — | [Amazon.de](https://www.amazon.de/s?k=24V+10A+Netzteil+DC+XT60) | — |
| 17 | LiPo safe bag (large) | [AliExpress](https://www.aliexpress.com/w/wholesale-LiPo-safe-bag-large.html) | [Amazon.de](https://www.amazon.de/s?k=LiPo+Sicherheitstasche+gro%C3%9F) | — |
| 18 | Smoke stopper (XT60) | [AliExpress](https://www.aliexpress.com/w/wholesale-smoke-stopper-XT60-drone.html) | [Amazon.de](https://www.amazon.de/s?k=Smoke+Stopper+XT60+FPV) | [n-Factory — search on site](https://n-factory.de/) |

### Soldering Kit (same as budget, add these upgrades)

| # | Component | AliExpress Search | Amazon.de Search | EU Shop |
|---|-----------|------------------|-----------------|---------|
| 19 | QuadHands helping hands | — | [Amazon.de](https://www.amazon.de/s?k=QuadHands+helping+hands+L%C3%B6ten) | — |
| 20 | Silicone soldering mat | [AliExpress](https://www.aliexpress.com/w/wholesale-silicone-soldering-mat-heat-resistant.html) | [Amazon.de](https://www.amazon.de/s?k=Silikon+L%C3%B6tmatte+hitzebeständig) | — |
| 21 | Kapton tape 10mm | [AliExpress](https://www.aliexpress.com/w/wholesale-Kapton-tape-10mm-heat-resistant.html) | [Amazon.de](https://www.amazon.de/s?k=Kapton+Klebeband+10mm) | — |

---

## Price Comparison Strategy

| Source | Typical Savings | Shipping Time | Best For |
|--------|----------------|---------------|----------|
| **AliExpress** | 20-40% cheaper | 2-4 weeks | Motors, props, frames, ESCs, small electronics |
| **Amazon.de** | Standard prices | 1-2 days (Prime) | Batteries (hazmat shipping), tools, power supplies, quick replacements |
| **n-Factory.de** | 5-15% vs Amazon | 1-3 days (DE) | Everything FPV — best single-shop EU experience |
| **Rotorama** | Similar to n-Factory | 3-5 days (from CZ) | Frames, stacks, good battery selection |
| **FlyingMachines.de** | Standard | 1-3 days (DE) | Goggles, DJI products, chargers |
| **TBS Direct** | Cheapest for TBS | 1-2 weeks | Source One frame, TBS antennas, Crossfire |

### Recommended Order Strategy

1. **Order first from AliExpress** (2-4 week shipping): Frame, motors, FC/ESC stack, VTX, camera, receiver, antenna, props, capacitors, GPS
2. **Order from Amazon.de** (arrives in days): Batteries, charger, power supply, LiPo bag, soldering supplies, tools, smoke stopper
3. **Order from EU FPV shop** (1-3 days): Anything out of stock on AliExpress, or if you want it faster — n-Factory.de is the best one-stop shop

> **Important:** LiPo batteries ship much faster from Amazon.de/EU shops because they can't air-ship from China. Always buy batteries locally.

---

## Quick Links — Manufacturer Direct Stores

Some manufacturers sell direct (sometimes cheaper, sometimes bundles):

| Manufacturer | Store URL | Products |
|--------------|-----------|----------|
| SpeedyBee | [speedybee.com](https://www.speedybee.com) | FC, ESC, stacks, VTX |
| RadioMaster | [radiomasterrc.com](https://www.radiomasterrc.com) | Radios, receivers, TX modules |
| iFlight | [iflight-rc.com](https://www.iflight-rc.com) | Motors, frames, stacks |
| GEPRC | [geprc.com](https://www.geprc.com) | Frames, BNF drones, stacks |
| Caddx | [caddxfpv.com](https://www.caddxfpv.com) | FPV cameras, DJI air units |
| Foxeer | [foxeer.com](https://www.foxeer.com) | Cameras, antennas, VTX |
| GNB/Gaoneng | [gaonengbattery.com](https://www.gaonengbattery.com) | LiPo batteries |
| CNHL | [chinahobbyline.com](https://www.chinahobbyline.com) | LiPo batteries |
| Gemfan | [gemfanhobby.com](https://www.gemfanhobby.com) | Propellers |

---

## Notes

- **VAT/Import:** Orders from AliExpress under €150 include VAT at checkout (IOSS system). No surprise customs fees.
- **Returns:** Amazon.de has the easiest returns. AliExpress buyer protection works but is slower (15-30 day dispute process).
- **Availability:** AliExpress stock is more stable for niche FPV parts. Amazon.de listings come and go.
- **Batteries:** Never ship LiPo from China by air — always buy from EU stock (Amazon.de, n-Factory, Rotorama).
