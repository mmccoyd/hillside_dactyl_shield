# Readme

These MCU breakout boards link the parts of a small Dactyl keyboard:
 the MCU, key matrix, battery, USB-C split, display, and under glow.

They provide:

- A header to socket or pin solder a ProMicro footprint MCU.
- Switch headers for four or five rows, six columns, thumbs and external
- A battery switch and JST connector
- Under glow indicator LEDs with power switch and cutoff solder jumpers
- A display header and Vik connector

It was designed for the [Hillside Dactyl 50 xxx],
  but should be useful in any similar Dactyl with at least a
  modest case volume.

See the [wiki xxx] for parts, ordering and build notes.

The board fits below the index finger columns and display area of a choc Dactyl.

## Status

In alpha.2 testing.

## Building Fab artifacts

A GitHub action creates Gerber and PCBA files using KiBot files in bin/.

## Firmware

These were used to create the Hillside Dactyl 50,
  so its [ZMK firmware xxx] should be helpful
  when creating a different Dactyl.

## Design notes

- The MCU goes face down.
  A dactyl is often not one's first ergo board
  and most ergo boards with a socketed MCU have it face down,
  so most of those building a dactyl likely have MCUs already pinned that way.
- The PCBA is configured for the Vik connector and battery and LED switches.
  It uses KiBot and is being tested using JLC's Economic PCBA.

## Other breakouts

- A similar breakout but with a built-in processor is
[BastardKB](https://bastardkb.com/)'s [Splinktegrated](https://bastardkb.com/product/splinktegrated-rp2040-controller/)

 The [Keebio Stampy](https://keeb.io/products/stampy-prototypes-rp2040-usb-c-controller-board-for-handwiring)
   RP2040 has three integrated switch footprints plus 26 pin breakouts.

## Images

Schematic
PCB
