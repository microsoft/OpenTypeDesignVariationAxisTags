## Proposed Axis Details

**Tag:** ytas

**Name:** Y Transparent Ascender 

**Axis type:** Parametric

**Description:** assigns a “white” per mille value to each instance of the design space

**Valid numeric range:**  0 to 1000

**Scale interpretation:** Values should be interpreted as per-mille-of-em

**Recommended or required “Regular” value:** N/A

**Suggested programmatic interactions:** Example: Program or script may adjust the ascenders in coordination leading and column width to prevent letters from touching vertically.

**UI recommendations:** Users may choose to program a variant in connection to direct or conjunctive input for a page description language, or via a user interface

**Script or language considerations:** Can be used for all scripts

**Related axes:** wght, width, opsz 

**Similar axes:** ytuc, ytlc, ytde

**Additional information:** `ytas` changes the y or vertical ascenders. Contributes opsz in making type fit better when size is reduced. The zone or general area that ascenders live in is an attribute that all users can easily point to (along with collisions in this area suffered by fonts without it) but not an area they may know by name. This name fits into the systematic structure of this overall proposal: Y dimension transparency of ascenders. ![Demonstration](demos/animation-ytas.gif)
