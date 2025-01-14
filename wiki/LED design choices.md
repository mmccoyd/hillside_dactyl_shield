# LED design choices

Much of this is just basic bare LED design.

## Only LEDs driveable with 3.3 v logic/power, thus mostly no bare blue LEDs.

For simplicity, and it is sufficient for both bare red or smart LEDs.

## Low side LED switching, to reduce needed transistor gate voltage

We did low side switching as it reduces the needed gate voltage and the load is just an LED so it getting a raised ground is fine. 

## Up to three series resistors, of which two could be 0Ω

Three is enough to easily add up close to the desired resistance.
The LED will on a wire off board, so the extra resistors' length
seems not very significant.
Zero Ω resistors can always be used if one can match exactly.

## Pull down and series input resistors, though MCU may cover that

They are a simple circuit and ensure wider MCU acceptance.

## Bare LED doesn't have close in capacitor, as the bulk one is about as close

The LED itself is a few inches away in the case body,
so an inch closer on the board seems of little benefit.
The LED is not that level sensitive.

## Design choice dilemmas avoided

- Offering both SMT and through-hole LED resistor options allows
  pros of either based on preference or need.
