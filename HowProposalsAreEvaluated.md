# How Proposals are Evaluated
This document describes ways in which proposals are evaluated. If you are considering proposing
a new registered axis, it will be helpful for you to consider the points mentioned here while
preparing your proposal.

While it would be possible to register any number of axes that might be proposed, it wouldn't be
beneficial to do that. In general, the best situation would be to have the fewest number of axes
that provide the greatest benefit for font developers, layout applications, content creators and
consumers. Such maximal efficiency may not be achievable, but it should still be a guiding
principle. Therefore, it's important to consider what makes a good candidate for being a
registered axis.

A proposal to register an axis will not be sufficiently mature until a case is made that it is a
good candidate for being a registered axis. Evaluation can proceed more quickly if a proposal
provides clear explanation of the merits early on. 

## Conventionality and Interoperability
Any axis that might be conceived can always be used in a font or font family as a custom axis. As
mentioned in the [README](README.md) file, a registered axis can provide benefits in relation to
conventionality or to interoperability. Thus, to determine whether an axis should a registered
axis, it’s important to consider whether there would be likely benefits these two areas.

An axis is a good candidate for registration if there are likely benefits in regard to
conventionality. If a type of design variation can only be usefully applied in a limited set of
cases, there is not much to be gained by striving to make that axis conventional. But if a type
of design variation can be broadly useful across many situations, then there will be benefits for
font developers, applications and end users if that axis becomes conventional. The broader the
range of potential usefulness for an axis in different fonts or font families, the better a
candidate it is for registration.

Similarly, an axis is a good candidate for registration if there are likely benefits in regard to
interoperability. If appliations can provide useful behaviors utilizing the axis, whether by
recognizing relationships between fonts or by being able to select axis values to get a
predictable result, then there is an interoperability benefit.

Consider as a hypothetical example an axis that specifies the thickness of the cross bar of the
capital letter A but nothing else. It's easy for users to understand, and they would be able to
know how to find fonts with a particular thickness to this stroke or would know how results with
two different fonts are likely to compare; and it could be applied to many different fonts. But
there would not be much benefit from making this conventional. Similarly, it’s unlikely that
applications would find interesting ways to make use of it. Hence, this would not be a good
candidate to be a registered axis.

## Other Considerations
In addition to benefits in relation to conventionality and interoperability, a proposed axis
should be evaluated in relation to alternative possibilities. For example:

- Would the kind of design variation be better handled using OpenType Layout features?

- Is there a different way to characterize a variation, or a different kind of scale, that would
provide the same benefits in a simpler, better, or more elegant way?

Alternatives should always be considered before concluding that the proposal is the best solution.

Also, a proposed axis should be considered in relation to other axes:

- Is it similar to another already-registered axis? If so, is there sufficient benefit to having
another similar axis registered?

- Is it part of a system of axes that need to be used in a coordinated way to provide the best
benefits? Or is it dependent on other axes to provide any real benefit at all?

- How does this axis interact with other commonly-used axes? Does it provide a useful complement?
Would it conflict with any other axes so that they could not, in practice, be used together?

When evaluating a proposed axis, it may be necessary to evaluate it together with other proposed
axes. The impact of the proposed axis for the entire set of registered axes should also be
considered.

## Formal Requirements for a Mature Proposal
Every proposal must include a copy of the [Proposal Summary](Proposals/ProposalSummary.md) form.
To be considered mature, the form must be completed, and the details reviewed. In particular,
the form must include a complete draft of the axis description that would be published in the
registry.

## Consensus and Commitment
Ultimately, a registered axis provides no benefits unless it gets used. For this reason, it's
important to establish a likelihood of usage. This begins by gaining consensus on the merits.
A proposal might assert that a candidate axis has merits, but if others don't perceive the
merits or have concerns with some aspects of the proposal, then they are not likely to implement
fonts using the axis, or applications that interact programmatically with it. Proposal authors
should view the need to build consensus as part of the investment it takes to ensure eventual
success.

Note that consensus does not require unanimous agreement. It does require broad agreement that
any serious objections have been addressed. A consensus very often requires some willingness
to make compromises to converge on something that most parties can accept.

If a proposed axis does have good merits, then it is likely there will be vendors that plan
to make use of it. Commitment from multiple, independent vendors to make use of the axis is
an important indicator that merits are perceived and that there will be value in making the
axis a _registered_ axis.

## Summary
In summary, then:
- A proposal should lay out a case as to how the proposed axis will be useful as
a registered axis, rather than being used as a custom axis. 
- A proposal should preferably discuss alternatives, and call out any relationships to other
registered or proposed axes.
- The Proposal Summary form must be completed, with a complete draft of text of the axis
description for use in the Registry.
- There needs to be consensus among independent parties that the proposal has merits and is
mature and good indication that the proposed axis will get used by multiple, independent
vendors.

Even though a proposal might cover some of these things, it is to be expected that other points
may arise in discussion of the proposal, potentially including alternative proposals. In some
cases, a full understanding of the merits of a proposal may require time to develop, perhaps
with prototypes or other investigations to gain better understanding.
