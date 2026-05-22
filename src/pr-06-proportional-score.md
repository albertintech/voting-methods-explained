# Score-Based Proportional Representation

## Cardinal Proportionality

---

## Currently Used / Proposed Use

**Currently Used:** Reweighted Range Voting (RRV) is used in two American organizational contexts:

- The **Academy of Motion Picture Arts and Sciences** has used RRV to select nominees for the Best Visual Effects category since the 85th Academy Awards (for films released in 2012, ceremony in 2013). Academy voters rate films on a 0-10 scale, and RRV selects five nominees. Tabulation is conducted by PricewaterhouseCoopers. This usage has been confirmed active through recent ceremonies.
- The **City of Berkeley, California** adopted RRV in 2016 for its annual council referral prioritization process. Council members rate proposed referrals on a 0-5 scale, and RRV ensures that members who already had high-priority referrals selected have their influence proportionally reduced for subsequent selections. This is a priority-setting process for staff work assignments, not an election of representatives. The adoption was facilitated by the Center for Election Science and has been confirmed active through the 2026 prioritization cycle.

Neither of these American uses involves the election of representatives to governmental office. No American governmental election uses RRV or multi-winner score voting. Multi-winner score voting (top-K) -- the non-proportional baseline covered in this article -- has no identified American usage as a distinct system.

**Proposed Use:** No American legislative proposals for RRV or multi-winner score voting in governmental elections have been identified.

---

## Statement of Purpose

The previous article examined approval-based proportional methods -- systems that use a binary ballot (approve or not) and achieve proportionality through harmonic reweighting or budget allocation. Those methods demonstrated that proportional representation does not require ranked ballots or party lists. A binary ballot, combined with the right counting algorithm, can produce proportional outcomes.

This article extends the multi-winner design space in one direction: from binary to cardinal. Instead of asking voters to approve or not approve each candidate, score-based methods ask voters to assign a numerical rating -- typically on a 0-to-5 scale -- expressing how much they support each candidate.

The potential advantage is expressiveness. An approval ballot treats all approved candidates identically: a voter who is enthusiastic about one candidate and merely tolerant of another must give both the same mark. A score ballot allows the voter to distinguish between the two -- giving one a 5 and the other a 2, for example. That additional information, in principle, lets the counting algorithm make more nuanced decisions about how to distribute representation.

This article examines two methods. The first -- multi-winner score voting (top-K) -- applies the simplest possible counting rule and serves as a non-proportional baseline, just as multi-winner approval voting served that role in the previous article. The second -- Reweighted Range Voting (RRV) -- introduces ballot reweighting to achieve proportionality, using the same sequential logic that SPAV applies to approval ballots but generalized to cardinal scores.

The article also examines a strategic consideration specific to score-based methods: the incentive to exaggerate scores, and the structural consequence that exaggeration can cause score-based methods to behave more like their approval-based counterparts -- a phenomenon that has implications for the entire family.

---

## Section 1: From Approval to Scores

The previous article established a distinction that carries forward here: the difference between **excellence rules** and **proportional rules**.

An excellence rule selects the candidates with the highest individual support. Multi-winner approval voting (top-K by approval count) is an excellence rule. It identifies the most broadly approved candidates, but a cohesive majority can sweep all seats -- the structural consequence Part 1 called the sweep effect.

Proportional rules adjust the counting process so that voters who have already helped elect a winner have less influence over subsequent seats. SPAV does this through harmonic reweighting. The Method of Equal Shares does it through budget allocation. Each mechanism achieves proportionality by different means.

Score-based methods face the same distinction. Multi-winner score voting (top-K by score total) is an excellence rule -- it selects the highest-scoring candidates without adjustment. RRV is a proportional rule -- it reduces the influence of voters who have already been represented. The mechanism is reweighting, extended from binary approvals to cardinal scores.

What is new in this article is the ballot itself. Approval ballots are binary: yes or no. Score ballots are cardinal: they express degrees of support. This difference changes three things.

