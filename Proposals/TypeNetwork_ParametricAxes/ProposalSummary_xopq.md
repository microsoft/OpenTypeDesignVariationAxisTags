# Proposal Summary Form: X Opaque

This proposal describes a proposed X Opaque axis as part of a proposed system of parametric and optical axes.

## Administrative Information

See details in [Type Network Parametric Axes Proposal Overview](Overview.md).

## General Technical Information

**Overview:** This describes a proposed X Opaque axis to vary the horizontal (x-direction) thickness of strokes.

**Related axes:** wght, width, opsz

**Similar axes:** [xtra](ProposalSummary_xtra.md), [ytra](ProposalSummary_ytra.md), [yopq](ProposalSummary_yopq.md)

**Axis type:** Parametric

## Proposed Axis Details

**Tag:** xopq

**Name:** X Opaque

**Description:** Assigns a “black” per mille value to each instance of the design space.

**Valid numeric range:**  -1000 to 2000

**Scale interpretation:** Values should be interpreted as per-mille-of-em.

**Recommended or required “Regular” value:** N/A

**Suggested programmatic interactions:** Example: Combined with the [Y Opaque axis](ProposalSummary_yopq.md),
a program or script can adjust each parameter to improve legibility at small sizes.

**UI recommendations:** Users may choose to program a variant in connection to direct or
conjunctive input for a page description language, or via a user interface

**Script or language considerations:** Can be used for all scripts

**Additional information:** X Opaque changes the black in the x, or horizontal, direction. By
itself it expands the design space, by providing reverse contrast. Combined with Y Opaque it
can create more legible type at small sizes in platforms where hinting is not available.

## Justification

See details in [Type Network Parametric Axes Proposal Overview](Overview.md).

## Other Supporting Information

The following image provides a visual demonstration:
![Demonstration](demos/animation-xopq.gif)
