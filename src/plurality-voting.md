# Plurality Voting

## The Most Common Method -- and Its Structural Consequences

---

## Statement of Purpose

This article explains **Plurality Voting**, the most widely used method for single-winner elections.

We will:

- Describe how plurality ballots are cast and counted
- Examine why the system became dominant
- Identify what it optimizes for
- Explore the structural tradeoffs it introduces

Plurality voting is often treated as the default. But it, too, is a design choice.

Understanding its structure is essential before evaluating alternatives.

---

## Section 1: How Plurality Voting Works

Plurality voting is straightforward:

- Each voter selects **one** candidate.
- The candidate with the most votes wins.
- A majority is **not** required.

There are:

- No elimination rounds
- No rankings
- No scoring scales
- No runoffs (unless separately required by law)

Counting consists of a single tally.

### A Simple Example

Three candidates:

- Alice 🤟🏼
- Ben 🫰🏼
- Carl ✌🏼

100 voters cast ballots.

| Candidate | Votes |
|---|---|
| Alice | 40 |
| Ben | 35 |
| Carl | 25 |

Alice wins.

She has more votes than any other candidate.

But she does **not** have a majority (51 would be required).

Plurality means:

> More votes than anyone else -- not more than half.

### A Categorical Ballot

The plurality ballot is the simplest type of ballot possible. Voting theorists call it a **categorical ballot**.

A categorical ballot records a selection -- and nothing else.

It does not capture how voters would rank the candidates. It does not capture how strongly voters feel. It records only one piece of information: which candidate the voter chose.

Later in this series, we will encounter other ballot types:

- **Ordinal ballots**, which ask voters to rank candidates in order of preference.
- **Cardinal ballots**, which ask voters to rate candidates on a numerical scale.

Each ballot type captures different information. Each enables different counting methods.

The categorical ballot captures the least information -- but it is also the simplest to cast and count.

---

## Section 2: Why Plurality Became Dominant

Plurality voting did not become widespread by accident.

It offers several administrative advantages:

### 1️⃣ Simplicity for Voters

- Mark one name.
- No ranking required.
- Minimal ballot instructions.

### 2️⃣ Simplicity of Counting

- One round.
- No transfers.
- No recalculation.
- Easy to audit and verify.

### 3️⃣ Speed of Results

Because counting is direct, results can often be determined quickly.

### 4️⃣ Transparency

The process is intuitive:

- Count the marks.
- Highest total wins.

Plurality scales easily.

It works reliably when:

- Only two candidates compete, **or**
- One candidate has clear majority support.

In those contexts, plurality produces the same winner as a majority-rule system.

---

## Section 3: Consensus, Majority, and Plurality

When groups make decisions, there are different standards that can determine an outcome.

These standards measure different kinds of agreement.

### Agreement Standards Matrix

| Standard | What It Measures | Threshold Type | What It Optimizes For | Can Strong Opposition Exist? | Requires Numeric Rule? |
|---|---|---|---|---|---|
| **Consensus** | Absence of significant opposition | Qualitative condition | Minimal resistance | Ideally minimal | Not inherently |
| **Majority** | More than half of total support | Absolute threshold | Support exceeding 50% | Yes (up to 49%) | Yes (50% + 1) |
| **Plurality** | Largest share among options | Relative comparison | Largest faction size | Yes (can be majority opposed) | Yes (largest count) |

### Consensus

**Consensus** refers to a condition in which a decision is accepted by all -- or nearly all -- participants.

It is defined primarily by the *absence of significant opposition* rather than by the presence of enthusiastic support.

A consensus outcome might:

- Not be everyone's first choice
- Not generate strong enthusiasm
- But also not provoke meaningful resistance

Consensus does not have a fixed mathematical threshold. It describes a condition of collective acceptance.

### Majority

A **majority** means:

> More than half of the relevant total.

In a 100-voter election, a majority requires at least 51 votes.

Majority rule is an absolute threshold.

A decision can pass with 51% support even if 49% strongly object.

### Plurality

**Plurality** means:

> More votes than any other single option.

Plurality is a relative measure:

- The winner has the largest share.
- That share may be well below half.

Plurality does not attempt to achieve consensus or guarantee majority support.

It identifies the largest supported bloc in a single round.

### A Three-Candidate Example

| Candidate | Votes |
|---|---|
| Alice | 40 |
| Ben | 35 |
| Carl | 25 |

- No candidate has consensus.
- No candidate has a majority.
- Alice has a plurality.

Plurality identifies the largest group of supporters.

It does not measure whether most voters accept the outcome.

---

## Section 4: Vote Splitting

Plurality performs cleanly when the electorate is divided between two clear options.

But when more candidates enter the race, a new dynamic can emerge.

Consider:

| Candidate | Votes |
|---|---|
| Progressive A | 28 |
| Progressive B | 27 |
| Conservative C | 45 |

A majority (55 voters) prefer a progressive candidate.

But because their support is divided, the conservative candidate wins.

This phenomenon is often called **vote splitting** or the **spoiler effect**.

Vote splitting is an example of what we will call a **pathology** -- a systematic outcome that no reasonable design would intentionally produce. No one designs a voting system hoping that similar candidates will cannibalize each other's support. When vote splitting changes the outcome of an election, the system has produced a result that undermines the purpose of holding the election in the first place.

Pathologies are different from **tradeoffs**. A tradeoff is a consequence that follows from a deliberate design choice -- it may be acceptable depending on what one values. Plurality's simplicity, for example, comes at the cost of not capturing backup preferences. That is a tradeoff. Vote splitting is not a feature anyone defends. It is a structural malfunction.

