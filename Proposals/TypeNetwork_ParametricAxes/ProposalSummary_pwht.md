# Proposal Summary Form: Per-Mille Weight

This proposal describes a proposed Per-Mille Weight axis as part of a proposed system of parametric and optical axes.

## Administrative Information

See details in [Type Network Parametric Axes Proposal Overview](Overview.md).

## General Technical Information

**Overview:** This describes a proposed per-mille weight axis, which would be similar to the
legacy Weight axis but with a per-mille-of-em scale to provide a unified scale across a system
of axes.

**Related axes:** Always: [xtra](ProposalSummary_xtra.md), [xopq](ProposalSummary_xopq.md).
Sometimes: [yopq](ProposalSummary_yopq.md), [ytlc](ProposalSummary_ytlc.md),
[ytas](ProposalSummary_ytas.md), [ytuc](ProposalSummary_ytuc.md).

**Similar axes:** wght

**Axis type:** Optical

## Proposed Axis Details

**Tag:** pwht

**Name:** Per-Mille Weight

**Description:** Used to vary stroke thicknesses or other design details to give variation from
lighter to blacker; may be constructed by blending other parametric axes, or via referenced
instances of other axes.

**Valid numeric range:**  1 to 2000

**Scale interpretation:** Values should be interpreted as per-mille-of-em.

**Recommended or required “Regular” value:** N/A

**Suggested programmatic interactions:** Example: Program or script may easily compute the
appropriate weight to get a specific stem thickness.

**UI recommendations:** Primarily through end-user interfaces.

**Script or language considerations:** Can be used for all scripts.

**Additional information:** This value range starts at 1 because if it was zero, no ink would be drawn. 

## Justification

See details in [Type Network Parametric Axes Proposal Overview](Overview.md).
