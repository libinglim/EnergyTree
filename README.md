# EnergyTree

A biomimetic wind energy harvester inspired by trees and leaves. Instead of a traditional turbine, EnergyTree uses PVDF (polyvinylidene fluoride) piezoelectric film strips mounted on a tree-like frame — much like leaves — that flap and collide in the wind to generate electricity.

## Overview

Conventional small-scale wind turbines lose efficiency in turbulent, low-speed, or gusty conditions — exactly the conditions found in urban and near-ground environments. EnergyTree takes a different approach: it mimics how leaves flutter and brush against each other in the wind, using flexible PVDF piezoelectric strips as "leaves" that generate small voltage spikes from mechanical strain and inter-strip collisions.

**Core concept:**
- PVDF film strips (LDT0-028K) are mounted on a branching frame, spaced ~8–12mm apart to intentionally induce inter-strip collisions — a phenomenon referred to here as **coupled Multiple Impact Excitation (MIE)**.
- Wind-driven flapping and collisions strain the piezoelectric film, producing small AC voltage spikes.
- Each strip's output is rectified (AC → DC) and combined in series across the tree structure.
- Using a bridge rectifier, the strip's output is stored in a capacitor for later use or discharge.
- The design is intended to scale: at larger scale, one **LTC3588** energy harvesting IC per branch (with a single blocking diode per strip) replaces discrete bridge rectifiers for more efficient power conditioning.

This project is built on and extends existing academic work on PVDF wind energy harvesting (notably an ASME Fluids Engineering 2022 paper on dimensional effects of polymer piezoelectric films), using it as a foundation rather than a limitation for independent design work.

## Timeline

**July 10** — Completed a working proof-of-concept circuit in Tinkercad, verifying the core energy harvesting concept. The simulation used two function generators (simulating PVDF strips flapping in the wind) as AC voltage sources, each feeding into its own full bridge rectifier to convert AC to DC. The rectified outputs were connected in series and fed into a shared capacitor for storage. The simulation validated a stable **3V DC output** at 1.5V per source.

## Roadmap

- [ ] LTspice simulation of the circuit for deeper electrical validation
- [ ] LTC3588 datasheet deep-dive for scalable per-branch power conditioning
- [ ] KiCad PCB design
- [ ] Circuit fundamentals review
- [ ] Review additional research papers on PVDF/piezoelectric wind harvesting
- [ ] Purchase parts (PVDF strips, diode kit, capacitors, breadboard, jumper wires) and begin physical prototyping

## Parts List (Phase 1 prototype)

| Part | Notes |
|---|---|
| LDT0-028K PVDF strips (×2) | Newark Electronics |
| Diode assortment kit (incl. 1N5817) | For bridge rectification |
| 100µF 25V electrolytic capacitors | Energy storage |
| 830-point breadboard + jumper wires | BOJACK kit |
| Alligator clip cables | For interfacing with film strips |

## Status

**Phase 1: Proof-of-concept circuit validation** — Tinkercad simulation complete. Moving toward LTspice validation and physical breadboard prototyping.
