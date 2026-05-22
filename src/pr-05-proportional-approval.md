# Approval-Based Proportional Representation

## Binary Ballots, Proportional Outcomes

---

## Currently Used / Proposed Use

**Currently Used:** No American governmental or organizational elections using proportional approval voting methods (PAV, SPAV, or the Method of Equal Shares) have been identified. The Method of Equal Shares has been used for participatory budgeting in several European cities, including Wieliczka, Poland (2023) and Aarau, Switzerland (2023). No American participatory budgeting programs using these methods have been identified. Multi-winner approval voting (top-K) -- the non-proportional baseline covered in this article -- is used informally in some organizational contexts but is not the focus of proportional representation proposals.

**Proposed Use:** No American legislative proposals for proportional approval voting methods have been identified.

**What this means for this article:** The approval-based proportional methods examined here exist primarily in academic literature, simulations, and a small number of European participatory budgeting experiments. They have not been adopted for any American election -- governmental, political, or organizational. The article covers them because they make a conceptual contribution that matters for the series: they demonstrate that proportional representation does not require ranked ballots, party lists, or score ballots. A binary ballot -- approve or not -- combined with the right counting algorithm, can produce proportional outcomes. That demonstration informs how the reader evaluates every other proportional system in the series.

---

## Statement of Purpose

The previous two articles examined Proportional RCV -- the ranked-ballot system historically known as the Single Transferable Vote (STV) that achieves proportional representation through individual candidate preferences rather than party labels. Proportional RCV demonstrated that proportionality is possible without party lists. But it requires a ranked ballot, a complex counting process, and surplus transfer decisions that can affect outcomes in ways voters may not anticipate.

This article asks whether proportional representation can be achieved with a simpler ballot.

The answer is yes -- and the ballot is as simple as it gets. Approval voting asks each voter a single question about each candidate: do you approve, or not? No rankings. No scores. Just a set of binary signals.

In a single-winner election, approval voting selects the most broadly approved candidate. Part 3 of the previous series examined how this works and what it optimizes for. In a multi-winner election, the question becomes: how should a set of approval ballots translate into a committee that proportionally represents the electorate?

The answer depends entirely on the counting algorithm. The same ballots can be processed by different rules that produce dramatically different outcomes -- from majoritarian sweeps to proportional committees. This article examines four such rules, progressing from the simplest (and least proportional) to the most theoretically sophisticated. The first -- multi-winner approval -- is a non-proportional baseline included for contrast. The remaining three -- Proportional Approval Voting (PAV), Sequential Proportional Approval Voting (SPAV), and the Method of Equal Shares (MES) -- each achieve proportionality through a different mechanism.

---

## Section 1: The Approval Ballot in Multi-Winner Elections

In the previous series, the approval ballot was introduced as the simplest expressive ballot: each voter marks every candidate they find acceptable. There are no rankings, no numerical scores, and no limit on how many candidates a voter may approve. The result is a binary signal for each candidate -- approved or not approved.

When this ballot is used to fill a single seat, the counting rule is straightforward: the candidate with the most approvals wins. But when multiple seats are available, the counting rule is no longer obvious. Consider a simple example.

### A Motivating Example

A city is electing a five-member committee from eight candidates. There are 100 voters, and the electorate divides into three groups based on shared preferences:

- **Group A** (50 voters) approves candidates Adams, Allen, Ayers, and Archer.
- **Group B** (30 voters) approves candidates Brooks, Bailey, and Burns.
- **Group C** (20 voters) approves candidates Chen and Brooks.

Notice that Groups B and C overlap: both approve Brooks. This kind of overlapping support -- where voters share some approvals but not others -- is characteristic of approval-based elections and has no direct analogue in party-list systems.

The question is: which five candidates should be elected?

If the rule simply selects the five candidates with the highest approval totals, the result looks like this:

