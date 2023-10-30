# Feature Name: `bevy-bounties`

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
   2. Funds are held in escrow until either the bounty is completed, or the maintainers decide that it should be cancelled.
   3. Bounties can be **cancelled** by the maintainers if they no longer fit the project direction in a way that cannot be fixed by amending the bounty.
   4. When this happens, all funds (other than the initial submission fee and any completed milestones) will be refunded for that bounty to the best of the maintainers' abilities.
4. As soon as a bounty is **posted**, community members may submit confidential **bids** to the maintainers, vying for the project.
   1. Bids stay open for 1 week following the first submitted bid. This deadline is publicly listed.
   2. Each bid contains the estimated timeline for completion (broken down by milestones), and (optionally) a section for the background and expertise of the bidder.
   3. Individuals, companies and ad-hoc teams may all submit bids for a project.
   4. Maintainers evaluate each candidate or team, ensuring that they have the expertise and available time to complete the bounty in a timely fashion.
   5. Every candidate will receive personal feedback from the maintainers, explaining why they did or did not receieve the bounty.
   6. If a bounty is completed incidentally, the bounty will be awarded to whoever completed it, but they shall be gently chided for not putting in a bid. A repeated pattern of behavior that is consistent with an attempt to bypass the bidding process will result in disqualification for future payouts.
5. Maintainers select a candidate from the **qualified bidders**, and assign them the bounty.
   1. Funds earned via the bounty program are publicly tracked.
   2. If multiple bidders are qualified, then the bounty is awarded to the bidder with the lowest earnings from this program within the last 12 months.
   3. If no bidders are qualified, the bounty is reopened.
6. Work starts on the bounty, and maintainers and SMEs evaluate its progress against the milestones in the bounty.
   1. Work must be completed to the existing standards of the Bevy project: high quality, correct, and useful, but often incremental.
   2. Paid Bevy maintainers will prioritize review for bounty work, to ensure it progresses steadily.
7. As milestones and bounties are completed, the Bevy legal organization pays out the earned funds to the **bounty completer(s)**.
   1. A fixed fraction (less than 50%, more than 5%) of the bounty is granted to the Bevy legal organization itself as **overhead**, funding the salaries of the paid maintainers and paying for administration of this program. All transaction fees are taken from the overhead.
   2. The remaining funds are disbursed however the bounty completer(s) chooses:
      1. Directly to them via payment methods of their choice
      2. Donated to the Bevy legal organization
      3. Put towards another bounty
      4. Donated to a charity of their choice
   3. No matter who performs or completes the work in the bounty, the team that won the bid for the bounty will receive the payout. They may but are not required to voluntarily choose to expand their team and share the payout with other contributors who completed the work.
8. Bounties can be **unassigned**, either voluntarily by the team responsible, or after severe time overruns.
   1. If a milestone is more than 200% behind schedule (3 times the amount of time bid), it will automatically be unassigned.
   2. Once a bounty has been unsassigned, bids will be reopened for any remaining milestones.
   3. Bidders who failed to complete a bounty within the margin of time alloted will not be able to rebid on it, but may bid on other bounties in the future.

## Implementation strategy

If this proposal is accepted, we will need:

1. A Bevy legal organization.
2. Paid full or part-time staff members of the Bevy legal organization to administer this process.
3. A place for bounties to be submitted.
4. A way for bounties to be publicized and tracked.
5. A mechanism for the Bevy legal organization to accepting and distribute funds in a trustworthy and legally-compliant way

## Drawbacks

### The bounty program may be time-consuming to create and administer

Creating the infrastructure, and then evaluating, shaping and helping out bounties will be a large project, both initially and on an ongoing basis.

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

### Why can bounties be funded by multiple sources?

This increases complexity in our implementation: why not just have a single fixed price upon submission?

There's two good reasons:

1. Bounties may initially be underpriced, relative to the amount of work / frustration required to fix the problem. If a bounty sits unclaimed for too long, it should be possible for interested users to incentivize it further.
2. The bounty program should be accessible to small donations. Individually, $5 or $10 may be justifiable for a hotly-awaited feature or particularly annoying bug, but that won't be enough to justify the overhead of the process or attract additional developers. By allowing them to pool their funds, we can ensure that they remain important stakeholders in all areas of Bevy's development.

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

### Why does the bounty get awarded to the team that won the bid, no matter who did the work?

Ultimately, the point of the bounty program is to ensure that valuable work is completed and Bevy becomes better.
Fairness, while valuable, is not the primary concern: ensuring that the development culture stays positive and collaborative is much more important.

Consider the alternative, where a bounty is awarded to whoever completed the work, regardless of who won the bid.
Then, an unscrupulous but talented contributor steps in, and puts together a fix before the original team has a chance.
Does the maintainer team merge this PR, and give that contributor the money?
The team may be counting on those funds, and this is incentivizing a toxic first-come-first-serve race to complete bounties.
Or do we reject the PR out of hand, causing the work to be wasted entirely?

