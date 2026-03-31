---
layout: documentation
title: Voltage Indicator PCB Documentation
permalink: /documentation/voltage-indicator/
---

## Voltage Indicator PCB

The Voltage Indicator PCB provides a hardware-powered high-voltage-present indication at the vehicle side of the isolation relays.

> **Rule check note:** Formula SAE rules are updated regularly. References below are team guidance and must be verified against the latest official rulebook before final release.

### Referenced Formula SAE rule areas

- High-voltage-present indication at the vehicle side of the isolation relays
- Indicator operation independent of software control
- Indicator visibility and required labeling near pack connect/disconnect operations

### Current implementation summary

- Indicator power and control derive directly from tractive-system voltage through hard-wired circuitry
- Dedicated regulator path used for indicator drive
- Labeling and placement are intended for clear visibility during pack service operations

### Core components
| Component | Model / Value | Data Sheet |
| -- | -- | -- |
| Linear Regulator | LR8 | [Microchip LR8 Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/20005399B.pdf) |
| R1 | 1 kΩ (CF14JT1K00) | [DigiKey](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/CF14JT1K00/1741314) |
| R2 | 18.2 kΩ (YR1B18K2CC) | [DigiKey](https://www.digikey.com/en/products/detail/te-connectivity-passive-product/YR1B18K2CC/18101816?curr=usd) |
| Capacitor | 1 µF | [Chemi-Con](https://www.chemi-con.co.jp/products/relatedfiles/capacitor/catalog/NTDA0-e.PDF) |
| Indicator LED | Panel-mount LED candidate | Team selection in progress |
| High-voltage connector | JST VL series | [JST VL Series](https://www.jst-mfg.com/product/pdf/eng/eVL1.pdf) |

### Calculation snapshot

For the current regulator divider values:

`Vout = 1.20V * (1 + R2/R1) + Iadj * R2`

Using `R1 = 1 kΩ` and `R2 = 18.2 kΩ` gives approximately `23.3 V` target output.

### Open design items

- Confirm thermal margin and power dissipation on LR8 at worst-case pack voltage
- Finalize LED operating current target and any required series resistance
- Finalize creepage/clearance and high-voltage-rated passive component selection