First, the ballot captures more information. A voter who gives Candidate A a score of 5, Candidate B a score of 3, and Candidate C a score of 1 has communicated a preference ordering and a set of intensity distinctions that an approval ballot could not express.

Second, the counting algorithm must decide what to do with that intensity information. Under approval voting, each approval counts equally. Under score voting, a score of 5 contributes five times as much as a score of 1 to a candidate's total. The cardinal information is not just available -- it is active in the count.

Third, the strategic landscape changes. Under approval voting, the strategic question is where to draw the approval threshold -- which candidates to approve and which to leave unmarked. Under score voting, the strategic question is whether to use the full scale sincerely or to exaggerate -- scoring favorites at the maximum and everyone else at zero. This strategic consideration is examined in Section 4.

---

## Section 2: Multi-Winner Score Voting (Top-K)

Multi-winner score voting is the simplest extension of single-winner score voting to multiple seats. It serves as the non-proportional baseline for this article, just as multi-winner approval voting served as the baseline in the previous one.

### How It Works

In a multi-winner score election with K seats:

1. Each voter assigns a score to each candidate on a fixed scale (e.g., 0 to 5).
2. Each candidate's scores are summed across all voters.
3. The K candidates with the highest total scores are elected.

There is no reweighting, no allocation, and no transfer. The counting rule is identical to single-winner score voting -- highest total wins -- applied K times.

### A Worked Example

Consider a five-seat election with 100 voters and eight candidates. The electorate divides into two groups:

- **Group A** (60 voters) strongly supports candidates A1, A2, and A3, and is lukewarm on the rest.
- **Group B** (40 voters) strongly supports candidates B1, B2, and B3, and is lukewarm on the rest.

Two additional candidates, C1 and C2, have modest cross-group appeal. Voters score sincerely on a 0-5 scale:

| Candidate | Group A score | Group B score | Total Score |
|---|---|---|---|
| A1 | 5 | 1 | (60 x 5) + (40 x 1) = 340 |
| A2 | 5 | 1 | 340 |
| A3 | 4 | 1 | 280 |
| B1 | 1 | 5 | 260 |
| B2 | 1 | 5 | 260 |
| B3 | 1 | 4 | 220 |
| C1 | 3 | 3 | 300 |
| C2 | 2 | 3 | 240 |

The five highest-scoring candidates are A1 (340), A2 (340), C1 (300), A3 (280), and either B1 or B2 (260, requiring a tiebreaker for the fifth seat). Group A captures three seats outright, plus shares influence over C1. Group B captures one seat. The cross-group candidate C1 benefits from moderate support on both sides.

### Why Top-K Score Is Not Proportional

The outcome above is not as dramatically skewed as the top-K approval example in the previous article -- sincere scoring with moderate cross-group appeal can produce more balanced results than binary approvals. But the structural mechanism is the same: top-K score is an excellence rule. It selects the candidates with the highest aggregate support. When a majority group gives uniformly high scores to its preferred candidates, those candidates will dominate the results regardless of how the minority scores its own.

Like its approval-based counterpart, top-K score voting has a legitimate role when the goal is identifying the most broadly supported candidates rather than achieving proportional representation. But when proportionality is the objective, a different counting mechanism is needed.

---

## Section 3: Reweighted Range Voting (RRV)

Reweighted Range Voting addresses the proportionality problem through ballot reweighting -- the same approach that SPAV applies to approval ballots. RRV is, in effect, SPAV generalized to score ballots: it fills seats sequentially, reducing each voter's influence after candidates they scored highly have been elected.

### How It Works

In an RRV election with K seats:

1. Every ballot begins with a weight of 1.
2. Sum each candidate's weighted scores across all ballots. Elect the candidate with the highest weighted score total.
3. After electing a candidate, reweight each ballot. The reweighting formula reflects how much satisfaction a voter has already received from elected candidates:

    New weight = 1 / (1 + (sum of scores the voter gave to all elected candidates so far) / MAX_SCORE)

    where MAX_SCORE is the highest possible score on the ballot (e.g., 5 on a 0-5 scale).

