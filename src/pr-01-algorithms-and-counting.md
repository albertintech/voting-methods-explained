# Algorithms and Counting

## The Tools Behind Proportional Systems

---

## Statement of Purpose

Every voting system examined in the previous series and in the multi-winner methods article used a counting method simple enough to describe in a sentence or two. Plurality: the candidate with the most votes wins. Bloc voting: the K candidates with the most votes win. Even the more expressive systems -- Approval, Score, STAR -- used straightforward aggregation: add up the totals, identify the leader, done.

Proportional systems are different. They cannot simply count and sort. They must count, evaluate, adjust, and count again -- sometimes through many rounds. The procedures that govern this process are called **algorithms**, and they are the machinery that makes proportional representation work.

This article introduces the concept of an algorithm in the electoral context. It explains why proportional systems require them, establishes the spectrum from methods that can be counted by hand to methods that require computers, and previews the algorithmic structures that will appear in the system articles to follow.

This is a Foundation article. It does not describe any specific voting system. It builds a conceptual tool -- the understanding of what an algorithm is, what it does, and what it costs -- that the reader will need before encountering the proportional systems themselves.

---

## Section 1: What Is an Algorithm?

An algorithm is a step-by-step procedure that takes an input, applies a defined sequence of operations, and produces an output. The steps must be precise enough that anyone following them -- a person, a committee, a computer -- would arrive at the same result from the same starting point.

Algorithms are not exotic or technical. A recipe is an algorithm: it takes ingredients (input), applies a sequence of steps (operations), and produces a dish (output). Driving directions are an algorithm. Tax preparation instructions are an algorithm. In each case, the procedure is defined in advance, and anyone following it correctly will reach the same destination.

In elections, the input is the set of ballots. The operations are the counting rules. The output is the set of winners.

Every voting system has an algorithm, even the simplest ones. Plurality's algorithm is: count first-choice votes; declare the candidate with the most votes the winner. It is a one-step algorithm -- count and sort -- and it produces a result immediately. There is nothing to revisit, no adjustment to make, no second pass required.

The algorithms behind proportional systems are longer. They involve multiple steps, conditional logic (if this happens, do one thing; if that happens, do another), and repetition (perform the same sequence of steps again for the next seat). Understanding that these are algorithms -- defined procedures, not arbitrary judgments -- is essential to understanding proportional systems. The procedure may be complex, but it is not mysterious. It can be written down, followed, and verified.

---

## Section 2: Why Proportional Systems Need Algorithms

The methods examined in Part 1 shared a structural feature: the counting was done once. Every ballot was tallied, every candidate's total was computed, and the top K candidates won. The process was a single pass through the ballots.

Proportional systems cannot work this way. Their defining goal -- distributing seats to reflect the distribution of voter support -- requires the system to track which voters have already been represented and to adjust subsequent rounds accordingly.

Consider the basic logic. A proportional system must answer a sequence of questions:

1. Which candidate has earned the most support?
2. Now that this candidate has been elected, which voters are "represented" by this winner?
3. How should the influence of those already-represented voters be adjusted before the next seat is filled?
4. Among the remaining candidates and with the adjusted voter influence, which candidate has the most support now?
5. Repeat until all seats are filled.

Each of these questions requires a decision rule. How is "most support" measured? How are represented voters identified? How is influence adjusted -- by reducing ballot weight, by removing voters entirely, by transferring surplus votes? Different proportional systems answer these questions differently. But all of them share the same sequential structure: elect, adjust, repeat.

This sequential structure is what makes proportional algorithms longer and more complex than the single-pass counting used in Part 1. It is also what makes them capable of producing proportional outcomes. The adjustment step -- the middle of the sequence -- is where proportionality is built. Without it, the same voters would dominate every round, and the result would be a sweep.

---

## Section 3: The Counting Spectrum

Not all algorithms are equally demanding to execute. The methods examined in this series span a wide range of computational complexity, from procedures that a room of volunteers can complete with paper and pencil to procedures that require dedicated software.

### Hand-Countable Methods

The methods from Part 1 -- bloc voting, limited voting, cumulative voting, and SNTV -- are hand-countable in a strong sense. Tallying requires nothing more than adding up marks on ballots. Any election official who can count can administer these methods. The results can be verified by anyone willing to recount.

