# Ordering

I've ordered it at JLC. The steps are:

## PCB

-   Board
    -   (Material: FR-4)
    -   (Layers: 4)
    -   (Type: Industrial/Consumer)
-   PCB spec
    -   Different designs: 2
    -   Format: Panel by Customer
    -   (Thickness: 1.6 mm. Optionally 1.0 or 1.2 mm, but little reason to)
    -   (Color: green. The only choice for an economical 4 layer PCBA board)
    -   (Material: standard)
    -   Surface finish: 
-   High-spec options
    -   (Impedance Control: No. It isn't needed for such short SPI use)
    -   Confirm production file: yes
    -   Mark on PCB (order number): specify location
- cost: $52  (if it were two layers without SPI display it would be only $12)

## PCBA

-   (PCB Type: Economic)
-   (Side: Top)
-   (Qty: 5)
-   Tooling: Added by Customer
-   Confirm parts: Yes
-   (Parts selection: Customer)

- Advanced: defaults

### Upload bill of materials and position files

Upload the bill of material and position files from
 the PCBA folder.

### Deselect unneeded components

Some parts are rather expensive to have the fab install,
  and others you may not need if you are not doing a wired split.

The biggest cost saving is to skip using PCBA for the
  battery and LED power switches.
They are easy to solder by hand and I would recommend that.
Done with PCBA, they require the more expensive Standard PCBA process,
  not just the Economic one.

If you will never use the breakouts for a wired split,
  you can eliminate some costs by not fitting those parts.
These are the: USB_C, SRV05, Ferrite Bead, Fuse, and ESD5Z5V0.
All of which are listed as extended parts.

That leaves just the Vic connector as an extended cost part.
Which you also may not need.

Staying with the Economic PCBA,
  you'll get a warning about it missing data for any components you deselect,
  which is fine.

### Cost

- $37
