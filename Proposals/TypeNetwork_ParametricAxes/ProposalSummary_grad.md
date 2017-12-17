# Proposal Summary Form: Grade

This proposal summary describes a proposed Grade axis as part of a proposed system of parametric and optical axes.

## Administrative information

See details in [Type Network Parametric Axes Proposal Overview](Overview.md).

## General Technical Information

**Overview:** This describes a proposed Grade axis, which would allow adjustments to visual weight without changes to text metrics.

**Related axes:** Always: [xtra](ProposalSummary_xtra.md), [xopq](ProposalSummary_xopq.md).
Sometimes: [yopq](ProposalSummary_yopq.md), [ytlc](ProposalSummary_ytlc.md),
[ytas](ProposalSummary_ytas.md), [ytuc](ProposalSummary_ytuc.md).

**Similar axes:** wght, wdth

**Axis type:** Optical

## Proposed Axis Details

**Tag:** grad

**Name:** Grade

**Description:** Used to vary stroke thicknesses or other design details to give variation from lighter to blacker without changing width; may be constructed by blending other primary axes, or via referenced instances of other axes

**Valid numeric range:**  1 to 2000

**Scale interpretation:** Values should be interpreted as per-mille-of-em

**Recommended or required “Regular” value:** N/A

**Suggested programmatic interactions:** Example: Program or script may easily compute the appropriate grade to bold or lighten text for affect. Program may easily set weight without changing width when trying to achieve consistency across platforms.

**UI recommendations:** Primarily through end-user interfaces

**Script or language considerations:** Can be used for all scripts

**Additional information:** This value range starts at 1 because if it was zero, no ink would be drawn. 

## Justification

See details in [Type Network Parametric Axes Proposal Overview](Overview.md).

## Other Supporting Information

The following image provides a visual demonstration:
![Demonstration](demos/animation-grad.gif)
