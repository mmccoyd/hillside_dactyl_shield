# Bare LED circuit resistors

We need resistors for

-   MOSFET gate 1/10 watt
    -   100 Ω SMT 0603 anti-ringing
    -   ~10k–100k Ω SMT 0603 pull down
-   LED current limiting
    -   1/4 watt ~76 Ω SMT or through-hole

## LED resistor

Dual SMT and through-hole footprints allow factory PCBA SMT assembly,
  fairly easy by hand SMT soldering, or easy by hand through-hole soldering.

### Watt rating: 125 mW SMT 0805, with through-hole allowing more

The resistor must handle 34 mW (20 mAh x 1.7 v).
As most 5 mm LEDs have a max draw of 20 mAh and a 1.6 volt or more drop.
Leaving a drop of at most 1.7 for the resistor.

Over sizing by three gives a 100 mW resistor, 
  which is covered by a 125 mW 0805 SMT resistor.
A larger planned draw can be handled by a through-hole resistor.

### Fabrication 100 Ω default PCBA resistance

-   TODO redo with MOSFET v drop

Using 100 Ω is a reasonable default for the PCBA files.
It is safe and not a massive hit when less could have served.
That can be changed as needed when ordering the PCB fabrication.

This is how it compares with other options, assuming a target of 17 mA:

-   LED Vd 1.6 -> Res Vd 1.7 -> Res 100 Ω 
    If used instead with LED 2.0 -> 13 mA, LED 2.5 -> 8 mA
-   LED Vd 2.0 -> Res Vd 1.3 -> Res 76 Ω
    If used instead with LED 1.6 -> 22 mA, LED 2.5 -> 10 mA
-   LED Vd 2.5 -> Res Vd 0.8 -> Res 47 Ω
    If used instead with LED 2.0 -> 36 mA, LED 2.0 -> 27 mA

## MOSFET gate resistor

The MOSFET gate resistors are SMT as they don't depend on the LED chosen.

## Physical size (typical) and availability

### SMT

JLC basic part resistors, all of which are uni-royal 

-   0402 63mW 50v, 30 basics — minimum size for economic PCBA
-   0603 100mW 75v, 80 basics — good PCBA size, but soldering is hard
    -   many
-   0805 125mW 150v, 57 basics
    -   0, 4.7, 5.1, 10, 20, 33, 100, 150, 470, 1k, 2k, 10k, 22k, 100k 
-   1206 250mW 200v, 15 basics
    -   0, 1, 10, 20, 22, 100, 120, 300, 1k, 2k, 4.7k, 10k, 100k, 1M

### Through hole cylindrical

-   1/4 watt: diameter 2.3 mm, body length 6 mm, lead diam .55 mm
-   1/6 watt: diameter 1.7 mm, body length 3.3 mm, lead diam .40 mm

## See also

[Resistor Tutorial](https://www.electronics-tutorials.ws/resistor/res_3.html)
[Ohm's Law Calculator](https://www.calculator.net/ohms-law-calculator.html)
