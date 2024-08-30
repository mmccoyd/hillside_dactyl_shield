# Two layer board option

The four layer board construction,
  used for reliable SPI without spurious emissions,
  is expensive when done in small numbers.
However, a two layer option is available
  that supports the core bits of:
  power, ground, MCU, key matrix, and battery or split.
Building as a two layer board reduces the PCB cost
  from around $50 to around $12.
Adding PCBA still adds $37 or more to that,

## What the two layer option provides

The MCU has dedicated power and ground tracks,
  and the key matrix doesn't care so should still be fine.

Specifically:

- Power and ground have dedicated tracks on the outer (two layer)
  copper layers from the battery or the split to the MCU.
- That power and ground routing includes the
  split protection circuits and reset.
- The key matrix signals have dedicated out (column)
  and back (row) traces already.

Other things such as the LED, display, and whatever is connected to
  the Vic connector will not work with a two layer board.
This is because SPI with fast switching signal edges wants an unbroken
  return ground path right next to or under the signal path,
  and the top and bottom layers are not laid out to provided that.

## Ordering as a two layer board

On the initial PCB order screen,
  change the layer count from four to two
  after uploading the Gerber files.
JLC staff may query you as to whether you really meant to do that,
  as the uploaded files include all four layers.