This distinction -- between pathologies that undermine the system's purpose and tradeoffs that reflect its priorities -- will recur throughout this series.

Plurality requires voters to concentrate support on a single candidate.

---

## Section 5: Strategic Coordination

Because only one choice is allowed, plurality creates incentives for coordination.

Recall the earlier example:

| Candidate | Votes |
|---|---|
| Progressive A | 28 |
| Progressive B | 27 |
| Conservative C | 45 |

If Progressive B's supporters had known their candidate would finish third, many might have supported Progressive A instead -- not because they preferred A, but because consolidating behind one progressive candidate was the only way to prevent a conservative victory.

This kind of reasoning -- choosing based on viability rather than genuine preference -- is called **strategic voting**.

Strategic voting occurs when a voter casts a ballot that does not reflect their genuine preferences because they believe a different ballot will produce a better outcome. It is not cheating. It is not a failure of the voter. It is rational behavior within the constraints of the system.

This dynamic is most visible in US presidential elections when third-party candidates enter the race. In 2000, voters who preferred Ralph Nader faced a question: vote for Nader, or vote for Al Gore to prevent a George W. Bush victory? In 1992, voters who preferred Ross Perot faced the same calculation in reverse. In each case, the choose-one ballot forced voters to weigh sincerity against strategy -- a decision imposed not by the candidates but by the structure of the ballot itself.

Voters may ask:

- Which candidate is viable?
- Should I support my favorite?
- Or should I support a compromise to avoid wasting my vote?

Every voting system creates some strategic landscape. The question is not whether strategy exists, but how much pressure the system places on voters to deviate from honest expression. Some systems -- as we will see later in this series -- are designed to reduce that pressure, making honest voting a stronger strategy than it is under plurality.

Political parties often emerge in part as coordination mechanisms under plurality systems.

---

## Section 6: The Two-Round Runoff

The problems described above -- non-majority winners, vote splitting, strategic coordination -- are not new observations.

One of the oldest structural responses is the **two-round runoff**.

### How It Works

A two-round runoff adds a second election when no candidate wins a majority in the first round.

1️⃣ **Round 1** -- All candidates compete. If one candidate receives a majority, they win outright.

2️⃣ **Round 2** -- If no candidate achieves a majority, a second election is held. Typically, only the top two vote-getters from Round 1 advance. Voters return to choose between them.

Because the second round has only two candidates, the winner is guaranteed a majority.

### A Familiar Structure

The two-round system is one of the most widely used alternatives to single-round plurality worldwide. France uses it for presidential and legislative elections. Many U.S. states and municipalities use a version of it, sometimes called a "runoff primary" or "general election runoff."

It is a direct attempt to combine plurality's simplicity (a categorical ballot, one choice per round) with a majority requirement.

### What It Attempts to Solve

The two-round runoff addresses a central concern about plurality:

- In the first round, voters can express their genuine preference without strategic pressure, because a second round exists as a safeguard.
- In the second round, the field is narrowed to two candidates, ensuring majority support for the winner.

Vote splitting in the first round is less consequential, because the second round provides a corrective mechanism.

### What It Introduces

The two-round runoff introduces tradeoffs of its own:

- **A second election must be held.** This increases administrative costs, extends the election timeline, and requires voters to participate twice.
- **Turnout often drops in the second round.** The majority winner of Round 2 may represent a majority of those who voted in the runoff -- but not necessarily a majority of those who voted in Round 1.
- **The candidate field changes between rounds.** Eliminated candidates may endorse a remaining candidate, shifting coalitions. Voters may reconsider their choices in light of new information or changed dynamics.
- **First-round results still depend on vote splitting.** If three similar candidates divide support in Round 1, all three may be eliminated -- and neither of the top-two finalists may represent that broader coalition.

The two-round runoff preserves the categorical ballot. Each round uses a simple choose-one format.

Its structural innovation is procedural: hold a second election to ensure majority support.

Its structural limitation is also procedural: that second election is costly, time-consuming, and not guaranteed to reflect the full electorate.

---

## Section 7: What Plurality Optimizes For

Plurality voting prioritizes:

- Administrative simplicity
- Speed of tabulation
- Transparency of counting
- Low voter burden

It does not attempt to:

- Guarantee majority winners
- Capture backup preferences
- Measure intensity of support
- Resolve vote splitting

Its strength lies in procedural clarity.

Its tradeoffs appear when electorates fragment.

---

## Section 8: Tradeoffs

Plurality voting:

- Is easy to understand
- Is easy to administer
- Produces decisive results in a single round

But it can:

- Elect candidates without majority support
- Penalize similar candidates
- Encourage strategic voting
- Reward concentrated factions

These are structural consequences of the rule design.

Plurality balances simplicity against expressive capacity.

---

## Conclusion

Plurality voting is the most widely used single-winner election method in the world.

It works cleanly in two-candidate contests and remains attractive because of its simplicity and transparency.

But when three or more candidates compete, plurality can produce outcomes in which:

- The winner lacks majority support.
- Similar candidates divide voters.
- Strategic coordination becomes central.

The two-round runoff is one of the oldest responses to these concerns. By adding a second election between the top two finishers, it guarantees a majority winner in the final round.

But a second election is costly. Turnout may decline. And the first round still relies on a categorical ballot, meaning vote splitting can still shape which candidates advance.

This raises a question:

> What if the runoff could happen during counting -- without requiring voters to return for a second election?

In the next article, we examine one response:

**Ranked Choice Voting**.
