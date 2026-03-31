# Voltage Indicator PCB




# Design
---

**Rules from FSAE**
> EV.5.7 Voltage Indicator
> - Each Tractive Battery Pack must have a prominent indicator when High Voltage T.9.1.1 is present at the vehicle side of the IRs
> - EV.5.7.1 The Voltage Indicator must always function, including when the Tractive Battery Pack is disconnected or removed
> - EV.5.7.2 The voltage present at the vehicle side of the Isolation Relays must directly control and power the Voltage Indicator using hard wired electronics with no software control
> - EV.5.7.3 The control signal which closes the IRs must not control the Voltage Indicator
> - EV.5.7.4 The Voltage Indicator must
> a. Be located where it is clearly visible when connecting/disconnecting the Tractive Battery Pack connections
> b. Be labeled “High Voltage Present”


|Component|Model/Value|Data Sheet|
|--|--|--|
|Linear Regulator|LR8|[https://ww1.microchip.com/downloads/en/DeviceDoc/20005399B.pdf](https://ww1.microchip.com/downloads/en/DeviceDoc/20005399B.pdf)|
|R1|1kOhm CF14JT1K00|https://www.digikey.com/en/products/detail/stackpole-electronics-inc/CF14JT1K00/1741314|
|R2|18.2kOhm YR1B18K2CC|https://www.digikey.com/en/products/detail/te-connectivity-passive-product/YR1B18K2CC/18101816?curr=usd|
|Capacitor|1uF|https://www.chemi-con.co.jp/products/relatedfiles/capacitor/catalog/NTDA0-e.PDF|
|LED|12V Led On Hand|||
|High Voltage Connector|VL Connecotr|https://www.jst-mfg.com/product/pdf/eng/eVL1.pdf|

**Calculations**

For resistor values:

LR8, Vmax = 450V

Vout = 1.20V(1+R2/R1)+Iadj*R2

1.20V(1+18.2kOhm/1kOhm)+15uA\*1kOhm

= 23.313V

# Schematic
---
Based on use case found in LR8 Linear Regualtor Documentation adjusted for an output of around 24V:
![Example Schematic](img/Example.jpg)

![Our Schematic](img/Schematic.PNG)

# Board
---
![Our Board](img/Board.PNG)

# Action Item List
**1/17/2026 Check LR8 for Power Disipation**
- 1-2mA LED?
- Large Resistor Design?
- Get reisstors for 450V

**1/22/2026 Notes**
- Still check for panel mount 1-2mA panel mount LED
    - Add resistor before LED? (Could use 0 Ohms if it doesn't work)
- Add more metal around LR
- Add vias to rear ground plane
- Move caps away from LR