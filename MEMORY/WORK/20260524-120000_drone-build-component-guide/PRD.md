---
task: Drone build guide with component trade-offs
slug: 20260524-120000_drone-build-component-guide
effort: standard
phase: complete
progress: 10/10
mode: interactive
started: 2026-05-24T12:00:00Z
updated: 2026-05-24T12:00:30Z
---

## Context

User wants to build their own drone for outdoor use, starting from scratch with soldering. They need:
1. Beginner-friendly recommendations for a first DIY drone build
2. Soldering guidance specific to drone assembly
3. Component trade-off analysis across distance, speed, and cost dimensions

This is educational/advisory — the user is learning the technology while building.

### Risks
- Recommending components that are outdated or discontinued
- Overwhelming a beginner with too many options
- Not addressing safety/legal considerations for outdoor flight

## Criteria

- [x] ISC-1: Recommended frame size and type for outdoor beginner build provided
- [x] ISC-2: Flight controller options with pros/cons listed
- [x] ISC-3: Motor recommendations with KV ratings explained
- [x] ISC-4: ESC options and sizing guidance provided
- [x] ISC-5: Battery chemistry and capacity trade-offs covered
- [x] ISC-6: Radio transmitter/receiver options for range covered
- [x] ISC-7: Propeller sizing and pitch trade-offs explained
- [x] ISC-8: Soldering tools and tips for drone assembly listed
- [x] ISC-9: Cost breakdown with budget tiers provided
- [x] ISC-10: Distance vs speed vs flight time trade-off matrix included

## Decisions

- Focused on 5" quadcopter as the standard beginner outdoor platform
- Recommended ExpressLRS over Crossfire/FrSky (clear 2025 winner on value)
- Provided 3 budget tiers with specific shopping lists
- Included regulations (US/EU/UK) since outdoor flying requires awareness
- Created 7 separate documents for easy reference during build

## Verification

- ISC-1: COMPONENTS.md section 1 covers frames with 6 specific models
- ISC-2: COMPONENTS.md section 2 covers FCs with processor comparison table
- ISC-3: COMPONENTS.md section 3 covers motors with KV explanation and 6 models
- ISC-4: COMPONENTS.md section 4 covers ESCs with amp sizing and firmware comparison
- ISC-5: COMPONENTS.md section 5 covers batteries with 4S/6S comparison and capacity curves
- ISC-6: COMPONENTS.md section 6 covers radio with ELRS/Crossfire/FrSky comparison
- ISC-7: COMPONENTS.md section 8 covers props with blade count, pitch, and material
- ISC-8: SOLDERING-GUIDE.md covers tools, techniques, joint types, and practice progression
- ISC-9: BUDGET-TIERS.md provides 3 complete builds with line-item costs
- ISC-10: TRADE-OFFS.md provides the iron triangle analysis with quantified impacts
