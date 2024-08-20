# Readme

These MCU breakout boards link the parts of a small Dactyl keyboard:
 the MCU, key matrix, battery, USB-C split, display, and underglow.
Though designed for the [Hillside Dactyl 50 xxx],
  they should be useful in any similar Dactyl with at least a
  modest case volume.
The board fits below the index columns and display area of a choc Dactyl.

## What they provide

They provide:

- A header to socket or pin solder a ProMicro footprint MCU.
- Key matrix headers for four or five rows, six columns,
   five thumbs, and three external switches.
- A battery switch and JST connector.
- A display header and Vik connector.
- Underglow indicator LEDs with power switch and cutoff solder jumpers.
- Extensive ESD protection on the USB-C split connection.
- Four or two layer construction options and PCBA construction.

## Ordering board fabrication, parts, and building

[Releases]() has the files for fabrication.
The four layer version is recommended when a display or LED is desired.
A two layer option is less expensive when fabrication just a small number of boards,
  but see the [two layer option]( xx )
  notes for its limitations.
See [ordering]() for an outline of the process of ordering from a
  fabrication house.

The [wiki xxx] has details for the parts, ordering and building.
A broader example of its use in a keyboard can be found in the
  separate [Hillside D50 wiki]().

## Firmware

These breakouts were used to create the Hillside Dactyl 50,
  so its [ZMK firmware xxx] should be a helpful starting point
  when creating similar Dactyls.

## Status

In alpha.2 testing.

## Building Fab artifacts

[Releases]() has Gerber and PCBA files for ordering,
  those are where to start.

If you want to build directly from the source,
  a GitHub action creates Gerber and PCBA files using KiBot files in bin/.

## Design notes

- The MCU goes face down.
  A dactyl is often not one's first ergo board
  and most ergo boards with a socketed MCU have it face down,
  so most of those building a dactyl likely have MCUs already pinned that way.
- The PCBA is configured for the Vik connector and battery and LED switches.
  It uses KiBot and is being tested using JLC's Economic PCBA.

## Other breakouts

- A breakout with a built-in processor is
[BastardKB](https://bastardkb.com/)'s [Splinktegrated](https://bastardkb.com/product/splinktegrated-rp2040-controller/)
- The [Keebio Stampy](https://keeb.io/products/stampy-prototypes-rp2040-usb-c-controller-board-for-handwiring)
   RP2040 has three integrated switch footprints plus 26 pin breakouts.

## Images

Render with components shown, but excluding those not in the POS file.
Schematic
PCB
