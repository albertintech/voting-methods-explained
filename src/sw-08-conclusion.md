# Conclusion

## From Single-Winner to Multi-Winner Systems

---

## Statement of Purpose

This article concludes the single-winner portion of this series.

Across the previous articles, we examined multiple voting systems used to select one officeholder at a time. Each system changed either:

- The structure of the ballot
- The method of counting
- Or both

The goal was not to determine which system is "best."

It was to understand how design choices shape outcomes.

This final article synthesizes what we have learned -- and prepares us to expand the design space beyond single-winner elections.

---

## What We Learned About Single-Winner Systems

Over the course of this series, we explored multiple structural dimensions.

Rather than summarizing by system, it is more useful to summarize by design choice.

### 1️⃣ Ballot Structure

We examined four distinct ways ballots can collect information:

| Ballot Type | What Voters Provide |
|---|---|
| Choose One | A single preferred candidate |
| Ranking | An ordered list of candidates |
| Approval | Any number of acceptable candidates |
| Rating (Score/STAR) | A numerical evaluation of each candidate |

Each ballot structure captures different information:

- Ranking captures order.
- Approval captures acceptability.
- Rating captures intensity.
- Choose-one captures only top preference.

More expressive ballots gather more information. They also change the strategic landscape -- not by introducing strategy where none existed, but by shifting the form that strategic reasoning takes.

### 2️⃣ Counting Logic

We examined several counting approaches:

- **Plurality tally** (single-round, most votes wins)
- **Sequential elimination** (RCV)
- **Aggregate approval totals**
- **Aggregate scoring totals**
- **Score + automatic runoff** (STAR)
- **Pairwise head-to-head comparisons** (Condorcet lens)

Each counting rule processes ballot information differently.

Some simulate runoffs. Some consolidate support. Some aggregate evaluation. Some check head-to-head viability.

The counting rule is not neutral. It determines what kind of support is decisive.

### 3️⃣ Majority vs Plurality

A central theme has been the difference between:

- **Plurality winners** (largest share)
- **Majority winners** (more than half)

Some systems guarantee a majority of active ballots. Others do not require one. Some confirm majority only between finalists. Some optimize for highest aggregate evaluation instead.

"Majority" itself turns out to be a defined threshold within a specific counting framework.

### 4️⃣ Expressiveness vs Simplicity

As ballots become more expressive, they ask more of voters:

- Rank fully?
- Approve strategically?
- Calibrate a score scale?

At the same time, more expressive systems often reduce pathologies -- systematic outcomes like vote splitting that no reasonable design would intentionally produce.

But they may introduce:

- Threshold decisions
- Score exaggeration incentives
- Elimination-order sensitivity

Simplicity and expressiveness are not opposites -- but they do trade off.

### 5️⃣ Strategic Incentives

No system eliminates strategy entirely.

Different systems relocate it:

- Plurality → coordination around viability
- RCV → ranking order and elimination effects
- Approval → approval threshold
- Score → scale compression
- STAR → score calibration + finalist positioning

Strategy changes form. It does not disappear.

### 6️⃣ Condorcet as Evaluative Lens

The final article introduced a benchmark:

If a candidate would defeat every other candidate in one-on-one majority comparisons, should that candidate win?

The **Condorcet criterion** provides an evaluative dimension -- not a complete design solution.

It reminds us that:

- Majority rule can be defined in different ways.
- Pairwise consistency is one structural value among many.
- Even majority-based systems must resolve cycles.

### 7️⃣ Voting Criteria: A Framework for Evaluation

The Condorcet criterion is one example of a broader concept: **voting criteria**.

A voting criterion is a specific, testable property that a voting system may or may not satisfy. Criteria provide a shared vocabulary for evaluating systems -- not by asking "which is best?" but by asking "what does this system guarantee, and what does it not?"

Throughout this series, we encountered several criteria by name or by demonstration, even when we did not always use formal labels.

#### Criteria Encountered in This Series

| Criterion | What It Asks | Where We Saw It |
|---|---|---|
| **Majority** | If a candidate is the first choice of more than half the voters, must that candidate win? | Part I (Plurality does not require majority), Part IIb (RCV guarantees majority of active ballots) |
| **Condorcet** | If a candidate would defeat every other candidate one-on-one, must that candidate win? | Part VI (introduced as a benchmark; no system covered guarantees it) |
| **Monotonicity** | Can gaining additional voter support ever cause a candidate to lose? | Part IIb (demonstrated that RCV can violate this in closely contested races) |
| **Later-no-harm** | Can ranking a backup candidate ever cause your first choice to lose? | Part IIa-IIb (implicit in the locked ballot model; RCV satisfies this, but Approval and Score do not -- approving or scoring a second candidate can hurt your favorite) |

These four criteria appeared because they were directly relevant to the structural consequences we examined. But they are not the only criteria that voting theorists use.

#### Criteria Beyond This Series

The following criteria are well-established in voting theory but were outside the scope of a 101 introduction. They are listed here as a roadmap for further exploration.

