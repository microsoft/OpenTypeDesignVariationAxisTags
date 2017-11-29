# Proposal: Height Axis ('hght')

## Administrative Information

**Proposers name:** Renzhi Li (aka. Belleve Invis)

**Vendor affiliation:** N/A

**Proposal name:** Height axis

**Date of submission:** 29 November 2017

**New or revised proposal:** New

**Previous revision date:** N/A


## General Technical Information

**Overview:** Height axis is the vertical version of `wdth` axis. It is used to vary height for vertical layout.

**Related axes:** N/A

**Similar axes:** `wdth`

**Axis type:** Optical


## Proposed Axis Details

**Tag:** `hght`

**Name:** Height

**Description:** Used to vary height of vertical text from shorter to taller

**Valid numeric range:** Values must be strictly greater than zero.

**Scale interpretation:** Values can be interpreted as a percentage of whatever the font designer considers “normal height” for that font design.

**Recommended or required ‘Regular’ value:** 100 is required.

**Suggested programmatic interactions:** Applications may choose to select a height variant in a variable font automatically in order to fit a span of text into a target height.

**UI recommendations:** Applications may show a slider to let users to select the proper height for vertical text.

**Script or language considerations:** This axis can potentially be used for scripts with vertical layout, including Han Ideographic, Kana, Hangul, Mongolian or Manchu.

**Additional information:** The height axis is mainly the vertical version of the Width axis (`wdth`). Instead of alternating glyph width, it changes glyph height, for vertical text. Thus, it may utilize `VVAR` table or vertical phantom points in `gvar`.

The Height axis can be used as a variation axis within a variable font. It can also be used within a ['STAT'](https://www.microsoft.com/typography/otspec/stat.htm) table in non-variable fonts within a family that has height variants to provide a complete characterization of a font in relation to its family within the 'STAT' table.

For some scripts (like Han Ideographic or Kana), the normal height (100) often represents that all glyphs of these scripts are exactly 1 em tall.

Percentage of normal height is a comparitive scale that will depend on the specific items being compared. The height of a vertical line of text very much depends on the content of the text. No specific reference string is specified here as the basis for comparisons; a font designer can choose what they consider to be representative strings assigning a '`hght`' value to a design variant. Ideally, the '`hght`' value should provide a good estimate for most strings in the target languages of how the height of the string formatted with that '`hght`' variant compares to the height of the same string when formatted with the “normal” variant.

When using a variable font, applications may choose to make small, automated '`hght`' adjustments in order to fit a span of text to some target size. This might be done, for instance, to fit headings within a column, or to improve paragraphy layout. The relative change in '`hght`' value (ratio of the original '`hght`' to the adjusted '`hght`') may be used as a first approximation of the adjustment needed. Since the relative change in height may depend on the actual text content, however, this may not provide the exact adjustment needed to obtain the desired height adjustment. The application will likely need to refine the adjustment over multiple attempts.

## Justification

**Vendor commitments:** Founder has a prototype version of YouHei with this axis, alongside Width and Weight axis.

**Conventionality benefits:** Similar to `wdth`, it provides way to adjust or fit the height of vertical text.

**Interoperability benefits:** Improvement of the quality of typography by giving the control of the height of vertical text.

## Additional information

- Demo from Founder: https://twitter.com/huangxuejun8/status/925931273067089920

