# KiCad Footprint standard setup

Property changes

-   List purpose in bottom Description.
-   List user.9 as a private layer.
-   Exclude from position files and BoM (for most footprints).

Editor changes

For anything with a good short name have

-   Value on F.silk and B.silk
    -   By changing
        -   Value to F.Silk from F.Fab
        -   Extra B.silk to ${VALUE} from ${REFERENCE} and formatting
-   Reference on F.fab (from F.Silk)

-   Copy F.Silk outlines to B.Silk.

-   Hide any extra clutter on User.9
    -   Footprint name
    -   Datasheet
    -   Description
    -   Config

-   Use User.9 text boxes for any design/usage notes.
