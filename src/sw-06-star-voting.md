# STAR Voting

## A Hybrid of Scoring and Runoff Logic

---

## Statement of Purpose

This article explains **STAR Voting** (Score Then Automatic Runoff) for single-winner elections.

STAR Voting combines two ideas we have already examined:

- Voters **score** candidates on a numerical scale.
- The top two scorers advance to an automatic **runoff comparison**.

We will:

- Walk through how ballots are cast and counted.
- Examine what problem STAR attempts to address.
- Compare it to Score Voting, Approval Voting, and Ranked Choice Voting.
- Evaluate the structural tradeoffs it introduces.

As in previous articles, the goal is clarity -- not advocacy.

---

## Section 1: What Is STAR Voting?

STAR stands for **S**core **T**hen **A**utomatic **R**unoff.

Like Score Voting, voters rate each candidate on a fixed scale (commonly 0-5).

The counting happens in two stages:

### Stage 1 -- Scoring Round

- Add up all scores for each candidate.
- The two candidates with the highest total scores advance.

### Stage 2 -- Automatic Runoff

- For those two finalists only:
  - On each ballot, whichever finalist received the higher score is preferred.
- The finalist preferred on more ballots wins.

No separate election is held. The runoff is simulated using the same ballots.

---

## Section 2: A Simple Example

Three candidates:

- Alice 🤟🏼
- Ben 🫰🏼
- Carl ✌🏼

100 voters. Scale: 0-5.

Ballots:

- 40 voters -- Alice: 5, Ben: 2, Carl: 0
- 35 voters -- Alice: 1, Ben: 5, Carl: 3
- 25 voters -- Alice: 3, Ben: 2, Carl: 5

### Stage 1 -- Add Scores

| Candidate | Total Score |
|---|---|
| Alice | 310 |
| Ben | 305 |
| Carl | 230 |

Alice and Ben advance to the runoff.

### Stage 2 -- Automatic Runoff

Now compare Alice and Ben ballot by ballot.

- 40 voters scored Alice (5) higher than Ben (2) → Alice preferred
- 35 voters scored Ben (5) higher than Alice (1) → Ben preferred
- 25 voters scored Alice (3) higher than Ben (2) → Alice preferred

Runoff totals:

| Candidate | Ballots Preferring |
|---|---|
| Alice | 65 |
| Ben | 35 |

Alice wins.

### What Changed Compared to Score Voting?

In pure Score Voting, Alice already won by total score.

In STAR, that result is confirmed through a majority-style head-to-head comparison between the top two.

The second round ensures that the winner defeats the other finalist in a direct comparison.

---

## Section 3: What Problem Does STAR Attempt to Solve?

STAR was developed in response to a concern about Score Voting.

### The Concern: Strategic Exaggeration

In Score Voting, voters may exaggerate:

- Give favorite: 5
- Give competitor: 0

If many voters compress the scale this way, Score Voting begins to resemble Approval or Plurality Voting.

STAR attempts to reduce this incentive.

Because:

- Advancing to the top two depends on total score.
- Winning depends on being preferred in the runoff.

Giving a compromise candidate a moderate score can help them reach the runoff -- without necessarily causing them to defeat your favorite.

The two-stage structure aims to balance:

- Intensity (from scores)
- Broad pairwise support (from runoff comparison)

---

## Section 4: Relationship to Majority Support

STAR does not require a majority in the scoring round.

But the final winner must defeat the other finalist in a head-to-head comparison of ballots.

In that sense, the winner:

- Has majority support **against the other finalist**,
- But not necessarily against every candidate in the field.

This differs from:

- **Ranked Choice Voting**, which produces a majority of active ballots after eliminations.
- **Score Voting**, which selects the highest total score without a runoff stage.

STAR adds a majority-style confirmation step -- but only between two candidates.

---

## Section 5: Comparison to Other Systems

| Feature | RCV | Approval | Score | STAR |
|---|---|---|---|---|
| Ranking required | Yes | No | No | No |
| Rating scale | No | No | Yes | Yes |
| Multiple support allowed | Via ranking | Yes | Yes | Yes |
| Elimination rounds | Yes | No | No | No |
| Runoff logic | Simulated elimination | No | No | Yes (top two) |
| Ballot exhaustion | Possible | No | No | No |
| Strategy focus | Ranking order | Approval threshold | Score exaggeration | Score use + finalist positioning |

STAR combines:

- The expressive input of Score Voting
- A runoff-style majority check

It does not use elimination rounds. It does not transfer ballots. Every ballot counts in both stages.

---

## Section 6: Structural Consequences

STAR addresses some concerns -- but introduces its own design effects.

### 1️⃣ Two Candidates Advance

Only the top two scorers enter the runoff.

A candidate who might defeat many opponents head-to-head may fail to advance if their total score is slightly lower.

### 2️⃣ Strategic Scoring Still Exists

Although STAR attempts to soften exaggeration incentives, voters still face decisions:

- Should I give a compromise a 4 or a 5?
- Could boosting a compromise push them into the runoff instead of my favorite?

Strategy is reduced in some contexts -- but not eliminated.

### 3️⃣ Majority Only Among Finalists

The winner defeats the other finalist -- but not necessarily all candidates.

This differs from systems designed to identify a candidate who would defeat every other candidate in one-on-one comparisons.

---

## Section 7: Tradeoffs

STAR Voting attempts to balance:

- Expressiveness (via scoring)
- Simplicity of tabulation
- A majority-style final check

It avoids:

- Ballot exhaustion
- Sequential elimination order
- Separate runoff elections

But it introduces:

- A two-stage counting process
- Continued incentives around score strategy
- Dependence on which candidates reach the top two

Like all voting systems, STAR optimizes for certain goals:

- Strong overall support
- Direct comparison between leading candidates
- Single-election resolution

It does not eliminate tradeoffs. It rearranges them.

---

## Conclusion

Plurality selects the most votes.

Ranked Choice Voting eliminates candidates until one has a majority of active ballots.

Approval Voting counts how many voters find each candidate acceptable.

Score Voting aggregates degrees of support.

STAR Voting combines scoring with an automatic runoff.

It seeks to preserve expressive ballots while ensuring the winner prevails in a head-to-head comparison between the top two scorers.

Whether this balance improves outcomes depends on:

- How voters use the scoring scale
- How competitive the field is
- What one values most in a voting system

In the final article of this series, we will examine a different lens altogether:

Rather than proposing a new ballot structure, we will explore a benchmark for evaluating systems -- the idea of a Condorcet winner.

Can a voting system guarantee that the candidate who would win every one-on-one contest is selected?

And what happens when preferences cycle?
