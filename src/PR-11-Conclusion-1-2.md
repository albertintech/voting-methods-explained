# Evaluating Multi-Winner Systems

## Conclusion

---

## Statement of Purpose

This series asked a question that the previous series did not:

> How should representation be distributed across multiple seats?

The answer, it turns out, depends on what one values -- and the design space within which those values must be expressed is larger, more varied, and more constrained than the single-winner space that preceded it.

Across ten preceding articles, the series examined multi-winner methods that use familiar ballots -- choose-one, ranked, approval, and score -- but apply counting rules with no single-winner analogue: surplus transfers, harmonic reweighting, budget allocation, quota-based weight spending. Each method made different decisions about how to translate individual preferences into collective representation. Each achieved some design objectives at the cost of others.

This article does not re-summarize the individual methods. The reader can consult the system-specific articles for mechanics and worked examples. Instead, it synthesizes the series by design dimension -- the cross-cutting structural properties that apply to every multi-winner system the reader may encounter, whether covered in this series or not. The goal is a comparative framework: a vocabulary for asking the right questions about any multi-winner system, not just the ones examined here.

---

## The Proportionality Spectrum

The systems examined in this series fall along a spectrum from fully majoritarian to proportional.

At the majoritarian end, bloc voting and Bloc STAR award all seats to the faction with the most support. A cohesive majority capturing 60% of the vote can win 100% of the seats. Part 1 documented this as the sweep effect -- a structural property, not a defect, that may be desirable in elections seeking consensus (primaries, steering committees) and problematic in elections seeking representation of diverse preferences (legislatures, large councils).

In between, limited voting, cumulative voting, and SNTV create structural space for minority representation -- but only through strategic coordination. A minority faction can elect representatives under these systems if it manages its votes effectively. Proportionality is possible but not guaranteed by the counting rule. It depends on voter behavior.

At the proportional end, Proportional RCV, PAV, SPAV, MES, RRV, and Allocated Score (Proportional STAR) all incorporate mechanisms designed to produce proportional outcomes by construction. These mechanisms differ -- surplus transfers, harmonic reweighting, budget allocation, quota-based weight spending -- but they share a structural logic: voters who have already helped elect a winner have their influence reduced for subsequent seats, creating space for unrepresented groups.

The spectrum is not a quality ranking. Where a method falls on it reflects a design choice about what the election is trying to accomplish. The reader's first question when encountering any multi-winner system should be: is proportionality the goal? If so, how is it achieved? If not, what is the goal, and does the system's structure serve it?

---

## The Design Choice: Majority Winners or Proportional Representation

The Introduction established a question that divided the entire series:

> Does this election need majority-preferred winners in every seat, or proportional representation across the seats?

Bloc methods answer: majority winners. They apply single-winner logic to each seat, and the faction with the broadest support wins all or most of them. This is structurally appropriate when the seats are meant to reflect the preference of the whole electorate (consensus bodies, at-large primaries) and structurally inappropriate when the seats are meant to represent the diversity of the electorate (legislatures, councils with geographic or ideological constituencies).

Proportional methods answer: proportional representation. They incorporate mechanisms that reduce the influence of already-represented voters, allowing minority factions to gain seats in proportion to their support. This is the design goal of every method in Movement 3 -- Proportional RCV, Proportional Approval, Proportional Score, and Proportional STAR.

The choice between majority rule and proportional representation is prior to the choice of counting method. A reader evaluating a multi-winner system should determine which goal it serves before comparing it to alternatives. Comparing Bloc STAR to Proportional RCV on proportionality is comparing a car to a boat on water speed -- the comparison is valid, but only one of them was designed for the task.

---

## Ballot Complexity and Voter Burden

Multi-winner systems use the same ballot types as single-winner systems -- choose-one, ranked, approval, score -- but the multi-winner context changes the cognitive demands.

Ranked ballots become more burdensome as the number of candidates increases. Ranking five candidates is manageable. Ranking fifteen imposes substantial cognitive effort and increases the risk of ballot errors and exhaustion. Proportional RCV inherits this burden. The Cambridge and Portland implementations manage it through ballot design and voter education, but the burden is structural and does not disappear with good administration.

Approval and score ballots handle large candidate fields more gracefully. Voters can approve or score as many or as few candidates as they wish, assign the same rating to multiple candidates, and skip candidates they have no opinion about. There is no rank-ordering constraint. This property makes approval-based and score-based methods structurally compatible with elections that attract many candidates.

Choose-one ballots impose the lightest burden: mark one candidate per seat (bloc voting) or one candidate total (SNTV). But the simplicity of the ballot coexists with the strategic complexity of the counting rule. SNTV's one-vote ballot is simple; the vote management required to use it effectively is not. Cumulative voting's point-allocation ballot is moderate in complexity but requires strategic decisions about how to distribute limited resources.

Ballot complexity and system complexity are not the same thing. A system can have a simple ballot and a complex counting process (Proportional RCV), a moderate ballot and a simple counting process (bloc voting), or an expressive ballot and a sophisticated counting process (Allocated Score). The voter burden depends on both the ballot and the degree to which the counting process requires strategic reasoning.

