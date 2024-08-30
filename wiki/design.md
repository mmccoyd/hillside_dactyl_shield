# Design choices for use in a Dactyl

## No extra ESD protection in front of MCU board

The ProMicro footprint we're using doesn't break out the USB data pins.
And having an option of wired (2040) or wireless (Nice!Nano) is important.
It would nice as it would allow linking the two shield grounds,
  providing a clean path to earth ground for the split shield.
Right now the only path from split shield ground to earth ground is through
  the MCU's logic ground.
For now that will have to suffice.

## Four layer board

- As a non electrical engineer, routing SPI on mirrored boards
  is much simpler with four layers,
  to easily handle the return grounds under the forward paths.
- Getting a solid design comes before trying to do it in two layers.
- The downside is that four layers is more expensive, particularly in a panel,
  thought not proportionally as much more when already using PCBA.
  The PCB part of the cost does go up considerably,
  but from minimal to on par with the PCBA costs for small runs.
- A less capable two layer option is offered as a compromise.

## No extra RAW/Bat+ capacitors, due to USB in rush limit

USB in rush current limits restrict capacitance it sees to around 10 uF
  which the major 2040 boards have on RAW already.
We already violate USB by exposing the left and right 10 uF capacitors
  directly to the host, adding to it would make it worse.
For nice!nano and Bat+, they already have a 4.7 uF capacitor
  which should suffice.
Adding two power managers on the split line seems overkill,
  at least for a first version;
  though it would be one directional.
The downside is we are not boosting what is already there.

## MCU component side up

The MCU faces up so its onboard diagnostic LEDs are more visible.
Expanding the back panel USB slot a little sideways and upward seems likely effective.
Then the LEDs shine toward the debugger and don't hide below the USB cable.
A direct view of them is likely possible assuming a modest hole expansion.
An alternative of making holes in the breakout PCB and the bottom of the Dactyl case
  seems over worked and less visible.

It can still be use with if the MCU has socket pins already on it that would
  place the components face down,
  it just means the jumpers under the MCU must be soldered.

## Full SPI via header and a Vik "subset" connector

Allows a display or various tackpads with an to wire or a more advanced connection.
Sacrifices a possibly encoder_b pin for the MISO pin.
But no certified [Vik](https://github.com/sadekbaroudi/vik/tree/master)
  connector as we don't have enough pins to supply I2C and possibly two GPIO pins.

## SPI for Nice!Nano and 2040 ATmega32U4, but not ATmega32U4 ProMicro

High speed for Nice!Nano and ATmega32U4 are on different rows.
The 2040 supplants the ATmega32U4 anyway.

## External switches header, as columns 0, 4, 5 and rows 4 or 5

Sometimes foot switches are essential or can ease work on injured hands!
The columns skipped are the existing utility row keys plus just left of them
  which some people might add to the utility row based on their thumb cluster location.
An option of using row 4 or 5 gives a choice between full or partial:
  utility, external or number/macro keys sets.

## External switches header used, not TRRS jack, as space by board is tight

Plugging directly to the board would be nice, but threading an angled
  plug through the case wall and having space for it seems problematic.
A header provides a clean option for external switches,
  but that likely needs a larger or taller case.

## Split USB routes just D+, to simplify ESD

The stock firmware only needs one data line.
The downside is anything exotic needs to modify the split circuit,
  but exotic is rarer and some mods are reasonable.

## Split USB shield only connected to a mount hole pad

None of the MCU's offer a shield ground out of the keyboard.
So there is nowhere else to go except for the logic ground.

## Didn't use shift registers for more pins, as matrix scan is more important

To avoid the matrix scan sharing a bus with the display,
a SIPO shift register isn't used to create more pins.

## Ports 0 and 1 are used for input, despite slight power cost

Reworking for one port can wait for some dongle mode.
Reworking all those traces currently looks too painful.
Savings might be 1 or 7 uA?
