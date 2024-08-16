# Design choices and reasons

## No extra ESD protection in front of MCU board

The ProMicro footprint we're using doesn't break out the USB data pins.
And having an option of wired (2040) or wireless (Nice!Nano) is important.
It would nice as it would allow linking the two shield grounds,
  providing a clean path to earth ground for the split shield.
Right now the only path from split shield ground to earth ground is through
  the MCU's logic ground.
For now that will have to suffice.
