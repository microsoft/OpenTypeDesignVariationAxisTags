# Proposal Summary Form: Per-Mille Width

This proposal summary describes a proposed Per-Mille Width axis as part of a proposed system of parametric and optical axes.

## Administrative Information

See details in [Type Network Parametric Axes Proposal Overview](Overview.md).

## General Technical Information

**Overview:** This describes a proposed per-mille width axis, which would be similar to the
legacy Width axis but with a per-mille-of-em scale to provide a unified scale across a system
of axes.

**Related axes:** Always: [xtra](ProposalSummary_xtra.md), [xopq](ProposalSummary_xopq.md).
Sometimes: [yopq](ProposalSummary_yopq.md), [ytas](ProposalSummary_ytas.md), [ytuc](ProposalSummary_ytuc.md).

**Similar axes:** wdth

**Axis type:** Optical

## Proposed Axis Details

**Tag:** pwth

**Name:** Per-Mille Width

**Description:** Used to vary width of text from narrower to wider; may be constructed
by blending other primary axes, or via referenced instances of other axes.

**Valid numeric range:**  0 to 2000

**Scale interpretation:** Values should be interpreted as per-mille-of-em.

**Recommended or required “Regular” value:** N/A

**Suggested programmatic interactions:** Example: Program or script may easily compute the
appropriate weight to get a specific stem thickness.

**UI recommendations:** Primarily through end-user interfaces.

**Script or language considerations:** Can be used for all scripts.

**Additional information:** This value range starts at 0 because if width is zero, counterforms
are all closed in; if the [X Transparent](ProposalSummary_xtra.md) value is negative, that
doesn't matter in the blended axes.

## Justification

See details in [Type Network Parametric Axes Proposal Overview](Overview.md).