| Candidate | Group A (50) | Group B (30) | Group C (20) | Total Approvals |
|---|---|---|---|---|
| Adams | Approved | -- | -- | 50 |
| Allen | Approved | -- | -- | 50 |
| Ayers | Approved | -- | -- | 50 |
| Archer | Approved | -- | -- | 50 |
| Brooks | -- | Approved | Approved | 50 |
| Bailey | -- | Approved | -- | 30 |
| Burns | -- | Approved | -- | 30 |
| Chen | -- | -- | Approved | 20 |

The top five are Adams, Allen, Ayers, Archer, and Brooks. Group A captures four of the five seats. Group B gets one seat (Brooks), but only because Group C's overlapping support boosted Brooks above Bailey and Burns. Group C -- 20% of the electorate -- has no candidate of its own on the committee.

Is this outcome proportional? Group A is 50% of the electorate and holds 80% of the seats. Group B is 30% and holds 20% (through a shared candidate). Group C is 20% and holds nothing. The answer is no.

This outcome is not a surprise. It is the multi-winner analogue of what Part 1 called the **sweep effect**. Selecting the candidates with the highest raw approval totals is an excellence rule: it identifies the individually most-approved candidates, just as single-winner approval voting identifies the single most-approved candidate. Excellence rules do not account for the fact that the same voters are providing support for multiple winning candidates. A group that approves four candidates can push all four to the top of the list, leaving smaller groups unrepresented.

The methods examined in the rest of this article attempt to solve this problem. Each one uses the same approval ballot but processes it through a different algorithm -- one designed to produce proportional outcomes rather than simply identifying the most-approved individuals.

---

## Section 2: Multi-Winner Approval Voting (Top-K)

Before examining proportional rules, the non-proportional baseline deserves a clear statement.

### How It Works

In a multi-winner approval election with K seats:

1. Each voter approves as many candidates as they wish.
2. Each candidate's approval total is the number of voters who approved them.
3. The K candidates with the highest approval totals are elected.

This is sometimes called "top-K approval" or "bloc approval." It is the direct multi-winner extension of single-winner approval voting, and it shares the structural logic of bloc voting from Part 1: the most broadly supported candidates win, regardless of whether the same voters are supporting all of them.

### Structural Consequences

Top-K approval is a utilitarian rule: it maximizes the total number of approvals received by the winning committee. If every voter's goal is to have as many approved candidates elected as possible, this rule produces the highest aggregate satisfaction.

But utilitarian optimization and proportional representation are different objectives. A committee that maximizes total satisfaction can leave a substantial minority entirely unrepresented, because the majority's approvals dominate every seat. This is precisely the sweep effect observed under bloc voting in Part 1 -- extended now to approval ballots.

The motivating example in Section 1 demonstrated the result: 50% of the electorate held 80% of the seats.

Top-K approval has a legitimate place in multi-winner elections. When the goal is to identify the most broadly acceptable candidates -- a shortlist, an advisory panel, a group that reflects consensus rather than diversity -- the excellence rule serves that goal. But when the goal is proportional representation, a different counting mechanism is needed.

---

## Section 3: Proportional Approval Voting (PAV)

Proportional Approval Voting was first proposed by the Danish mathematician Thorvald Thiele in the 1890s and independently rediscovered by Forest Simmons in 2001. It is the approval-ballot analogue of the oldest proportional method in mathematical voting theory.

### The Idea: Diminishing Returns

PAV's central insight is simple: the more representatives a voter already has on the committee, the less an additional representative should be worth to them.

A voter with zero representatives on the committee is entirely unrepresented. Electing one candidate they approved is very valuable. Electing a second candidate they approved is still valuable, but somewhat less so -- they already have one voice on the committee. A third is worth less still. PAV formalizes this intuition with a specific mathematical structure: a voter's total satisfaction from the committee is the sum of a harmonic series.

If a voter has approved R members of the elected committee, their total satisfaction is:

1 + 1/2 + 1/3 + ... + 1/R

