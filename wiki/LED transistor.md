# Transistors

The AO3400A in SOT-23 seems a decent choice.
Our use is for visual PWM of a bare LED, with a low switching frequency,
    with the ZMK docs using 100 Hz in the PWM configuration example.

## Gate resistor value

300 Ω limits a 3.3v pin to 11mA, inline with the MCU GPIO drive strength
  ranges of 2-12 mA for RP2040 and 6–15 mA for nRF52480.
This slowing down the gate frequency is not an issue 
  as PWM for an LED is a rather low frequency circuit.

The other keyboard designs I've seen don't use a gate resistor.
But every EE discussion I've seen says to use them.
The most significant to me is for limiting the max amp draw
on the GPIO.

## JLC parts availability (n-channel MOSFET SOT-23)

https://jlcpcb.com/parts/2nd/Triode_MOS_Tube_Transistor/MOSFETs_79435?spm=search

### Basic

-   AO3400A, 30v, Vgs ±12, Gth 0.7–1.5, on/off specs 3–25 ns, C20917
    Rds(on) (at Vgs = 4.5V) < 32mΩ
    Rds(on) (at Vgs = 2.5V) < 48mΩ  more resistance than AO3416 but mΩ.
    Gate resistance 3Ω.
    Zero gate voltage drain 5µA.
    Total gate charge 6 nC (6 nC / 11 mA from MCU = 0.5 µs rough switch time)

-   2N7002, 60v, Vgs ±20v, Gth 1–2.5, switching 20–40 ns, C8545
    Rds(on)Max: 7Ω @5v
    Zero gate voltage drain 80nA 
    It seems designed for higher voltage use

-   MDD2302, 20V, Vgs ±12, Gth 0.5–1.2, C427390

### Extended

-   AwO3416A, 20v, Vgs ±8v, Gth 0.4–1.1v, on/off specs 3–300 ns
    Rds(on)Max (at Vgs 2.5v) < 33mΩ
    Zero gate voltage drain 5µA 
    AO version is ESD protected
    Used by some other keyboards.

## Transistor overview

Two main types:

-   BJT
    -   current driven
-   MOSFET: used when need high operating speed
    -   voltage driven, no need for continued current.
    -   Can handle more current

Limits:
voltage and currant

Pins:

- Emitter
- Base: between 0.6—0.7v to turn main current on more
- Collector

Beta is collector current/base current

Two types of bipolor 
- npn: collector and control to +, current combines
- pnp: emittor to +, 


## See also

https://electronics.stackexchange.com/questions/13079/when-is-a-mosfet-more-appropriate-as-a-switch-than-a-bjt

https://electronics.stackexchange.com/questions/64638/what-transistor-to-use-when-building-a-simple-mcu-controlled-led-blinking-circui

https://en.wikipedia.org/wiki/2N2222

https://hackaday.com/2016/12/13/ask-hackaday-dude-wheres-my-mosfet/

https://learn.adafruit.com/transistors-101

[How to select a MOSTFET](https://www.youtube.com/watch?v=mZKTafaF3xc)

[MOSFETS](https://www.youtube.com/playlist?list=PLZkKm0LtEBudhc0-c-5tA32N82MmUVvlX) particularly the biasing and switching videos

-   [Seven Myths](https://www.baldengineer.com/7-mosfet-myths-and-misconceptions-addressed.html)
    -   Gate resistor 100–1000Ω, value not critical for < 10 kHz.
