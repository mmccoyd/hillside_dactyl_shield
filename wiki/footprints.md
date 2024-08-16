# Footprint standard setup

- In properties:
  - List user.9 as a footprint private layer.
  - Exclude from BoM and position files for most footprints.
- Change the layer of these fields from:
  - F.Silk to F.Fab
    - Reference
  - F.Fab to
    - F.Silk
      - Value (for pin headers)
    - B.Silk
      - ${REFERENCE} -> ${VALUE}
    - User.9
      - Footprint name
      - Datasheet
      - Description
      - Config
- Copy F.Silk outlines to B.Silk.