4. In each subsequent round, sum weighted scores and elect the candidate with the highest weighted total.
5. Repeat until all K seats are filled.

### The Logic of Reweighting

The reweighting formula reduces a voter's influence after candidates they scored highly have been elected. A voter who gave the first winner a score of 5 on a 0-5 scale has their ballot weight reduced to 1 / (1 + 5/5) = 1/2. A voter who gave the first winner a score of 0 retains their full weight of 1 / (1 + 0/5) = 1.

This is the cardinal analogue of what SPAV does with approval ballots. Under SPAV, a voter who approved the first winner has their weight halved; a voter who did not approve retains full weight. Under RRV, the degree of weight reduction is proportional to the scores the voter gave to elected candidates. A voter who scored a winner at 3 out of 5 loses less weight than a voter who scored the same winner at 5.

The effect is proportional representation through diminishing influence: voters who have already been "represented" by high-scoring winners contribute less to the election of subsequent winners, creating space for groups that have not yet been represented.

### A Worked Example

Return to the five-seat, 100-voter example from Section 2, with the same scores.

**Round 1:** All ballots have weight 1. The candidate scores are the same as the top-K calculation. A1 and A2 tie at 340. Suppose A1 is elected (by tiebreaker).

**Round 2:** Ballots are reweighted. Group A voters gave A1 a score of 5, so their new weight is 1 / (1 + 5/5) = 0.5. Group B voters gave A1 a score of 1, so their new weight is 1 / (1 + 1/5) = 0.833.

Recalculate weighted scores:

| Candidate | Group A weighted (60 x 0.5) | Group B weighted (40 x 0.833) | Weighted Total |
|---|---|---|---|
| A2 | 30 x 5 = 150 | 33.3 x 1 = 33.3 | 183.3 |
| A3 | 30 x 4 = 120 | 33.3 x 1 = 33.3 | 153.3 |
| B1 | 30 x 1 = 30 | 33.3 x 5 = 166.7 | 196.7 |
| B2 | 30 x 1 = 30 | 33.3 x 5 = 166.7 | 196.7 |
| B3 | 30 x 1 = 30 | 33.3 x 4 = 133.3 | 163.3 |
| C1 | 30 x 3 = 90 | 33.3 x 3 = 100 | 190 |
| C2 | 30 x 2 = 60 | 33.3 x 3 = 100 | 160 |

B1 and B2 are now tied at the top (196.7), having overtaken A2. Group B's candidates benefit because Group B voters retained more ballot weight -- they gave A1 a low score, so the reweighting reduced their influence only slightly. Elect B1.

**Round 3:** Reweight again. Group B voters now have weight 1 / (1 + (1 + 5)/5) = 1 / (1 + 6/5) = 1/2.2 = 0.455 (they gave scores of 1 to A1 and 5 to B1). Group A voters have weight 1 / (1 + (5 + 1)/5) = 1 / (1 + 6/5) = 0.455 (they gave 5 to A1 and 1 to B1). At this point both groups have contributed one elected candidate each, and their weights are similar. The subsequent rounds continue the balancing process.

Under sincere scoring with these numbers, the final five-seat committee would include two or three Group A candidates, two Group B candidates, and possibly C1 -- a substantially more proportional outcome than top-K score voting produced. Group A (60% of voters) gets 40-60% of seats rather than the 60-80% it captured under top-K.

### Continuous vs. Binary Reweighting

The key structural difference between RRV and SPAV is the granularity of the reweighting. Under SPAV, the weight reduction is binary: a voter either approved the winner (and loses weight) or did not (and retains full weight). Under RRV, the weight reduction is continuous: it reflects the degree to which a voter supported the winner.

A voter who scored a winner at 3 out of 5 loses less weight than a voter who scored the same winner at 5, even though both contributed to that candidate's election. This creates a more gradual transition of influence across rounds. Whether this gradation produces better outcomes depends on whether voters score sincerely -- a question the next section addresses.

---

## Section 4: Strategic Exaggeration and Devolution