Next, consider a much more common and innocent case where, after seeing an implementation, an alternative, higher quality alternative can be quickly be put together.
Are the maintainers bound to merge the winning team's counterproposal instead?
Do we rely on the helpful contributor to graciously share money (like they currently share credit) in an ad-hoc fashion?

Or if an bounty team's proposal is dramatically altered and improved in the process of code review, are the reviewers entitled to a share of the bounty?

By having clear rules that uphold the primacy of the bidding process, we can strengthen its legitimacy, disincentivize bad behavior and reduce conflict arising due to good-natured collaboration.
Everyone wants to ensure that Bevy is the best it can be: we should be careful not to get in the way of that.

### Why does the Bevy legal organization deserve an overhead payout?

We think that a hands-on approach to bounty reviews will lead to better outcomes for everyone involved, but it requires a great deal of time and expertise for each bounty.
Maintenance of code doesn't end when the first PR is merged either: every new feature requires ongoing resources to keep working as the code base changes around it.
By incentivizing maintainers to participate in and steward the bounty process, we can make sure it continues to keep working smoothly.

This time commitment (in addition to the transaction costs) are likely to scale proportionally with the amount of work for each bounty: hence, a proportional cut.
By funding maintainers through the bounty program, we can align incentives for everyone, and ensure that work done this way

### Why should we build our own tools for this, rather than using an existing solution?

This idea isn't novel: [various platforms](https://www.oss.fund/categories/bounties/) offer a premade solution, which packages up all of infrastructure needed to run a bounty program that works roughly like this.
Referring to themselves as "crowdsourcing" or "open source bug bounty" platforms, they often focus on security issues, use cryptocurrency in a poorly-motivated fashion, and are young, VC-backed platforms.

There are three key arguments for giving in to not-invented-here syndrome in this case:

