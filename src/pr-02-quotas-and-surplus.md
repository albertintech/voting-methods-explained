# Quotas and the Price of a Seat

## The Mathematics of Fair Allocation

---

## Statement of Purpose

The previous Foundation article introduced the concept of an algorithm: a step-by-step procedure that proportional systems use to elect candidates sequentially, adjusting voter influence after each seat is filled. That article described the structure of these algorithms without specifying the mathematical tools they operate on.

This article introduces those tools.

The central concept is the **quota** -- the number of votes a candidate needs to earn a seat. Quotas answer a question that never arose in Part 1: how much support is "enough"? Under bloc voting or SNTV, the answer was implicit -- the candidates with the most votes win, regardless of how much support they have. Proportional systems make the answer explicit. They define a threshold of support, and candidates who reach it have earned representation.

Defining that threshold turns out to be more consequential than it first appears. Two quota formulas are in wide use, and the choice between them affects which groups benefit and by how much. The quota also creates two problems that every proportional system must solve: what happens when a candidate receives more support than the quota requires (the surplus problem), and what happens when the vote totals do not divide evenly into seats (the remainder problem).

These are the mathematical tools that the proportional systems examined in the rest of this series depend on. This article builds them explicitly so that the system articles can focus on mechanics rather than prerequisite explanation.

---

## Section 1: The Price of a Seat

In a single-winner election, the threshold for winning depends on the system. Under plurality, it is one vote more than the second-place finisher. Under a majority-rule system, it is more than half the votes cast. But the threshold is always relative -- defined by how other candidates perform, not by an absolute number.

Proportional systems work differently. When multiple seats must be distributed to reflect the distribution of voter support, the system needs an absolute standard: a defined quantity of support that is "enough" to earn one seat. This quantity is the quota.

The intuition is straightforward. If 100,000 people vote in an election for 5 seats, and the goal is to distribute those seats proportionally, then each seat should "cost" roughly the same number of votes. The quota is that cost -- the price of a seat, expressed in votes.

Two quota formulas dominate multi-winner voting theory and practice. They produce different prices, and the difference matters.

---

## Section 2: The Hare Quota

The Hare quota is the simpler of the two formulas. It divides the total number of valid votes by the number of seats:

> Hare quota = total votes / seats

In an election with 100,000 votes and 5 seats:

> 100,000 / 5 = 20,000

The Hare quota is 20,000. Each seat "costs" 20,000 votes.

The logic is intuitive: if the total vote is divided equally among the available seats, each seat's share is the Hare quota. A group commanding exactly 20% of the vote -- one Hare quota's worth -- has earned exactly one seat.

### A Worked Example

Consider a simpler election: 60 voters, 3 seats, and four candidates.

> Hare quota = 60 / 3 = 20

Any candidate who receives 20 or more votes has reached the quota and is entitled to a seat.

Suppose the first-choice vote totals are:

| Candidate | Votes |
|---|---|
| Alvarado | 25 |
| Burgess | 18 |
| Chen | 12 |
| Diaz | 5 |

Alvarado has exceeded the quota (25 > 20) and wins a seat. Burgess, Chen, and Diaz have not reached the quota. How the remaining seats are filled depends on the specific system in use -- a question for later articles. The quota's role is to establish the threshold: 20 votes earns a seat.

Notice that Alvarado received 25 votes but only needed 20. The 5 extra votes are a **surplus** -- support beyond what was needed to win. What happens to those surplus votes is one of the central design questions in proportional systems, addressed later in this article.

---

## Section 3: The Droop Quota

The Droop quota uses a slightly different formula. It divides the total votes by one more than the number of seats, then adds one:

> Droop quota = floor(total votes / (seats + 1)) + 1

In the same election with 100,000 votes and 5 seats:

> floor(100,000 / 6) + 1 = floor(16,666.67) + 1 = 16,666 + 1 = 16,667

The Droop quota is 16,667. This is substantially lower than the Hare quota of 20,000.

### Why the Droop Quota Is Lower

The Droop quota is designed around a specific guarantee: it is the smallest number of votes such that it is mathematically impossible for more candidates to reach the quota than there are seats to fill.

The reasoning works as follows. In an election with S seats and V total votes, if each of (S + 1) candidates received more than V / (S + 1) votes, the total would exceed V -- which is impossible. Therefore, at most S candidates can reach the Droop quota. This means the Droop quota can never produce more winners than seats.

The Hare quota does not have this property. In some configurations, it is possible for more candidates to reach the Hare quota than there are seats, which creates a tie-like situation requiring an additional resolution rule. The Droop quota avoids this by setting the bar slightly lower.

