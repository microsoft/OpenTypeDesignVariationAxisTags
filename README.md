# OpenType Design Variation Axis Tags
This repo is used for discussion and review of proposals for registration of OpenType design-variation axis tags.

For background on OpenType variable fonts and design-variation axes, see [Background on Design Variation Axes](/BackgroundOnAxes.md).

## Why register a design-variation axis?

OpenType supports custom or “foundry-defined” axes, allowing any font developer to create a font with whatever axes they wish (provided the syntactic requirements for a custom tag are met). So, why bother going through the process to register an axis? The short answer is that it can provide better experiences for end users and create opportunities for font and application developers.

While a font family design can be varied in any number of arbitrary ways, there are some kinds of variation that can seem useful and interesting to many different foundries. With custom axes, different foundries could create families with the same kinds of design variants, but because they have each identified the same variants in different ways, applications have no way to interact with particular variants, and users have inconsistent experiences.

A registered axis provides two key benefits over custom axes:
* It fosters conventionality and familiarity.
* It facilitates interoperability.

**Conventionality and familiarity:** If different font developers independently decide to incorporate the same kind of design variation into their fonts, but refer to that variation in different ways, use different names for common instances, and use different scales, then usability is hindered: experience from using one font or family of fonts provides less benefit in relation to other fonts. Users can't anticipate that a behavior in one case will be in any way similar to other cases unless they happen to try them. But users can't even go looking for new fonts with a particular design variation if they can't even predict how to refer to it. This is the situation with custom axes: they don't provide any familiarity beyond a single font vendor. In contrast, a registered axis provides a basis for creating familiarity across fonts coming from any vendor. This increases usability of fonts for end users: if they want fonts with a particular characteristic, they can more easily find them. If they acquire fonts described as having a particular characteristic, they can more easily anticipate the results they will get in use. For example, by having optical size as a registered axis, many different font vendors can create fonts that incorporate this type of design variation, more users will gain familiarity and learn the benefits, and they will be more likely to seek this feature in new font acquisitions.

**Interoperability:** Interoperability means that certain relationships exist between different fonts, and that applications can utilize those relationships, or utilize characteristics of fonts that are implied. For example, consider font substitution behaviors: if certain text has been formatted with an italic font, but a different font must be substituted when content is viewed in some context, then the result will be best if another italic font is used (other things being equal). By having a conventionally-defined property of “italic”, an application can determine when the preferre font is italic, which alternate fonts are italic, and make the best choice. As another example, consider the optical size axis: by specifying the numeric scale to correspond to text size in points, that makes it possible for applications to create mechanisms to automatically choose an optical-size font variant.

## Process for registration of new design-variation axes
The process described here will be used for registration of new axes for addition to the OpenType spec.

### Goals of the process
The goals of the process are to ensure that:
- There is consensus that a registered axis will be beneficial for use in fonts and text-layout applications, and there is commitment or, at least, reasonable expectation that the axis will be used by multiple vendors.
- A proposed axis is appropriate for use as a design variation axis and doesn't duplicate other registered axes, and there is a valid reason for treating this as a registered axis rather than as a custom axis.
- The proposed axis has a well-formed axis tag, and there is adequate and clear documentation of how the axis is meant to be used.

For more details, see [How Proposals Are Evaluated](HowProposalsAreEvaluated.md), and the
[Proposal Summary](Proposals/ProposalSummary.md) form template. See also information provided in
[OpenType Design-Variation Axis Tag Registry](https://www.microsoft.com/typography/otspec/dvaraxisreg.htm).

### Submitting a proposal
Anyone is welcome to submit a proposal. You must have a GitHub account to do so. Also, your
actual identity must be reasonably clear to other participants.

Before submitting a proposal, it may be helpful to get some preliminary feedback on your
idea from other peers. This can be done in various ways, including discussion on TypeDrawers
or the OpenType email list. You can also use the Issue mechanism for this repository: please
apply the &ldquo;new axis idea&rdquo; label to your issue.

Also, please make sure you read the Contributing section below.

To submit a proposal, use a new topic branch to create a new copy of the
[Proposal Summary](Proposals/ProposalSummary.md) form in a new sub-folder of the Proposals
folder, then submit a pull request. The sub-folder name must be unique and should be a short
name that can be used to refer to your proposal. If you are submitting an alternative to
another proposal with the same name, then append your ID or the name of the vendor you 
represent. (Please use _ or - as delimiters, not spaces.) Your pull request will be checked
to make sure the submission is well formed and in scope.

In addition to the Proposal Summary form, a proposal can include other supporting files to
help clarify the way the axis is meant to work or how it might be used. These might provide
additional background information or demonstrations of usage. 

Demo fonts and specimens can be particularly useful to help others understand the intent
and merits. These can be submitted into the repo, or pointers to external sites can be
provided. These can be provided at the same time the Proposal Summary is first submitted,
or at any time later.

### Review and discussion
Every proposal for a new registered axis must be available for review and discussion for a
period of at least one month before the axis will be registered. In addition to this minimum
time period, there must be actual discussion and evaluation by independent contributors. It
is essential to establish there is broad consensus on merits, and intent among independent
vendors to use and support the new axis. The review period is intended for building and
establishing this consensus. The proposal submitter should monitor activity and respond to
questions or concerns.

For general information on evaluation criteria, see
[How Proposals Are Evaluated](HowProposalsAreEvaluated.md).

Feedback can be provided using the Issues mechanism, or by submitting a new pull request
with proposed changes to the proposal contents. Any pull request generated by the proposal
submitter will be approved by adminstrators if the proposal remains well formed and in
scope. A pull request with changes to a proposal that is generated by parties other than
the original submitter will need to be approved by the submitter.

### Establishing consensus and vendor commitment
The ultimate goal of registered axes is that they be used, not just that they appear in
the registry. Therefore, in order for a proposed axis to be registered, there must be
broad consensus on the proposal: that the proposal itself is mature, that the axis has
merits, that it will get used.

Consensus does not require unanimous agreement. It does require broad agreement that any
serious objections have been addressed. A consensus very often requires some willingness
to make compromises to converge on something that most parties can accept.

A particular requirement for a mature proposal is that the draft description of the axis
for publication in the Registry is complete and clear.

For details on how merits of a proposed axis will be evaluated, see
[How Proposals Are Evaluated](HowProposalsAreEvaluated.md). Consensus on merits will be
established by seeing that questions are answered and the proposal is sufficiently clear,
and that any significant objections have at least been responded to, if not addressed.

Beyond agreement in principle on merits, it is also necessary to establish that the
proposed axis will be used. For any proposed axis, there must be at least three
independent foundries that indicate intent to use the axis in three or more separate font
families or variable fonts. If the intended usage for an axis is primarily to have
selection of axis values be controlled via programmatic interaction rather than direct
user manipulation, then additionally there must be a statement of intent to implement
support for the axis from at least two major platform vendors or three independent layout
library owners. 

Microsoft, as owners of the OpenType specification, will be the final judge that a
proposal is mature, and that there is broad consensus and industry support. This
decision will be made in consultation with a small panel of independent advisors.

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
