# Multi-Seat STAR

## An Expressive Ballot in a Majoritarian Structure

---

## Statement of Purpose

The four methods examined so far -- bloc voting, limited voting, cumulative voting, and SNTV -- all use simple ballots. Voters mark one or more candidates. The counting rule tallies those marks. What varies is how many votes the voter receives and whether they can be concentrated.

Multi-Seat STAR uses a fundamentally different ballot. Voters rate every candidate on a 0-5 scale -- the same score ballot introduced in the single-winner Part of this series. The system then applies the two-phase STAR process (Score Then Automatic Runoff) seat by seat. The ballot collects far more information than a simple choose-one or choose-many ballot. The question is whether that information changes the structural outcome.

The answer is nuanced. Multi-Seat STAR produces qualitatively different winners than simple bloc voting -- winners who are broadly acceptable, not merely plurality-preferred. But it does not produce proportional outcomes. The sweep effect remains structurally possible because the counting logic does not reduce a voter's influence after their preferred candidate has been elected. The expressive ballot changes the quality of the majoritarian outcome without changing the majoritarian structure.

This article examines how Multi-Seat STAR works, what the score ballot adds, what it does not add, and when the combination of consensus-seeking and majoritarian selection is the right tool for the job.

Multi-Seat STAR is also known as **Bloc STAR** -- the term commonly used in reform discussions and by the Equal Vote Coalition, which developed the method.

---

## Currently Used / Proposed Use

**Currently Used:** The Python Software Foundation (PSF) adopted Multi-Seat STAR for its Steering Council elections in 2024, replacing Approval Voting. The community concluded that Approval Voting could not distinguish between strong support and weak acceptance, and that a method capturing preference intensity was needed to reflect the community's genuine judgments about candidate quality.

**Proposed Use:** The Federal Judicial Balance and Accountability Act (FJBAA) proposes using Multi-Seat STAR for Senate confirmation of Supreme Court nominees from a presidential slate.

---

## Section 1: How Multi-Seat STAR Works

In a Multi-Seat STAR election with K seats:

1. Each voter assigns a score from 0 to 5 to each candidate. A score of 5 indicates the strongest support; a score of 0 indicates no support. Voters may give the same score to multiple candidates.
2. For the first seat, all scores are totaled. The two candidates with the highest total scores advance to an automatic runoff.
3. In the runoff, every ballot is examined to determine which of the two finalists the voter scored higher. The finalist scored higher on more ballots wins the seat.
4. The winning candidate is elected and removed from the field. The process repeats from step 2 for the next seat, using the same ballots but with one fewer candidate.
5. This continues until all K seats are filled.

### Two Phases, One Ballot

Each seat is filled through two phases using the same ballot. No second election is required.

The **scoring phase** identifies the two strongest candidates by total score. A candidate who accumulates a high total score has drawn support -- at various intensities -- from across the electorate.

The **automatic runoff phase** provides a majority-preference check. The two highest-scoring candidates advance, but the winner is determined by which of the two more voters actually prefer in a direct comparison. The runoff uses the scores already on the ballot: whichever finalist a voter scored higher is counted as that voter's preference.

This two-phase structure is what distinguishes STAR from pure Score Voting. Under pure Score Voting, the highest total score wins outright. Under STAR, a high total score earns a finalist position, but winning requires majority preference in the head-to-head comparison.

### The Iterative Process

In a multi-winner context, Multi-Seat STAR applies this two-phase process once for each seat. After each seat is filled, the winning candidate is removed, and the scoring and runoff phases are applied again among the remaining candidates.

Every voter participates at full strength in every round. No ballots are removed, no voter's influence is reduced, and no reweighting occurs. The same 100 ballots that determined the first seat also determine the second, third, and every subsequent seat.

---

## Section 2: What the Score Ballot Adds

The score ballot collects information that simpler ballots cannot.

Under bloc voting, the ballot records a selection: which candidates the voter supports. Under SNTV, it records a single choice. Neither captures how strongly the voter feels about any candidate, or how the voter evaluates candidates they did not select.