The first representative contributes 1 unit of satisfaction. The second contributes 1/2. The third contributes 1/3. And so on. These diminishing returns create an implicit cost to giving one group too many representatives: each additional seat for a well-represented group produces less total satisfaction than giving a seat to an unrepresented group.

### How It Works

PAV selects the committee of K candidates that maximizes total harmonic satisfaction across all voters. In the motivating example:

**Outcome A: Adams, Allen, Ayers, Archer, Brooks (the top-K result)**

- Group A (50 voters): each approved 4 winners. Satisfaction per voter: 1 + 1/2 + 1/3 + 1/4 = 2.083. Group total: 104.17.
- Group B (30 voters): each approved 1 winner (Brooks). Satisfaction per voter: 1. Group total: 30.
- Group C (20 voters): each approved 1 winner (Brooks). Satisfaction per voter: 1. Group total: 20.
- **Committee total: 154.17**

**Outcome B: Adams, Allen, Brooks, Bailey, Chen**

- Group A (50 voters): each approved 2 winners (Adams, Allen). Satisfaction per voter: 1 + 1/2 = 1.5. Group total: 75.
- Group B (30 voters): each approved 2 winners (Brooks, Bailey). Satisfaction per voter: 1 + 1/2 = 1.5. Group total: 45.
- Group C (20 voters): each approved 2 winners (Brooks, Chen). Satisfaction per voter: 1 + 1/2 = 1.5. Group total: 30.
- **Committee total: 150**

**Outcome C: Adams, Allen, Ayers, Brooks, Bailey**

- Group A (50 voters): each approved 3 winners. Satisfaction per voter: 1 + 1/2 + 1/3 = 1.833. Group total: 91.67.
- Group B (30 voters): each approved 2 winners. Satisfaction per voter: 1.5. Group total: 45.
- Group C (20 voters): each approved 1 winner (Brooks). Satisfaction per voter: 1. Group total: 20.
- **Committee total: 156.67**

The committee with the highest total harmonic satisfaction turns out to be Outcome C -- a result that gives Group A three seats (60% for 50% of voters), Group B two seats, and Group C one shared representative (Brooks). This is closer to proportional than the top-K result, though not perfectly proportional.

The exact optimal committee requires checking all possible combinations. For larger elections, this exhaustive search is where PAV encounters its central practical limitation.

### The NP-Hardness Problem

Computing the exact PAV winner is NP-hard. In computational terms, this means that the time required to guarantee the optimal committee grows faster than any polynomial function of the number of candidates and seats. For small elections -- a dozen candidates and five seats -- the calculation is manageable. For elections with hundreds of candidates and dozens of seats, finding the optimal PAV committee becomes computationally intractable.

This is not a theoretical curiosity. It is a practical constraint that has prevented PAV from being used in real elections. the Algorithms and Counting article introduced the hand-countable vs. computer-required spectrum. PAV sits at the extreme end: not only does it require a computer, it requires a computer running an algorithm that may not produce a result in reasonable time for large elections.

The next two methods -- SPAV and MES -- each offer a different solution to this problem. Both produce proportional results in polynomial time.

---

## Section 4: Sequential Proportional Approval Voting (SPAV)

SPAV was also first proposed by Thiele in the 1890s, as a practical approximation of PAV. It was used in Swedish parliamentary elections from 1909 to 1921 before being replaced by a party-list system. No American usage -- governmental or organizational -- has been identified.

### How It Works

SPAV converts PAV's global optimization into a sequential process. Instead of evaluating every possible committee, SPAV fills seats one at a time:

**Round 1:** Each voter has a ballot weight of 1. The candidate with the highest weighted approval total is elected.

**After each round:** Every voter who approved the just-elected candidate has their ballot weight reduced. The new weight follows the harmonic formula: a voter who has approved R winners so far receives a weight of 1/(1 + R) for the next round.

**Subsequent rounds:** The candidate with the highest weighted approval total among the remaining candidates is elected. Weights are updated. The process continues until all K seats are filled.

