# Condorcet as Benchmark

## A Standard for Evaluating Voting Systems

---

## Statement of Purpose

Throughout this series, we examined several single-winner voting systems:

- Plurality
- Ranked Choice Voting (RCV)
- Approval Voting
- Score Voting
- STAR Voting

Each system altered either the ballot structure, the counting rule, or both.

This article introduces something different.

It does not propose a new ballot.

Instead, it introduces a theoretical benchmark -- a way to evaluate voting systems.

That principle is known as the Condorcet principle.

---

## Section 1: Head-to-Head Majority Comparisons

To understand the Condorcet principle, we begin with a simple idea:

Compare candidates two at a time.

This is called a pairwise comparison.

Instead of asking "Who has the most first-choice votes?" or "Who has the highest score?" we ask:

> If the election were only between Candidate A and Candidate B, who would win?

### A Fully Worked Example

Three candidates:

- Alice 🤟🏼
- Ben 🫰🏼
- Carl ✌🏼

100 voters cast ranked ballots.

#### Ballot Groups

- 35 voters: Alice > Ben > Carl
- 33 voters: Ben > Carl > Alice
- 32 voters: Carl > Alice > Ben

No candidate has a majority of first-choice votes.

Instead of eliminating anyone, we calculate head-to-head totals.

#### Step 1 -- Alice vs Ben

Prefer Alice over Ben:

- 35 voters
- 32 voters

Total: 67

Prefer Ben over Alice:

- 33 voters

Result: Alice defeats Ben, 67-33.

#### Step 2 -- Alice vs Carl

Prefer Alice over Carl:

- 35 voters

Total: 35

Prefer Carl over Alice:

- 33 voters
- 32 voters

Total: 65

Result: Carl defeats Alice, 65-35.

#### Step 3 -- Ben vs Carl

Prefer Ben over Carl:

- 35 voters
- 33 voters

Total: 68

Prefer Carl over Ben:

- 32 voters

Result: Ben defeats Carl, 68-32.

### Pairwise Matrix

| | Alice | Ben | Carl |
|---|---|---|---|
| **Alice** | -- | 67 | 35 |
| **Ben** | 33 | -- | 68 |
| **Carl** | 65 | 32 | -- |

No candidate defeats both opponents.

---

## Section 2: The Condorcet Winner

A Condorcet winner is:

> A candidate who would defeat every other candidate in one-on-one majority comparisons.

Not every election produces one.

When one exists, it represents a candidate preferred by a majority over each alternative.

---

## Section 3: Cycles (The Condorcet Paradox)

Majority preferences can form a loop:

- A majority prefers Alice over Ben
- A majority prefers Ben over Carl
- A majority prefers Carl over Alice

This is called a Condorcet cycle.

It is a structural property of collective decision-making.

---

## Section 4: Completion Methods

If a Condorcet winner exists, selecting them is straightforward.

If preferences cycle, additional rules -- called completion methods -- are required.

Different approaches resolve cycles differently. To see how, we can return to the cycle from Section 1 and apply one of the simplest completion methods.

### Minimax: A Worked Example

One approach to resolving a cycle is called **Minimax**.

The idea: every candidate in a cycle loses at least one head-to-head matchup. Minimax selects the candidate whose worst loss is the smallest.

We already have the results from Section 1:

| Matchup | Winner | Margin |
|---|---|---|
| Alice vs Ben | Alice wins, 67-33 | 34 |
| Alice vs Carl | Carl wins, 65-35 | 30 |
| Ben vs Carl | Ben wins, 68-32 | 36 |

Now identify each candidate's worst defeat:

- **Alice** -- lost to Carl by 30 (65-35)
- **Ben** -- lost to Alice by 34 (67-33)
- **Carl** -- lost to Ben by 36 (68-32)

Alice's worst defeat is the smallest.

Under Minimax, Alice wins.

### What This Illustrates

Minimax resolves the cycle by asking: which candidate has the strongest claim even in their weakest matchup?

Other completion methods use different logic. Some prioritize the strength of victories rather than the size of defeats. Some lock in the strongest pairwise results one at a time and discard weaker results that would create a cycle.

Each method produces a defensible winner -- but not always the same winner.

Even within the Condorcet family, design choices shape outcomes.

---

## Section 5: Using Condorcet as a Criterion

A system passes the Condorcet criterion if it always elects the Condorcet winner when one exists.

Many commonly used systems do not guarantee this outcome.

The criterion is one evaluative dimension among many.

---

## Section 6: Structural Comparison

| System | Ballot Structure | Counting Logic | What It Rewards | Condorcet Criterion? |
|---|---|---|---|---|
| Plurality | Choose one candidate | Single-round plurality tally | Concentrated first-choice support | Does not guarantee |
| RCV | Ranked ballot | Sequential elimination until majority | Transferable support and consolidation | Does not guarantee |
| Approval | Approve any number | Single-round approval tally | Broad acceptability | Does not guarantee |
| Score | Rate each candidate (scale) | Highest total score | Intensity of support | Does not guarantee |
| STAR | Rate + top-two runoff | Score round + finalist head-to-head | Aggregate score + finalist viability | Does not guarantee |

---

## Conclusion

The Condorcet principle provides a benchmark for evaluating voting systems.

It does not rank them.

It clarifies one structural question:

If a candidate would defeat every other candidate head-to-head, should the system select that candidate?

Voting systems reflect design priorities.

Criteria sometimes conflict. In 1951, the economist Kenneth Arrow proved that this is not merely an observation -- it is a mathematical certainty. No ranked voting system can simultaneously satisfy a small set of reasonable fairness criteria. This result, known as **Arrow's Impossibility Theorem**, is sometimes sensationalized as proof that "democracy is impossible." That framing misses the point. Just as no single food can satisfy all of a person's nutritional needs, no single voting method can satisfy everything we might want in a voting system. The impossibility is a design constraint, not a fatal flaw. It means that choosing a voting system requires understanding which criteria it prioritizes -- and which it does not.

Tradeoffs are unavoidable.

Understanding those tradeoffs is the purpose of this series.