The score ballot captures both. A voter who strongly supports one candidate, moderately accepts a second, and opposes a third can express all three positions on a single ballot: scores of 5, 3, and 0. This information is available to the counting rule, and the counting rule uses it.

### Consensus-Seeking

The two-phase structure uses this information to identify winners who are broadly acceptable, not merely faction-preferred.

In the scoring phase, a candidate who draws moderate scores from across the electorate can accumulate a higher total than a candidate who draws maximum scores from one faction and zeros from everyone else. Broad acceptability is rewarded alongside intense support.

In the runoff phase, the head-to-head comparison uses the full range of scores. A voter who scored both finalists -- even at different levels -- contributes to the comparison. A voter who scored one finalist at 4 and the other at 2 has expressed a preference. The runoff captures that preference even though both candidates received positive scores.

The result is a winner-selection process that is sensitive to the breadth of support, not just its depth. Among the methods examined in this Part, this is a meaningful distinction.

### What Simpler Ballots Cannot Express

Consider two candidates in a five-seat election:

- Candidate A is scored 5 by 60 voters and 0 by 40 voters. Total score: 300.
- Candidate B is scored 4 by 60 voters and 3 by 40 voters. Total score: 360.

Under bloc voting, if both candidates appear on the majority slate, both receive 60 votes and are indistinguishable. Under Multi-Seat STAR's scoring phase, Candidate B's broader support is visible: a higher total score despite lower maximum intensity. The score ballot captures a dimension of voter sentiment that a choose-many ballot cannot.

---

## Section 3: What the Score Ballot Does Not Change

Multi-Seat STAR shares a structural property with every other method examined in this Part: it does not contain a mechanism to reduce a voter's influence after one of their preferred candidates has been elected.

There is no reweighting. There is no allocation. There is no removal of satisfied voters from subsequent rounds. Every voter participates at full strength in every round.

This means that a cohesive majority can still capture every seat under Multi-Seat STAR. If a group constituting 60 percent of the electorate scores its candidates at 5, scores all others at 0, and votes as a unified bloc, it will dominate both the scoring rounds and the automatic runoffs for every seat. The sweep effect is structurally possible.

### Ballot Format Does Not Determine Proportionality

This is a critical distinction that the reader should carry forward into the next Part of the series. The ballot format -- whether it is a simple choose-one, a choose-many, or an expressive score ballot -- is not what determines whether a system produces proportional outcomes. The counting logic is.

Proportional systems use mechanisms that reduce the influence of voters whose preferred candidates have already been elected: reweighting, allocation, or surplus transfer. These mechanisms create structural space for underrepresented groups by ensuring that voters who have already helped elect a winner contribute less to subsequent seat decisions.

Multi-Seat STAR does not use any such mechanism. The ballot is expressive. The counting logic is majoritarian. The result is a system that produces high-quality majoritarian outcomes -- consensus-oriented winners -- but not proportional ones.

This is also why Multi-Seat STAR is examined here, alongside the other multi-winner methods, rather than alongside the proportional score-based systems examined in the Proportional Representation Part. The ballot format is the same as Proportional STAR's. The counting logic is what differs.

The Equal Vote Coalition, which developed both Multi-Seat STAR and Proportional STAR, draws this distinction explicitly: Multi-Seat STAR is designed for elections where consensus-oriented majoritarian selection is the goal, while Proportional STAR is designed for elections where proportional representation is the goal.

---

## Section 4: Not All Majoritarian Outcomes Are Equal

The sweep effect is a structural property shared by all the methods in this Part. But the character of the sweep differs depending on the method.

Bloc voting selects the candidates who receive the most individual votes. A candidate who is intensely supported by a majority faction wins, regardless of whether the broader electorate finds that candidate acceptable. The sweep produces winners who are majority-preferred, but not necessarily broadly preferred.

Multi-Seat STAR selects differently. The scoring phase surfaces candidates who accumulate high total scores, which rewards broad acceptability alongside factional support. The automatic runoff phase confirms each winner through a head-to-head majority-preference check. A candidate who scores moderately across both factions can outscore a candidate who draws maximum scores from one faction and zeros from everyone else. The sweep still occurs -- the majority still fills every seat -- but the winners are consensus-oriented rather than narrowly faction-preferred.

