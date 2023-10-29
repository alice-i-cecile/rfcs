# Feature Name: (fill me in with a unique ident, `my_awesome_feature`)

## Summary

Bevy users want features and fixes, and Bevy developers need to pay the bills!
Let's facilitate that, through a carefully designed bounty board run by the Bevy legal organization.

## Motivation

Bevy is built and maintained by both volunteer contributors and maintainers (who need to eat).
We would like to expand the set of "people paid to work on Bevy" and make sure that the project can be maintained steadily into the indefinite future.
To do that, we need to generate revenue.
We *could* ask more aggressively for donations, but this is both unpleasant for  and poorly suited to serious commercial users.

If you just love the project and want to see it continue to exist, it's easy enough to throw a few bucks a month as a recurring donation.
But from a commercial perspective: why would they donate thousands of dollars a year without any tangible, specific return.
[Sponsorship advertismenet](https://bevyengine.org/) is really nice, but community goodwill doesn't stand up particularly well to the scrutiny of accountants.
Sure, in the abstract this helps them avoid their critical dependency going unmaintained and improves development velocity and quality!

But that's a [collective action problem](https://www.e-education.psu.edu/geog30/node/342): without tangible reasons to give Bevy money,
it's really easy for corporate users to simply defect and hope that others (volunteers, overworked maintainers, corporate peers) pick up the slack.
We can't (and won't!) add a license fee, or sell a commercial version of the software: "Free and Open Source Forever!" is not just a slogan.

We could charge for support, especially of long-term stable versions with backported bug fixes.
Not a terrible idea, but right now, Bevy needs features, fixes and improvements, so then it *can* be reasonably used by the large, risk averse companies that would prioritize paying for support.
Conveniently, hobbyists and commerical game studios are all largely aligned: Bevy should be better, and they don't mind sharing the work that they do to make it better.
So how do we combine a desire to improve Bevy and the money to do so such that people are actually paid to improve Bevy and the changes are released for everyone to benefit from?

The answer is simple, even if the details are tricky.
Create a bounty program for tangible tasks, run by the Bevy legal organization, and then make sure that work actually gets shipped.

## User-facing explanation

The **Bevy legal organization** is a legal entity run by a collection of individuals who make their living stewarding Bevy.
While development decisions are made like before (via a mixture of paid and volunteer contributors, collaborating in the open as peers),
the legal organization exists to serve as a central point for project finances, collecting and disbursing funds to meet the goals set by the project as a whole.

One of its key tasks is to run the **Bevy Bounty** program.
This program connects users (commercial and hobbyist) who want to pay for improvements to Bevy, to the developers (paid maintainers or community members) who would like to make them, but can't tackle or prioritize them without more resources.

To keep everything running smoothly, the lifecycle of a **bounty** is carefully administered by members of the legal organization:

1. A bounty is **submitted for approval**, via a pull request to a repository.
   1. This is later rendered on a dedicated web UI on the bevyengine.org site.
   2. Bounties may be broken down into **milestones**, with seperate funds dedicated to each milestone, in order to split work.
2. Maintainers and SMEs evaluate each bounty, ensuring that it is clear, actionable and something that would be good for Bevy as a whole.
   1. Community member review is very welcome, but each bounty is automatically treated as controversial and subject to those review standards.
3. **Funds** are raised for the bounty, and are submitted to the Bevy legal organization for safekeeping in a seperate account.
   1. Funds may be contributed by any number of individuals or organizations for the same bounty.
   2. Funds are held in escrow until either the bounty is completed, or the maintainers decide that is no longer suitable. If it cannot be amended, all funds will be returned for that bounty.
4. As soon as a bounty is **posted**, community members may submit confidential **bids** to the maintainers, vying for the project.
   1. Bids stay open for 1 week following the first submitted bid. This deadline is publicly listed.
   2. Each bid contains the estimated timeline for completion (broken down by milestones), and (optionally) a section for the background and expertise of the bidder.
   3. Individuals, companies and ad-hoc teams may all submit bids for a project.
   4. Maintainers evaluate each candidate or team, ensuring that they have the expertise and available time to complete the bounty in a timely fashion.
   5. Every candidate will receive personal feedback from the maintainers, explaining why they did or did not receieve the bounty.
5. Maintainers select a candidate from the **qualified bidders**, and assign them the bounty.
   1. Funds earned via the bounty program are publicly tracked.
   2. If multiple bidders are qualified, then the bounty is awarded to the bidder with the lowest earnings from this program within the last 12 months.
6. Work starts on the bounty, and maintainers and SMEs evaluate its progress.
   1. Work must be completed to the existing standards of the Bevy project: high quality, correct and useful, but not necessarily complete.
   2. Paid Bevy maintainers will prioritize review for bounty work, to ensure it progresses steadily.
7. As milestones and bounties are completed, the Bevy legal organization pays out the earned funds to the **bounty completer(s)**.
   1. A fixed fraction (less than 50%, more than 5%) of the bounty is granted to the Bevy legal organization itself as **overhead**, funding the salaries of the paid maintainers and paying for administration of this program. All transaction fees are taken from the overhead.
   2. The remaining funds are dispersed however the bounty completer chooses: directly to them via a payment method of their choice, donated to the Bevy legal organization, put towards another bounty or donated to another charity of their choice.
8. If a milestone is more than 200% behind schedule (3 times the amount of time bid), it will automatically be marked as **failed**.
   1. Once a bounty has been failed, bids will be reopened.
   2. Bidders who failed a bounty will not be able to rebid on it, but may bid on other bounties in the future.

## Drawbacks

Why should we *not* do this?

## Rationale and alternatives

- Why is this design the best in the space of possible designs?
- What other designs have been considered and what is the rationale for not choosing them?
- What objections immediately spring to mind? How have you addressed them?
- What is the impact of not doing this?
- Why is this important to implement as a feature of Bevy itself, rather than an ecosystem crate?

## \[Optional\] Prior art

Discuss prior art, both the good and the bad, in relation to this proposal.
This can include:

- Does this feature exist in other libraries and what experiences have their community had?
- Papers: Are there any published papers or great posts that discuss this?

This section is intended to encourage you as an author to think about the lessons from other tools and provide readers of your RFC with a fuller picture.

Note that while precedent set by other engines is some motivation, it does not on its own motivate an RFC.

## Unresolved questions

- What parts of the design do you expect to resolve through the RFC process before this gets merged?
- What parts of the design do you expect to resolve through the implementation of this feature before the feature PR is merged?
- What related issues do you consider out of scope for this RFC that could be addressed in the future independently of the solution that comes out of this RFC?

## \[Optional\] Future possibilities

Think about what the natural extension and evolution of your proposal would
be and how it would affect Bevy as a whole in a holistic way.
Try to use this section as a tool to more fully consider other possible
interactions with the engine in your proposal.

This is also a good place to "dump ideas", if they are out of scope for the
RFC you are writing but otherwise related.

Note that having something written down in the future-possibilities section
is not a reason to accept the current or a future RFC; such notes should be
in the section on motivation or rationale in this or subsequent RFCs.
If a feature or change has no direct value on its own, expand your RFC to include the first valuable feature that would build on it.
