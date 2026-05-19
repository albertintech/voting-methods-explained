# Ranked Choice Voting (RCV)

## Part B -- Structural Consequences

---

## Statement of Purpose

In the previous article, we examined how Ranked Choice Voting works: ranked ballots, sequential elimination, ballot transfers, and the locked ballot model.

The mechanics are straightforward.

But the design of the counting process -- sequential elimination based on first-choice totals -- produces structural consequences that are not always obvious from the rules alone.

This article examines three:

- A broadly acceptable candidate can be eliminated early.
- Gaining additional support can, in rare cases, change the outcome.
- Ballots can become inactive before the final round.

Understanding these consequences is essential for evaluating what RCV optimizes for -- and what it does not.

---

## Section 1: The Center Squeeze 🎯

RCV eliminates candidates one at a time, starting with the fewest first-choice votes.

This means a candidate who is broadly acceptable -- but not many voters' first choice -- can be eliminated before their support becomes visible.

### A Fully Worked Example

Three candidates:

- Lefty 🔴
- Center 🟡
- Righty 🔵

100 voters.

#### Ballots

- 40: Lefty > Center > Righty
- 20: Center > Lefty > Righty
- 40: Righty > Center > Lefty

#### Round 1

| Candidate | First-Choice Votes |
|---|---|
| Lefty | 40 |
| Center | 20 |
| Righty | 40 |

No candidate has a majority (51 required).

Center 🟡 has the fewest first-choice votes and is eliminated ❌.

#### Round 2

Center's 20 ballots transfer to their next ranked choice:

20: Center ❌ → Lefty 🔴

New totals:

| Candidate | Votes |
|---|---|
| Lefty | 60 |
| Righty | 40 |

Lefty wins with a majority.

#### But Consider the Head-to-Head Comparisons

What if the election had been only between Center and Lefty?

- 40 voters prefer Lefty over Center
- 20 voters prefer Center over Lefty
- 40 voters prefer Center over Lefty (Righty voters ranked Center second)

Center defeats Lefty, 60-40.

What about Center versus Righty?

- 40 voters prefer Lefty, who ranked Center second → prefer Center over Righty
- 20 voters prefer Center over Righty
- 40 voters prefer Righty over Center

Center defeats Righty, 60-40.

Center would have won against either opponent one-on-one.

Yet Center was eliminated first -- because RCV rewards concentrated first-choice support, not broad acceptability.

This is called the **center squeeze**: a broadly preferred candidate is squeezed out by opponents with stronger but narrower first-choice bases.

---

## Section 2: When Increasing Support Changes Who Wins

In many voting systems, if additional voters rank a candidate higher -- and nothing else changes -- that candidate's position either improves or remains unchanged.

Voting theorists refer to this property as **monotonicity**.

> A voting system is monotonic if, whenever a candidate would win under one set of ballots, that candidate would still win if some voters changed their ballots to rank that candidate higher, with no other changes.

Under this definition, increasing support cannot reverse a winning outcome.

Most single-round tally systems are monotonic.

Elimination-based systems operate differently.

Because candidates are removed one round at a time, increasing first-choice support can change which candidate is eliminated first. That shift can alter how later ballots are transferred.

In certain structured elections, a candidate who would have won may lose after gaining additional support.

### A Fully Worked Example

Three candidates:

- Alice 🤟🏼
- Ben 🫰🏼
- Carl ✌🏼

100 voters.

### Version 1 -- Original Election

- 36: Alice > Carl > Ben
- 35: Ben > Carl > Alice
- 29: Carl > Alice > Ben

#### Round 1

| Candidate | First-Choice Votes |
|---|---|
| Alice | 36 |
| Ben | 35 |
| Carl | 29 |

Carl is eliminated ❌.

#### Round 2

29: Carl ❌ → Alice 🤟🏼

| Candidate | Votes |
|---|---|
| Alice | 65 |
| Ben | 35 |

Alice wins.

### Version 2 -- Alice Gains Support

Now suppose **7 Ben voters switch to Alice**.

- 43: Alice > Carl > Ben
- 28: Ben > Carl > Alice
- 29: Carl > Alice > Ben

#### Round 1

| Candidate | First-Choice Votes |
|---|---|
| Alice | 43 |
| Ben | 28 |
| Carl | 29 |

Ben is eliminated ❌.