### Hand-Countable but Laborious

Some proportional methods can be counted by hand but require significantly more effort. Proportional RCV -- historically known as the Single Transferable Vote (STV), and examined in detail later in the series -- involves multiple rounds of counting. In each round, either a candidate is elected and surplus votes are transferred, or the weakest candidate is eliminated and those votes are redistributed. In a small election -- a nine-seat city council with a dozen candidates -- this process can be completed by hand, though it takes time and care. Ireland counts its STV elections by hand, a tradition that reflects both the method's age and the country's commitment to transparent public counting.

As the number of candidates and seats increases, hand counting becomes increasingly impractical. A Proportional RCV election with 20 candidates and 5 seats might require dozens of rounds. Fractional vote transfers -- where a portion of each ballot is transferred rather than the whole ballot -- add arithmetic complexity. At sufficient scale, hand counting remains theoretically possible but practically unreasonable.

### Computer-Required Methods

Some proportional methods are designed with computational assistance in mind. Sequential methods that use reweighting -- adjusting every participating voter's ballot weight after each seat is filled -- require recalculating weighted totals across the entire electorate for every round. When the electorate is large, this is work for a computer, not a clipboard.

The distinction between "hand-countable but laborious" and "computer-required" is not always sharp. It depends on the size of the election, the specific transfer rules in use, and the resources available for counting. The important point is that the computational demand increases as the algorithm becomes more sophisticated.

### Computationally Intractable Methods

A small number of multi-winner methods present a more fundamental challenge: they are computationally intractable in the formal sense. Finding the optimal outcome -- the committee of winners that maximizes or minimizes a specific mathematical criterion -- requires examining a number of possible combinations that grows so rapidly with the number of candidates that no computer can check them all in a reasonable time.

These methods are said to be **NP-hard**, a classification from computer science indicating that no known efficient algorithm can guarantee an optimal solution for large inputs. In practice, elections using these criteria rely on sequential approximations -- algorithms that produce good results quickly but cannot guarantee they have found the best possible result.

This is not merely a technical curiosity. It has design implications. A method whose optimal outcome cannot be computed in practice must either accept an approximation or restrict itself to election sizes where computation is feasible. The choice between an optimal-but-intractable method and its sequential-but-tractable approximation is itself a design decision, and one that later articles will examine.

---

## Section 4: Sequential Algorithms

The dominant structure among proportional election algorithms is **sequential**: fill one seat at a time, adjust after each seat, and repeat.

This structure appears across every ballot family. Ranked-ballot proportional methods (Proportional RCV) elect a candidate or eliminate the weakest, transfer votes, and repeat. Approval-based proportional methods (SPAV) elect the candidate with the highest weighted approval, reduce the weight of voters who approved the winner, and repeat. Score-based proportional methods (RRV, Allocated Score) elect the candidate with the highest weighted score, adjust voter weights or allocate voters to the winner, and repeat.

The sequential structure has several consequences worth noting before the reader encounters it in specific systems.

**Order can matter.** Because each round's result affects subsequent rounds -- which voters are adjusted, which candidates remain -- the sequence in which candidates are elected or eliminated can influence the final outcome. Two algorithms that agree on which candidate should win the first seat might disagree about the second, because their adjustment rules produce different voter weight distributions after the first seat is filled.

**Ties are more consequential.** In a single-winner plurality election, a tie affects one outcome. In a sequential multi-winner algorithm, a tie in an early round can cascade through all subsequent rounds. If Candidate A and Candidate B are tied for the last elimination spot, and the algorithm eliminates A, the voters whose ballots transfer from A may change the outcome of every later round. Different systems handle ties differently, and the choice of tiebreaking rule is not trivial.

**Adjustment rules are where values enter.** The factual question -- which candidate received the most support in this round? -- is straightforward. The normative question -- how should the influence of represented voters be adjusted? -- is where systems diverge. Some systems reduce ballot weight gradually (reweighting). Some remove voters entirely (allocation). Some transfer surplus votes to the next-ranked candidate (Proportional RCV). Each approach encodes a different judgment about how voter influence should work across multiple seats. The adjustment rule is not a technical detail. It is the mechanism through which the system's proportionality logic operates.

