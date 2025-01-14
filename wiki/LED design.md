# LED design

A bare red LED powered by VCC and controlled by a PWM pin through a MOSFET.

-   MCU: 3.3 volts for VSS and PWM
-   LED: Red 5 mm (or yellow, but not blue)
    -   Vd: 2.0 volts, range 1.8–2.2
    -   I: 16–18 mA suggested, max 20
    -   Through hole pads for wires to case, silk logo.
    -   SMT on board is less useful.
-   Resistor on LED drain
    -   xx Ohms
    -   Thorough hole wide, for easy matching to LED changes.
-   MOSFET
    -   SMT
    -   100 mA max, generously 
-   Resistor anti ring on MOSFET
    -   SMT
    -   likely


VCC -> LED -> resistor -> D MOSFET S     -> GND
PWM        -> resistor ->   MOSFET gate
