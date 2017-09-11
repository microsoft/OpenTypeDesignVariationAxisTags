# OpenTypeDesignVariationAxisTags
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
A process is used for registration of new axes for addition to the OpenType spec. The goals of the process are to ensure that:
- There is consensus that a registered axis will be beneficial for use in fonts and text-layout applications, and there is commitment or, at least, reasonable expectation that the axis will be used by multiple vendors.
- A proposed axis is appropriate for use as a design variation axis and doesn't duplicate other registered axes, and there is a valid reason for treating this as a registered axis rather than as a custom axis.
- The proposed axis has a well-formed axis tag, and there is adequate and clear documentation of how the axis is meant to be used.

Each of these points is discussed in more detail in the following sub-sections. See also information provided in [OpenType Design-Variation Axis Tag Registry](https://www.microsoft.com/typography/otspec/dvaraxisreg.htm).

### What makes a good candidate for being a registered axis?

While it would be possible to register any number of axes that might be proposed, it wouldn't be beneficial to do that. In general, the best situation would be to have the fewest number of axes that provide the greatest benefit for font developers, layout applications, content creators and consumers. Such maximal efficiency may not be achievable, but it should still be a guiding principle. Therefore, it's important to consider what makes a good candidate for being a registered axis.

A proposal to register an axis will not be sufficiently mature until a case is made that it is a good candidate for being a registered axis. Evaluation can proceed more quickly if a proposal provides clear explanation of the merits early on.

Any axis that might be conceived can always be used in a font or font family as a custom axis. As mentioned above, a _registered_ axis can provide benefits in relation to conventionality or to interoperability. Thus, to determine whether an axis should a _registered_ axis, it’s important to consider whether there would be likely benefits these two areas.

An axis is a good candidate for registration if there are likely benefits in regard to conventionality. If a type of design variation can only be usefully applied in a limited set of cases, there is not much to be gained by striving to make that axis conventional. But if a type of design variation can be broadly useful across many situations, then there will be benefits for font developers, applications and end users if that axis becomes conventional. The broader the range of potential usefulness for an axis in different fonts or font families, the better a candidate it is for registration.

Similarly, an axis is a good candidate for registration if there are likely benefits in regard to interoperability. If appliations can provide useful behaviors utilizing the axis, whether by recognizing relationships between fonts or by being able to select axis values to get a predictable result, then there is an interoperability benefit.

Consider as a hypothetical example an axis that specifies the thickness of the cross bar of the capital letter A but nothing else. It's easy for users to understand, and they would be able to know how to find fonts with a particular thickness to this stroke or would know how results with two different fonts are likely to compare; and it could be applied to many different fonts. But there would not be much benefit from making this conventional. Similarly, it’s unlikely that applications would find interesting ways to make use of it. Hence, this would not be a good candidate to be a registered axis.

In addition to benefits in relation to conventionality and interoperability, a proposed axis should be evaluated in relation to alternative possibilities. For example:
- Would the kind of design variation be better handled using OpenType Layout features?
- Is there a different way to characterize a variation, or a different kind of scale, that would provide the same benefits in a simpler, better, or more elegant way?
Alternatives should always be considered before concluding that the proposal is the best solution.

Also, a proposed axis should be considered in relation to other axes:
- Is it similar to another already-registered axis? If so, is there sufficient benefit to having another similar axis registered?
- Is it part of a system of axes that need to be used in a coordinated way to provide the best benefits? Or is it dependent on other axes to provide any real benefit at all?
- How does this axis interact with other commonly-used axes? Does it provide a useful complement? Would it conflict with any other axes so that they could not, in practice, be used together?
When evaluating a proposed axis, it may be necessary to evaluate it together with other proposed axes. The impact of the proposed axis for the entire set of registered axes should also be considered.

In summary, then, a proposal should lay out a case as to how the proposed axis will be useful as a registered axis, rather than being used as a custom axis. A proposal should preferably discuss alternatives, and call out any relationships to other registered or proposed axes. Even though a proposal might cover some of these things, it is to be expected that other points may arise in discussion of the proposal, potentially including alternative proposals. In some cases, a full understanding of the merits of a proposal may require time to develop, perhaps with prototypes or other investigations to gain better understanding. 

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
