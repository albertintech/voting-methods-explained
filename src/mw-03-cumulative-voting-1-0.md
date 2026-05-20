# Cumulative Voting

## Concentration as a Tool

---

## Statement of Purpose

The previous article examined limited voting, which softens the sweep effect by giving voters fewer votes than there are seats. Limited voting creates structural space for minority representation, but whether minorities achieve that representation depends on strategic coordination. The system is semi-proportional: proportional outcomes are possible but not guaranteed.

Cumulative voting modifies the ballot constraint in a different direction. Instead of reducing the number of votes, it changes how votes can be distributed. Each voter receives as many votes as there are seats -- just like bloc voting -- but may give multiple votes to the same candidate. A voter can spread votes evenly, concentrate them on a few candidates, or give all of them to a single candidate.

This flexibility introduces a mathematical property that limited voting does not have: under ideal coordination, a cohesive group can **guarantee** itself a proportional share of seats. The guarantee is conditional -- it requires that the group's voters coordinate perfectly -- but it is a guarantee nonetheless. This is what distinguishes cumulative voting from the methods examined so far.

---

## Currently Used

More than 50 communities in the United States use cumulative voting for local elections, with almost all adoptions resulting from Voting Rights Act litigation. Port Chester, New York uses cumulative voting for Board of Trustees elections following a 2009 federal court order; voters subsequently approved keeping the system permanently. Peoria, Illinois has used cumulative voting for five at-large City Council seats since 1991, after settlement of a 1987 VRA challenge.

Cumulative voting also has a significant presence in corporate governance: seven U.S. state constitutions mandate cumulative voting for corporate board elections, and hundreds of corporations use it.

The most prominent historical use was the Illinois House of Representatives, which elected members by cumulative voting from three-member districts for 110 years, from 1870 to 1980. That system allowed minority party representation in both strongly Democratic and strongly Republican areas of the state.

---

## Section 1: How Cumulative Voting Works

In a cumulative voting election with K seats:

1. Each voter receives K votes (equal to the number of seats).
2. Voters may distribute these votes among candidates in any combination -- including giving multiple votes to the same candidate.
3. All votes are tallied.
4. The K candidates with the highest vote totals are elected.

The counting rule is identical to bloc voting and limited voting: highest vote totals win. The ballot constraint is what changes. Under bloc voting, each vote must go to a different candidate. Under cumulative voting, a voter can concentrate.

The act of giving all of one's votes to a single candidate is called **plumping**. Plumping is the strongest expression of preference intensity available under cumulative voting. A voter who plumps is choosing to maximize support for one candidate at the cost of having no influence over the other seats.

---

## Section 2: A Worked Example

Return to the city council election: three seats, 100 voters, and the same two groups. Group A (60 voters) supports Adams, Allen, and Ayers. Group B (40 voters) supports Brooks, Bailey, and Burns.

Each voter now has three votes to distribute.

### Scenario A: Group B Plumps, Group A Spreads

Group B's 40 voters each give all three votes to Brooks. Group A's 60 voters spread their votes evenly across Adams, Allen, and Ayers.

| Candidate | Vote-Points |
|---|---|
| Brooks | 120 |
| Adams | 60 |
| Allen | 60 |
| Ayers | 60 |
| Bailey | 0 |
| Burns | 0 |

The top three are Brooks (120), Adams (60), and Allen (60). Group B wins one seat with a substantial margin to spare.

Notice the column label: **vote-points**, not votes. Under cumulative voting, the tallied quantities are not individual votes (one per voter per candidate) but accumulated points that reflect how voters chose to distribute their ballots. This distinction matters when comparing across methods.

### Scenario B: Group B Tries for Two Seats

Group B splits its votes between two candidates: each of the 40 voters gives two votes to Brooks and one to Bailey.

| Candidate | Vote-Points |
|---|---|
| Brooks | 80 |
| Adams | 60 |
| Allen | 60 |
| Ayers | 60 |
| Bailey | 40 |
| Burns | 0 |

The top three are Brooks (80), Adams (60), and Allen (60) -- or Ayers, in a three-way tie for the remaining seats. Group B still wins only one seat. Bailey's 40 vote-points are not enough to displace any of Group A's candidates.

To win two seats, Group B would need to split its 120 vote-points more evenly between two candidates -- 60 each. But Group A's candidates also receive 60 each. The result would be a five-way tie for three seats. Group B cannot guarantee two seats out of three with 40 percent of the electorate. It can guarantee one.

### What the Numbers Show

In Scenario A, Group B controlled 120 out of 300 total vote-points (40 percent). By concentrating all 120 on one candidate, Group B guaranteed that Brooks would finish ahead of any Group A candidate -- because Group A, even with 180 vote-points, had to spread them across at least two candidates to win two seats.

In Scenario B, Group B tried to win more than its proportional share and fell short. The arithmetic enforces a ceiling: a group can guarantee a proportional share of seats, but not more.

---

## Section 3: The Self-Help Guarantee

