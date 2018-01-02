# Proposal Summary Form

## Administrative Information
**Proposers name:** Sahar Afshar and José Solé

**Vendor affiliation:** N/A

**Proposal name:** Glyph Extension axis

**Date of submission:** 2 January 2018

**New or revised proposal:** New

**Previous revision date:** N/A

## General Technical Information
**Overview:** This axis applies a change to the width (or extension) of a single glyph, in addition to any global parameters previously set in place by other axes. This is especially useful for manipulating the length of words or sentences locally, as opposed to adjusting the overall width of the font.

**Related axes:** This axis should take effect once all other axes have been applied.

**Similar axes:** To clarify, the proposed axis is different from the width or extended/condensed axis; the Glyph Extension axis is intended for local use, an example is that in a condensed typeface, a single glyph can be made wider. In connecting scripts, this will only affect connecting strokes.

**Axis type:** Parametric with optical option

## Proposed Axis Details

**Tag:** gext

**Name:** Glyph Extension

**Description:** Used to vary the extension of a glyph by a positive or negative value, depending on parameters assigned by the layout engine (when setting lines of text) or by optical adjustments made by the user (for single words or shorter lengths of text).

This axis works on a single instance of a glyph, where it will apply a change on its extension (outline and spacing) on top of any other changes that have been previously applied via other axes.

**Valid numeric range:** Any negative, zero or positive value.

**Scale interpretation:** Starting with 0 as the glyph in its ‘normal’ state after all other axes have been applied, any increase or decrease should represent the delta applied to the advanced width in font units.

**Recommended or required ‘Regular’ value:** 0

**Suggested programmatic interactions:** When used to adjust the space of a line of justified text, applications should, taking into consideration the script's rules, adjust the extensions of individual glyphs to satisfy the desired line length.

**UI recommendations:** UI recommendations change depending on how the axis is being used, which is itself dependant on environment, script and type of user.

For Arabic the default should be to set this axis as hidden. Programmatic interaction for the Arabic script happens when a user sets a paragraph of text to be ‘fully justified’ or flush with both sides of the text box. The layout engine will then apply this axis on selected glyphs within a line of text to best fit the line to a specific length for justification purposes. A fully defined algorithm for this interaction should be defined, communicated and discussed with application developers for conventionality and interoperability purposes.

When setting Arabic or other scripts in professional typesetting software, users should be given the option of manual control over the axis, allowing them to apply any given extension value to a specific glyph. When selecting a glyph, the user would be presented with the option to change the value of this axis for that glyph. This selection would also override any programmatic interaction for this axis on the selected glyph. This can be particularly useful for the stylistic setting of Arabic words or short sentences; for example in poetry, which requires extensions to appear in specific places.

For other scripts/styles/uses, different programmatic interactions could be developed to automate microtypographic adjustments to glyph-fitting in a way that would help enhance the appearance of set text.

**Script or language considerations:** This axis will be applicable to most scripts.

For connecting scripts such as Arabic, Syriac or Nko this could require the development and implementation of a different way of justifying text, potentially dispensing of the requirements for characters such as the Arabic extension character—often referred to as the ‘Kashida’ or ‘Tatweel’. This depends on what is established as the best method for designing the glyph extension and how this affects connections.

For non-connecting scripts/styles, the development of a separate strategy for adjusting character widths may be needed, depending on how the axis is expected to work and the effect it should have on the text layout.

**Additional information:** The initial intent for this axis was a means to organically justify connecting scripts such as Arabic, Syriac or Nko. However, the same concept can also be applied to non-connecting scripts as a way of making small or large changes to glyphs to affect the length of a line of text.

An example of this is the minute adjustments to the contours of certain glyphs in the 42-line Gutenberg bible to create tighter fitting of certain character combinations that produced too much white-space within words (see [B-42 Story](http://www.daleguild.com/B-42_Story_01.html)).

## Justification

**Vendor commitments:** [none at this time]

**Conventionality benefits:** This axis and the proper layout engine implementation would provide a more flexible and familiar way of adjusting the length of a line of text by adjusting single glyphs. This is especially relevant for connecting scripts where the lack of flexibility of previous typesetting methods prevented the use of a more natural or even correct way of adjusting space within a line of text.

For the above reasons and the additional functionality this would provide to non-connecting scripts, we think this would be a welcome addition to the OpenType specification by both users and the industry, and it would have a noticeably positive impact on the quality of typesetting when compared to the current status quo.

**Interoperability benefits:** Having a properly defined axis for single-glyph adjustment and the additional definition of more advanced justification methods would allow users to know what to expect when setting type in different environments and applications. This would also help standardise how fonts that contain such an axis would need to be developed and implemented, ensuring consistency and interoperability.