### When Consensus-Oriented Majoritarian Selection Is the Goal

This distinction matters when the election's purpose is to select the most broadly acceptable candidates from a field -- not to distribute representation proportionally.

The Python Software Foundation replaced Approval Voting with Multi-Seat STAR specifically because it needed a method that could distinguish between strong support and weak acceptance among a field of qualified candidates. The Steering Council election is not a legislative body representing competing factions. It is a technical governing body where broad confidence in each member matters more than factional representation.

The Federal Judicial Balance and Accountability Act proposes Multi-Seat STAR for Senate confirmation of Supreme Court nominees from a presidential slate. The goal is to identify the most broadly acceptable nominees -- not to allocate confirmation slots to competing political factions. The sweep effect is structurally appropriate because the election's purpose is consensus selection.

In both cases, the consensus-seeking properties of STAR's two-phase process are what make Multi-Seat STAR a stronger choice than simple bloc voting for the specific task. And in both cases, the distinction between Multi-Seat STAR and Proportional STAR reflects a deliberate choice about what the election is trying to accomplish.

---

## Section 5: Structural Properties

### What Multi-Seat STAR Changes

Multi-Seat STAR replaces the simple ballot with an expressive score ballot and replaces the single-tally counting rule with a two-phase process (scoring round plus automatic runoff) applied iteratively. These changes introduce:

- Preference intensity information that simpler ballots cannot capture
- A consensus-seeking winner-selection process that rewards broad acceptability
- A majority-preference check (the automatic runoff) that resists strategic bullet voting
- Qualitatively different majoritarian winners compared to simple bloc methods

### What Multi-Seat STAR Does Not Change

Multi-Seat STAR does not introduce any mechanism for proportional seat allocation. There is no reweighting, no surplus transfer, and no reduction of voter influence across rounds. The sweep effect remains structurally possible. Multi-Seat STAR is a majoritarian method that produces high-quality majoritarian outcomes.

### Candidate Incentives

While we cannot attribute all candidate and campaign behavior to the voting system, we can identify the structural incentives it puts in place.

Under Multi-Seat STAR, the path to winning involves both phases. A candidate must accumulate a high total score (to reach the top two) and then win a head-to-head comparison (to win the runoff). This creates an incentive to seek broad support rather than relying exclusively on intense factional backing.

A candidate who is scored 5 by their own faction and 0 by everyone else accumulates a lower total score than a candidate who is scored 4 by their faction and 2 or 3 by the opposing faction. The former strategy risks not reaching the runoff. The latter is more likely to advance and more likely to win the head-to-head comparison.

This incentive toward broad acceptability distinguishes Multi-Seat STAR from bloc voting, where factional loyalty alone can be sufficient.

### Administrative Properties

Multi-Seat STAR is more complex to administer than the other methods examined in this Part. The ballot requires a scoring grid rather than a simple mark-one or mark-many format. Tallying requires summing scores, identifying the top two, and conducting a head-to-head comparison -- then repeating the process for each seat. The iterative nature of the count means results take longer to finalize than a single-tally method.

These are real costs. They are the administrative price of the information richness that the score ballot provides.

---

## Conclusion

Multi-Seat STAR is the only method examined in this Part that uses an expressive ballot -- one that captures not just which candidates the voter supports, but how strongly the voter evaluates each candidate relative to the others. The two-phase STAR process uses that information to find consensus-oriented winners: candidates who are broadly acceptable, not merely plurality-preferred.

But the expressive ballot does not produce proportional outcomes. Multi-Seat STAR does not contain any mechanism to reduce a voter's influence after their preferred candidate has been elected. The sweep effect remains structurally possible. The quality of the majoritarian outcome is different from simple bloc voting. The majoritarian structure is the same.

This distinction -- between ballot expressiveness and counting logic -- is one of the most important structural insights in this Part. A more expressive ballot can change the character of the winners. Only a different counting mechanism can change whether the system produces majoritarian or proportional outcomes.

The five methods examined in this Part form a spectrum. The next article synthesizes that spectrum and asks the question that has been building across every article: when is the sweep effect the right structural choice, and when does the election's goal require something the methods in this Part cannot provide?
