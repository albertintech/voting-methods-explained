# Proportional STAR Voting

## Quota-Based Cardinal Proportionality

---

## Currently Used / Proposed Use

**Currently Used:** DSA-LA adopted Proportional STAR for internal multi-winner leadership elections in 2024. This is an organizational election, not a governmental one.

**Proposed Use:** The Congressional Elections Modernization Act (CEMA) would establish Proportional STAR as the method for electing all members of the U.S. House of Representatives from multi-member congressional districts.

---

## Statement of Purpose

Proportional STAR Voting -- also referred to as STAR-PR in other literature -- is the proportional representation method in the STAR voting family. It uses the same 0-5 star ballot as single-winner STAR voting, but replaces the single-winner counting process with a multi-winner algorithm that produces proportional outcomes.

The previous article introduced reweighting as one way to manage voter influence across rounds in score-based proportional systems. Proportional STAR uses a different mechanism: quota-based allocation. Rather than diminishing every voter's weight gradually, it removes a defined quota of the winner's strongest supporters after each seat is filled. The remaining voters continue at full strength.

The counting algorithm that implements this allocation is called Allocated Score. In 2018, the Equal Vote Coalition convened a research committee of election scientists and voting method researchers to evaluate competing approaches to proportional tabulation with star ballots. After two years of study, the committee recommended Allocated Score as the tabulation method for Proportional STAR. Other algorithms were evaluated -- including Sequentially Spent Score and Sequential Monroe -- but Allocated Score was the consensus recommendation, balancing proportionality, simplicity, and strategic resilience.

This article explains how Proportional STAR works, demonstrates the counting process through a fully worked example, and examines the method's structural properties, strategic considerations, and candidate incentives.

---

## Section 1: How Proportional STAR Works

In a Proportional STAR election with K seats and V voters, seats are filled one at a time through sequential rounds. Each round has two stages: scoring and allocation.

### Scoring

For each remaining candidate, the system computes a weighted score total -- the sum of every voter's score for that candidate, multiplied by that voter's current ballot weight. In the first round, all ballot weights are 1, so weighted scores equal raw scores. In later rounds, voters whose weight has been reduced contribute less to each candidate's total. The candidate with the highest weighted score total wins the seat.

### Allocation

After a winner is elected, the system allocates one quota's worth of ballot weight from the winner's supporters. Proportional STAR uses a Hare quota: the total number of voters divided by the number of seats.

> Quota = V / K

Allocation proceeds by sorting all voters by the score they gave the winner, from highest to lowest. Working from the top of this sorted list, voters are fully allocated -- their ballot weight is set to zero -- until one quota has been consumed. Voters who gave the winner the highest scores are allocated first.

If the quota boundary falls within a group of voters who all gave the winner the same score, fractional surplus handling applies. The remaining quota need is divided equally among all voters in that group, and each has their weight reduced by an equal fraction. This ensures that voters who supported the winner equally are treated equally.

Voters below the allocation boundary -- those who gave the winner a lower score than the group where the quota was filled -- are not affected at all. Their ballot weight remains exactly where it was.

### What This Produces

Each seat is associated with a specific group of voters who paid for it. The boundaries are hard: once a voter has been allocated, their influence on subsequent seats is removed (fully) or reduced (fractionally, for voters at the threshold). Each elected candidate has a defined constituency -- the voters whose support was spent to fill that seat. Voters who have not yet been represented retain their full voice for the remaining seats.

This is the structural logic that produces proportional outcomes. A large group's voters are progressively consumed as their preferred candidates win seats, creating space for smaller groups -- whose voters remain at full weight -- to elect representatives in later rounds.

### The Optional Runoff

Single-winner STAR voting is defined by its two-step process: score, then automatic runoff. In the proportional context, the automatic runoff is a design variable rather than a fixed feature. The core Allocated Score algorithm does not include a runoff. A variant called Allocated STAR adds a head-to-head runoff for the final seat: the two highest-scoring remaining candidates advance to a pairwise comparison, and the candidate preferred by more weighted voters wins. The Equal Vote Coalition's Phase 2 report notes that runoffs can be added to each round, to the final round only, or not at all.

---

## Section 2: A Worked Example

