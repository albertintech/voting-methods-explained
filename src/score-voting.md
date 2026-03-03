# Score Voting

## Measuring Degrees of Support

---

## Statement of Purpose

In the previous article, we examined **Approval Voting**, which allows voters to support more than one candidate.

Approval answers a simple question:

> Which candidates are acceptable?

Score Voting asks a different one:

> How strongly do you support each candidate?

This article explains how Score Voting works, demonstrates its counting process step by step, and evaluates the structural tradeoffs it introduces compared to Approval Voting and Ranked Choice Voting (RCV).

---

## Section 1: What Score Voting Is

Score Voting (sometimes called *Range Voting*) uses a **fixed numerical rating scale**.

Common scales include:

- 0-5
- 0-10
- 0-100

The scale is defined before the election.

On the ballot, voters assign a score to each candidate. For example, on a 0-5 scale:

- 0 = lowest support
- 5 = highest support

Voters may:

- Give the same score to multiple candidates
- Give all candidates the same score
- Use only part of the scale

### How Counting Works

1. Add all scores for each candidate.
2. (Sometimes totals are averaged, but totals and averages produce the same ranking.)
3. The candidate with the highest total score wins.

There are:

- No eliminations
- No ballot transfers
- No runoff stage
- A single round of tabulation

Every ballot contributes to every candidate's total.

---

## Section 2: Fully Worked Example

Let's walk through a complete example.

**Candidates:**

- Alice 🤟🏼
- Ben 🫰🏼
- Carl ✌🏼

**Voters:** 100

**Scale:** 0-5

For clarity, we group voters by scoring pattern.

### Ballot Groups

**Group 1 -- 40 voters**

| Candidate | Score |
|---|---|
| Alice | 5 |
| Ben | 2 |
| Carl | 0 |

**Group 2 -- 35 voters**

| Candidate | Score |
|---|---|
| Alice | 1 |
| Ben | 5 |
| Carl | 3 |

**Group 3 -- 25 voters**

| Candidate | Score |
|---|---|
| Alice | 3 |
| Ben | 2 |
| Carl | 5 |

### Step 1 -- Multiply Scores by Voter Count

**Alice**

- 40 x 5 = 200
- 35 x 1 = 35
- 25 x 3 = 75

**Total for Alice = 200 + 35 + 75 = 310**

**Ben**

- 40 x 2 = 80
- 35 x 5 = 175
- 25 x 2 = 50

**Total for Ben = 80 + 175 + 50 = 305**

**Carl**

- 40 x 0 = 0
- 35 x 3 = 105
- 25 x 5 = 125

**Total for Carl = 0 + 105 + 125 = 230**

### Final Totals

| Candidate | Total Score |
|---|---|
| Alice | **310** |
| Ben | 305 |
| Carl | 230 |

Alice wins with the highest aggregate score.

No candidates were eliminated. No ballots transferred. All 100 voters influenced the totals for all three candidates.

---

## Section 3: What Problem Score Voting Attempts to Solve

Score Voting builds on concerns raised in earlier systems.

### 1️⃣ Vote Splitting

Like Approval Voting, Score Voting allows voters to support more than one candidate.

A voter who prefers Alice but finds Carl acceptable could score:

- Alice: 5
- Carl: 4

This reduces pressure to abandon acceptable alternatives in order to avoid splitting support.

### 2️⃣ Loss of Intensity

Approval Voting captures acceptability -- but not degree.

Ranking systems capture order -- but not strength.

Score Voting captures **intensity of support**.

### 3️⃣ Information Compression in Ranking

Ranking forces a strict order.

Score Voting allows ties and near-ties naturally through similar scores.

---

## Section 4: Strategic Exaggeration

Because Score Voting uses a scale, voters must decide how to use it.

Honest scoring:

| Candidate | Honest Score |
|---|---|
| Alice | 5 |
| Ben | 4 |
| Carl | 0 |

Possible exaggerated scoring:

| Candidate | Exaggerated Score |
|---|---|
| Alice | 5 |
| Ben | 0 |
| Carl | 0 |

When many voters compress the scale, Score Voting can resemble Approval Voting.

This is a structural incentive, not a counting error.

---

## Section 5: Relationship to Majority Support

Score Voting does not require a majority threshold.

The candidate with the highest total score wins.

It optimizes for aggregate evaluation, not majority consolidation.

---

## Section 6: Tradeoffs

Score Voting attempts to solve:

- Vote splitting
- Loss of intensity
- Binary approval limitation

It introduces:

- Strategic score exaggeration
- Scale interpretation variance
- No majority guarantee
- Less intuitive majority framing

---

## Structural Comparison

| Feature | Approval | Score |
|---|---|---|
| Ballot type | Approve any number | Rate each candidate (fixed scale) |
| Expresses intensity | No | Yes |
| Eliminations | No | No |
| Transfers | No | No |
| Majority guarantee | No | No |
| Strategy focus | Approval threshold | Score distribution / compression |

---

## Conclusion

Score Voting allows voters to express degrees of support.

It captures more information than Approval Voting.

It reduces vote splitting while introducing scale-based strategy considerations.

It is another branch in the voting system design space.

In the next article, we will examine STAR Voting, which combines scoring with an automatic runoff.
