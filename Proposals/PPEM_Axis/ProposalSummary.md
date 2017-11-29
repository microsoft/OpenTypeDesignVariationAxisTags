# Proposal: PPEM Axis ('ppem')

## Administrative Information

**Proposers name:** Renzhi Li (aka. Belleve Invis)

**Vendor affiliation:** N/A

**Proposal name:** PPEM Axis

**Date of submission:** 29 November 2017

**New or revised proposal:** New

**Previous revision date:** N/A


## General Technical Information

**Overview:** Pixel alignment may be crucial in some cases, and the form of such mechanism (TrueType instructions) are very hard to understand, for designers. Therefore, a variation axis could be a easier way to encode pixel alignment data into fonts.

**Related axes:** N/A

**Similar axes:** N/A

**Axis type:** optical


## Proposed Axis Details

**Tag:** `ppem`

**Name:** PPEM

**Description:** Used to encode necessary data for pixel alignment.

**Valid numeric range:** Must be a non-negative integer.

**Scale interpretation:** The value must be interpreted as the text size, in physical pixels, when it is positive; or "ignore pixel alignment", when it is zero. For TrueType fonts, the value must be equal to the result of `MPPEM[]` instruction. 

**Recommended or required ‘Regular’ value:** 0

**Suggested programmatic interactions:** A proper rasterizer should pass the current PPEM value to this axis, or pass "0", representing "ignore pixel alignment". If a rasterizer passes a positive integer to this axis, then it should also interpret TrueType instructions of CFF hints, if present.

**UI recommendations:** This axis should be hidden from direct user-selection in UI if it is used for implementation of other user-selectable settings such as tracking. If the axis becomes adopted for use in implementation of tracking features in applications, then use of the HIDDEN_AXIS flag in the 'fvar' table should be considered for this axis.

**Script or language considerations:** This axis can potentially be used for any script. For scripts that contain complex outline while requiring pixel alignment, like icon fonts or CJK ideographs, it could be extremely useful. If used for scripts with connecting behaviour, such as Arabic or Devanagari, or, for example, connecting cursive typefaces for the Latin script, then the design of inter-glyph connections may need particular attention.

**Additional information:** The `ppem` axis is used to encode deltas that shift points to the place closer to the pixel grid. Values of `ppem` axis would always be a non-negative integer.

The deltas added by the `ppem` axis must be zero, when the `ppem` value is zero. It is also recommended that, for a large enough `ppem` value, the deltas should also be zero.

The `ppem` axis variation could be combined with existing TrueType hints, i.e., the deltas in `ppem` axis could be a value that not move points to the *exact* pixel grid, but to a closer place, and let TrueType instructions to perform the final rounding. Thus, interpreting TrueType instructions (or CFF hints) is required when activating `ppem` axis.

## Justification

**Vendor commitments:** N/A

**Conventionality benefits:** Pixel alignment may be crucial in some cases, and the form of such mechanism (TrueType instructions) are very hard to understand, for designers. Therefore, a variation axis could be a easier way to encode pixel alignment data into fonts.

**Interoperability benefits:** Simplifies the process of creating pixel-perfect icon fonts or hinting dense glyphs.

## Additional information

N/A