Consider a five-seat election with 100 voters scoring candidates on a 0-5 scale. The Hare quota is 100 / 5 = 20 voters.

The electorate divides into four groups based on shared preferences:

- **Group A** (35 voters): scores A1 = 5, A2 = 4, C1 = 2, B1 = 0, B2 = 0, D1 = 1
- **Group B** (30 voters): scores B1 = 5, B2 = 4, C1 = 3, A1 = 1, A2 = 0, D1 = 0
- **Group C** (20 voters): scores C1 = 5, A1 = 2, B1 = 2, A2 = 1, B2 = 1, D1 = 3
- **Group D** (15 voters): scores D1 = 5, C1 = 3, B1 = 1, A1 = 0, A2 = 0, B2 = 0

Candidate C1 has cross-group appeal: scored at 2 by Group A, 3 by Group B, 5 by Group C, and 3 by Group D.

### Round 1

All 100 voters are active at full weight. Sum scores:

| Candidate | Group A (35) | Group B (30) | Group C (20) | Group D (15) | Total |
|---|---|---|---|---|---|
| A1 | 175 | 30 | 40 | 0 | 245 |
| A2 | 140 | 0 | 20 | 0 | 160 |
| B1 | 0 | 150 | 40 | 15 | 205 |
| B2 | 0 | 120 | 20 | 0 | 140 |
| C1 | 70 | 90 | 100 | 45 | 305 |
| D1 | 35 | 0 | 60 | 75 | 170 |

**C1 wins with 305.** C1's broad cross-group support produces the highest total despite no single group constituting a majority.

Now allocate one quota (20 voters) of C1's strongest supporters. Sort all voters by their score for C1:

- Score 5: 20 voters (all of Group C)
- Score 3: 45 voters (30 from Group B, 15 from Group D)
- Score 2: 35 voters (all of Group A)

Start at the top. The 20 Group C voters gave C1 a score of 5. Allocating all 20 exactly fills the quota.

**After Round 1:** Group C (20 voters) is fully allocated and removed. Groups A (35), B (30), and D (15) remain at full weight. 80 active voters remain.

### Round 2

Sum weighted scores among active voters:

| Candidate | Group A (35) | Group B (30) | Group D (15) | Total |
|---|---|---|---|---|
| A1 | 175 | 30 | 0 | 205 |
| A2 | 140 | 0 | 0 | 140 |
| B1 | 0 | 150 | 15 | 165 |
| B2 | 0 | 120 | 0 | 120 |
| D1 | 35 | 0 | 75 | 110 |

**A1 wins with 205.** A1 benefits from Group A's concentrated support (35 voters at score 5) plus modest cross-group support from Group B (score 1).

Allocate one quota (20) of A1's strongest supporters. Sort by score for A1:

- Score 5: 35 voters (all of Group A)
- Score 1: 30 voters (all of Group B)

The quota is 20. All 35 Group A voters scored A1 at 5, but only 20 are needed to fill the quota. Allocate 20 of the 35 Group A voters. The remaining 15 Group A voters continue at full weight.

**After Round 2:** 20 Group A voters are allocated and removed. Active voters: 15 from Group A (full weight), 30 from Group B (full weight), 15 from Group D (full weight). 60 active voters remain.

### Round 3

| Candidate | Group A (15) | Group B (30) | Group D (15) | Total |
|---|---|---|---|---|
| A2 | 60 | 0 | 0 | 60 |
| B1 | 0 | 150 | 15 | 165 |
| B2 | 0 | 120 | 0 | 120 |
| D1 | 15 | 0 | 75 | 90 |

**B1 wins with 165.** Group B's 30 voters at score 5 dominate this round.

Allocate one quota (20) of B1's strongest supporters:

- Score 5: 30 voters (all of Group B)
- Score 1: 15 voters (all of Group D)

Allocate 20 of the 30 Group B voters. The remaining 10 Group B voters continue at full weight.

**After Round 3:** Active voters: 15 from Group A, 10 from Group B, 15 from Group D. 40 active voters remain.

### Round 4

| Candidate | Group A (15) | Group B (10) | Group D (15) | Total |
|---|---|---|---|---|
| A2 | 60 | 0 | 0 | 60 |
| B2 | 0 | 40 | 0 | 40 |
| D1 | 15 | 0 | 75 | 90 |

