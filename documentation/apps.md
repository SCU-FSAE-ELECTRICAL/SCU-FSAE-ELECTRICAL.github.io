---
layout: documentation
title: APPS PCB Documentation
permalink: /documentation/apps/
---

## APPS PCB

The APPS PCB conditions APPS and brake sensor signals for the control electronics and supports plausibility checks used by the shutdown logic.

> **Rule check note:** Formula SAE rules are updated regularly. The references below reflect the team mapping at the time of writing and must be re-validated against the current official rulebook before design freeze and competition.

### Referenced Formula SAE rule areas
- APPS sensor plausibility and signal handling requirements
- Brake system encoder/sensor signal interface requirements
- Open-circuit detectability for critical pedal/sensor inputs

### Current implementation summary
- Uses resistor dividers to scale sensor voltages into the safe range for the MCU
- Provides 3.3 V and 5 V rails as needed by sensor and logic domains
- Includes pull-down resistors on sensor inputs to improve open-circuit detection

### Design status notes
- Evaluate alternate regulator package selection for final board revision