Every score-based method -- proportional or not -- faces a strategic consideration that does not arise in the same form under approval, ranked, or party-list ballots: the incentive to exaggerate.

### How Exaggeration Works

A sincere voter using a 0-5 scale might score their favorite candidate a 5, a tolerable candidate a 3, and a disliked candidate a 1. That ballot reflects genuine intensity differences.

A strategic voter recognizes that the counting algorithm sums scores. Giving a tolerable candidate a 3 instead of a 0 helps that candidate at the expense of the voter's favorite. The strategic response is to score favorites at the maximum (5) and everyone else at the minimum (0) -- collapsing the score ballot into a de facto approval ballot.

This strategic behavior is called **min-maxing** or **score exaggeration**. It is the score-ballot analogue of the approval threshold decision: a strategic choice about how much of the ballot's expressive capacity to use.

### The Devolution Insight

Score exaggeration points to a structural relationship between ballot families. When voters exaggerate fully on a score ballot -- using only the maximum and minimum scores -- the information actually processed by the counting algorithm is identical to what an approval ballot would have collected. The score ballot devolves into an approval ballot.

This devolution is not a malfunction. It is a consequence of the scoring mechanism: because scores are summed, a voter who uses intermediate values is diluting their own influence relative to a voter who uses only the extremes. The incentive to exaggerate exists in any method that sums scores -- top-K, RRV, or any other score-based rule.

The previous series identified the same structural relationship between score voting and approval voting in the single-winner context. The devolution insight extends to the multi-winner space: if enough voters exaggerate, RRV begins to behave like SPAV. The cardinal information that distinguishes score-based methods from approval-based methods becomes noise rather than signal.

### Exaggeration and the Reweighting Mechanism

The reweighting mechanism in RRV creates a partial self-correction for exaggeration. A voter who exaggerates -- scoring a winner at 5 and all others at 0 -- experiences the maximum reweighting penalty after that winner is elected. Their weight drops to 1 / (1 + 5/5) = 0.5. A voter who scored the same winner sincerely at 3 experiences a smaller penalty: 1 / (1 + 3/5) = 0.625. The exaggerating voter loses more influence in subsequent rounds.

This means exaggeration involves a trade-off: it increases a voter's influence in the current round (higher scores contribute more to a candidate's total) but decreases their influence in subsequent rounds (higher scores trigger stronger reweighting). A voter must weigh the benefit of helping their favorite win now against the cost of having less voice in later seats.

The partial self-correction does not eliminate the strategic incentive. In any given round, a higher score for a preferred candidate increases that candidate's chance of winning. But the reweighting mechanism ensures that the strategic advantage is not free -- it comes at the cost of future influence. This is a structural property of the method, not a guarantee of sincere behavior.

### The Expressiveness Tension

This creates a tension at the heart of score-based multi-winner design. Score ballots are designed to capture more information than approval ballots -- the capacity to express degrees of support is the primary reason for using a more complex ballot type. But if voters exaggerate to maximize their influence, the intermediate scores disappear and the counting algorithm receives the same information an approval ballot would have provided.

This does not mean score-based methods are identical to approval-based methods in every election. Sincere voters who use intermediate scores do change outcomes. The degree to which exaggeration occurs in practice depends on voter sophistication, the competitiveness of the election, and the information available to voters about likely outcomes. But the tension between theoretical expressiveness and strategic incentives is a structural trade-off of every score-based method.

---

## Section 5: Candidate Strategy

Voters are not the only actors who respond to the structure of the ballot and counting rule. Candidates and campaigns face incentives shaped by the same design.

Under **multi-winner score voting (top-K)**, the incentive structure parallels plurality-at-large: accumulate the highest aggregate score total. A candidate benefits from being scored highly by as many voters as possible. There is no diminishing-returns mechanism, so the incentive is base mobilization -- energize supporters to give maximum scores.