---

## Auditability and Transparency

Multi-winner methods vary substantially in how easily their counting processes can be verified by observers, audited by officials, and understood by voters.

**Hand-countable methods.** Bloc voting, limited voting, cumulative voting, and SNTV are hand-countable. The counting process is simple enough to be performed and verified without computers. Precinct-level results can be reported independently and combined. Ireland hand-counts Proportional RCV elections -- a tradition that demonstrates Proportional RCV's auditability under a specific institutional culture, though it depends on ballot volumes that some larger electorates would exceed.

**Precinct-summable methods.** Single-winner STAR voting and top-K score voting are precinct-summable: local precincts can report score totals that are combined centrally. Multi-winner proportional methods -- Proportional RCV, RRV, Allocated Score, PAV, SPAV, MES -- are not precinct-summable. They require centralized access to individual ballot records because ballot weights or transfer values change across rounds. This is a structural requirement of sequential proportional allocation, not an implementation failure.

**Algorithmic transparency.** All methods examined in this series use deterministic algorithms (with the exception of random-transfer Proportional RCV variants). Given the same ballots, they produce the same results. The algorithms are public and reproducible. But reproducibility and intuitiveness are different properties. A voter who observes the RRV reweighting formula can verify that the calculation is correct without understanding why their ballot weight changed from 1.0 to 0.37. The allocation step in Allocated Score is similarly transparent to auditors and similarly opaque to casual observers.

The transparency question is not whether the method is mathematically correct but whether it is politically legible. A method that produces defensible outcomes through a process voters cannot follow faces a legitimacy challenge that no amount of mathematical rigor resolves. The previous series documented this for single-winner RCV: Burlington, Vermont repealed it following a visible anomaly. The same dynamic applies to multi-winner methods where the counting process is more complex than anything most voters have encountered.

---

## Candidate Incentive Structures

Every voting method creates structural incentives for how candidates campaign, which voters they court, and how they relate to other candidates. These incentives were examined individually in the system-specific articles. The cross-cutting patterns are visible when viewed together.

**Bloc methods** incentivize slate coordination and base mobilization. A candidate benefits from being part of a majority coalition that scores or votes for all of its candidates consistently. The incentive is to consolidate factional support, not to reach across factions.

**Proportional RCV** incentivizes first-preference depth and strategic transfer positioning. A candidate needs to accumulate enough first-preference votes to survive elimination rounds, but also benefits from being ranked favorably by voters whose first-choice candidates are eliminated. The incentive combines core-support intensity with transfer-friendly positioning.

**Approval-based proportional methods** incentivize approval breadth. Under PAV and SPAV, candidates benefit from being approved by voters who have not yet been represented, creating an incentive to build support beyond the candidate's natural base.

**Score-based proportional methods** incentivize broad appeal across the scoring scale. Under RRV and Allocated Score, candidates who accumulate moderate scores from voters across multiple groups outscore candidates with intense but narrow support. The consensus incentive is a structural property of the scoring mechanism.

While we cannot attribute all candidate and campaign behavior to the voting system, we can identify the structural incentives it puts in place. The pattern across this series is that proportional methods with reweighting or allocation mechanisms create broader incentive structures than bloc methods or Proportional RCV. This is not a universal advantage -- some elections may benefit from the factional clarity that bloc methods produce or the transfer dynamics that Proportional RCV creates -- but it is a consistent structural difference.

---

## Interaction with Party Systems

The multi-winner methods examined in this series are candidate-centered: voters evaluate individual candidates, not party lists. This scope was established in the Introduction. But candidate-centered methods still interact with party systems, even in nonpartisan elections.

Under Proportional RCV, candidates from the same party compete against each other for transfers. This creates intra-party competition that party-list systems avoid. Irish Proportional RCV elections illustrate this dynamic: candidates from the same party campaign against each other within multi-member constituencies, and the party's ability to manage this competition affects how many seats it wins.

Under score-based and approval-based methods, there is no formal party role in the counting process. But parties can coordinate voter behavior: instructing supporters to score certain candidates highly, to approve specific slates, or to withhold support from intra-party competitors. The degree to which this coordination occurs -- and the degree to which it is effective -- depends on the party system's strength, the election's stakes, and the voters' willingness to follow instructions.

The candidate-centered methods in this series are structurally compatible with both partisan and nonpartisan elections. But their interaction with party systems is an empirical question that varies by context, and simulation evidence on this dimension is limited. The systems deferred to a future series -- party-list PR, MMP, MMM -- place party systems at the center of the design rather than at the periphery.

---

## The Simulation Evidence and Its Limits

The previous article examined voting simulations in detail. The synthesis relevant to this Conclusion is brief.

The multi-winner methods examined in this series differ substantially in the depth of their empirical records. Proportional RCV has over a century of governmental use. Bloc voting is ubiquitous. Approval-based proportional methods exist primarily in academic literature. Score-based proportional methods have minimal operational experience. Proportional STAR has one organizational use and one federal legislative proposal.

