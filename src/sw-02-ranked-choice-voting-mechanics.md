# Ranked Choice Voting (RCV)

## Part A -- How It Works

---

## Statement of Purpose

This article explains the mechanics of **Ranked Choice Voting (RCV)** for single-winner elections.

We will:

- Describe how ranked ballots are cast
- Walk through the counting process step by step
- Demonstrate a full multi-candidate example
- Introduce the locked ballot model

In the previous article, we examined **Plurality Voting** and the structural consequences that follow from its choose-one design.

Some reform efforts ask:

> Can we move closer to majority outcomes without requiring a separate runoff election?

One response is Ranked Choice Voting.

---

## Section 1: From Plurality to Ranked Choice Voting

Under plurality:

- Each voter selects one candidate.
- The candidate with the most votes wins.
- A majority is not required.

Plurality identifies the largest bloc of support in a single round.

But plurality does not attempt to:

- Guarantee majority winners
- Capture backup preferences
- Reduce vote splitting

Ranked Choice Voting adds a new dimension of information to the ballot: an ordered ranking of candidates.

Instead of selecting one name, voters indicate how candidates compare to one another.

### What Is Ranked Choice Voting?

**Ranked Choice Voting (RCV)** allows voters to rank candidates in order of preference:

- 🥇 1st choice
- 🥈 2nd choice
- 🥉 3rd choice
- and so on.

For single-winner elections, the counting method used with ranked ballots is commonly called **Instant Runoff Voting (IRV)**.

### The Runoff Concept 🔁

A **runoff election** occurs when no candidate receives a majority in the first round of voting.

In traditional runoff systems:

1. Voters cast ballots.
2. If no candidate exceeds 50%, the top two candidates compete in a second election.
3. Voters return to vote again.

Ranked Choice Voting attempts to simulate this process within a single election.

➡️ The runoff happens during counting.

However:

> In a traditional runoff, voters may reconsider their choices between rounds. In RCV, all rankings are fixed when the ballot is cast.

---

## Section 2: How RCV Counting Works 🗳️

The counting process proceeds in rounds.

### Step 1 -- Count First Choices 🥇

All first-choice votes are tallied.

If a candidate receives a majority of the ballots still in play (often called **active ballots**), they win.

At the beginning of the count, all ballots are still in play.

If no candidate has a majority, the process continues.

### Step 2 -- Eliminate the Lowest Candidate ❌

The candidate with the fewest first-choice votes is eliminated.

### Step 3 -- Transfer Ballots 🔄

Ballots that ranked the eliminated candidate first are transferred to the next ranked candidate who has not been eliminated.

### Step 4 -- Repeat 🔁

After transfers:

- Totals are recalculated.
- If a candidate now has a majority, they win.
- If not, the next lowest candidate is eliminated.

---

## Section 3: The Locked Ballot Model 🔒

At any given moment in the count:

> A ballot counts for only one candidate.

Ballots remain locked onto their highest-ranked remaining candidate.

If that candidate is eliminated ❌:

- The ballot unlocks 🔓
- Moves to the next ranked candidate 🔄
- Locks again 🔒

---

## Section 4: A 5-Candidate Example

### A Note on Simplification

For clarity, this example groups voters into a small number of ranking patterns.

In a real five-candidate election, there are **120 different possible full ranking orders**, and even more possible ballot types if voters rank only some candidates.

Real elections are usually much more varied than this simplified illustration -- but the counting process works the same way.

### Candidates

- Alice 🤟🏼
- Ben 🫰🏼
- Carl ✌🏼
- Dale 👍🏼
- Erin 👌🏼

100 voters.

### Ballots

- 30: Alice > Carl > Dale > Ben > Erin
- 24: Ben > Dale > Erin > Carl > Alice
- 20: Carl > Dale > Alice > Ben > Erin
- 16: Dale > Erin > Ben > Carl > Alice
- 10: Erin > Dale > Ben > Carl > Alice

Majority threshold: 51.

### Round 1

| Candidate | Votes |
|---|---|
| Alice | 30 |
| Ben | 24 |
| Carl | 20 |
| Dale | 16 |
| Erin | 10 |

Erin 👌🏼 is eliminated ❌.

### Round 2

Erin's ballots transfer:

10: Erin ❌ → Dale 👍🏼

New totals:

| Candidate | Votes |
|---|---|
| Alice | 30 |
| Ben | 24 |
| Carl | 20 |
| Dale | 26 |

Carl ✌🏼 is eliminated ❌.

### Round 3

Carl's ballots transfer:

20: Carl ❌ → Dale 👍🏼

New totals:

| Candidate | Votes |
|---|---|
| Alice | 30 |
| Ben | 24 |
| Dale | 46 |

Ben 🫰🏼 is eliminated ❌.

### Round 4

Ben's ballots transfer:

24: Ben ❌ → Dale 👍🏼

Final totals:

| Candidate | Votes |
|---|---|
| Alice | 30 |
| Dale | 70 |

Dale wins with a majority of active ballots.

### What Just Happened?

Dale began in fourth place with only 16 first-choice votes.

Through four rounds of elimination and transfer, Dale accumulated support from voters whose earlier choices were eliminated.

No voter changed their ballot. The counting process revealed support that was already present but not visible in first-choice totals alone.

This is the core mechanical idea behind RCV: backup preferences become active as candidates are eliminated.

---

## Conclusion

Ranked Choice Voting changes both the ballot and the counting process.

Instead of selecting one candidate, voters rank candidates in order of preference. Instead of a single tally, counting proceeds through rounds of elimination and transfer until one candidate holds a majority of active ballots.

The locked ballot model captures the key mechanic: each ballot counts for one candidate at a time, moving to the next ranked choice only when the current choice is eliminated.

These mechanics are straightforward.

But the design of the counting process -- sequential elimination based on first-choice totals -- produces structural consequences that are not always obvious from the rules alone.

In the next article, we examine those consequences:

What happens when a broadly acceptable candidate lacks first-choice support?

What happens when gaining additional support changes the elimination order?

And what happens when ballots run out of ranked candidates before the final round?
