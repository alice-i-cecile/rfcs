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
   3. There is a $50 non-refundable **submission fee** for each bounty. If a bounty accepted, this money is put towards the bounty itself.
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
   3. If no bidders are qualified, the bounty is reopened.
6. Work starts on the bounty, and maintainers and SMEs evaluate its progress.
   1. Work must be completed to the existing standards of the Bevy project: high quality, correct and useful, but not necessarily complete.
   2. Paid Bevy maintainers will prioritize review for bounty work, to ensure it progresses steadily.
7. As milestones and bounties are completed, the Bevy legal organization pays out the earned funds to the **bounty completer(s)**.
   1. A fixed fraction (less than 50%, more than 5%) of the bounty is granted to the Bevy legal organization itself as **overhead**, funding the salaries of the paid maintainers and paying for administration of this program. All transaction fees are taken from the overhead.
   2. The remaining funds are disbursed however the bounty completer chooses: directly to them via a payment method of their choice, donated to the Bevy legal organization, put towards another bounty or donated to another charity of their choice.
8. If a milestone is more than 200% behind schedule (3 times the amount of time bid), it will automatically be marked as **failed**.
   1. Once a bounty has been failed, bids will be reopened.
   2. Bidders who failed a bounty will not be able to rebid on it, but may bid on other bounties in the future.

## Drawbacks

### The bounty program may be time-consuming to create and administer

Creating the infrastructure, and then evaluating, shaping and helping out bounties will be a large project, both initially and on an ongoing basis.

### Paid work may compete with open source work for the same feature

TODO: Open vs closed bids for existing work in progress??

### The existence of a bounty program may change Bevy's priorities and direction

## Rationale and alternatives

### Why do bounties need to be screened?

Collecting funds for a bounty is a soft-promise that "if this work is done, Bevy will merge and ship it".
If it *wasn't*, and used the ordinary review process, both significant work and money will be wasted, and trust will be broken.

One of the key tenets of the [Bevy Sponsorship Pledge](https://bevyengine.org/sponsorship-pledge/) is that money can never buy project direction.

Unless we screen the bounties for alignment *before* funds can be raised by them, it's very easy for maintainers to feel (or be perceived to feel) pressured to accept paid work that does not align with Bevy's vision.
This is very bad for the long-term community of Bevy itself: even when money is involved, the needs of the community as a whole must come first.

By screening and helping to shape bounties, we can both ensure alignment and strengthen the proposal based on the inside view of how the engine and project works.

### Why do bounties have a submission fee?

Bounties aren't issues: work and casual ideas should be tracked there.
They should be used for work that is unusually important to the submitter, that they are willing to chip in to see completed.

Adding a submission fee:

- encourages community members to focus on the problems and features they care about most
- ensures that *some* funding exists for every submitted bounty
- covers the maintainer time spent reviewing the initial submission

### Why are bids confidential?

In order to ensure that bounties are completed effectively and at a high quality level, it's important to evaluate the skills of the bidders.
While it's totally fine if an ordinary PR is submitted and then abandoned due to difficulty, this is much more worrying with money on the line.
The funders will be frustrated by the delays, and other bidders may grow resentful.

As a result, screening bidders based on their experience and expertise is a good way to match work with workers.
In order for this to work effectively, maintainers and SMEs must be able to share their fully honest opinions about the capacity and skills of specific people.
Doing this confidentially helps reduce hurt feelings and public embarassment, and encourages a safe environment for critical feedback.

While anonymity is generally valuable to reduce bias when evaluating these processes, specific histories of open source work within the Bevy ecosystem are incredibly relevant when evaluating bids.
As a result, the bidder(s) identity must be known at the time of submission.

### Why are bids given to the lowest-paid qualified bidder?

A central challenge in running a paid bounty program in open source is building and maintaining community and funder trust in the process.
As a result, fairness and transparency *must* be prioritized.

The proposed mechanism:

1. Does not encourage rushed first-come-first serve bids, but still lets work start relatively quickly.
2. Fights nepotism, as it is objectively measurable, and has internal accountability between maintainers and SMEs.
3. Still allows maintainers and SMEs to ensure that bounties are only claimed by qualified appplicants, to reduce the rate of failure.
4. Encourages broad participation and spreads out the financial benefits.

### Why does the Bevy legal organization deserve an overhead payout?

We think that a hands-on approach to review will lead to better outcomes for everyone involved, but it requires a great deal of time and expertise for each bounty.

This time commitment (in addition to the transaction costs) are likely to scale proportionally with the amount of work for each bounty: hence, a proportional cut.
By funding maintainers through the bounty program, we can align incentives for everyone, and ensure that work done this way

## \[Optional\] Prior art

TODO.

## Unresolved questions

1. Should we use a minimal funding or submission fee?
2. What, exactly, does the Bevy legal organization look like?
3. What submission fee should we set?
4. What percentage of overhead should the Bevy org ask for?

## \[Optional\] Future possibilities

1. Using this project for 