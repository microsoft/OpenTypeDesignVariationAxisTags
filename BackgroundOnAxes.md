# Background on Design Variation Axes
Version 1.8 of the [OpenType spec](http://www.microsoft.com/typography/otspec/) introduced support for variable fonts. An OpenType variable font is a single font that behaves like an entire family of fonts by including data that defines ways in which the glyph outlines can vary. For a given font, variations are defined on one or more dimensions or _axes_ of design variation.

For example, a font may define variation on a weight axis, allowing the thickness of stems or other strokes to be larger (heavier) or smaller (lighter). Or a font may define variation on a “serifness” axis, so that it can vary from no serifs, to small, medium-sized or large serifs. Or a font might define variation on weight and “serifness”, as well as other axes. 

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
