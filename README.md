# OpenTypeDesignVariationAxisTags
This repo is used for discussion and review of proposals for registration of OpenType design-variation axis tags.

## Background: Design variation axes
Version 1.8 of the [OpenType spec](http://www.microsoft.com/typography/otspec/) introduced support for variable fonts. An OpenType variable font is a single font that behaves like an entire family of fonts by including data that defines ways in which the glyph outlines can vary. For a given font, variations are defined on one or more dimensions or _axes_ of design variation. For example, a font may define variation on a weight axis, allowing the thickness of stems or other strokes to be larger (heavier) or smaller (lighter). Or a font may define variation on a “serifness” axis, so that it can vary from no serifs, to small, medium-sized or large serifs. Or a font might define variation on weight and “serifness”, as well as other axes. 

Each axis of variation in a variable font is defined with a numeric range, and the design variation along the axis is continous: any numeric value within that range can be selected. In this way, the variation axes that are defined within a variable font define an n-dimensional space of design variation, and the font is able to support any design variant within that space.

Design variation axes are also relevant for traditional, non-variable fonts. Fonts often exist in families in which each individual font is a variant of some common design elements. For example, Arial Regular and Arial Bold have common design elements that comprise the essense of “Arial”, but each is a variant of “Arial”. Most families have members that represent variation at one or more points along a given axis. For example, Arial Regular, Arial Bold and Arial Black are variants of “Arial” at different points along a weight axis. 

In principle, any font member of any family can be characterized in terms of values for some combination of design-variation axes. This is true even in the most seemingly arbitrary cases. For instance, if someone were to create an “Arial Wonky”, it could always be characterized as being the member of the Arial family at 100% on an “Arial-Wonkiness” axis, even if there was no obvious way to characterize it in terms of other more-familiar axes.

OpenType allows for fonts to specify custom, designer-defined axes, but it also provides a conventional set of axes with standardized definitions. These are referred to as _registered_ axes. Documentation of registered axes is provided in the [OpenType Design-Variation Axis Tag Registry](https://www.microsoft.com/typography/otspec/dvaraxisreg.htm). 

Within the OpenType format, the axes defined within a font are identified using a _axis tag_, which is a four-byte array that can be interpreted as a four-character ASCII string. For example, 'wght'. Tags for custom axes must always begin with an uppercase ASCII letter and use only uppercase letters or digits. Tags for registered axes never use this pattern but can use any other well-formed pattern.

Because they have documented definitions, registered axes provide certain benefits:
* They allow for interoperability (at least to some degree): fonts that have the same values on some axis have a certain similarity, and applications can programmatically use or manipulate the axis values in certain ways. For example: an italic font will be a better substitute for another italic font than would a non-italic font, and an application can associate particular fonts or variable-font instances with the state of an “Bold” user-interface control based on the fonts' weight-axis values.
* A registered axis is more likely to be used across multiple fonts and present the same user experience than custom axes, increasing familiarity for users and, therefore, relevance and usability.

When OpenType 1.8 was published, five design-variation axes (with their associated tags) were defined:
* Italic (tag: 'ital')
* Optical size (tag: 'opsz')
* Slant (tag: 'slnt')
* Weight (tag: 'wght')
* Width (tag: 'wdth')

But OpenType allows for additional axes to be registered over time as standardized axes defined in the spec.

With this background in mind, then, the purpose of this repository is to provide a forum in which proposals for new registered axes can be submitted and discussed.

## Registration of new design-variation axes
A process is used for registration of new axes for addition to the OpenType spec. The aim of the process is to ensure that:
- The proposed axis has a well-formed axis tag, and there is adequate and clear documentation of how the axis is meant to be used.
- A proposed axis is appropriate for use as a design variation axis and doesn't duplicate other registered axes, and there is a valid reason for treating this as a registered axis rather than as a custom axis.
- There is indication that the axis will be beneficial for use in fonts and text-layout applications, and is likely to get actual use.

Each of these points is discussed in more detail in the following sub-sections. See also information provided in [OpenType Design-Variation Axis Tag Registry](https://www.microsoft.com/typography/otspec/dvaraxisreg.htm).

### Formal requirements for a registered axis
For an axis to be registered, certain formal requirements must be met. These have to do with the axis tag, and the documentation that describes the axis.

A registered axis tag must have exactly four ASCII characters; it must begin with a letter, and must use only letters, digits, or the space character. Space character must only occur as trailing characters in tags that have fewer than four letters or digits.

Documentation for the axis must include the following:
- A US English name for the axis.
- A clear description of the intended meaning and behavior for the axis.
- A clear specification of the numeric scale used for the axis.
- When appropriate, a numeric value on the axis scale that is recommended or required for that axis in a “Regular” font.
- When appropriate, recommendations for how applications might interact programmatically with the axis.
- Other additional information that is relevant to guide font or application developers in usage of the axis.

**Name:** It shouold be noted that some applications may use the specified name as a display string in user interfaces to refer to an axis, or as the basis for translation to derive localized display strings. An axis name should be chosen with this in mind.

**Description:** The description should be complete and clear enough that independent font or application developers will be able to implement the axis as intended, with consistent behaviors from one font or application to another. The description should be written with interoperability in mind.

**Numeric scale:** Every axis must have an associated numeric scale. This is implicitly required for axes that will be used in variable fonts, but also applies to axes that are only expected to be relevant for families with static, non-variable fonts. 

The description of the scale must indicate what range of values are valid for that axis. Every axis scale must fit within the limits supported by the variation format, which uses a signed 16.16 (binary) representation. For a given axis, specific minimum or maximum values can be specified, so that only a sub-range of that range is permitted for that axis. For example, the optical size axis requires values that are strictly greater than zero, since the scale is meant to be correlated with text size which is always greater than zero.

Note that a given font may use only a portion of the range that is valid for a given axis. For example, the valid range for the weight ('wght') axis is 1 to 1000, but a given variable font might only support weight instances in the range 300 to 700.

In addition to the specifying what numeric range is valid, there must also be a specification of how the numeric scale is to be interpreted — what do the numbers mean or physically represent. The nature of the scale interpretation can vary considerably from one axis to another. Some axes might use a scale that corresponds to an objective, physical measure, such as the text em size or font design units. Other axis scales might be a proportion relative to some reference; for example, the scale for the width ('wdth') axis gives a proportional width of design instance (as a percentage) related to what the font designer considers to be “normal” width for that family or variable font. Other scales may be somewhat more abstract, but should at least relate to something that is conventionally understood; for example, values for the weight ('wght') axis are to be interpreted in the same way that OS/2.usWeightClass values have always been understood.

In generally, it is preferable for an axis scale to be tied to a specific, physical measure that can be determined unambiguously. The closer a scale is to that ideal, the better the opportunities will be for consistent behaviors in independently-developed fonts, and for devising useful algorithms by which applications can control text layout to produce pleasing and effective typography. 

For example, the weight axis uses a scale that is very vaguely defined, with the result that there is limited consistency in the typographic color obtained from one “Bold” font to another. In comparison, the width axis uses a scale with a somewhat more specific interpretation that is specific enough to be used in an algorithm for automatically fitting text formatted with a variable font to a specified width. But this proportional width scale is still somewhat imprecise, and the algorithm for fitting text would require some repeated, trial-and-error attempts. A different, hypothetical axis with a scale that gave the specific, design-unit advance width of each character in a monospaced font, then the text-fitting algorithm could compute in advance the specific design instance required to fit the specified width precisely. The more closely the scale is tied to a specific physical measure, the more useful it can be.

However the scale is defined, the description should be complete and clear enough that independent developers will be able to implement the axis as intended, with consistent behaviors from one implementation to another. 

**Recommended or required “Regular” value:** It is conventional practice that a font family has a “Regular” font member. Depending on the nature of an axis, there may be a certain numeric value that is required or recommended for a “Regular” font. 

For example, a “Regular” font is not italic or oblique. Hence, the italic ('ital') value and slant ('slnt') values for a “Regular” font are, by implicit defition, zero.

The documentation should make clear whether a specified value for that axis is recommended or is required.

**Recommended programmatic interaction:** When an axis lends itself to defining algorithms for programmatic interaction by which applications might automatically select an axis value, it is useful to provide some guidance or, at least, suggestions as to how this might be done. Precise definition of algorithms isn't required or even expected. But by providing pointers to ways that programmatic interaction might be useful, this will increase the usefulness of the axis in fonts and applications.

**Additional information:** There are no specific details that are required, but the documentation of an axis should include anything else beyond the above categories of information that will be essential or helpful in enabling different font and application developers to implement the axis as intended, with consistent behaviors from one implementation to another.

### What makes a good candidate for being a registered axis?

### Determining that a proposed axis is likely to be used

## Contributing

This project welcomes contributions and suggestions. Most contributions require you to
agree to a Contributor License Agreement (CLA) declaring that you have the right to,
and actually do, grant us the rights to use your contribution. For details, visit
https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need
to provide a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the
instructions provided by the bot. You will only need to do this once across all repositories using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/)
or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