For methods with thin empirical records, simulation evidence fills the gap. Simulations can reveal comparative performance, sensitivity to strategic behavior, and frequency of edge cases. They cannot reveal how a method performs under the pressures of real governmental elections: administrative implementation, voter comprehension, partisan adaptation, and the political dynamics of adoption and durability.

The reader should calibrate their confidence in any multi-winner method to the type and depth of evidence available. Empirical evidence from decades of governmental use carries different weight than simulation evidence from synthetic electorates. Both are informative. Neither is sufficient alone. And the methods with the thinnest empirical records are, by structural necessity, the ones most dependent on the type of evidence that is most assumption-dependent.

---

## What No Multi-Winner System Can Do

The previous series concluded with a foundational insight: no single-winner system satisfies all desirable criteria simultaneously. Arrow's Impossibility Theorem establishes this as a mathematical result for systems that use ranked preferences.

The multi-winner design space has its own impossibility results. They are more technically demanding than Arrow's theorem and were not given dedicated article-length treatment in this series. But the structural lesson they convey is essential to the series' conclusion, and the reader should know it exists.

Several formal results demonstrate that proportional representation, monotonicity, strategyproofness, and clone independence cannot all be achieved simultaneously. A system can satisfy strong proportionality guarantees (like Extended Justified Representation) or strong monotonicity guarantees, but trade tensions between them are unavoidable. The Duggan-Schwartz theorem establishes that any multi-winner method is susceptible to strategic manipulation under general conditions. Balinski and Young's impossibility result shows that no apportionment method can simultaneously satisfy quota and house monotonicity.

These results explain why the tradeoffs documented throughout this series are not accidents of specific system designs. Proportional RCV violates monotonicity not because its designers were careless but because the elimination mechanism that produces its proportionality properties is structurally incompatible with monotonicity. Proportional STAR fails later-no-harm not because of an implementation gap but because the consensus incentive that produces its broad-appeal properties requires considering all of a voter's scores simultaneously. PAV achieves the strongest proportionality guarantee among approval-based methods but is computationally intractable for large elections.

Each tradeoff reflects a constraint. Understanding those constraints is the highest form of structural literacy the series can offer.

---

## The Recurring Theme

Throughout both series, one principle has remained constant:

> Voting systems reflect priority choices.

Each system examined in this series collects certain information from voters, processes it through a specific algorithm, guarantees some structural properties, and leaves others unguaranteed. The choice of what to guarantee and what to sacrifice is a design choice -- and design choices reflect values.

A system that guarantees proportionality for solid coalitions (Proportional RCV) accepts monotonicity failures. A system that guarantees monotonicity (Proportional STAR) accepts later-no-harm failures. A system that guarantees the strongest proportionality axiom (PAV with EJR) accepts computational intractability. A system that guarantees simplicity and hand-countability (bloc voting) accepts the sweep effect.

None of these tradeoffs is avoidable. The impossibility results confirm that they are structural.

What is avoidable is ignorance of the tradeoffs. A voter, a legislator, or a reform advocate who understands what a system guarantees and what it sacrifices is in a fundamentally different position than one who does not. The former can make an informed choice among real alternatives. The latter can only choose among sales pitches.

---

## The Design Space, Expanded

The previous series asked:

> How should we select one winner?

This series asked:

> How should representation be distributed across multiple seats?

The design space is now substantially larger. The reader has encountered methods that use ranked ballots, binary ballots, and cardinal ballots. Methods that achieve proportionality through surplus transfers, harmonic reweighting, budget allocation, and quota-based weight spending. Methods with century-long empirical records and methods with none. Methods proposed for organizational elections and methods proposed for the United States Congress.

The vocabulary for evaluation is also larger. The reader now knows how to assess a method's proportionality guarantees, its ballot complexity, its auditability, its candidate incentive structure, its strategic vulnerabilities, and the type and quality of evidence supporting claims about its performance. The reader knows what voting simulations can and cannot reveal, and how to read simulation evidence critically.

The series deferred several important topics. Party-list proportional representation, Mixed-Member Proportional, and Mixed-Member Majoritarian systems are the dominant global families and will receive full treatment in a future series. Condorcet committee methods, biproportional apportionment, and sortition expand the design space in directions this series did not explore. The political dynamics of system adoption, repeal, and procedural durability -- the question of whether a system that is technically sound can survive the political pressures it faces -- belong to a future series that addresses normative and strategic questions this one deliberately set aside.

What remains is the principle that has governed both series from the beginning.

Voting systems are tools. They encode assumptions about what information matters, how it should be processed, and what outcomes are acceptable. They distribute power. They shape incentives. They constrain the possible.

Understanding them is not a matter of finding the right answer. It is a matter of asking the right questions -- and knowing enough to evaluate the answers.

---

*Prepared for the Voting Methods Explained -- Proportional Representation Series*
*Phase 6 -- Closing*
