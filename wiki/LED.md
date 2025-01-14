# LED choice and setup

The board can be configured for two RGB LEDs
  or one bare single-color LED.
They are intended primarily as mode indicators —
  with a 5 mm LED sticking through an upper case hole 
  or the RGBs shining through a case bottom hole.
A bare LED is preferable for mobile use
  as the smart RGB LEDs have a high current draw even when idle.

The hardware and firmware can be configured for only one LED type.
You can install both types, but only one can be configured at a time.

## Bare LED and resistor choice

The expected use for the bare LED option
  is for a 5 mm red or yellow LED
  sticking out of the upper case and
  wired down to the board.
The board leaves space to directly solder a 5 mm LED,
  but wiring up to the case will be more visible.

The bare LED needs a resistance load to limit the current through it.
That can be from a single through-hole resistor
  or from a series of three 0805 SMT resistors.
The SMT resistors can be factory installed by PCBA.
The PCBA files have a set of resistance values pre-configured
  but you need to confirm that those values match
  what is needed for the LED you will use.

TODO: a pointer to LED and resistor sizing.

Blue or white LEDs are unlikely to be viable
  color options as the power to the LED is the MCU's VCC line,
  which is 3.3 volts in most cases.

If using a bare LED, 
  you must use a through-hole resistor 
  or a series of SMT resistors.
Using both is more involved and mostly counter productive.

## Smart RGB LED option

The board is designed for one or two SK6812 smart LEDs with 
  recesses set to shine below the board.

## LED power switch and configuration jumpers

To send power to any LED, the mechanical LED power switch
  must be installed and switched on.
The board jumpers come configured to send data and power to the 
  bare LED circuit.

To send data to the RGB LEDs, cut the bare side of the data 
  jumper and solder closed the RGB side.
Having both data sides soldered would at least confuse any installed RGB
  LEDs or the bare LED transformer, and could possibly do them harm.

To send power to the RGB LEDs, solder closed at least the power RGB
  jumper, plus the RGB2 jumper if you want to use two LEDs.
If you later decide to not use these, you can just cut that solder link.

There is not a jumper to cut power to just the bare LED,
  but with its data input low or off its idle draw is very small.


## Some bare LEDs and their specs

Generally only red and yellow are suited for use with 3.3 v power
  as the blue and green voltage drop is too high.

### Max 20 mA current draw for almost all bare LEDs

A [DigiKey search](https://www.digikey.com/en/products/filter/led-indication-discrete/105)
  for bare through-hole LEDs shows almost all are 20 mA or less 
  with a very few 50 mA,
  when filtered by Stocked normally, Mounting through-hole, and Package radial.

### Retail LED examples

-   [5 mm](https://www.sparkfun.com/products/9590)
    -   Red Vd 1.8–2.2, 20 mA, suggested 16–18 mA, 150–200 mcd
-   [3 mm](https://www.sparkfun.com/products/533)
    -   Red Vd 1.8–2.2, 20 mA, suggested 16–18 mA, 150-200 mcd
    -   Yellow dimmer and more power: Vd 2.0–2.4, 40–100mcd
-   [Assorted](https://www.sparkfun.com/products/20120)

## See also

- [SparkFun LED tutorial](https://learn.sparkfun.com/tutorials/light-emitting-diodes-leds)
- [Current limiting resistor](https://learn.sparkfun.com/tutorials/resistors/example-applications)
