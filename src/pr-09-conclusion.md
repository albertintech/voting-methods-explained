# Evaluating Proportional Systems

## Conclusion

---

## Statement of Purpose

This Part asked a question that the previous Parts did not:

> How should a counting rule distribute seats to reflect the distribution of voter support?

The Multi-Winner Part demonstrated that multi-winner elections do not automatically produce proportional outcomes. Adding seats changes the design problem, but proportionality depends on strategy when the counting rule does not enforce it. This Part examined what happens when proportionality is built into the counting rule itself.

Across eight preceding articles, the Part built two Foundation tools -- algorithms and quotas -- and examined four families of proportional methods that use familiar ballots (ranked, approval, score) but apply counting rules with no single-winner or multi-winner analogue: surplus transfers, harmonic reweighting, budget allocation, quota-based weight spending. Each method made different decisions about how to translate individual preferences into proportional representation. Each achieved some design objectives at the cost of others.

This article does not re-summarize the individual methods. The reader can consult the system-specific articles for mechanics and worked examples. Instead, it synthesizes the Part by design dimension -- the cross-cutting structural properties that apply to every proportional system the reader may encounter, whether covered in this Part or not. The goal is a comparative framework: a vocabulary for asking the right questions about any proportional system, not just the ones examined here.

---

## How Proportional Systems Differ From Each Other

The Multi-Winner Conclusion established the broad spectrum from majoritarian to proportional outcomes. This Part examined the proportional end of that spectrum in depth. All four families share the defining structural feature: a mechanism that reduces voter influence after a preferred candidate is elected, creating space for unrepresented groups. But the families differ substantially in how they implement that mechanism.

**Surplus transfer** is the approach used by Proportional RCV. When a candidate wins with more votes than the quota, the excess transfers to voters' next-ranked candidates at a reduced value. The mechanism operates on individual ballots and respects the ordinal structure of voters' preferences. Its design challenge is the surplus transfer method itself -- how to select which ballots transfer, at what value, and whether all supporters are treated equally.

**Harmonic reweighting** is the approach used by the approval-based proportional methods (PAV, SPAV, MES). After each seat is filled, every ballot that approved the winner has its weight reduced according to a formula that depends on how many of the voter's approved candidates have already been elected. The mechanism operates globally on ballot weights rather than transferring individual ballots.

**Score-based reweighting** extends the harmonic logic to cardinal ballots. Under RRV, a voter who gave the winner a high score has their ballot weight reduced proportionally. The mechanism captures preference intensity -- a voter who scored the winner 5/5 is reweighted more heavily than a voter who scored the winner 2/5.

**Quota-based allocation** is the approach used by Proportional STAR (Allocated Score). After each seat is filled, a quota's worth of voter influence is allocated to the winner and spent. Voters are sorted by the score they gave the winner, and those with the highest scores are allocated first -- their influence is consumed rather than merely reduced.

These four mechanisms produce different kinds of proportionality. Surplus transfer respects ordinal preference structure but inherits the path dependence and monotonicity issues of sequential elimination. Harmonic reweighting provides strong axiomatic proportionality guarantees (EJR for PAV and MES) but operates on binary information. Score-based reweighting captures preference intensity but lacks the formal proportionality guarantees established for the approval-based family. Quota-based allocation provides a clear accounting of how voter influence is spent but requires a sequential STAR process that is more complex than any of the alternatives.

The choice among these mechanisms is a design choice -- one that reflects judgments about what information matters, how influence should be managed, and what formal guarantees the system should provide.

---

## Ballot Complexity and Voter Burden

The proportional methods examined in this Part use the same ballot types that the Single-Winner Part introduced -- ranked, approval, and score -- but the multi-winner context changes the cognitive demands.

Ranked ballots become more burdensome as the number of candidates increases. Ranking five candidates is manageable. Ranking fifteen imposes substantial cognitive effort and increases the risk of ballot errors and exhaustion. Proportional RCV inherits this burden. The Cambridge and Portland implementations manage it through ballot design and voter education, but the burden is structural and does not disappear with good administration.

Approval and score ballots handle large candidate fields more gracefully. Voters can approve or score as many or as few candidates as they wish, assign the same rating to multiple candidates, and skip candidates they have no opinion about. There is no rank-ordering constraint. This property makes approval-based and score-based proportional methods structurally compatible with elections that attract many candidates.

Ballot complexity and system complexity are not the same thing. Proportional RCV has a simple ballot and a complex counting process. PAV has a simple ballot and a computationally demanding optimization. Allocated Score has a moderate ballot and a multi-phase sequential process. The voter burden depends on both the ballot format and the degree to which the counting process requires strategic reasoning from voters.

---

## Auditability and Transparency

Proportional methods vary substantially in how easily their counting processes can be verified by observers, audited by officials, and understood by voters.

