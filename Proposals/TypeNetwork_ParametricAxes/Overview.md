# Type Network Parametric Axes Proposal Overview

## Administrative Information
**Proposers name:** Sam Berlow

**Vendor affiliation:** Type Network

**Proposal name:** Type Network Parametric Axes

**Date of submission:** 12/15/2017

**New or revised proposal:** New

**Previous revision date:** N/A

**Additional information and demonstrations:**

## General Technical Information

### Overview

Everyone using fonts is familiar with the weight, width and postural (slant) attributes of a typeface family, and many professional typographers are familiar with fonts mastered for different optical size ranges. Traditionally, the most common attributes are available as named font instances (or styles) within font families. These attributes and others are also recorded in the font metadata fields of the OpenType v1.0 specification, such as values in the OS/2 table (e.g. cap height and x-height.)

But these could not be altered by users, and this led to widespread simplification about how typography is formed from the attributes of typefaces. Users want to manipulate more parameters than static font formats contain, or applications could offer. The metadata that was available was mostly for Latin, and the users of world scripts have found difficulties with more limited metadata, especially when mixing scripts on a page for print or digital media.

The variable fonts specification in the OpenType v1.8 font format changes that situation. We see the possibility to solve many typographic problems with it, if it includes a more in-depth and complete set of attributes that users can interact with, or adjust through programming.

 OpenType variable fonts launched with registered axes that pertain to some of these attributes, such as width, weight, optical size, and slant. This proposal contains additional axes for attributes that are universal for all scripts and designs, and also some specific to Latin, such as cap height and vertical depth of descenders.

This initial proposal for Latin axes  is interrelated, and forms a gestalt system. The system can be extended with more axes, not in this proposal, for all the world’s scripts. A Latin variable font with these axes can be adjusted to harmonize with a static font from any of those scripts. For example, such a font paired in a document with a non-variable Chinese font can have multiple descender lengths, depending on whether Chinese or Latin is the primary script in a text run. We expect to see single variable fonts that contain several scripts and several sets of glyph group alignment axes.

We carefully chose these axis names and tags to convey their systematic nature. Instead of choosing familiar, common, general terms (like "x height" or "weight" or "spacing") with widely understood meanings, and then dissecting a specific meaning for use in a sharply defined axis using that name, we created names that may at first seem unfamiliar, but are descriptive – and soon become intuitive. 

These names represent a patterned sequence of direction, form and glyph group alignment. This pattern is the foundation for a new kind of discourse about type that has become very convenient internally at Type Network for discussing the details of all kinds of type design projects, variable or not, with our clients, including the Google Fonts team. We have made the distinction between ‘Universal’ parametric axes and ‘Latin’ parametric axes. The naming scheme helps to de-emphasize the Latin script as a default.

We also carefully designed the axes value ranges to form a unified programmable set that is built on typographic tradition, where measures of variation are reasoned about in per-mille-of-em, points, and degrees. This allows users to define spatial values relatively, which is especially useful when specifying typography with variable fonts, or to work with absolute values that can be found in any font.

Most of these axes are “lower level” in that they can be used in concert to define “higher level” axes (like a “weight” or “x height” axis.) Currently this means finding 2 positions on a set of lower level axes, and instantiating them as new masters, to be re-inserted into the design space as the extremes of a new axis. For users, the ability to control the low level parameters of high level type attributes with precision increases the number of typographic problems that they can solve. For typeface designers, their design process is simplified, as the number of masters that they are required to draw from scratch is reduced, while increasing the number of high level axes they can offer users.

Overall, we believe these axes allow type users, especially software developers and educators, to have a clearer picture of how typography is shaped by the attributes of typefaces. A near-future proposal, will follow with an overview containing world script alignments, time-base axes and axes for glyph-referencing among instances.

**Parametric Axes**

The goal of this proposal is to name and define universal parametric axes in the X and Y
dimensions: [X Opaque](ProposalSummary_xopq.md), [Y Opaque](ProposalSummary_yopq.md),
[X Transparent](ProposalSummary_xtra.md), and [Y Transparent](ProposalSummary_ytra.md).

Since these axes are for the overall typeface, they are universal across scripts and designs.

Consistently naming and defining these terms and axes will enable developers to consistently refer to and access the core elements of letterforms, which can be used to compose Optical Size, Weight and Width variations. This gives users more precise control over typography than is possible with the existing axes for those high-level typeface attributes.

An example of a composed “high level” axis is one for “grade,” where X Transparent is increased as X Opaque is decreased, keeping overall glyph widths the same while reducing the apparent weight of the letterforms; using existing registered Weight and Width axes in tandem like this produces uneven results (see the “Winner” example in https://pixelambacht.nl/2017/variable-hover-effects.) An example of programmatic use would be to slightly reduce or expand the X Transparent axis during a paragraph justification algorithm, while keeping all other axis choices the same.

**Latin Parametric**

These four Latin axes apply to glyphs and parts of glyphs specific to the Latin script:
[Y Transparent Uppercase](ProposalSummary_ytuc.md), [Y Transparent Lowercase](ProposalSummary_ytlc.md),
[Y Transparent Ascender](ProposalSummary_ytas.md), and [Y Transparent Descender](ProposalSummary_ytde.md).

These axes allow users to tailor these attributes of type independently from their other axis position choices, such as a specific position on an Optical Size axes which may itself adjust these attributes, but too little or too much for a particular situation.

The ability to change the height of the lowercase and/or uppercase, independently, increases the design range of a typeface which has many benefits for users. A graphic example is to adjust the lowercase upwards and uppercase downwards to produce a “unicase” styling; a refined typography example is to adjust the uppercase downwards to create a rarely offered “petite caps” styling; a simple programmatic example is to detect collisions from the descenders of a line above with the ascenders of a line below, and adjust the ascenders and descenders just enough to untangle them. These are just a few examples, and many problems of Latin typography can be solved with this system which can not be solved without such precise independent control.

**Optical Axes**

This proposal includes 3 “higher level” axes: [Per-Mille Weight](ProposalSummary_pwht.md),
[Per-Mille Width](ProposalSummary_pwth.md), and [Grade](ProposalSummary_grad.md). 

The first 2 differ from the already-existing registered axes ‘Weight’ and ‘Width’ in value systems. While those existing axes are useful with value systems designed for backwards compatibility (such as Regular at 400 and Bold at 700,) we think it is important to offer users the same per-mille-of-em user experience as the other axes in this proposal. These are formed by using “lower level” axes in concert.

Grade is a type attribute from refined typography, meaning that apparent weight changes occur without changes to glyph widths, so that line layouts remain constant – no reflow. It is formed mainly by increasing X Opaque while decreasing X Transparent (or vice versa.) However, other “lower level” axes will typically also be blended in, so changes are not only in the X dimension; for example, as grade gets very high and counterforms become narrow, a slight increase in Y Transparent and decrease in Y Opaque can open them up. 


## Justification

**Vendor commitments:** Google Fonts, Font Bureau, TYPETR

**Conventionality benefits:** "Foreground/background", or "Positive/Negative Shapes", and "white space" are common concepts in visual arts, but many users don't think about the opaque and transparent areas of type deconstructed (or essentially isolated) to the X and Y dimensions. These axes help users to structure their thinking about positive and negative space horizontally and vertically, for the overall/total typeface. A secondary benefit is the encouragement for people to reason about their typography in per-mille measurements.

**Interoperability benefits:** justification, legibility, contrast, weight matching, height matching, linespacing, design space