#### Round 2

28: Ben ❌ → Carl ✌🏼

| Candidate | Votes |
|---|---|
| Alice | 43 |
| Carl | 57 |

Carl wins.

### What Happened?

Alice gained support -- but the elimination order changed -- and the outcome reversed.

In Version 1, Carl was eliminated first. In Version 2, Ben was eliminated first -- and Ben's voters transferred to Carl rather than Alice.

This requires a close race and similar levels of support among candidates. It does not occur in most elections, but it is a real structural possibility within elimination-based systems.

---

## Section 3: When Ballots Leave the Count

Ranked Choice Voting does not require voters to rank all candidates.

When a ballot no longer lists any remaining candidates, it **exhausts** and can no longer influence subsequent rounds.

### Active and Exhausted Ballots

- An **active ballot** lists at least one candidate who has not been eliminated.
- An **exhausted ballot** lists no remaining candidates.

Exhausted ballots were counted in earlier rounds. They simply no longer participate once all ranked candidates are eliminated.

### The Two-Table Model 🗂️

Imagine the count taking place across two tables: one for ballots still in play, another for ballots that have exhausted.

#### Beginning of the Count

| Active Table | Exhausted Table |
|---|---|
| 100 ballots | 0 ballots |

Majority threshold: 100 x 0.50 + 1 = **51**

All 100 ballots are in play.

#### After Round 2

5 ballots exhaust.

| Active Table | Exhausted Table |
|---|---|
| 95 ballots | 5 ballots |

New majority threshold: 95 x 0.50 + 1 = **48**

#### After Round 3

10 additional ballots exhaust.

| Active Table | Exhausted Table |
|---|---|
| 85 ballots | 15 ballots |

New majority threshold: 85 x 0.50 + 1 = **43**

### What Has Changed?

Originally, 51 votes were required -- a majority of 100 ballots cast.

After exhaustion, 43 votes are required -- a majority of 85 ballots still active.

The definition of majority has not changed.

What has changed is the number of ballots participating in the decisive round.

When we say that RCV produces a "majority winner," we mean a majority of the ballots still active in the final round.

---

## Section 4: What Ranked Choice Voting Optimizes For

Ranked Choice Voting changes both the information collected on the ballot and the method used to process that information.

Compared to plurality, RCV:

- Allows voters to rank candidates rather than select only one.
- Simulates a runoff without requiring a second election.
- Transfers votes from eliminated candidates rather than splitting similar support.
- Produces winners who receive a majority of ballots still active in the final round.

Plurality identifies the largest bloc of support.

RCV attempts to consolidate support through successive rounds of elimination.

### Structural Advantages

RCV can:

- Reduce vote splitting among similar candidates.
- Eliminate the need for a separate runoff election.
- Encourage voters to express backup preferences.
- Allow candidates to accumulate support beyond their initial base.

### Structural Tradeoffs

Because RCV relies on sequential elimination:

- The order of elimination can affect the outcome.
- Broadly acceptable candidates may be eliminated early.
- Increasing support can, in rare cases, change who wins.
- Ballots may exhaust, reducing the number of ballots active in the final round.
- The majority threshold may differ from a majority of all ballots originally cast.

These are consequences of the rule structure.

### Relationship to Majority and Consensus

RCV is designed to produce a majority winner under its counting framework.

Consensus, as examined in Part I, describes a condition of broad collective acceptance rather than a numerical threshold. RCV does not guarantee that condition.

RCV prioritizes majority consolidation through elimination rounds.

That design choice rearranges tradeoffs rather than eliminating them.

---

## Conclusion

Ranked Choice Voting modifies the ballot and the counting rule in order to address vote splitting and produce majority outcomes without a second election.

It introduces structural consequences of its own:

- The center squeeze can eliminate broadly acceptable candidates.
- Gaining additional support can, in closely contested races, reverse outcomes.
- Ballot exhaustion can reduce the number of voters represented in the final round.

These are not errors in the system. They are products of its design.

Like plurality, RCV balances clarity, legitimacy, and expressiveness differently.

No voting system perfectly satisfies every desirable criterion. Each system defines what kind of agreement it is designed to measure.

But ranking is not the only way to express preference.

In the next article, we ask a broader question:

What if the ballot collected different information altogether -- not the order of preference, but the type and degree of support?
