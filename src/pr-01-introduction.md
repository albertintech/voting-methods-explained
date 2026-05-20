# From One Winner to Many

## The Multi-Winner Design Space

---

## Statement of Purpose

The previous series examined single-winner elections. Each system answered the same question:

> Who should win?

Different ballots collected different information. Different counting rules processed that information differently. But the outcome was always the same type of object: one winner.

This series asks a different question:

> How should representation be distributed across multiple seats?

That shift -- from selecting an individual to distributing representation -- changes what voting systems must do, what tradeoffs they face, and what vocabulary is needed to evaluate them.

This article introduces the foundational concepts that recur throughout the series. It establishes the frame -- the central question, the key structural variables, and the scope of what follows. It does not survey every system. That is the work of the articles to come.

---

## Section 1: The Single-Winner Assumption

Every system examined in the previous series shared a structural feature so basic it was easy to overlook: there was one seat to fill.

That constraint shaped every design choice. Plurality asked who received the most first-choice votes. Ranked Choice Voting eliminated candidates sequentially until one remained. Approval and Score aggregated evaluations to identify a single most-supported candidate. Condorcet methods checked whether one candidate could defeat every other head-to-head.

Each approach made different decisions about ballot design and counting logic. But all of them compressed many preferences into one outcome.

Most elections do not work this way.

City councils, legislatures, school boards, and corporate boards typically fill multiple seats at once. When more than one candidate can win, the design problem changes. It is no longer enough to identify the strongest individual. The system must also decide how support across the electorate translates into seats -- and for whom.

---

## Section 2: District Magnitude

The number of seats filled in a single election has a name: **district magnitude**.

A single-winner election has a district magnitude of one. A city council election that fills five seats at once has a district magnitude of five. A state legislative district that elects two representatives has a district magnitude of two.

District magnitude is not a procedural detail. It is a structural variable that shapes representation more powerfully than almost any other feature of an electoral system.

In a single-winner election, any group smaller than a plurality is shut out entirely. If 30 percent of voters share a preference, they may win nothing -- because 30 percent is not enough when only one candidate can win.

Increase the district magnitude to five, and that same 30 percent of voters could, under the right system, elect at least one representative. Increase it to ten, and smaller groups -- 15 percent, even 10 percent -- may gain a voice.

The relationship is roughly inverse: as district magnitude increases, the share of the vote needed to guarantee a seat decreases. This share is called the **threshold of representation** -- the minimum level of support at which a group can secure a seat if its voters coordinate effectively.

> The threshold of representation is not a legal requirement. It is a mathematical consequence of how many seats are available.

Under common formulas, the approximate threshold of representation for a given district magnitude is:

| District Magnitude | Approximate Threshold |
|---|---|
| 1 | 50% (majority needed) |
| 3 | 25% |
| 5 | 17% |
| 9 | 10% |
| 20 | ~5% |

These figures are approximations. The exact threshold depends on the voting system and the quota formula in use -- concepts that will be developed in later articles. But the pattern holds: more seats mean lower barriers to representation.

This is why district magnitude matters. It determines who can be represented -- before a single ballot is cast.

---

## Section 3: Proportionality as a Design Objective

Once more than one seat is available, a new question arises: should the distribution of seats reflect the distribution of voter support?

This idea -- that groups of voters should receive seats roughly in proportion to their share of the vote -- is called **proportional representation**. A faction with 40 percent of the vote would receive approximately 40 percent of the seats. A group with 10 percent would receive approximately 10 percent.

It is tempting to treat proportionality as an obvious goal. If an election has ten seats and a group commands a third of the vote, shouldn't they receive roughly three seats?

But proportionality is a design choice, not an inevitable feature. Some multi-winner systems produce proportional outcomes by design. Others do not. And some systems that appear multi-winner in structure are functionally majoritarian -- giving a cohesive majority all or nearly all of the seats.

Consider a simple case: a five-seat election in which voters may vote for up to five candidates. If 60 percent of voters belong to one faction and they all support the same five candidates, that faction wins every seat. The remaining 40 percent elect no one.

This is not a malfunction. It is the structural consequence of applying single-winner logic to a multi-seat contest. Whether proportionality is desirable depends on what the election is trying to accomplish. A primary seeking consensus delegates may have different goals than a legislature seeking to represent a diverse electorate. The series teaches the reader to ask this question -- what is the election's goal? -- before evaluating any method.

---

## Section 4: Candidate-Centered Scope

The multi-winner design space is vast. Globally, the most common proportional systems are party-centered: voters choose parties, and seats are allocated to parties based on vote shares. Party-list proportional representation, Mixed-Member Proportional systems, and Mixed-Member Majoritarian systems collectively govern elections in more countries than any other family.

This series does not cover those systems.

The scope is candidate-centered multi-winner methods -- systems in which voters evaluate individual candidates, not party lists. This reflects the American electoral context. Americans vote for people, not parties -- at least on the ballot itself. The systems examined in this series are either currently used in the United States, have been proposed through American legislation, or represent active areas of American reform discussion.

Party-list PR, MMP, and MMM are important. They deserve -- and will receive -- full treatment in a future series. Deferring them here is not a judgment of their merit. It is a recognition that the American reader's frame of reference is candidate-centered, and that the systems most likely to appear on an American ballot or in American reform proposals belong to the candidate-centered family.

---

## Section 5: How This Series Is Organized

The series begins where the previous one left off.

The next article takes single-winner methods -- the same methods the reader studied in Series 1 -- and extends them to fill multiple seats. Bloc voting, limited voting, cumulative voting, the Single Non-Transferable Vote, and Bloc STAR all use familiar ballot formats and straightforward counting rules. What changes is the structural consequence: some produce sweep effects that shut out minorities entirely, while others create space for minority representation through different mechanisms. This is the reader's first encounter with the multi-winner design space, and it delivers the promise made at the end of Series 1.

With those methods in view, the series turns to the mathematical foundations that proportional systems require. Two articles develop the tools that have no single-winner analogue: algorithms and sequential counting processes, then quotas, surplus handling, and ballot reweighting. These concepts are taught explicitly because every proportional method that follows depends on them. The reader who understands quota arithmetic and surplus transfers will find Proportional RCV, Proportional Approval, Proportional Score, and Proportional STAR substantially more accessible than the reader who encounters these ideas for the first time inside a system article.

The proportional methods themselves follow: Proportional RCV (the multi-winner extension of Ranked Choice Voting, historically known as the Single Transferable Vote), approval-based proportional methods, score-based proportional methods, and Proportional STAR. Each article opens with where the system is currently used or has been formally proposed in the United States -- establishing stakes before mechanics. The series concludes with an article on voting simulations, equipping the reader to evaluate systems whose real-world track records are thin, followed by a Conclusion that synthesizes across design dimensions rather than by system.

---

## The Frame

The previous series established a principle that carries forward unchanged:

> Voting systems reflect priority choices.

Every system examined in that series collected certain information, processed it in a particular way, guaranteed some outcomes, and left others unguaranteed. No single-winner system satisfied all desirable criteria simultaneously. Understanding this was the goal.

The same principle applies here -- but the design space is larger, the tradeoffs are more numerous, and the vocabulary needed to navigate them is more demanding. Proportionality, accountability, simplicity, auditability, and representational fairness can all pull in different directions. No multi-winner system resolves all of these tensions at once.

The goal of this series is the same as the last: not to determine which system is best, but to develop the structural understanding needed to evaluate any system one encounters.

The question is no longer who should win.

It is how representation itself should be structured.