**D1 wins with 90.** Group D's 15 voters at score 5, combined with modest support from Group A (score 1), push D1 to the top now that larger groups have been partially allocated.

Allocate one quota (20) of D1's strongest supporters:

- Score 5: 15 voters (all of Group D)
- Score 1: 15 voters (all of Group A)

The 15 Group D voters are allocated first (score 5). That accounts for 15 of the 20-voter quota. The remaining 5 must come from the next tier: Group A voters who scored D1 at 1. Five of the 15 remaining Group A voters are allocated. The other 10 Group A voters continue at full weight.

**After Round 4:** Active voters: 10 from Group A (full weight), 10 from Group B (full weight). 20 active voters remain.

### Round 5

| Candidate | Group A (10) | Group B (10) | Total |
|---|---|---|---|
| A2 | 40 | 0 | 40 |
| B2 | 0 | 40 | 40 |

**A2 and B2 tie at 40.** A tiebreaker is needed. The specific tiebreaker rule varies by implementation. In this example, suppose A2 wins the tiebreaker.

### Final Result

| Seat | Winner | Primary Constituency |
|---|---|---|
| 1 | C1 | Group C (20 voters) -- cross-group consensus candidate |
| 2 | A1 | Group A (20 voters allocated) |
| 3 | B1 | Group B (20 voters allocated) |
| 4 | D1 | Group D (15) + partial Group A (5) |
| 5 | A2 | Remaining Group A (10) + tiebreaker |

The outcome is proportional: Group A (35% of voters) elects two representatives. Group B (30%) elects one (and nearly a second). Group C (20%) elects one. Group D (15%) elects one. Every group with at least a quota's worth of voters has representation. The cross-group consensus candidate (C1) wins first, rewarding broad appeal.

### What the Example Illustrates

Three features of Proportional STAR are visible in this example.

First, the consensus candidate wins first. C1 accumulated the highest score total not through concentrated factional support but through moderate-to-strong support across all four groups. The scoring mechanism rewards breadth of appeal -- a structural property that persists from single-winner score voting into the multi-winner context.

Second, allocation creates defined constituencies. After each round, a specific group of voters has been identified as "represented by" that winner. The system does not just elect candidates; it assigns voters to the candidates who represent them.

