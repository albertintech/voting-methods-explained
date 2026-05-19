# Approval Voting

## A Different Way to Express Preference

---

## Statement of Purpose

This article explains **Approval Voting** for single-winner elections. It describes how ballots are cast and counted, illustrates how the system addresses vote splitting, and evaluates the structural tradeoffs it introduces.

Approval Voting changes not how votes are counted -- but how voters express preference.

---

## Section 1: Is Ranking the Only Way to Express Preference?

In the previous article, we examined **Ranked Choice Voting (RCV)**, where voters rank candidates in order of preference.

Ranking allows voters to say:

- "I prefer A to B."
- "If A is eliminated, count me for C."

But ranking is not the only way to express support.

Another question is:

> What if voters could support more than one candidate at the same time?

Instead of ordering candidates, voters could simply **approve** of any candidate they find acceptable.

That is the idea behind Approval Voting.

---

## Section 2: How Approval Voting Works

Approval Voting ballots list all candidates.

Voters may:

- Approve one candidate
- Approve several candidates
- Approve all candidates
- Or approve only one

There is no ranking.

There is no scoring scale.

Each approved candidate receives one vote from that ballot.

The candidate with the most approvals wins.

No majority is required.

### A Simple Example

Three candidates:

- Alice 🤟🏼
- Ben 🫰🏼
- Carl ✌🏼

100 voters.

Ballots:

40 voters approve: Alice
35 voters approve: Ben
25 voters approve: Carl

| Candidate | Approvals |
|---|---|
| Alice | 40 |
| Ben | 35 |
| Carl | 25 |

Alice wins.

So far, this looks identical to plurality voting.

The difference appears when voters approve **more than one** candidate.

### Allowing Multiple Approvals

Suppose the same voters instead cast ballots this way:

40 voters approve: Alice and Carl
35 voters approve: Ben
25 voters approve: Carl

Now the totals are:

| Candidate | Approvals |
|---|---|
| Alice | 40 |
| Ben | 35 |
| Carl | 65 |

Carl wins.

Carl may not have been the first choice of most voters -- but many voters found Carl acceptable.

Approval Voting rewards broad acceptability.

---

## Section 3: What Problem Does Approval Voting Attempt to Solve?

### Vote Splitting

Under plurality voting, similar candidates can divide support.

Recall the earlier example:

| Candidate | Votes |
|---|---|
| Progressive A | 28 |
| Progressive B | 27 |
| Conservative | 45 |

The conservative wins even though 55 voters preferred a progressive candidate.

Under Approval Voting, progressive voters could approve both progressive candidates.

If those same voters approved both A and B:

| Candidate | Approvals |
|---|---|
| Progressive A | 55 |
| Progressive B | 55 |
| Conservative | 45 |

Now one of the progressives wins (depending on tie-breaking rules).

Approval Voting reduces the spoiler effect because voters are not forced to choose only one acceptable option.

---

## Section 4: Strategic Approval Thresholds

Approval Voting introduces a new decision for voters:

> Where should I draw the line between "approve" and "do not approve"?

This is sometimes called an **approval threshold**.

Consider three candidates:

- Left 🔴
- Center 🟡
- Right 🔵

A voter who prefers Left most but finds Center acceptable must decide:

- Approve only Left?
- Approve Left and Center?

If they approve both, they increase Center's total -- possibly helping Center defeat Left.

If they approve only Left, they risk helping Right win.

Approval Voting reduces vote splitting -- but it introduces strategic judgment about how much compromise to signal.

### Honesty and Strategy

In Part I, we defined strategic voting as casting a ballot that does not reflect genuine preferences in order to achieve a better outcome. Under plurality, strategy takes the form of abandoning a preferred candidate to consolidate support behind a viable one.

Approval Voting changes the shape of the strategic question. The decision is no longer "should I abandon my favorite?" but "should I extend support beyond my favorite?"

This distinction matters.

Under Approval Voting, a voter can always approve their genuine first choice. The strategic question is whether to also approve others. Approving your favorite is never a wasted vote -- a structural improvement over plurality, where supporting a non-viable candidate can directly help elect the candidate you like least.

Some systems are more **strategy-resistant** than others, meaning that honest expression is more frequently the optimal strategy. No system with three or more candidates is perfectly strategy-proof -- this is a proven mathematical result, much like Arrow's theorem. But "no system is perfectly strategy-proof" is very different from "all systems are equally strategic." Systems differ meaningfully in how much they reward deviation from honest expression.

This dimension -- how much a system incentivizes honest voting -- will continue to surface as we examine Score Voting and STAR Voting in later articles.

---

## Section 5: Relationship to Majority Support

Approval Voting does not guarantee a majority winner.

A candidate can win with the highest number of approvals even if most voters preferred someone else as their top choice.

However, it often selects candidates with broad support because:

- Candidates benefit from being widely acceptable.
- Campaigns may seek second-tier approval.

Unlike Ranked Choice Voting:

- There is no elimination order.
- There are no transfers.
- There is no ballot exhaustion.

Every ballot counts equally in the final tally.

But voters must decide how much information to reveal.

---

## Section 6: Tradeoffs

Approval Voting attempts to solve:

- Vote splitting
- The need for separate runoff elections
- The complexity of ranked ballots

It does so by:

- Allowing support for multiple candidates
- Counting approvals in a single round

But it introduces tradeoffs:

- Voters must choose an approval threshold.
- Strong compromise signaling may disadvantage a voter's favorite.
- It does not guarantee majority winners.
- It does not measure intensity of preference -- only acceptability.

Approval Voting is mechanically simple.

Its complexity lies in voter strategy.

---

## Comparison to Ranked Choice Voting

| Feature | Ranked Choice Voting | Approval Voting |
|---|---|---|
| Ballot type | Ranking | Multiple approvals |
| Eliminations | Yes | No |
| Transfers | Yes | No |
| Ballot exhaustion | Possible | No |
| Majority of active ballots | Yes | Not guaranteed |
| Strategy focus | Ranking order | Approval threshold |

RCV structures choice through elimination order.

Approval structures choice through simultaneous acceptability.

Each reduces vote splitting in different ways.

Each introduces distinct strategic considerations.

---

## Conclusion

Approval Voting changes how voters express preference.

Instead of ranking candidates, voters indicate which candidates they find acceptable.

This can reduce vote splitting and reward broadly acceptable candidates.

At the same time, it shifts strategic decisions to the voter:

- How many candidates should I approve?
- Should I approve a compromise?

Approval Voting simplifies counting -- but it does not eliminate tradeoffs.

The next question is:

If we allow voters to express not just acceptability, but degrees of support -- what changes?

In the next article, we will examine **Score Voting**, which adds a rating scale to the ballot and introduces a new set of structural considerations.
