# Hillside Dactyl Shield

|                 |                 |
|:-----------     |:----------------|
| ![Render front](./image/Dactyl_Shield-3D_top.png) | ![Use in Dactyl](./image/D50_build_open.png) |


These shields link the parts of a small Dactyl keyboard:
    the MCU, key matrix, battery, USB-C split, display, and underglow.
The shield fits below the index columns and display area of a
    choc Dactyl keyboard.
They should be useful for creating any modest sized Dactyl,
    but were designed for the
    [Hillside Dactyl 50](https://github.com/mmccoyd/hillside_dactyl_50).

## Feature levels

There are three main choice points in a shield cost vs features trade off.
See the wiki ordering page for costs.

- Wireless with key matrix, display, reset, power switch, and battery.
- Wired with ESD protection and PCBA parts placement.
- Vic link, LED underglow, and a decently clean emissions profile,
  using a four layer board with higher setup fees.


## What the shield provides

- A header to socket or solder a ProMicro footprint MCU.
- Key matrix headers for four or five rows, six columns,
   five thumbs, and three external switches.
- A battery switch and JST connector.
- A display header and Vik connector.
- Underglow or side indicator LEDs with power switch and cutoff solder jumpers.
- Extensive ESD protection on the USB-C split connection.
- Four or two layer construction options and PCBA construction.


## Designed as a four layer board, but also to work with two layers

Our highest priority was a cleanly working key matrix,
 followed by an informational display or LED.
Both with clean signal integrity and a properly low
  spurious emissions profile.
So the key matrix routing came first,
  followed by SPI routing for the display and LEDs.
Best practice for SPI seemed to be a four layer board,
    as SPI has fast edge transitions on typical keyboard processors.
Best practice is also to route high speed signals like SPI first,
    but I care more about the key matrix,
    and it seems to have high speed signal edge transitions as well.
So our layout is based on four layers with the inner layers as ground.
That gives the best signal integrity
  and hopefully a properly low emissions profile.
(The signal integrity in the wires flapping around inside the case
    is a different question.)

But four layer boards are more expensive in the small batches
    common with hobbyists.
So a two layer fabrication is also possible,
    as the MCU has direct outer layer ground traces to all ground pin uses.
But with two layers,
  the signal integrity for the matrix, LED, and display is unknown
  and an improper spurious emissions profile seems likely.

## Ordering board fabrication, parts, and building

[Releases](https://github.com/mmccoyd/hillside_dactyl_shield/releases)
    has the files for fabrication.

The [wiki](https://github.com/mmccoyd/hillside_dactyl_shield/wiki)
  has information on parts and ordering.
An example of its use in a keyboard can be found in the
    [Hillside Dactyl 50](https://github.com/mmccoyd/hillside_dactyl_50).

## Firmware

The [Hillside Dactyl 50](https://github.com/mmccoyd/hillside_dactyl_50),
    keyboard's ZMK and QMK firmware
    should be good starting points for creating similar Dactyls.

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

There is also a STEP file in the GitHub action result files.

![Front](./image/Dactyl_Shield-3D_top.png)

![Back](./image/Dactyl_Shield-3D_bottom.png)

![Schematic side](./image/Dactyl_Shield-Right.svg)

![Schematic](./image/Dactyl_Shield-schematic.svg)