No proportional method examined in this Part is precinct-summable. All of them require centralized access to individual ballot records because ballot weights or transfer values change across rounds. This is a structural requirement of sequential proportional allocation, not an implementation failure. It distinguishes proportional methods from both the single-winner methods in the first Part (most of which are precinct-summable) and the multi-winner methods in the second Part (which use single-pass counting that can be reported precinct by precinct).

Within the proportional family, transparency varies. Ireland hand-counts Proportional RCV elections -- a tradition that demonstrates the method's auditability under a specific institutional culture, though it depends on ballot volumes that some larger electorates would exceed. The simpler surplus transfer methods (random, Gregory) are hand-countable; the more refined methods (Weighted Inclusive Gregory, Meek) are not. Approval-based methods range from the computationally tractable (SPAV, MES) to the computationally intractable for large elections (PAV with EJR solved exactly). RRV and Allocated Score require computers but are deterministic and reproducible.

All methods examined in this Part use deterministic algorithms (with the exception of random-transfer Proportional RCV variants). Given the same ballots, they produce the same results. The algorithms are public and reproducible. But reproducibility and intuitiveness are different properties. A voter who observes the RRV reweighting formula can verify that the calculation is correct without understanding why their ballot weight changed from 1.0 to 0.37. The allocation step in Allocated Score is similarly transparent to auditors and similarly opaque to casual observers.

The transparency question is not whether the method is mathematically correct but whether it is politically legible. A method that produces defensible outcomes through a process voters cannot follow faces a legitimacy challenge that no amount of mathematical rigor resolves. The Single-Winner Part documented this for single-winner RCV: Burlington, Vermont repealed it following a visible anomaly. The same dynamic applies to proportional methods where the counting process is more complex than anything most voters have encountered.

---

## Candidate Incentive Structures

Every voting method creates structural incentives for how candidates campaign, which voters they court, and how they relate to other candidates. These incentives were examined individually in the system-specific articles. The cross-cutting patterns are visible when viewed together.

The Multi-Winner Part documented that the multi-winner methods in that Part incentivize slate coordination and base mobilization -- the structural logic of majoritarian competition. The proportional methods examined in this Part create different incentive structures.

**Proportional RCV** incentivizes first-preference depth and strategic transfer positioning. A candidate needs to accumulate enough first-preference votes to survive elimination rounds, but also benefits from being ranked favorably by voters whose first-choice candidates are eliminated. The incentive combines core-support intensity with transfer-friendly positioning.

**Approval-based proportional methods** incentivize approval breadth. Under PAV and SPAV, candidates benefit from being approved by voters who have not yet been represented, creating an incentive to build support beyond the candidate's natural base.

**Score-based proportional methods** incentivize broad appeal across the scoring scale. Under RRV and Allocated Score, candidates who accumulate moderate scores from voters across multiple groups outscore candidates with intense but narrow support. The consensus incentive is a structural property of the scoring mechanism.

While we cannot attribute all candidate and campaign behavior to the voting system, we can identify the structural incentives it puts in place. The pattern across this Part is that proportional methods with reweighting or allocation mechanisms create broader incentive structures than Proportional RCV's elimination-based process. This is not a universal advantage -- some elections may benefit from the transfer dynamics that Proportional RCV creates -- but it is a consistent structural difference.

---

## Interaction with Party Systems

The proportional methods examined in this Part are candidate-centered: voters evaluate individual candidates, not party lists. This scope was established in the Introduction. But candidate-centered proportional methods still interact with party systems, even in nonpartisan elections.

Under Proportional RCV, candidates from the same party compete against each other for transfers. This creates intra-party competition that party-list systems avoid. Irish Proportional RCV elections illustrate this dynamic: candidates from the same party campaign against each other within multi-member constituencies, and the party's ability to manage this competition affects how many seats it wins.

Under score-based and approval-based methods, there is no formal party role in the counting process. But parties can coordinate voter behavior: instructing supporters to score certain candidates highly, to approve specific slates, or to withhold support from intra-party competitors. The degree to which this coordination occurs -- and the degree to which it is effective -- depends on the party system's strength, the election's stakes, and the voters' willingness to follow instructions.

The candidate-centered methods in this Part are structurally compatible with both partisan and nonpartisan elections. But their interaction with party systems is an empirical question that varies by context, and simulation evidence on this dimension is limited. The systems deferred to a future series -- party-list PR, MMP, MMM -- place party systems at the center of the design rather than at the periphery.

---

## The Simulation Evidence and Its Limits

The previous article examined voting simulations in detail. The synthesis relevant to this Conclusion is brief.

The proportional methods examined in this Part differ substantially in the depth of their empirical records. Proportional RCV has over a century of governmental use. Approval-based proportional methods exist primarily in academic literature. Score-based proportional methods have minimal operational experience. Proportional STAR has one organizational use and one federal legislative proposal.

