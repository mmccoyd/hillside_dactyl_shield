# Readme

These shields link the parts of a small Dactyl keyboard:
 the MCU, key matrix, battery, USB-C split, display, and underglow.
The board fits below the index columns and display area of a
  choc Dactyl keyboard.
Though designed for the [Hillside Dactyl 50 xxx],
  they should be useful in any similar Dactyl with at least a
  modest case volume.

> [!Note]
> I recommend waiting for an issue fixing release that should be
> up shortly, hopefully within about a week.
> See the change log for those known issues.
> Some links are broken as I stage related parts of the keyboard.

## Feature levels and ordering

There are three main choice points in a features vs cost trade off.

- A simple shield for rows, columns, reset, and a battery with a switch
  using a two layer board at low cost.
- Wired split with ESD protection,
  by adding PCBA parts placement; though you could hand solder most of that.
- SPI display or Vic link, LED underglow,
  and hopefully a decently clean emissions profile,
  using a four layer board and higher setup fees.

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

## Designed as a four layer board, it *should* work as two layers

Our highest priority was a cleanly working key matrix,
 followed by an informational display or LEDs.
Both with clean signal integrity and a properly low
  spurious emissions profile.
Thus the key matrix routing came first
  followed by SPI routing for the display and LEDs.
Best practice for SPI seemed to be a four layer board,
    as SPI has fast edge transitions on typical keyboard processors.
Best practice is also to route high speed signals like SPI first,
    but I care more about the key matrix,
    and it seems to have high speed signal edge transitions as well.
So our layout is based on four layers with the inner layers as ground.
That gives the best signal integrity
  and hopefully a properly low emissions profile.
How that signal integrity changes as the signals go into wires
  flapping around inside a Dactyl case is a separate question.

But four layer boards are fairly expensive in the small batches
    common with hobbyists.
So the key matrix should work even on a two layer board,
    as the MCU has direct outer layer ground traces
    to the battery, split connection, and reset switch.
Currently, the outer layer ground fills also provide at least a low
    speed circuitous ground path from the LED, display, and Vic.
But with two layers,
  the signal integrity for the matrix, the LED, and the display is unknown
  and an improper spurious emissions profile seems likely.
Leaving the outer ground unconnected to ensure the shield is only used
  as designed as a four layer board
  would seem to just ensure someone forked it, connected ground,
  and everyone then missed all the
  "likely suspect signal integrity and improper spurious emissions"
  warnings here.
So leaving a two layer path with warnings
    that it might not work as well and your electronic neighbors
    might be annoyed or mad, seems the best.

There is a layer count indicator viewport on the PCB to see if a physical board
  has two or four copper layers.
The outer silkscreen is removed to show the bare PCB material in two bars
  on the front and back.
Below the bars, the outer copper layers are removed.
On a two layer board, a light placed on the back of the board
  should shine clearly through both bars.
On a four layer board, the light should shine clearly through only one bar,
  as the inner copper layers cover one bar but not both.

Sorry for the length, I wanted to be clear on the layers setup.

## Ordering board fabrication, parts, and building

[Releases]() has the files for fabrication.

[Ordering]() has an outline of the process of ordering from a
  fabrication house.

The [wiki xxx] has details for the parts, ordering and building.
A broader example of its use in a keyboard can be found in the
  separate [Hillside D50 wiki]().

## Firmware

These shields were used to create the Hillside Dactyl 50,
  so its [ZMK firmware xxx] should be a helpful starting point
  when creating similar Dactyls.

## Status

In alpha.2 testing.

## Building Fab artifacts

[Releases]() has Gerber and PCBA files for ordering,
  those are where to start.

## Design notes

- The MCU goes face down.
  A dactyl is often not one's first ergo board
  and most ergo boards with a socketed MCU have it face down,
  so most of those building a dactyl likely have MCUs already pinned that way.
- The PCBA is configured for the Vik connector and battery and LED switches.
  It uses KiBot and is being tested using JLC's Economic PCBA.

## Other controller boards

Some other shields provide related abilities, including:

- A board with a built-in processor is
[BastardKB](https://bastardkb.com/)'s [Splinktegrated](https://bastardkb.com/product/splinktegrated-rp2040-controller/)
- The [Keebio Stampy](https://keeb.io/products/stampy-prototypes-rp2040-usb-c-controller-board-for-handwiring)
   RP2040 has three integrated switch footprints plus 26 pin breakouts.

## Images

Render with components shown, but excluding those not in the POS file.
Schematic
PCB