Third, fractional allocation preserves influence. When the quota boundary falls within a group of voters who gave the same score (as in Round 4, where only 5 of Group A's 15 remaining voters were allocated), the unallocated voters continue at full weight. Their preferences for other candidates remain fully active. The allocation mechanism consumes only what is needed and preserves the rest.

---

## Section 3: Structural Properties

Proportional STAR has structural properties that distinguish it from other proportional methods. Some of these properties are advantages. Others are tradeoffs. Evaluating the method requires examining both.

### Properties the Method Satisfies

**Monotonicity.** Increasing a candidate's score on any ballot can never cause that candidate to lose a seat. A candidate who would have won Round 3 will still win Round 3 (or an earlier round) if additional voters increase their score for that candidate. This property holds for both the scoring stage and the allocation step. It is a structural advantage over Proportional RCV, which violates monotonicity through the interaction of the elimination mechanism with vote transfers.

**No ballot exhaustion.** Every voter's scores for every candidate are available to the algorithm at every stage. Ballot weight diminishes as preferred candidates win seats, but the ballot itself does not become inactive. The ballot exhaustion problem documented for Proportional RCV -- where ballots become inert when all ranked candidates have been eliminated -- does not occur.

**Determinism.** Given the same set of ballots, Proportional STAR always produces the same result. The sort-by-score rule for allocation eliminates the randomness that some Proportional RCV surplus transfer methods introduce.

**Consensus incentive.** The scoring mechanism rewards breadth of appeal. A candidate who receives moderate scores from a wide base will outscore a candidate who receives maximum scores from a narrow base but zeros from everyone else. The worked example illustrated this: C1 won the first seat through cross-group support, not factional concentration.

### Accepted Tradeoffs

**Later-no-harm failure.** Honestly scoring a second-choice candidate can help that candidate defeat the voter's first choice. Under Proportional RCV, ranking lower choices cannot hurt higher-ranked candidates -- Proportional RCV satisfies the later-no-harm criterion. Proportional STAR does not. This tradeoff is structural: a method that considers all of a voter's scores simultaneously (rewarding consensus) cannot also guarantee that lower preferences never affect higher ones (later-no-harm). The two properties are in direct tension.

**Centralized tabulation.** Proportional STAR is not precinct-summable. Because ballot weights change after each seat is filled, the full set of individual ballot records must be aggregated centrally before allocation rounds can proceed. Local precincts cannot independently report results that can be simply combined into a final outcome. This is the same tabulation requirement that Proportional RCV imposes. It is a tradeoff relative to single-winner STAR voting, which is precinct-summable.

**Allocation legibility.** The sort-by-score allocation rule is mathematically transparent and fully auditable: every step is deterministic, reproducible, and publicly verifiable. But the process of sorting voters, computing fractional allocations, and tracking ballot weights across rounds is not intuitively obvious. A voter whose ballot weight drops from 1.0 to 0.4 after two rounds may not immediately understand why, even though the calculation is public and reproducible. This is a transparency challenge shared with all proportional methods that use sequential ballot-weight adjustments.

### The State of the Evidence Base

The axiomatic evidence base for Allocated Score is less developed than for the best-studied approval-based methods. The justified representation axioms (JR, PJR, EJR) were defined for approval ballots, and extending them to cardinal ballots with allocation-based proportionality is an active area of research. Allocated Score produces proportional outcomes in worked examples and in simulation evidence, but formal proofs of specific axiomatic guarantees have not been established with the same rigor as the corresponding results for PAV or MES.

Other evaluation tools have been applied. Voter Satisfaction Efficiency simulations measure how closely the method's outcomes match the electorate's aggregate welfare. Candidate Incentive Distribution analysis evaluates the structural incentives the method creates for candidates. Criterion compliance testing checks specific formal properties across large numbers of simulated elections. These are legitimate instruments that provide meaningful information about how the method behaves.

The practical implication for the reader is that the evidence base is composed of different types of evidence than the approval-based methods benefit from. The axiomatic proofs are less developed. The simulation-based and criterion-compliance evidence is more extensive. Both types of evidence are relevant to evaluation.

---

## Section 4: Strategic Considerations

Score-based methods face a strategic consideration that does not arise in the same form under approval, ranked, or party-list ballots: the incentive to exaggerate. The allocation mechanism in Proportional STAR creates a distinctive interaction with this incentive.

### Exaggeration and Allocation

A voter who exaggerates -- scoring a preferred candidate at 5 and everyone else at 0 -- will be among the first voters allocated after that candidate wins. The sort-by-score allocation rule consumes highest-scoring voters first. An exaggerating voter who gives a 5 is consumed before a sincere voter who gives a 3.

This creates a structural feedback: exaggeration increases the voter's contribution to a preferred candidate's victory but also increases the likelihood that the voter will be fully allocated -- and therefore unable to influence subsequent seats. A voter who scores sincerely at 3 may survive allocation and retain influence over later rounds.

The tradeoff is between maximizing influence in the current round (where a higher score helps the preferred candidate) and preserving influence for future rounds (where retaining ballot weight helps elect additional preferred candidates).

### Potential Counterstrategies

A sophisticated voter might consider scoring a likely winner at 4 rather than 5, reasoning that the reduced score still contributes to the candidate's victory while placing the voter lower in the allocation order. If the candidate wins anyway, the voter retains more weight for later rounds.

Whether this counterstrategy is practically effective depends on the competitive environment. If the election is close, the reduced score might cost the preferred candidate the seat. If the outcome is not close, the counterstrategy may preserve influence at low risk. The expected value of the counterstrategy varies by election, and voters lack the information to calculate it precisely.

### The Broader Pattern

The strategic incentive to exaggerate exists as a structural feature of all score-based methods. The key finding from the previous article carries forward: the proportionality mechanism partially self-corrects for exaggeration, and evidence from single-winner STAR voting suggests that the practical incentive magnitude may be smaller than the theoretical incentive. But the tension between ballot expressiveness and strategic behavior is a real design consideration that any evaluation of Proportional STAR should include.

---

## Section 5: Candidate Strategy

Voters are not the only actors who respond to the structure of the ballot and counting rule. Candidates and campaigns face incentives shaped by the same design.

Under Proportional STAR, the scoring mechanism rewards breadth of appeal. A candidate who receives moderate scores from voters across multiple groups benefits from the fact that many of those voters may not yet have been allocated after earlier rounds. A candidate who receives maximum scores only from a narrow faction may find that faction already consumed by the allocation of a previous winner.

The structural incentive rewards building support beyond a single base. A candidate who can earn 3s and 4s from voters in other groups -- in addition to 5s from their own -- will accumulate score from voters who are still active, while a purely factional candidate's supporters may already have been removed.

This incentive structure contrasts with Proportional RCV, where candidates benefit most from being ranked first. Under Proportional RCV, a candidate needs to survive elimination rounds, and first-preference votes are the currency that keeps a candidate alive. Under Proportional STAR, a candidate needs to accumulate the highest weighted score total, and scores from any voter at any level contribute.

While we cannot attribute all candidate and campaign behavior to the voting system, we can identify the structural incentives it puts in place. Proportional STAR creates a consensus incentive that does not exist in bloc methods and that differs from the first-preference concentration incentive under Proportional RCV.

---

## Conclusion

This article examined Proportional STAR Voting -- the proportional representation method in the STAR voting family -- and the Allocated Score algorithm that implements it.

The counting mechanism uses quota-based allocation: after each candidate is elected, a quota of that candidate's strongest supporters is removed from the active electorate. The boundaries between represented and unrepresented voters are hard. Each seat has a defined constituency. Voters who have not yet been represented retain their full influence over the remaining seats. This is the structural logic that produces proportional outcomes.

The worked example demonstrated the method's operation across five rounds. The cross-group consensus candidate won first, illustrating the scoring mechanism's breadth-of-appeal incentive. Subsequent rounds progressively allocated the largest groups' voters, allowing smaller groups to gain influence and elect representatives. The result was a body reflecting the electorate's proportional composition.

Several structural properties emerged. Proportional STAR satisfies monotonicity, produces no ballot exhaustion, generates deterministic outcomes, and creates a consensus incentive for candidates. These properties distinguish it from Proportional RCV, which violates monotonicity and can exhaust ballots. The later-no-harm failure and centralized tabulation requirement are accepted tradeoffs -- structural consequences of the design choices that produce the method's other properties.

The axiomatic evidence base remains less developed than for the best-studied approval-based methods. The simulation-based and criterion-compliance evidence is more extensive. Both types of evidence are relevant to evaluation, and the reader should weigh them alongside the method's thin operational track record.

Proportional STAR has been used in one organizational election in the United States (DSA-LA) and has been proposed for all U.S. House elections under CEMA. That combination -- minimal operational experience alongside a maximally ambitious legislative proposal -- makes the gap between theoretical understanding and practical experience unusually wide. The mechanics are clear. The structural properties are identifiable. What remains unknown is how the method performs under the pressures of large-scale governmental elections: administrative implementation, voter comprehension, strategic adaptation, and the political dynamics of adoption and use.

The next article steps back from specific systems to examine a tool that addresses exactly this kind of uncertainty: voting simulations. When a system's empirical record is thin, simulations offer a structured way to explore how it might perform under controlled conditions. The reader will learn what simulations can and cannot tell us -- and how to evaluate simulation evidence encountered in reform advocacy.


---

<!--
## Revision History

**Revision 1.5** (Current)
- Series-wide revision alignment with pr-08 reframe; article content unchanged from Revision 1.4

**Revision 1.4**
- Added revision history footer per formatting convention
- Article content unchanged

**Revisions 1.0 through 1.3**
- Development history prior to adoption of on-document revision tracking
- Final pre-convention state: five numbered sections plus conclusion covering Proportional STAR mechanics, a worked example, structural properties, strategic considerations, and candidate strategy
-->

*Revision history available in the raw file.*

> 📥 [Download this document](https://github.com/albertintech/voting-methods-explained/blob/main/src/pr-07-proportional-star.md) (opens on GitHub -- click the ⬇ download button)

---

*© 2026 Albert Ramos. All rights reserved.*