Under **RRV**, the reweighting mechanism changes the incentive structure across rounds. A candidate running for a later seat benefits from drawing support from voters who have not already helped elect a winner -- because those voters retain more ballot weight. This creates an incentive for candidates to appeal beyond the base of voters who supported the first-round winners. The structural incentive tilts toward broad cross-cutting appeal rather than concentrated factional support.

While we cannot attribute all candidate and campaign behavior to the voting system, we can identify the structural incentives it puts in place. The reweighting mechanism in RRV creates a consensus incentive that does not exist in top-K score -- and that differs from the first-preference concentration incentive under Proportional RCV, where candidates benefit most from being ranked first rather than from accumulating broad moderate support.

---

## Section 6: The 101-to-102 Bridge

Readers who followed the previous series will recognize score voting as a single-winner method examined in Part 4 of that series. The multi-winner methods in this article are its multi-seat analogues, and the relationship is worth making explicit.

### Score Voting to Multi-Winner Score and RRV

Single-winner score voting sums each candidate's scores and elects the candidate with the highest total. The multi-winner version simply elects the K highest-scoring candidates -- top-K by score total. The ballot is identical. The counting rule is the same, applied multiple times.

The structural problem that emerges in the multi-winner context is the same one that appeared when plurality was extended to bloc voting in Part 1: applying a single-winner excellence rule to multiple seats does not produce proportional outcomes. Top-K score, like bloc voting, can produce majority sweeps.

RRV solves this problem by adding ballot reweighting -- a mechanism that has no single-winner analogue because there are no subsequent seats to protect. The reweighting formula is the core innovation: everything else about the ballot and counting logic is inherited from single-winner score voting.

### What the 101 Series Established

The previous series established several properties of single-winner score voting that carry forward into the multi-winner context. The ballot's expressiveness allows voters to communicate intensity of preference. The summation mechanism rewards candidates with broad support. Strategic exaggeration reduces the information available to the counting algorithm -- the devolution toward approval that the previous series identified in the single-winner case extends to multi-winner methods.

The key new property in the multi-winner context is the reweighting mechanism itself. Reweighting does not exist in single-winner score voting because it is unnecessary: with one seat, there is no second seat to protect. The entire design innovation of score-based multi-winner proportional methods lies in how voter influence is managed after each seat is filled.

---

## Section 7: The Formal Properties Gap

The previous article introduced the justified representation axioms -- JR, PJR, and EJR -- as formal standards for evaluating proportionality in approval-based methods. PAV satisfies EJR. MES satisfies EJR. SPAV satisfies JR. These results give the approval-based family a well-characterized axiomatic profile.

For score-based methods, the axiomatic landscape is less developed. The justified representation axioms, as originally defined, apply to approval ballots -- binary preferences. Extending them to cardinal ballots requires adapting the definitions to accommodate degrees of support, and this extension is not straightforward. A voter who gives a candidate a score of 3 out of 5 is partially supporting that candidate. How that partial support should be counted toward the representation threshold is not a purely mathematical question -- it involves judgments about what "being represented" means when support is a matter of degree.

As a consequence, the formal proportionality guarantees for RRV have not been established with the same rigor as the corresponding results for PAV and MES. RRV produces proportional outcomes in worked examples and in simulation, but the peer-reviewed axiomatic analysis that underpins the approval-based methods is more limited for score-based methods.

This does not mean RRV lacks an evidence base. Simulation-based evaluation tools have been applied extensively: Voter Satisfaction Efficiency measurements, Candidate Incentive Distribution analysis, and criterion compliance testing across large numbers of simulated elections. These are legitimate evaluation instruments that provide meaningful information about how the method behaves. But they are different types of evidence than axiomatic proofs, and the reader should understand the distinction.

The practical implication is that the approval-based and score-based proportional families rest on different evidentiary foundations. The approval-based family has stronger formal guarantees. The score-based family has a more expressive ballot and extensive simulation evidence. Neither advantage is automatically decisive -- they represent different dimensions of evaluation.

---

## Comparison Table: Multi-Winner Score Voting vs. RRV