### The Same Example with the Droop Quota

Return to the 60-voter, 3-seat election:

> Droop quota = floor(60 / 4) + 1 = floor(15) + 1 = 16

The Droop quota is 16 -- four fewer votes than the Hare quota of 20.

With the same vote totals:

| Candidate | Votes |
|---|---|
| Alvarado | 25 |
| Burgess | 18 |
| Chen | 12 |
| Diaz | 5 |

Under the Droop quota, both Alvarado (25 > 16) and Burgess (18 > 16) have reached the quota and win seats immediately. Only one seat remains to be filled by the remaining candidates. Under the Hare quota, only Alvarado would have cleared the threshold in the first round.

The lower threshold means more candidates can reach the quota earlier in the process, which reduces the number of rounds needed and the volume of transfers or adjustments required.

---

## Section 4: Hare vs. Droop

The choice between Hare and Droop quotas is not neutral. Each formula has structural consequences.

**The Droop quota favors larger groups slightly.** Because the threshold is lower, a large faction can fill its seats with fewer votes per seat, leaving fewer votes available for smaller groups. In the extreme case, a group with just over 50% of the vote can always win a majority of seats under the Droop quota, even when the Hare quota would not guarantee this.

**The Hare quota tends to produce more proportional outcomes for smaller parties.** The higher threshold means that larger groups must "spend" more votes per seat, leaving a greater share of votes available for smaller groups to reach the quota or compete for remaining seats.

**Most systems in practice use the Droop quota.** Proportional RCV elections in Ireland, Australia, Cambridge (Massachusetts), and most other implementations use the Droop quota. The mathematical guarantee -- that the quota can never produce more winners than seats -- makes it operationally cleaner. The slight bias toward larger groups is accepted as a tradeoff for avoiding the ambiguities that the Hare quota can create.

Both quotas will appear in the system articles that follow. When a specific system specifies one formula over the other, the choice is noted. When the choice matters for outcomes, the consequences are discussed.

---

## Section 5: The Surplus Problem

The surplus problem arises whenever a candidate receives more votes than the quota. Those extra votes -- the support beyond what was needed to win -- represent voters whose full preferences have not yet been used. If those surplus votes are simply discarded, then the voters who cast them have less influence over the remaining seats than voters whose first choice was not yet elected. This is a form of inequity: some voters' ballots counted fully, while others' ballots were partially wasted on a candidate who was going to win anyway.

### Why Surplus Handling Matters

Consider a concrete situation. In a 5-seat election with a Droop quota of 10,000 votes, Candidate A receives 15,000 first-choice votes. Candidate A needs only 10,000 to win. The remaining 5,000 votes are surplus.

If those 5,000 votes are ignored, the voters who cast them are effectively locked out of influencing the remaining four seats. They participated, their candidate won, but their full voting power was consumed by a candidate who did not need all of it.

If those 5,000 votes are transferred -- redirected to the voters' next-preferred candidates at an appropriate weight -- then those voters retain influence over subsequent seats. Their first choice won, and now their remaining preferences can help fill the other seats.

### How Surplus Is Handled

Different proportional systems handle surplus differently. The specific mechanisms will be examined in the system articles, but the general approaches fall into several categories.

**Transfer.** Surplus votes are redistributed to other candidates based on the voters' expressed preferences. This is the approach used by Proportional RCV. The mechanics of transfer -- which ballots move, at what value, and how fractional values are calculated -- vary by implementation and have real consequences for outcomes.

**Reweighting.** Rather than transferring specific ballots, the system reduces the weight of every ballot that contributed to the winner. A voter whose top candidate won might have their ballot weight reduced from 1.0 to 0.5 for subsequent rounds, reflecting the fact that they have already received some representation. This is the approach used by several approval-based and score-based proportional methods.

**Allocation.** A defined number of voters -- equal to one quota's worth -- are assigned to the elected candidate and removed from the counting process entirely. The remaining voters continue at full weight. This is a more aggressive form of adjustment: rather than reducing influence gradually, it removes represented voters completely.

Each approach reflects a different judgment about how voter influence should work across multiple seats. Transfer preserves the most information from the original ballot. Reweighting is computationally simpler and does not require ranked preferences. Allocation creates the cleanest separation between represented and unrepresented voters. None is objectively superior. The choice is a design decision.

---

## Section 6: The Remainder Problem

Even with a well-defined quota, votes rarely divide perfectly into seats. The remainder problem arises when the arithmetic of proportional allocation does not produce whole numbers.

### An Illustration

Consider an election with 100 voters, 5 seats, and three factions:

