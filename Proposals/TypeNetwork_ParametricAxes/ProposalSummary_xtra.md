# Proposal Summary Form: X Transparent

This proposal summary describes a proposed X Transparent axis as part of a
proposed system of parametric and optical axes.

## Administrative Information

See details in [Type Network Parametric Axes Proposal Overview](Overview.md).

## General Technical Information

**Overview:** This describes a proposed X Transparent axis to vary the horizontal
(x-direction) size of counters.

**Related axes:** wght, width, opsz

**Similar axes:** [ytra](ProposalSummary_ytra.md), [xopq](ProposalSummary_xopq.md), [yopq](ProposalSummary_yopq.md).

**Axis type:** Parametric

## Proposed Axis Details

**Tag:** xtra

**Name:** X Transparent

**Description:** assigns a “white” per mille value to each instance of the design space.

**Valid numeric range:** -1000 to 2000

**Scale interpretation:** Values should be interpreted as per-mille-of-em.

**Recommended or required “Regular” value:** N/A

**Suggested programmatic interactions:** Example: by setting a maximum word space parameter,
and adjusting the XTRA units to a min and max. A developer could adjust justified text
without tracking letters. Maintaining the apparent weight and width. 

**UI recommendations:** Users may choose to program a variant in connection to direct or
conjunctive input for a page description language, or via a user interface.

**Script or language considerations:** Can be used for all scripts.

**Additional information:** X Transparent changes the white space in the x, or horizontal,
direction. This useful in adjusting type horizontally without changing the opaque (black).
This can be useful in VR, TV, and justification of text blocks.

## Justification

See details in [Type Network Parametric Axes Proposal Overview](Overview.md).

## Other Supporting Information

The following image provides a visual demonstration:
![Demonstration](demos/animation-xtra.gif)

