## Proposed Axis Details

**Tag:** grad

**Name:** Grade

**Axis type:** Optical

**Description:** Used to vary stroke thicknesses or other design details to give variation from lighter to blacker without changing width; may be constructed by blending other primary axes, or via referenced instances of other axes

**Valid numeric range:**  1 to 2000

**Scale interpretation:** Values should be interpreted as per-mille-of-em

**Recommended or required “Regular” value:** N/A

**Suggested programmatic interactions:** Example: Program or script may easily compute the appropriate grade to bold or lighten text for affect. Program may easily set weight without changing width when trying to achieve consistency across platforms.

**UI recommendations:** Primarily through end-user interfaces

**Script or language considerations:** Can be used for all scripts

**Related axes:** Always: xtra xopq. Sometime: yopq ytlc ytos ytus

**Similar axes:** wght, wdth

**Additional information:** This value range starts at 1 because if it was zero, no ink would be drawn. ![Demonstration](demos/animation-grad.gif)
