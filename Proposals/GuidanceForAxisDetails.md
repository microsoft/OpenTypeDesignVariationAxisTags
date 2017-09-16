# Guidance for Axis Details

The [Proposal Summary](ProposalSummary.md) form has a section for you to provide draft text
for details about an axis that would be published as the description of the axis in the
registry. This file provides guidance regarding each of the fields of information that
are included in the description of a registered axis.

## Tag 
The proposed tag must be unique, different from other registered axis tags, and must conform
to the [syntactic requirements](https://www.microsoft.com/typography/otspec/dvaraxisreg.htm) for axis
tags described in the OpenType spec.

## Name
The name provided should be a US English string. Other translations can be provided separately
in the Proposal Summary form. The name should be short, preferably a single word. Note that some
applications may use the specified name as a display string in user interfaces to refer to an axis,
or as the basis for translation to derive localized display strings. An axis name should be chosen with
this in mind.

## Description
The description should be complete and clear enough that independent font or application
developers will be able to implement the axis as intended, with consistent behaviors from one font or
application to another. The description should be written with interoperability in mind.

## Valid numeric range
Every axis must have an associated numeric scale. This is implicitly required for axes
that will be used in variable fonts, but also applies to axes that are only expected to be relevant for
families with static, non-variable fonts. 

The description of the scale must indicate what range of values are valid for that axis. Every axis scale
must fit within the limits supported by the variation format, which uses a signed 16.16 (binary)
representation. For a given axis, specific minimum or maximum values can be specified, so that only a
sub-range of that range is permitted for that axis. For example, the optical size axis requires values
that are strictly greater than zero, since the scale is meant to be correlated with text size which is
always greater than zero.

Note that a given font may use only a portion of the range that is valid for a given axis. For example,
the valid range for the weight ('wght') axis is 1 to 1000, but a given variable font might only support
weight instances in the range 300 to 700.

## Interpretation of scale
In addition to the specifying what numeric range is valid, there must also be a specification of how the
numeric scale is to be interpreted&mdash;what do the numbers mean or physically represent. The nature of
the scale interpretation can vary considerably from one axis to another. Some axes might use a scale that
corresponds to an objective, physical measure, such as the text em size or font design units. Other axis
scales might be a proportion relative to some reference; for example, the scale for the width ('wdth')
axis gives a proportional width of design instance (as a percentage) related to what the font designer
considers to be “normal” width for that family or variable font. Other scales may be somewhat more
abstract, but should at least relate to something that is conventionally understood; for example, values
for the weight ('wght') axis are to be interpreted in the same way that OS/2.usWeightClass values have
always been understood.

In generally, it is preferable for an axis scale to be tied to a specific, physical measure that can be
determined unambiguously. The closer a scale is to that ideal, the better the opportunities will be for
consistent behaviors in independently-developed fonts, and for devising useful algorithms by which
applications can control text layout to produce pleasing and effective typography. 

For example, the weight axis uses a scale that is very vaguely defined, with the result that there is
limited consistency in the typographic color obtained from one “Bold” font to another. In comparison, the
width axis uses a scale with a somewhat more specific interpretation that is specific enough to be used
in an algorithm for automatically fitting text formatted with a variable font to a specified width.
But this proportional width scale is still somewhat imprecise, and the algorithm for fitting text would
require some repeated, trial-and-error attempts. A different, hypothetical axis with a scale that gave
the specific, design-unit advance width of each character in a monospaced font, then the text-fitting
algorithm could compute in advance the specific design instance required to fit the specified width
precisely. The more closely the scale is tied to a specific physical measure, the more useful it can be.

However the scale is defined, the description should be complete and clear enough that independent
developers will be able to implement the axis as intended, with consistent behaviors from one
implementation to another.

If an axis is expected normally to be used with specific discrete values, the specifc numeric values and
can their meaning can be enumerated. 

## Recommended or required “Regular” value
It is conventional practice that a font family has a “Regular” font member. Depending on the nature of
an axis, there may be a certain numeric value that is required or recommended for a “Regular” font. 

For example, a “Regular” font is not italic or oblique. Hence, the italic ('ital') value and slant
('slnt') values for a “Regular” font are, by implicit defition, zero.

The documentation should make clear whether a specified value for that axis is recommended or is required.

## Suggested programmatic interaction
When an axis lends itself to defining algorithms for programmatic interaction by which applications
might automatically select an axis value, it is useful to provide some guidance or, at least, suggestions
as to how this might be done. Precise definition of algorithms isn't required or even expected. But by
providing pointers to ways that programmatic interaction might be useful, this will increase the
usefulness of the axis in fonts and applications.

## UI recommendations
Provide any recommendations for how an axis should be handled in application user interfaces. These should
be general recommendations that will be useful to all font or application developers to understand how the axis would be used typically. It should not
include recommendations about what type of control mechanisms (sliders, knobs, pads, etc.) should be used
in UI. 

Proposals should also include a recommendation on whether the axis should normally be marked hidden via the 
HIDDEN_AXIS flag in the 'fvar' table. If it is recommended that an axis generally be hidden, then there must be 
clear recommendations for programmatic interaction. Note that only variable fonts can have hidden axes.

UI recommendations should be provided if recommendations are given for programmatic interaction, especially
if it is recommended that an axis generally remain hidden from end users. For example, if a proposal were being 
written for the the Optical Size ('opsz') axis, that proposal might list 'opsz' as being hidden, and offer the UI 
recommendation that the 'opsz' coordinate would be automatically selected when the user selects the text size.

If applicable, it is also useful to provide recommendations to application developers regarding kinds of
users for which it would or would not be useful to have direct control over the axis, or scenarios in
which control over the axis may be most useful.

## Script or language considerations
Indicate whether the axis would be applicable only to specific scripts or languages, or groups of scripts or
languages. Also, describe any special considerations that are relevant when the axis is being applied to
fonts for different scripts or languages.

## Additional information
There are no specific details that are required, but the documentation of an axis should include anything else beyond the above categories of information that will be essential or helpful in enabling different font and application developers to implement the axis as intended, with consistent behaviors from one implementation to another.