Cumulative voting has a mathematical property that distinguishes it from both bloc voting and limited voting: under ideal coordination, a cohesive group can guarantee itself a proportional share of seats.

### How the Arithmetic Works

In a K-seat election with V voters, the total pool of vote-points is V x K. A group constituting a fraction p of the electorate controls p x V x K vote-points.

If the group concentrates all of its vote-points on a number of candidates equal to its proportional share of seats (rounded down), each of those candidates will receive more vote-points than any candidate the opposing group can field -- provided the opposing group is also trying to win its proportional share.

In the running example: Group B has 40 percent of voters and controls 40 percent of the 300 total vote-points (120 points). The proportional share of three seats, rounded down, is one seat (floor of 0.40 x 3 = 1). By concentrating all 120 points on one candidate, Group B guarantees that candidate finishes above any of Group A's candidates (who split 180 points across at most three candidates, yielding 60 each).

### The Condition

The guarantee is conditional. It requires that the group's voters coordinate perfectly -- everyone must plump on the same candidate. If they split across two candidates, the guarantee weakens. If they split across three, it disappears entirely. A group that cannot coordinate its voters cannot use the self-help mechanism, no matter how large its share of the electorate.

This is the fundamental tension of cumulative voting. The mathematics guarantee proportional representation to any group that can coordinate. But coordination is a real-world problem, not a mathematical given. It requires communication, trust, and organizational infrastructure. Groups that lack these resources may be unable to use the tools the system provides.

### Why "Self-Help"

Cumulative voting is sometimes described as a **self-help** mechanism for minority representation. The term captures both the opportunity and the burden: the system gives minorities the mathematical tools to achieve proportional representation, but places the responsibility for using those tools on the minority group itself.

Under bloc voting, the majority controls the outcome regardless of minority strategy. Under limited voting, the minority has an opening but no guarantee. Under cumulative voting, the minority has a guarantee -- but only if it helps itself through effective coordination. The counting rule does not ensure proportional outcomes. It enables them.

---

## Section 4: Structural Properties

### What Cumulative Voting Changes

Cumulative voting modifies one element of bloc voting: the ability to give multiple votes to the same candidate. The counting rule (top K win), the number of votes per voter (K), and the ballot format (mark individual candidates) are otherwise unchanged.

This modification:

- Preserves the total number of votes per voter (unlike limited voting, which reduces them)
- Allows vote concentration as a strategic tool
- Creates a mathematical guarantee of proportional representation -- conditional on coordination
- Shifts the burden of achieving proportionality from the counting rule to the voters

### What Cumulative Voting Shares with the Previous Methods

Like bloc voting and limited voting, cumulative voting does not contain any mechanism that adjusts seat allocation to reflect voter support. There is no quota, no reweighting, and no transfer. The counting rule is the same: highest totals win. If a minority group fails to coordinate, it can still be shut out entirely.

Cumulative voting is semi-proportional: proportional outcomes are achievable but contingent on strategic behavior. What distinguishes it from limited voting is the strength of the guarantee available to groups that do coordinate.

### Candidate Incentives

While we cannot attribute all candidate and campaign behavior to the voting system, we can identify the structural incentives it puts in place.

Under cumulative voting, the strategic complexity for candidates is higher than under bloc voting or limited voting. A candidate who is the sole nominee of a cohesive minority group is well-positioned -- the group can plump on that candidate and guarantee a seat. A candidate who is one of several nominees from the same group faces a different problem: the group must split its vote-points, and each candidate's position depends on how the split is managed.

This creates incentives for intra-group negotiation. Groups benefit from limiting the number of candidates they support and concentrating behind a shared slate. A minority group that runs two candidates when it can only guarantee one seat risks electing neither. The pressure to coordinate before election day -- deciding who runs and who stands aside -- is a direct consequence of the system's structure.

### Administrative Properties

Cumulative voting is slightly more complex to administer than bloc voting or limited voting. The ballot must accommodate multiple votes per candidate (either through fractional allocation or explicit multi-vote marking). Tallying requires summing vote-points rather than counting individual marks. But the process is still a single-round count with no eliminations, no transfers, and no reweighting -- well within the capacity of standard election administration.

---

## Conclusion

Cumulative voting demonstrates that changing how votes can be distributed -- without changing the counting rule -- introduces a meaningful new property: a mathematical guarantee of proportional representation for any group that can coordinate effectively.

This guarantee distinguishes cumulative voting from both bloc voting and limited voting. Under bloc voting, the majority controls the outcome structurally. Under limited voting, the minority has an opening but no guarantee. Under cumulative voting, the minority has a guarantee -- conditional on coordination.

The condition matters. A group that cannot coordinate its voters cannot use the self-help mechanism. The system provides the tools; the group must provide the organization.

The methods examined so far have modified the ballot in different ways: how many votes the voter receives (limited voting) and whether those votes can be concentrated (cumulative voting). The next article takes the simplification to its logical conclusion. What happens when each voter receives exactly one vote -- the same ballot as single-winner plurality -- but the election fills multiple seats?

This is the Single Non-Transferable Vote.
