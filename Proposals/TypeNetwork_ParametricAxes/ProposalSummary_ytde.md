## Proposed Axis Details

**Tag:** ytde

**Name:** Y Transparent Descender

**Axis type:** Parametric

**Description:** assigns a “white” per mille value to each instance of the design space

**Valid numeric range:**  -1000 to 0

**Scale interpretation:** Values should be interpreted as per-mille-of-em

**Recommended or required “Regular” value:** N/A

**Suggested programmatic interactions:** Example: Program or script may adjust the descenders in coordination leading and column width to prevent letters from touching vertically.

**UI recommendations:** Users may choose to program a variant in connection to direct or conjunctive input for a page description language, or via a user interface

**Script or language considerations:** Can be used for all scripts

**Related axes:** wght, width, opsz

**Similar axes:** ytuc, ytlc, ytas

**Additional information:** `ytde` changes the y or vertical descenders. Contributes to opsz in making small sizes fit better in text settings. Useful in adjusting letters when leading is reduced, in all sizes. Very useful in responsive design when headlines change from single lines to multiple lines of text. The zone or general area that descenders live in is an attribute that all users can easily point to (along with collisions in this area suffered by fonts without it) but not an area they may know by name. This name fits into the systematic structure of this overall proposal: Y dimension transparency of descenders. ![Demonstration](demos/animation-ytde.gif)
