# Examples of keyboards with dumb LEDs


##  [Klotz 0.2](https://github.com/GEIGEIGEIST/KLOTZ/tree/main)

-   3 mm LEDs driven directly from Nice!nano pins 3, 4, 5.
-   Pin -> LED -> 220 Ohm -> GND

## [Nice!Nano](https://nicekeyboards.com/docs/nice-nano/pinout-schematic/)

-   On board LED driven directly
-   Pin -> LED -> 1k Ohm -> GND

## Revxlp

https://gitlab.com/lpgalaxy/revxlp

Back light

-   MOSFET AO3416 SOT-23  (a JLC extended part)
-   Pull down resistor 1206 4.7k Ω
-   No gate resistor
-   LEDs PLCC-2 x42
-   resistors 1206 x42

## [ZMK Uno]()

Power run through transistor.

    -   A 5v logic board
    -   3.3v -> LED -> 100 Ω -> transistor -> GND, pwm pin with 4.7k pull down
    -   no gate resistor
    -   7x led resistor pairs in parallel
    -   LED 0603 white
    -   Transistor AO3416A SOT-23-3 FET N-Channel
        -   20 V max drain-source
        -   6.5A (Ta) max drain current continuous (25° C)
        -   1.4W (Ta) power dispersion 
        -   Gate threshold 0.4, 0.7, 1.1 V

Typical Fall Time (ns) 2240
Typical Rise Time (ns) 328
Typical Turn-Off Delay Time (ns) 3760
Typical Turn-On Delay Time (ns) 280