---

## Section 5: Auditability and Transparency

Simple counting methods are transparent by default. Anyone can recount a stack of ballots and verify a plurality result. The simplicity of the algorithm is itself a form of public trust.

Proportional algorithms introduce a tension. The procedures that produce proportional outcomes are longer, involve conditional logic, and may require computation that is difficult to replicate by hand. This raises a practical question: can voters and observers verify that the count was conducted correctly?

The answer depends on the method and the implementation.

Some proportional methods are auditable in the traditional sense. STV in Ireland is counted publicly, with observers watching each round of counting and transfer. The process is slow but transparent -- every ballot movement is visible. The algorithm is complex, but because it operates on physical ballots in a defined sequence, any observer can follow the steps.

Other methods are auditable in a computational sense. If the algorithm is published, the software is open-source, and the ballots (or anonymized ballot images) are made available, then anyone with the technical resources can re-run the computation and verify the result. This is a different kind of transparency -- it requires technical capacity rather than physical observation -- but it provides equivalent assurance to those who can exercise it.

The relationship between algorithmic complexity and public trust is not straightforward. A method can be mathematically superior and practically unverifiable if the counting process is opaque. Conversely, a method can be transparent and publicly trusted while producing outcomes that a more sophisticated algorithm would improve. The design choice is real: transparency and algorithmic sophistication can pull in different directions.

This tension will reappear throughout the series as each proportional system is evaluated on its mechanical properties. Auditability is one of those properties. It is not the only one -- but for a system that depends on public trust in its outcomes, it is not one that can be dismissed.

---

## Section 6: What Follows

The Foundation articles exist to equip the reader with tools before they are needed. This article has introduced the first tool: the concept of an algorithm as a defined, verifiable procedure -- and the understanding that proportional systems require sequential algorithms whose adjustment rules encode the system's proportionality logic.

The next Foundation article introduces the second tool: quotas. A quota defines how many votes constitute "enough support" to earn a seat. Different quota formulas -- Hare and Droop -- produce different thresholds, and the choice between them is not neutral. Quotas also introduce the surplus problem (what happens when a candidate receives more votes than needed) and the remainder problem (what happens when votes do not divide evenly into seats). These are the mathematical tools that proportional algorithms operate on.

With both tools in hand -- algorithms and quotas -- the reader will be prepared to encounter the proportional systems themselves, beginning with the Single Transferable Vote.

---

## Conclusion

This article introduced three ideas that will recur throughout the rest of the series.

First, proportional systems require algorithms -- multi-step, sequential procedures -- because proportionality cannot be achieved in a single pass through the ballots. The system must track which voters have been represented and adjust subsequent rounds accordingly.

Second, these algorithms span a spectrum of computational demand, from methods that can be counted by hand to methods that require computers to methods whose optimal solutions are computationally intractable. Where a method falls on this spectrum is a design property with practical consequences for implementation, cost, and public trust.

Third, the adjustment rules within these algorithms are where the system's values operate. Whether voter influence is reduced gradually, removed entirely, or transferred to other candidates is not a technical detail but a normative choice -- one that determines what kind of proportionality the system produces.

The reader does not yet need to know the specific adjustment rules of any particular system. That is the work of the system articles. What this article establishes is the framework: proportional systems are sequential, their complexity varies, and their adjustment rules encode design choices. The next Foundation article adds the mathematical tools -- quotas, surplus handling, and the remainder problem -- that those adjustment rules operate on.

---

<!--
## Revision History

**Revision 1.4** (Current)
- Added revision history footer per formatting convention
- Article content unchanged

**Revisions 1.0 through 1.3**
- Development history prior to adoption of on-document revision tracking
- Final pre-convention state: six numbered sections plus conclusion covering algorithm definition, why proportional systems need algorithms, the counting spectrum, sequential algorithms, auditability and transparency, and transition to subsequent articles
-->

*Revision history available in the raw file.*

> 📥 [Download this document](https://github.com/albertintech/voting-methods-explained/blob/main/src/pr-01-algorithms-and-counting.md) (opens on GitHub -- click the ⬇ download button)

---

*© 2026 Albert Ramos. All rights reserved.*