For methods with thin empirical records, simulation evidence fills the gap. Simulations can reveal comparative performance, sensitivity to strategic behavior, and frequency of edge cases. They cannot reveal how a method performs under the pressures of real governmental elections: administrative implementation, voter comprehension, partisan adaptation, and the political dynamics of adoption and durability.

The reader should calibrate their confidence in any proportional method to the type and depth of evidence available. Empirical evidence from decades of governmental use carries different weight than simulation evidence from synthetic electorates. Both are informative. Neither is sufficient alone. And the methods with the thinnest empirical records are, by structural necessity, the ones most dependent on the type of evidence that is most assumption-dependent.

---

## What No Proportional System Can Do

The Single-Winner Part concluded with a foundational insight: no single-winner system satisfies all desirable criteria simultaneously. Arrow's Impossibility Theorem establishes this as a mathematical result for systems that use ranked preferences.

The proportional design space has its own impossibility results. They are more technically demanding than Arrow's theorem and were not given dedicated article-length treatment in this Part. But the structural lesson they convey is essential to this Conclusion, and the reader should know it exists.

Several formal results demonstrate that proportional representation, monotonicity, strategyproofness, and clone independence cannot all be achieved simultaneously. A system can satisfy strong proportionality guarantees (like Extended Justified Representation) or strong monotonicity guarantees, but trade tensions between them are unavoidable. The Duggan-Schwartz theorem establishes that any multi-winner method is susceptible to strategic manipulation under general conditions. Balinski and Young's impossibility result shows that no apportionment method can simultaneously satisfy quota and house monotonicity.

These results explain why the tradeoffs documented throughout this Part are not accidents of specific system designs. Proportional RCV violates monotonicity not because its designers were careless but because the elimination mechanism that produces its proportionality properties is structurally incompatible with monotonicity. Proportional STAR fails later-no-harm not because of an implementation gap but because the consensus incentive that produces its broad-appeal properties requires considering all of a voter's scores simultaneously. PAV achieves the strongest proportionality guarantee among approval-based methods but is computationally intractable for large elections.

Each tradeoff reflects a constraint. Understanding those constraints is the highest form of structural literacy this Part can offer.

---

## The Recurring Theme

Throughout all three Parts, one principle has remained constant:

> Voting systems reflect priority choices.

Each system examined in this Part collects certain information from voters, processes it through a specific algorithm, guarantees some structural properties, and leaves others unguaranteed. The choice of what to guarantee and what to sacrifice is a design choice -- and design choices reflect values.

A system that guarantees proportionality for solid coalitions (Proportional RCV) accepts monotonicity failures. A system that guarantees monotonicity (Proportional STAR) accepts later-no-harm failures. A system that guarantees the strongest proportionality axiom (PAV with EJR) accepts computational intractability. The multi-winner methods in the previous Part that guarantee simplicity and hand-countability accept that proportionality depends on strategic coordination rather than institutional design.

None of these tradeoffs is avoidable. The impossibility results confirm that they are structural.

What is avoidable is ignorance of the tradeoffs. A voter, a legislator, or a reform advocate who understands what a system guarantees and what it sacrifices is in a fundamentally different position than one who does not. The former can make an informed choice among real alternatives. The latter can only choose among sales pitches.

---

## The Design Space, Complete

The Single-Winner Part asked:

> How should we select one winner?

The Multi-Winner Part asked:

> How should representation be distributed when multiple seats are available?

This Part asked:

> How should a counting rule distribute seats to reflect the distribution of voter support?

The design space is now substantially larger than where the reader began. Across three Parts, the reader has encountered methods that use ranked ballots, binary ballots, and cardinal ballots. Methods that achieve proportionality through surplus transfers, harmonic reweighting, budget allocation, and quota-based weight spending. Methods with century-long empirical records and methods with none. Methods proposed for organizational elections and methods proposed for the United States Congress.

The vocabulary for evaluation is also larger. The reader now knows how to assess a method's proportionality guarantees, its ballot complexity, its auditability, its candidate incentive structure, its strategic vulnerabilities, and the type and quality of evidence supporting claims about its performance. The reader knows what voting simulations can and cannot reveal, and how to read simulation evidence critically.

This Part deferred several important topics. Party-list proportional representation, Mixed-Member Proportional, and Mixed-Member Majoritarian systems are the dominant global families and will receive full treatment in a future series. Condorcet committee methods, biproportional apportionment, and sortition expand the design space in directions this series did not explore. The political dynamics of system adoption, repeal, and procedural durability -- the question of whether a system that is technically sound can survive the political pressures it faces -- belong to a future series that addresses normative and strategic questions this one deliberately set aside.

What remains is the principle that has governed all three Parts from the beginning.

Voting systems are tools. They encode assumptions about what information matters, how it should be processed, and what outcomes are acceptable. They distribute power. They shape incentives. They constrain the possible.

Understanding them is not a matter of finding the right answer. It is a matter of asking the right questions -- and knowing enough to evaluate the answers.

---

*Prepared for the Voting Methods Explained -- Proportional Representation Part*