| Criterion | What It Asks |
|---|---|
| **Independence of Irrelevant Alternatives (IIA)** | Does adding or removing a non-winning candidate ever change who wins? (Closely related to the spoiler effect discussed in Part I.) |
| **Participation** | Can a voter ever cause a worse outcome by showing up to vote than by staying home? |
| **Consistency** | If two separate groups of voters would each independently elect the same candidate, does combining them still elect that candidate? |
| **Clone Independence** | Does adding a nearly identical candidate ever change the outcome? (Related to vote splitting, but defined more precisely.) |
| **Later-no-help** | Can ranking a backup candidate ever help your first choice? (The counterpart to later-no-harm.) |
| **Reversal Symmetry** | If a system selects a winner, and every voter reverses their entire ranking, must that original winner now finish last? |

No system satisfies all criteria simultaneously -- as Arrow's theorem confirms. But knowing which criteria a system satisfies, and which it sacrifices, is the foundation of informed evaluation.

This is the structural vocabulary that allows a reader to move beyond "which system is best?" and toward a more precise question: "best according to which priorities?"

### Core Insight

No single-winner system optimizes every evaluative criterion simultaneously.

This is not just an empirical pattern. Arrow's Impossibility Theorem establishes it as a mathematical result: any voting system that uses ranked preferences must sacrifice at least one of a set of basic fairness properties. The question is not whether tradeoffs exist, but which ones a given system accepts.

Different systems prioritize:

- Concentrated first-choice support
- Majority consolidation
- Broad acceptability
- Intensity of support
- Pairwise dominance

When one value is strengthened, another may weaken.

Tradeoffs of this kind are inherent to institutional design. The central task is recognizing which priorities a system elevates -- and which it does not.

---

## The Limits of Single-Winner Design

All systems we examined share a defining feature:

They select **one officeholder**.

This constraint shapes every tradeoff.

When a group must choose a single individual:

- Preferences are compressed.
- Coalitions consolidate.
- Minor factions may go unrepresented.
- Compromise is forced into a single outcome.

Some tensions we observed -- such as vote splitting, elimination order sensitivity, or threshold strategy -- arise within this structural constraint.

But other tensions stem from the constraint itself.

When only one position exists:

- Representation is zero-sum.
- One coalition governs.
- Others do not.

Single-winner systems differ in how they determine who that coalition will be.

They do not change the fact that only one coalition ultimately governs.

Recognizing this helps clarify a broader point:

Ballot format is only one dimension of institutional design.

The number of seats available is another.

---

## Preview: Multi-Winner Methods

So far, the design problem has been:

> How should we select one winner?

Multi-winner systems change the question:

> How should representation be allocated across multiple seats?

This shift introduces new structural concepts.

### District Magnitude

**District magnitude** refers to how many representatives are elected from a district.

- Magnitude 1 → single-winner
- Magnitude 3, 5, 10, etc. → multi-winner

As magnitude increases, the design problem changes.

### Majority vs Proportional Logic

Single-winner systems often prioritize:

- Identifying a majority-supported individual
- Or selecting the most broadly supported candidate

Multi-winner systems often introduce:

- **Proportional representation**
- Allocation of seats to reflect group support

Instead of compressing preferences into one outcome, multi-winner systems may distribute representation across factions.

### Coalition Representation

In multi-winner systems:

- Groups may gain seats roughly proportional to their support.
- Representation can be shared rather than concentrated.
- Majority and minority blocs may both hold seats.

This does not eliminate tradeoffs.

It changes the type of tradeoffs being considered.

The design objective shifts from:

> Who wins?

To:

> How should representation be distributed?

---

## The Broader Design Space

Voting systems are part of institutional architecture.

They interact with:

- District size
- Number of seats
- Party systems
- Legislative rules
- Executive structure

Changing ballot format alters incentives.

Changing district magnitude alters representation itself.

Tradeoffs do not disappear in multi-winner systems.

They reappear in new forms:

- Simplicity vs proportionality
- Local accountability vs coalition diversity
- Stability vs fragmentation

Criteria may conflict differently at larger scales.

But they still conflict.

---

## Expanding the Frame

Throughout this series, one theme has remained constant:

Voting systems reflect priority choices.

Each design:

- Collects certain information
- Processes it in a particular way
- Guarantees some outcomes
- Leaves others unguaranteed

Evaluative criteria sometimes conflict:

- Majority consolidation
- Broad acceptability
- Intensity of support
- Pairwise consistency
- Simplicity
- Proportional fairness

No single-winner system satisfies all simultaneously.

Understanding this is structural literacy.

As we move forward, we expand the design space.

The question is no longer only:

> Which individual should hold office?

It becomes:

> How should representation itself be structured?

Multi-winner systems do not solve the tradeoffs we have studied.

They reconfigure them.

The next phase of this series will examine how expanding the number of seats changes the nature of democratic choice -- and what new design questions emerge when representation is shared rather than singular.
