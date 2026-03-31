---
layout: documentation
title: BSPD PCB Documentation
permalink: /documentation/bspd/
---

## BSPD PCB

The BSPD PCB implements brake system plausibility processing and generates a fault output for shutdown-chain integration when plausibility conditions are violated.

> **Rule check note:** Formula SAE rules are updated regularly. This page documents design intent and rule mapping guidance only; final compliance must be verified against the current official Formula SAE rules before release.

### Referenced Formula SAE rule areas
- Brake system plausibility device behavior and fault reaction
- Hardware-based fault signaling into the shutdown path
- Deterministic behavior independent of software-only control

### Current implementation summary
- Comparator-based plausibility detection architecture
- OR-gate aggregation of fault paths before shutdown signaling
- Debug indicator strategy under review for final hardware revision

### Open design items
- Confirm final comparator family for automotive environment robustness
- Confirm final logic-gate part selection and thresholds for worst-case corners