### Applying SPAV to the Motivating Example

**Round 1:** All voters have weight 1. Adams, Allen, Ayers, and Archer each have 50 weighted approvals. Brooks has 50. Ties are broken (assume alphabetically). Adams is elected.

**Weight update:** Group A's 50 voters now have weight 1/(1 + 1) = 1/2. Groups B and C are unchanged at weight 1.

**Round 2:** Allen, Ayers, Archer each have 50 x 1/2 = 25 weighted approvals. Brooks has 30 x 1 + 20 x 1 = 50. Bailey has 30. Burns has 30. Chen has 20. Brooks is elected (50 weighted approvals).

**Weight update:** Group B's 30 voters now have weight 1/2 (one winner). Group C's 20 voters now have weight 1/2 (one winner). Group A is still at 1/2.

**Round 3:** Allen, Ayers, Archer each have 50 x 1/2 = 25. Bailey has 30 x 1/2 = 15. Burns has 30 x 1/2 = 15. Chen has 20 x 1/2 = 10. Allen is elected (25).

**Weight update:** Group A's weight drops to 1/(1 + 2) = 1/3.

**Round 4:** Ayers, Archer each have 50 x 1/3 = 16.67. Bailey has 30 x 1/2 = 15. Burns has 15. Chen has 10. Ayers is elected (16.67).

**Weight update:** Group A's weight drops to 1/(1 + 3) = 1/4.

**Round 5:** Archer has 50 x 1/4 = 12.5. Bailey has 30 x 1/2 = 15. Burns has 15. Chen has 10. Bailey is elected (15).

**Final committee: Adams, Brooks, Allen, Ayers, Bailey.**

Group A holds three seats (60% for 50% of the electorate). Group B holds two seats (one exclusively -- Bailey -- and one shared with Group C -- Brooks). Group C is represented through Brooks. This is closer to proportional than top-K but still over-represents Group A slightly.

### What SPAV Gains and Loses

SPAV's advantage is computational tractability. Each round requires only a pass through the candidate list to find the highest weighted total. The calculation is polynomial-time -- manageable even for large elections.

What SPAV loses is optimality. Because it makes greedy choices (electing the best candidate in each round without reconsidering earlier choices), it can produce committees that are not the PAV-optimal solution. Early rounds can lock in decisions that a global optimization would have made differently. In practice, SPAV tends to produce results close to PAV, but the guarantee is weaker.

---

## Section 5: The Method of Equal Shares (MES)

The Method of Equal Shares -- also called Rule X -- was developed by Dominik Peters and Piotr Skowron, with key results published between 2020 and 2023. It has been used for participatory budgeting in European municipalities. No American usage has been identified.

### A Different Philosophy

PAV and SPAV achieve proportionality through diminishing returns. Each additional representative is worth less to a voter who already has representation, so the optimization naturally spreads seats across groups. The mechanism is welfarist: it asks how to maximize total satisfaction subject to diminishing marginal value.

MES takes a fundamentally different approach. It treats proportionality as a consequence of equal spending power.

### The Budget Metaphor

MES begins by giving each voter an equal virtual budget. If there are 100 voters and 5 seats, and each seat "costs" a fixed price, each voter starts with 1/5 of the total budget -- enough to buy one seat if every voter in the electorate contributes equally.

A candidate is elected when enough of their approvers pool their budgets to cover the cost of a seat. After the candidate is elected, each contributing voter's budget is reduced by their share of the cost. Voters who have already helped elect a representative have less budget remaining to influence subsequent seats. Voters who have not yet been represented retain their full budget.

### How It Works

The algorithm proceeds in rounds:

**Setup:** Each voter receives an equal virtual budget. Define a "cost" that each elected candidate must meet.

**Each round:** For each remaining candidate, check whether the candidate's approvers can collectively afford to elect that candidate. If multiple candidates are affordable, elect the one whose cost can be covered with the most equal distribution of burden among their approvers. After election, deduct each contributing voter's share from their budget.

