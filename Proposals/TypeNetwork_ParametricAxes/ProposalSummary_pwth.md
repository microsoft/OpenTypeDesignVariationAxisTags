## Proposed Axis Details

**Tag:** pwth

**Name:** Per-Mille Width

**Axis type:** Optical

**Description:** Used to vary width of text from narrower to wider; may be constructed by blending other primary axes, or via referenced instances of other
axes

**Valid numeric range:**  0 to 2000

**Scale interpretation:** Values should be interpreted as per-mille-of-em

**Recommended or required “Regular” value:** N/A

**Suggested programmatic interactions:** Example: Program or script may easily compute the appropriate weight to get a specific stem thickness.

**UI recommendations:** Primarily through end-user interfaces

**Script or language considerations:** Can be used for all scripts

**Related axes:** Always: xtra xopq. Sometimes: yopq ytos ytus

**Similar axes:** wdth

**Additional information:** This value range starts at 0 because if width is zero, counterforms are all closed in; if the `xtra` value is negative, that doesn't matter in the blended axes. 
