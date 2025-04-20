# Change log

## v0.1.0-alpha.3: Fix soldering and resistors; easier hand wiring

Thou planned for only crucial fixes, this also reorganizes the lower board half
and keywell edge for clarity and easier keywell wiring.

### Changes

Fixes

-   Ground pins have manual thermal relief, not massive auto spoke counts.
-   LED configuration jumpers are all open, not cut-a-trace to open.
-   LED resistors have the intended values.
-   Bare LED can now reach its spot in the side wall, in a lengthened PCB.

Enhancements

-   The physical layout of the key-matrix contacts matches the layout of the
    thumb cluster and keywell edges they connect to. This makes it easier to
    see which wire connects where. At least for the Hillside Dactyl 50, but it
    does have a typical layout.
-   Small test pads allow routing the LED data line to the second LED, to see
    if the first LED got fried by overzealous soldering. Or to bodge wire to
    the second LED with some solid core 26 AGW wire.
-   Reset and battery JST are included in PCBA. Though reset is out of stock.
-   CI uses KiBot JLCPCB template to create four and two layer versions.


## v0.1.0-alpha.2: Left side and bare LED

The major addition is a left hand side. It is my daily board and works well.

### Known issues

-   Ground pins are very hard to solder because of far too many ground plane
    connections for a four layer board.
-   Opening solder jumpers requires cutting the trace,
    which is a pain and suspect on a four layer board.
-   The bare LED needs extra wire to reach outside the case.
-   Creating the release PCBA files required manually rotating the LED
    transistor.

### Changes

-   Panel of left and right shields.
-   Four layer, though can still be built as two layer.
-   Bare or smart LEDs.
-   Split ESD protection.


## v0.1.0-alpha.1: Initial. Not released

-   Initial. Not released.
-   Right hand only.
-   Smart LEDs.
-   Works fine, I've been using it for months.