1. Every intermediary will take their own cut, reducing the money avialable to both bounty completers and the Bevy legal organization.
2. We want to be able to control and tailor the process to Bevy's needs.
3. Virtually all of the options here are precarious (see [this historical analysis](https://wiki.snowdrift.coop/market-research/history/software)): what happens to the funds, our workflows and community traction when they shut down?

For example, two of the most prominent options are [Algora](https://www.oss.fund/algora/) and [BountySource](https://www.oss.fund/bounty-source/).
Algora takes a 20% cut, and as of this writing, has only $74k of awarded bounties: not exactly a company that is likely to exist in its current form in 10 years.
BountySource's main app is, at the time of this writing, completely down, and many of the links in that list are completely dead, only a couple of years later.

[HackerOne](https://www.oss.fund/hackerone/) appears to be the longest lived and most sustainable business, but it's very much focused on security features and does not support the workflows we need.

[Snowdrift.coop](https://snowdrift.coop/) looks at first glance like a promising option: community-led, competently run and full of [great insights](https://wiki.snowdrift.coop/).
However, they seem to be in alpha still and cannot be used for other projects, and it's not clear how active [ongoing development](https://gitlab.com/snowdrift/) is.

## Prior art

[Bug bounty programs](https://en.wikipedia.org/wiki/Bug_bounty_program) are a long-standing tradition in software, traditionally funded by the company that makes the software to reward people who report high-priority vulnerabilities, crashes and critical logical flaws.
However, what we're attempting here is something slightly different.
Rather than being funded by the Bevy legal org itself, it is a mechanism for fundraising: we're just an intermediary for the market.
And instead of being awarded to "any qualifying fix", specific requests are put out.

Instead, this proposal is much closer to a [crowdfunded](https://www.bdc.ca/en/articles-tools/entrepreneur-toolkit/templates-business-guides/glossary/crowdfunding) [two-sided marketplace](https://en.wikipedia.org/wiki/Two-sided_market) for [procurement](https://en.wikipedia.org/wiki/Procurement) of Bevy development.
Fortunately, we can avoid the classic chicken-and-egg problem of two-sided markets: due to the thriving open source nature of the project, there are plenty of users itching to pay for the features and fixes they need, and skilled contributors who would love an excuse to contribute more, dive into gnarly bugs and tackle bigger projects.
Bevy would act as both a crowdfunding platform and a specialized [freelancing agency](https://en.wikipedia.org/wiki/Freelancer#Internet_and_online_marketplaces), pooling funds, promoting projects and providing [escrow services](https://en.wikipedia.org/wiki/Escrow) to reduce transactional costs and create a trusted place for funders and contributors to come together.

Each bounty is an open [request for proposal](https://en.wikipedia.org/wiki/Request_for_proposal), driven by the needs of Bevy users and vetted and refined by the Bevy project.
While the literature on RFPs often prescribes a more formal and rigid process than we need to follow here, there are a good lessons to learn:

1. Use a standardized template that covers all of the important details to streamline the process.
2. Make sure the bidding process is fair and transparent.
3. Make sure that vendors (contributors in this case) are actually equipped to complete the request.
4. Break the work to be completed into clear, actionable milestones.

### Zig's criticisms of bounty programs in open source

The [Zig team wrote a scathing critique of bounty programs](https://ziglang.org/news/bounties-damage-open-source-projects/) that's worth digging into.

> - Bounties foster competition at the expense of cooperation.
> - Bounties are an utterly simplistic way of dealing with the business management side of creating software:
>   - Instead of scouting for a suitable candidate, you’re letting battle royale dynamics pick a winner for you, at the expense of everybody who’s going to lose the competition.
>   - Instead of creating a clear contract where you take on some of the risk, you implicitly put the entirety of the risk on the contestants (eg partial solutions don’t get any payout).
>   - Instead of allocating time and resources to proper due diligence, you instead penalize any form of thoughtfulness in favor of reckless action (eg a solution just needs to pass a test suite).
>   - Instead of planning for the full lifecycle of software, which also includes maintenance, you end up with a quickly bitrotting artifact that is of no practical use to anybody.
>   - Instead of spreading unease to all the people involved, it would be preferable you instead learned how to do business properly.
> - On projects less radical than Zig, you might also put pressure on the development team to accept the winning submission, which, given the above, will probably not be the most well-thought-out and maintainable solution.

As [discussed on HackerNews](https://news.ycombinator.com/item?id=37541994), the story that prompted this post is not as clear cut as "all bounties are bad".

> You proposed a change to a repo you do not own. You offered an incentive to 3rd party developers to push PRs to that repo. You did not wait until the proposal was accepted. You thus required the community maintaining that repo to do extra review work on a feature they hadn't officially accepted yet. You were refused, and then offered the same incentives somewhere else, with the same drawbacks on the zig community.

Similar experiences were shared, in the context of developing a game:

> I have always been of the same opinion, which I formed years ago helping with Cataclysm: Dark Days Ahead development: "development by bounty" leads to inevitable "(un)designed by a whale", i.e. a few with cash to spend on such things enforcing whatever they *feel they will like* on everybody else. The notion of a coherent whole, whether it's a game or anything else, doesn't really go well with "voting with wallets".

Unsurprisingly, "design by the richest" is a poor strategy.

As discussed in the Rationale and Alternatives sectuib, this proposal is deliberately different from the situation created here in important ways:

1. Bounties are carefully vetted and refined by project leadership.
2. Bounties are assigned via a bidding process, rather than a first-come-first-serve process.
3. Would-be bounty completers are vetted by project leadership to match the needs of a task with the skills available.
4. Partial solutions get partial payout, via milestones and the ability to form ad hoc teams.
5. A fraction of the bounties is allocated to the maintainers, to help cover administration, review and maintenance.

### FossFactory's analysis of bounty programs

FossFactory, a semi-defunct FOSS bounty site, offers [their own analysis](https://www.fossfactory.org/why.php) of the problem space, and why so many other companies have tried and failed to build a marketplace.

To summarize and respond to their insights:

- First-come-first-serve is a terrible model, which encourages racing and disincentivizes collaboration.
  - We firmly agree with this: this a recurring problem in this space and appears to be structural.
- Exclusive project assignment via a bidding process (pioneered in 1999 by Cosource.com) does a good job to fix this.
  - This is the model that Bevy's project is using.
- Project assignment requires substantial project management overhead.
  - This is expected, and why the Bevy legal organization takes an overhead fee on each bounty.
- Project assignment must be fairly opaque, but then needs to be carefully managed for fairness and transparency.
  - This is definitely a challenge.
  - Clear, explicit processes and feedback go a long way.
  - By requiring transparency within a vetted group of maintainers, we should be able to eliminate the worst forms of favoritism while allowing for open submissions.
- Work within (open source) software projects is often stalled, infeasible or abandoned.
  - Bevy definitely experiences this!
  - This is why the proposal includes estimated timelines, and clear processes for dealing with failed and cancelled bounties.
- Without the promise of exclusivity, raising funds can be challenging.
  - So far, this has not been a concern. Many of the companies working with Bevy have been happy to contribute to or fund shared open source libraries.
  - Only the core game (or other technology) generally remains proprietary: for the rest, reducing maintenance burden wins out over complete control and competitive exclusion.
- Sponsors often want control over the details of the final product.
  - By making Bevy leadership the intermediaries who have final say over both what's contained in a bounty, and when it is complete, we can remove this tension.
  - Sponsors can continue to engage throughout the development process, but are not structurally privileged over other community members when doing so.

## Unresolved questions

1. Should we use a minimal funding threshold or submission fee?
   1. Very similar, the only difference is "do you need to pay if your bounty is rejected"
2. What, exactly, does the Bevy legal organization look like?
3. How much should the submission fee be?
4. What percentage of overhead should the Bevy org ask for?
5. In terms of websites, APIs and bank accounts, how should the bounty process be implemented?
6. How polished should our initial Bevy Bounties site be before we ship it?

## Future possibilities

1. Submitting bounties for improvments to / the creation of third-party open source tools in the Bevy ecosystem.
2. Making the underlying bounty infrastructure reusable for other open source projects.
