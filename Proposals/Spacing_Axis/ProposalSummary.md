Tag: spac

Name: Spacing

Description: Used to vary glyph spacing.

Valid numeric range: any negative, zero or positive value

Scale interpretation: Values can be interpreted as per-mille-of-em changes in glyph spacing from ‘normal’ spacing.

Recommended or required ‘Regular’ value: 0

Suggested programmatic interactions: Applications may choose to select a spacing variant in connection to user-selected layout settings for ‘tracking’ or ‘character spacing’.

UI recommendations: This axis should be hidden from direct user-selection in UI if it is used for implementation of other user-selectable settings such as tracking. If the axis becomes adopted for use in implementation of tracking features in applications, then use of the HIDDEN_AXIS flag in the 'fvar' table should be considered for this axis.

Script or language considerations: This axis can potentially be used for any script. If used for scripts with connecting behaviour, such as Arabic or Devanagari, then the design of inter-glyph connections may need particular attention.

Additional information:

Glyph side-bearing distances (with ensuing effect on advance widths) are typically the primary aspect of design that varies, though details such as serifs may also be encompassed in this variation. If used for scripts with connecting behaviour, such as Arabic or Devanagari, then the design of inter-glyph connections may need particular attention. Variation may also be applied to other font values that are sensitive to glyph metrics, such as kerning distances or mark anchor positioning.

The Spacing axis can be used as a variation axis within a variable font. That is the primary use case anticipated. It can also be used within a ‘STAT’ table in non-variable fonts within a family that has spacing variants to provide a complete characterization of a font in relation to its family within the ‘STAT’ table.

It is recommended that applications use Spacing variants to implement layout features such as ‘tracking’ or ‘character spacing’. This may be limited to variable fonts that implement Spacing as a variable axis. Applications that do this can use the axis values in combination with the font’s head.unitsPerEm value to map between the axis-value scale and physical units such as points. When Spacing variants are selected in this way, applications should assume that the font will provide all of the spacing adjustment, and not apply any additional glyph metric adjustments.

Vendor commitments:
DTL

Conventionality benefits:
Tracking and CSS letterspacing are highly primitive mechanisms and they mess up spacing (for instance with unwanted negative side bearings) and ruin the kerning. Tighter and wider spacing should be controlled by the font producer and hence needs to be recalculated. 

Example:
<https://youtu.be/oXSuRSBMzmI>