**Completion:** If at some point no remaining candidate can be afforded by their approvers' remaining budgets, the remaining seats are filled by a completion method (typically a greedy rule applied to whatever budgets remain).

The details of the cost calculation and burden distribution make the full algorithm more involved than this summary suggests. The important structural point is the philosophy: each voter controls an equal share of the decision-making power, and representation is purchased with that power rather than emerging as a side effect of satisfaction optimization.

### The Result in the Motivating Example

Without walking through the full budget arithmetic (which involves fractional budget allocations that are less instructive than the conceptual point), MES applied to the motivating example produces a committee that gives each group representation roughly proportional to its size. Group A, with 50% of the electorate, would receive approximately two to three seats. Group B, with 30%, would receive one to two seats. Group C, with 20%, would receive one seat. The exact result depends on tie-breaking and completion rules, but the distribution is closer to proportional than either top-K or SPAV.

### What MES Achieves

MES satisfies strong formal proportionality properties. In the academic literature, it has been shown to satisfy **Extended Justified Representation (EJR)** -- the same strong guarantee that PAV satisfies -- while remaining computationally efficient (polynomial time). This combination -- strong proportionality guarantee plus tractable computation -- is the central achievement of MES and the reason it has attracted significant academic attention.

The concept of justified representation deserves a brief explanation. The family of justified representation axioms -- JR, PJR, and EJR, in increasing strength -- formalizes the intuition that groups of voters large enough to "deserve" representation should receive it. The weakest version (JR) says that if a group of voters large enough to fill one seat all approve a common candidate, at least one of their approved candidates must be elected. The strongest version (EJR) extends this to proportional shares: a group large enough to fill three seats must have collectively approved three or more winners.

PAV satisfies EJR but is NP-hard to compute. SPAV satisfies JR (the weakest axiom) but not PJR or EJR. MES satisfies EJR in polynomial time. This makes MES the most theoretically attractive of the three methods: it provides the strongest proportionality guarantee at a computational cost that permits practical use.

---

## Section 6: Proportionality Without Rankings or Parties

The four methods in this article share a ballot -- approve or not -- but produce outcomes that range from majoritarian (top-K) to strongly proportional (PAV, MES). The difference lies entirely in the counting algorithm. This has several implications worth making explicit.

### The Algorithm Encodes a Normative Choice

Top-K approval maximizes total approvals on the winning committee. PAV maximizes total harmonic satisfaction. MES equalizes spending power. These are not just different computational procedures. They are different answers to the question of what fair representation means.

An institution choosing among these methods is choosing what it values. If the goal is to identify the most broadly acceptable candidates -- a shortlist, an advisory panel -- top-K serves that goal. If the goal is proportional representation with the strongest formal guarantees, PAV or MES is the appropriate choice. If practical computation matters (as it does for any large election), MES offers the strongest proportionality achievable in reasonable time.

### Proportionality Without Party Labels

Every method in this article achieves (or attempts) proportional outcomes without requiring voters to identify with parties or candidates to run on party tickets. The proportionality emerges from the structure of overlapping approvals in the electorate, not from party vote shares.

This makes approval-based methods relevant to contexts where party labels are absent or weak: non-partisan local elections, organizational governance, and multi-winner elections in weak-party systems. It also means these methods can represent cross-cutting cleavages -- voters who share some preferences but differ on others -- in ways that party-list systems cannot.

### The Trade-off: Expressiveness vs. Simplicity

The approval ballot's simplicity is both its strength and its limitation. A voter who enthusiastically supports one candidate and merely tolerates another must give both the same mark. The ballot cannot distinguish between strong and weak approval. This is the expressiveness trade-off that the next article -- on score-based proportional methods -- addresses.

---

## Comparison Table: Approval-Based Multi-Winner Methods