| Faction | Votes | Hare Quotas Earned (Votes / 20) |
|---|---|---|
| Faction A | 47 | 2.35 |
| Faction B | 34 | 1.70 |
| Faction C | 19 | 0.95 |
| **Total** | **100** | **5.00** |

The quotas earned add up to exactly 5.00 -- the number of seats -- but no faction has earned a whole number of quotas. Faction A has earned two full quotas with a remainder of 0.35. Faction B has earned one with a remainder of 0.70. Faction C has earned zero full quotas but has a remainder of 0.95 -- nearly a full quota.

The whole-number portions account for three seats (2 + 1 + 0). Two seats remain. How should they be distributed?

### Why Remainders Matter

The remainder problem is not a rounding error. It is a structural feature of proportional allocation, and different solutions produce different outcomes.

**Largest remainder method.** Award the remaining seats to the factions with the largest remainders. In the example, Faction C (0.95) and Faction B (0.70) receive one additional seat each. Final allocation: A = 2, B = 2, C = 1. Faction C, with only 19% of the vote, wins a seat -- roughly proportional.

**Under an alternative approach** that favors larger factions, the two remaining seats might go to Factions A and B, producing A = 3, B = 2, C = 0. Faction C, with nearly one quota's worth of support, wins nothing.

The difference between these outcomes is one seat for Faction C -- the difference between representation and exclusion. The remainder method is not a minor technical detail. It determines whether groups near the margin of a quota gain a voice or are shut out.

In party-list systems, the remainder problem is resolved through formal allocation methods (largest remainders, D'Hondt, Sainte-Lague) that are the subject of extensive mathematical and political analysis. In candidate-centered systems like those examined in this series, the remainder problem manifests differently -- through the sequence of eliminations, transfers, and adjustments that determine which candidates fill the final seats. But the underlying mathematical tension is the same: votes do not divide evenly, and the rules for handling the remainder encode a judgment about who deserves representation at the margin.

---

## Section 7: What Follows

The reader now has two foundational tools.

From Foundation A: proportional systems use sequential algorithms that elect candidates one at a time, adjusting voter influence after each seat is filled. These algorithms vary in computational complexity, and their adjustment rules encode design choices about how voter influence should work.

From this article: quotas define the price of a seat -- the quantity of support that earns representation. Two formulas (Hare and Droop) set this price differently, with consequences for which groups benefit. Quotas create the surplus problem (what happens to votes beyond the quota) and interact with the remainder problem (what happens when votes do not divide evenly into seats).

These tools are not abstract. They are the operating components of every proportional system examined in the rest of the series.

The next article begins Movement 3: the proportional systems themselves. It opens with Proportional RCV -- historically known as the Single Transferable Vote, and the multi-winner extension of Ranked Choice Voting. Proportional RCV uses the Droop quota, transfers surplus votes based on ranked preferences, and eliminates candidates sequentially when no one reaches the quota. Every concept introduced in the two Foundation articles -- algorithms, sequential processing, quotas, surplus handling, and the remainder problem -- appears in Proportional RCV's mechanics. The reader will encounter them not as new prerequisites but as familiar tools applied to a specific system.

---

## Conclusion

This article introduced three mathematical tools that proportional systems depend on.

First, the quota -- the defined quantity of support that earns a seat. The Hare quota (total votes divided by seats) is intuitive but can produce more quota-reaching candidates than there are seats. The Droop quota (total votes divided by seats plus one, plus one) is lower and carries a mathematical guarantee that it cannot produce more winners than seats. Most systems in practice use the Droop quota.

Second, the surplus problem -- what happens when a candidate receives more votes than the quota. Surplus votes represent voters whose full preferences have not been used. Different systems handle this through transfer, reweighting, or allocation, and the choice among these mechanisms is a design decision that shapes the kind of proportionality the system produces.

Third, the remainder problem -- what happens when votes do not divide evenly into seats. The rules for distributing seats at the margin determine whether groups near the threshold of a quota gain representation or are shut out.

Together with the algorithmic framework from Foundation A, these tools form the conceptual vocabulary needed to understand how proportional systems work. The series now turns to those systems themselves.

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
- Final pre-convention state: seven numbered sections plus conclusion covering the price of a seat, Hare quota, Droop quota, Hare versus Droop comparison, the surplus problem, the remainder problem, and transition to system articles
-->

*Revision history available in the raw file.*

> 📥 [Download this document](https://github.com/albertintech/voting-methods-explained/blob/main/src/pr-02-quotas-and-surplus.md) (opens on GitHub -- click the ⬇ download button)

---

*© 2026 Albert Ramos. All rights reserved.*