| Dimension | Multi-Winner Score (Top-K) | Reweighted Range Voting (RRV) |
|---|---|---|
| Ballot type | Score (0-5 or 0-10) | Score (0-5 or 0-10) |
| Proportionality | None (excellence rule) | Proportional-like |
| Proportionality mechanism | None | Harmonic reweighting (sequential) |
| Formal proportionality guarantees | None | Not formally established |
| Monotonicity | Yes | Yes |
| Ballot exhaustion | None | None |
| Strategic exaggeration incentive | Strong | Strong (partially self-correcting) |
| Candidate incentive structure | Base mobilization | Broad appeal / consensus |
| Precinct summability | Yes | No |
| Computational complexity | Polynomial (trivial) | Polynomial |
| American usage | None | Academy Awards VFX nominations; Berkeley, CA referral prioritization |
| Closest approval-based analogue | Multi-winner Approval (top-K) | SPAV |

---

## Conclusion

This article examined two multi-winner methods that use score ballots -- extending the design space from the binary approvals of the previous article to cardinal ratings that express degrees of support.

Multi-winner score voting (top-K) applies the simplest possible counting rule: sum scores, elect the highest-scoring candidates. Like its approval-based counterpart, it is an excellence rule that can produce majority sweeps. It has no proportionality mechanism and no proportionality guarantee.

Reweighted Range Voting adds proportionality through sequential reweighting -- the same structural approach that SPAV applies to approval ballots, generalized to cardinal scores. After each seat is filled, voters who scored the winner highly have their ballot weight reduced, creating space for underrepresented groups to influence subsequent seats. The result is a proportional-like outcome where the representation each group receives is closer to its share of the electorate.

RRV's American usage -- Academy Awards nominations and Berkeley's council referral process -- demonstrates that the method is operational in organizational contexts, though neither use involves the election of governmental representatives. No American governmental election uses RRV or multi-winner score voting.

Several concepts carry forward from this article:

**Reweighting as a proportionality mechanism** appeared here in its cardinal form. The next article -- on Proportional STAR -- introduces an alternative proportionality mechanism: allocation, which removes a quota of the winner's strongest supporters rather than reweighting all ballots. The distinction between reweighting and allocation is one of the central design choices in score-based proportional representation.

**Strategic exaggeration and the devolution toward approval** revealed a structural tension in all score-based methods. The score ballot is designed to capture intensity of preference, but the strategic incentive to exaggerate can collapse that information into binary signals -- making the method behave more like its approval-based counterpart. The reweighting mechanism creates a partial self-correction (exaggeration triggers stronger reweighting), but the tension between expressiveness and strategic incentives is a structural trade-off that does not disappear.

**The formal properties gap** between approval-based and score-based proportional methods is a consequence of the research landscape, not a verdict on method quality. Approval-based methods have stronger axiomatic guarantees. Score-based methods have a more expressive ballot and extensive simulation evidence. The reader evaluating these families should understand what types of evidence support each.

The next article examines Proportional STAR, which uses a counting algorithm called Allocated Score to address the same design challenge through a different proportionality mechanism. Where RRV reweights all ballots after each seat, Allocated Score removes a quota of supporters entirely, creating clean partitions between represented and unrepresented voters. The difference in mechanism produces different structural properties and different strategic considerations.


---

<!--
## Revision History

**Revision 1.4** (Current)
- Added revision history footer per formatting convention
- Article content unchanged

**Revisions 1.0 through 1.3**
- Development history prior to adoption of on-document revision tracking
- Final pre-convention state: seven numbered sections plus comparison table and conclusion covering the transition from approval to scores, Multi-Winner Score Voting (Top-K), Reweighted Range Voting (RRV), strategic exaggeration and devolution, candidate strategy, the 101-to-102 bridge, and the formal properties gap
-->

*Revision history available in the raw file.*

> 📥 [Download this document](https://github.com/albertintech/voting-methods-explained/blob/main/src/pr-06-proportional-score.md) (opens on GitHub -- click the ⬇ download button)

---

*© 2026 Albert Ramos. All rights reserved.*