| Dimension | Top-K Approval | PAV | SPAV | MES |
|---|---|---|---|---|
| Ballot type | Approval | Approval | Approval | Approval |
| Proportionality | None (excellence rule) | Proportional | Semi-proportional | Proportional |
| Proportionality mechanism | None | Harmonic satisfaction (global) | Harmonic reweighting (sequential) | Budget allocation |
| Strongest axiom satisfied | None | EJR | JR | EJR |
| Computational complexity | Polynomial | NP-hard | Polynomial | Polynomial |
| Practical for large elections? | Yes | No (exact computation) | Yes | Yes |
| Requires parties? | No | No | No | No |
| American usage | Informal / organizational | None | None | None |
| International usage | Various | Theoretical | Sweden (1909-1921) | European PB (2023-present) |

---

## Conclusion

This article examined a family of multi-winner methods that share the simplest possible ballot -- approve or not -- but produce dramatically different outcomes depending on the counting algorithm.

Multi-winner approval voting (top-K) selects the individually most-approved candidates without adjustment. Like bloc voting in Part 1, it can produce sweep effects where a cohesive majority captures all seats. It has a legitimate role in elections where the goal is broad consensus rather than proportional representation.

Three methods add proportionality mechanisms to the same ballot. PAV uses harmonic diminishing returns to create an implicit cost to over-representing any group, producing results that satisfy Extended Justified Representation -- the strongest standard proportionality guarantee available for approval-based methods. But PAV is NP-hard, making it impractical for large elections. SPAV approximates PAV's logic sequentially, gaining computational tractability at the cost of weaker proportionality guarantees. MES reframes proportionality as equal budget allocation, achieving the same strong EJR guarantee as PAV while remaining computationally efficient.

None of the proportional methods examined in this article has been used in any American election -- governmental, organizational, or political. The Method of Equal Shares has seen limited use in European participatory budgeting. PAV and SPAV remain primarily theoretical. This thin adoption record is itself informative: these methods demonstrate that proportional representation from approval ballots is mathematically possible and computationally tractable, but the path from theoretical development to practical adoption has not yet been traveled in the American context.

Several concepts from this article carry forward:

The distinction between **excellence rules** (top-K) and **proportional rules** (PAV, MES) demonstrated that the same ballot can serve fundamentally different design objectives depending on the counting algorithm. This distinction recurs in the next article, where score ballots face the same choice.

**Harmonic reweighting** and **budget allocation** revealed two distinct approaches to the proportionality problem. Reweighting treats proportionality as a consequence of diminishing marginal value. Budget allocation treats it as a consequence of equal spending power. Each produces proportionality through a different mechanism and encodes a different judgment about what fair representation means.

**NP-hardness** appeared as a practical constraint with real design consequences. The theoretically optimal method (PAV) is computationally intractable for large elections. MES demonstrated that the same proportionality guarantee is achievable in polynomial time -- a result that matters not just technically but practically, because a method that cannot be computed cannot be used.

The next article extends the multi-winner design space to score ballots, where voters can express not just approval or disapproval but degrees of support. The additional expressiveness of the score ballot creates new possibilities for proportional allocation -- and new strategic considerations that do not arise with binary approvals.


---

<!--
## Revision History

**Revision 1.4** (Current)
- Added revision history footer per formatting convention
- Article content unchanged

**Revisions 1.0 through 1.3**
- Development history prior to adoption of on-document revision tracking
- Final pre-convention state: six numbered sections plus comparison table and conclusion covering the approval ballot in multi-winner elections, Multi-Winner Approval (Top-K), Proportional Approval Voting (PAV), Sequential Proportional Approval Voting (SPAV), Method of Equal Shares (MES), and proportionality without rankings or parties
-->

*Revision history available in the raw file.*

> 📥 [Download this document](https://github.com/albertintech/voting-methods-explained/blob/main/src/pr-05-proportional-approval.md) (opens on GitHub -- click the ⬇ download button)

---

*© 2026 Albert Ramos. All rights reserved.*
