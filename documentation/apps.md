**Description**
- Implements rules T.4.2.3, T.4.2.7-11
- Has a 1/2 current divider for BSEs to shift logic down to safe range for teensy (5V -> 2.5V)
- Has current dividers for both APPS sensors using different transfer functions(T.4.2.3)
- Supplys 5V power to BSEs and 3.3V power to APPS using a linear regulator
    - Different because teensy is 3.3V logic so its easier to just supply 3.3V power but the BSEs need
      5V because the BSPD requires that they do
- Pull down resistors are on all sensors to be able to detect open circuits

**Notes 1/22/2026**
- Get smaller regulator T092