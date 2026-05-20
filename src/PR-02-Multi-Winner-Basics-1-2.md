# Single-Winner Methods Go Multi-Seat

## Part 1 -- Bloc Voting, Limited Voting, Cumulative Voting, SNTV, and Bloc STAR

---

## Currently Used / Proposed Use

The methods examined in this article include some of the most widely used multi-winner election formats in the United States. Bloc voting is the baseline: it operates in several state legislatures and thousands of local jurisdictions. Limited voting, cumulative voting, and SNTV are used in state and local elections across multiple states, often as Voting Rights Act remedies. Bloc STAR is newer, with organizational use beginning in 2024 and a federal legislative proposal.

Specific usage is documented within each system's section below.

---

## Statement of Purpose

This article begins the multi-winner portion of the series by examining the most familiar approach to filling multiple seats: extending single-winner logic.

In the previous series, every election had one seat and one winner. The question was always:

> Who should win?

When more than one seat is available, the question changes:

> How should representation be distributed?

The simplest answer is to apply what we already know. If a voting method works for one seat, perhaps a version of it can work for three, five, or ten.

This article examines five methods that take this approach. Four of them use a simple ballot -- no rankings, no scores, no party lists -- and a familiar counting rule: the candidates with the most votes win. What changes is how many votes each voter receives and whether those votes can be concentrated. The fifth, Bloc STAR, applies the more expressive score ballot from the previous series and repeats the single-winner STAR procedure for each seat, producing consensus-oriented majoritarian outcomes.

These five methods form a spectrum. At one end, bloc voting gives a cohesive majority full control of every seat. At the other end, the Single Non-Transferable Vote creates structural space for minority representation -- but only if parties and voters coordinate effectively. In between, limited voting and cumulative voting offer intermediate positions. Bloc STAR produces qualitatively different majoritarian winners than simple bloc methods, but like all the methods examined here, it does not contain a mechanism to produce proportional outcomes.

The progression across these methods reveals a foundational insight: applying single-winner logic to multi-winner elections does not automatically produce representative outcomes. Whether the sweep effect that results is a problem depends on what the election is trying to accomplish -- a question this article will return to after examining the mechanics.

---

## Section 1: From One Seat to Many

In the previous series, every election filled a single seat. Whether the method used was plurality, ranked choice, approval, score, or STAR, the structural problem was the same: given a group of candidates, select one winner.

Multi-winner elections change the structural problem. A city council election might fill five seats simultaneously. A school board election might fill three. A state legislative district might elect two representatives. In each case, the output is not a single winner but a group of winners.

The Introduction established that the number of seats in an election -- the district magnitude -- shapes representation more powerfully than almost any other feature of an electoral system. This article begins with the simplest possible approach: take the ballot structure and counting logic of familiar single-winner methods and extend them to fill multiple seats.

---

## Section 2: Bloc Voting (Plurality-at-Large)

Bloc voting -- also called plurality-at-large -- is the most direct extension of plurality voting to multi-seat elections. If plurality voting lets each voter choose one candidate for one seat, bloc voting lets each voter choose as many candidates as there are seats.

### Currently Used

Bloc voting is the most common multi-winner election format in American government. It operates at two levels.

At the state level, several legislative chambers currently use multi-member districts with bloc voting. Arizona's House of Representatives elects two representatives at large from each of 30 legislative districts. Maryland's House of Delegates elects up to three delegates from multi-member districts, with 41 of 71 districts being multi-member. New Hampshire's House of Representatives uses multi-member districts electing up to 10 representatives, with over half of its 203 districts being multi-member. New Jersey's General Assembly elects two members at large from each of 40 Senate districts. North Dakota, South Dakota, Vermont, and other states also use multi-member bloc-voting districts.

At the local level, thousands of jurisdictions use at-large elections for city councils, school boards, and county commissions. At-large bloc voting has been the subject of extensive Voting Rights Act Section 2 litigation. The Supreme Court's 1986 decision in *Thornburg v. Gingles* established the framework for challenging at-large systems that dilute minority voting strength through racial bloc voting. Numerous jurisdictions have been ordered to adopt alternative methods as a result.

Bloc voting is not a reform proposal. It is the existing baseline from which reforms depart.

### How It Works

In a bloc voting election with K seats:

1. Each voter may vote for up to K candidates. Each vote goes to a different candidate -- no voter can give two votes to the same person.
2. All votes are tallied. Each candidate's total is the number of voters who selected them.
3. The K candidates with the highest vote totals are elected.

There is no transfer of votes, no elimination rounds, and no reweighting. The counting rule is identical to single-winner plurality -- most votes wins -- applied K times.

### A Worked Example

Consider a city council election with three seats and 100 voters. Six candidates are running. The electorate is divided into two groups:

- **Group A** (60 voters) supports candidates Adams, Allen, and Ayers.
- **Group B** (40 voters) supports candidates Brooks, Bailey, and Burns.

Under bloc voting, each voter may vote for up to three candidates. If both groups vote as blocs -- each voter selecting their group's full slate -- the results are:

| Candidate | Votes |
|---|---|
| Adams | 60 |
| Allen | 60 |
| Ayers | 60 |
| Brooks | 40 |
| Bailey | 40 |
| Burns | 40 |

The three highest vote-getters are Adams, Allen, and Ayers. Group A wins all three seats.

Group A constitutes 60% of the electorate but captures 100% of the seats. Group B, despite constituting 40% of the electorate, wins nothing.

### The Sweep Effect

This outcome is not an accident of this particular example. It is a structural feature of bloc voting. Whenever a cohesive majority votes as a bloc -- selecting the same slate of candidates -- it can capture every available seat, regardless of how large the minority is.

This phenomenon is called the **sweep effect**: a coordinated majority sweeps all seats, shutting out the minority entirely. The sweep effect occurs because bloc voting treats each seat independently. A group that has more supporters than any opposing group will have more supporters for every one of its candidates, not just one of them.

The sweep effect is well-documented in practice. At-large bloc voting in racially polarized communities has been shown to prevent geographically concentrated minorities from electing any representatives -- even when those minorities constitute a substantial share of the population. This pattern gave rise to decades of Voting Rights Act litigation and the adoption of alternative methods in affected jurisdictions.

It is worth stating clearly what the sweep effect is not: it is not a malfunction. Bloc voting was designed to reflect majority preferences, and it does so -- decisively. The sweep effect is a structural consequence of applying majoritarian logic to multi-winner elections. Whether that consequence is acceptable depends on what the election is designed to accomplish. This article will return to that question after examining the full range of methods.

---

## Section 3: Limited Voting

Limited voting is a direct modification of bloc voting. The counting rule is identical -- the K candidates with the most votes win -- but voters receive fewer votes than there are seats.

### Currently Used

Limited voting has deep roots in American elections. Pennsylvania county commissioners have been elected under a limited voting system since an 1871 constitutional amendment, with voters casting two votes for three seats -- one of the oldest continuous uses in the United States. Philadelphia's City Council uses limited voting at significant urban scale: voters may vote for five candidates to fill seven at-large seats, a structure established under the 1951 Home Rule Charter.

Connecticut state laws enacted in 1949 and 1959 created limited voting systems for most local boards and commissions. As of 2021, at least 42 boards and town councils in Connecticut use limited voting.

Limited voting has also been adopted in more than 20 municipalities across Alabama and North Carolina as Voting Rights Act remedies.

### How It Works

In a limited voting election with K seats:

1. Each voter may vote for up to L candidates, where L is less than K. Each vote goes to a different candidate.
2. All votes are tallied.
3. The K candidates with the highest vote totals are elected.

The only structural difference from bloc voting is the ballot constraint: voters have fewer votes than seats. This single change has significant consequences.

### The Same Example Under Limited Voting

Return to the city council election: three seats, 100 voters, and the same two groups. Under limited voting with one vote per voter (L = 1, K = 3):

**Scenario A: Group B concentrates, Group A spreads.**

Group B directs all 40 votes to Brooks. Group A splits its 60 votes evenly across its three candidates.

| Candidate | Votes |
|---|---|
| Brooks | 40 |
| Adams | 20 |
| Allen | 20 |
| Ayers | 20 |
| Bailey | 0 |
| Burns | 0 |

The top three are Brooks, Adams, and Allen. Group A wins two seats; Group B wins one. The 40% minority has achieved representation.

**Scenario B: Group A also concentrates.**

If Group A recognizes the risk and concentrates its 60 votes on just two candidates:

| Candidate | Votes |
|---|---|
| Adams | 30 |
| Allen | 30 |
| Brooks | 40 |
| Ayers | 0 |
| Bailey | 0 |
| Burns | 0 |

The top three are Brooks (40), Adams (30), and Allen (30). The result is the same: Group A wins two seats, Group B wins one. Even when Group A adapts its strategy, Group B's concentration guarantees it a seat.

**Scenario C: Coordination failure.**

If Group B splits its votes between two candidates, things change:

| Candidate | Votes |
|---|---|
| Adams | 30 |
| Allen | 30 |
| Brooks | 20 |
| Bailey | 20 |
| Ayers | 0 |
| Burns | 0 |

Now the top three are Adams (30), Allen (30), and either Brooks or Bailey (20, requiring a tiebreaker). Group B still wins one seat, but the margin is thinner. If Group B had split its votes three ways -- Brooks 14, Bailey 13, Burns 13 -- Group A could have swept all three seats by concentrating on three candidates at 20 votes each.

### Vote Management

These scenarios illustrate the central strategic challenge of limited voting: **vote management**. Both groups must decide how many candidates to support and how to distribute votes among them. Run too many candidates and the group's support is diluted. Run too few and votes are wasted as surplus on safe candidates.

Vote management is not a voter-level decision alone. It requires coordination -- between parties and voters, or among voters who share political interests. The effectiveness of limited voting as a tool for minority representation depends heavily on whether minority groups can coordinate their voting behavior.

This strategic dependency is what makes limited voting **semi-proportional**: it creates structural space for minority representation, but does not guarantee it. Proportionality is achievable but contingent on strategic behavior.

---

## Section 4: Cumulative Voting

Cumulative voting modifies the ballot constraint in a different direction. Instead of reducing the number of votes, it changes how votes can be distributed.

### Currently Used

More than 50 communities in the United States use cumulative voting for local elections, with almost all adoptions resulting from Voting Rights Act litigation. Port Chester, New York uses cumulative voting for Board of Trustees elections following a 2009 federal court order; voters subsequently approved keeping the system permanently. Peoria, Illinois has used cumulative voting for five at-large City Council seats since 1991, after settlement of a 1987 VRA challenge.

Cumulative voting also has a significant presence in corporate governance: seven U.S. state constitutions mandate cumulative voting for corporate board elections, and hundreds of corporations use it.

The most prominent historical use was the Illinois House of Representatives, which elected members by cumulative voting from three-member districts for 110 years, from 1870 to 1980. That system allowed minority party representation in both strongly Democratic and strongly Republican areas of the state.

### How It Works

In a cumulative voting election with K seats:

1. Each voter receives K votes (equal to the number of seats).
2. Voters may distribute these votes among candidates in any combination -- including giving multiple votes to the same candidate.
3. All votes are tallied.
4. The K candidates with the highest vote totals are elected.

The key difference from bloc voting is the ability to **cumulate**: a voter can concentrate all K votes on a single candidate, spread them evenly, or choose any combination.

### The Same Example Under Cumulative Voting

Return to the three-seat, 100-voter example. Each voter now has three votes to distribute.

**Scenario A: Group B plumps, Group A spreads.**

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

**Scenario B: Group B tries for two seats.**

Group B splits its votes between two candidates: 40 voters give two votes to Brooks and one to Bailey.

| Candidate | Vote-Points |
|---|---|
| Adams | 60 |
| Allen | 60 |
| Brooks | 80 |
| Ayers | 60 |
| Bailey | 40 |
| Burns | 0 |

The top three are Brooks (80), Adams (60), and Allen (60) -- or Ayers, in a three-way tie for the last two seats. Group B still wins only one seat. To win two, Group B would need to split its votes more aggressively, but doing so risks falling below Group A's candidates.

### The Self-Help Guarantee

Cumulative voting has a mathematical property that distinguishes it from limited voting: under ideal coordination, a cohesive group can **guarantee** itself a proportional share of seats.

The arithmetic works as follows. In a K-seat election, the total number of vote-points is (number of voters) x K. A group constituting fraction p of the electorate controls p x (voters x K) vote-points. By concentrating all of its vote-points on floor(p x K) candidates, the group can guarantee that each of those candidates receives more vote-points than any candidate that the opposing group can field -- provided the opposing group is also trying to win its proportional share.

In the example: Group B has 40% of voters and controls 40% of the 300 total vote-points (120 points). By concentrating all 120 on one candidate, Group B guarantees that candidate finishes above any of Group A's candidates (who split 180 points across at most three candidates, yielding 60 each). Since floor(0.40 x 3) = 1, Group B can guarantee one seat -- exactly its proportional share, rounded down.

This guarantee is conditional. It requires that Group B's voters coordinate perfectly -- everyone must cumulate on the same candidate. If they split across two candidates, the guarantee weakens. If they split across three, it disappears entirely.

This is why cumulative voting is sometimes described as a **self-help** mechanism: it gives minorities the tools to achieve proportional representation, but only if they use those tools effectively.

---

## Section 5: Single Non-Transferable Vote (SNTV)

The Single Non-Transferable Vote takes the simplification in the opposite direction from cumulative voting. Instead of giving voters more flexibility in how to distribute votes, SNTV gives each voter exactly one vote -- the same ballot as single-winner plurality -- but uses it to fill multiple seats.

### Currently Used

SNTV is used extensively in Connecticut, where state laws create one-vote multi-seat elections for numerous local boards and commissions. Puerto Rico uses SNTV for its territorial legislature. In Alabama, multiple small towns adopted SNTV as part of Voting Rights Act remedies under the *Dillard v. Town of Cuba* settlements. Euclid, Ohio uses a functionally identical system (one vote for three school board seats) under a 2009 court order.

SNTV is the limiting case of limited voting -- limited voting where voters have exactly one vote. The distinction between "limited voting with one vote" and "SNTV" is definitional rather than mechanical: the system works the same way.

### How It Works

In an SNTV election with K seats:

1. Each voter casts exactly one vote for one candidate.
2. All votes are tallied.
3. The K candidates with the highest vote totals are elected.

The ballot is identical to single-winner plurality. The counting rule is identical to single-winner plurality. The only difference is that K candidates win instead of one.

### The Same Example Under SNTV

Return to the three-seat, 100-voter example.

**Scenario A: Efficient coordination by both groups.**

Group A nominates two candidates and splits its 60 votes: Adams receives 30, Allen receives 30. Group B nominates one candidate: Brooks receives all 40 votes.

| Candidate | Votes |
|---|---|
| Brooks | 40 |
| Adams | 30 |
| Allen | 30 |

Three candidates, three seats. Group A wins two, Group B wins one. The outcome is roughly proportional.

**Scenario B: Group A over-nominates.**

Group A runs three candidates and splits its 60 votes evenly: Adams 20, Allen 20, Ayers 20. Group B runs one candidate: Brooks 40.

| Candidate | Votes |
|---|---|
| Brooks | 40 |
| Adams | 20 |
| Allen | 20 |
| Ayers | 20 |

Group B wins one seat; Group A wins two (with Ayers winning the third seat at 20 votes). The outcome is proportional despite the over-nomination -- but only because Group B ran the right number of candidates.

**Scenario C: Vote management failure.**

Group A runs three candidates but its votes cluster unevenly: Adams 35, Allen 20, Ayers 5. Group B runs two candidates: Brooks 25, Bailey 15.

| Candidate | Votes |
|---|---|
| Adams | 35 |
| Brooks | 25 |
| Allen | 20 |
| Bailey | 15 |
| Ayers | 5 |

Top three: Adams (35), Brooks (25), Allen (20). Group A wins two seats, Group B wins one. This outcome is proportional, but Ayers's 5 votes are effectively wasted, and Bailey's 15 are wasted too. A slight shift in how Group A's voters distributed themselves could have changed the outcome.

### Intra-Party Competition

SNTV introduces a dynamic that does not exist in the other methods examined so far: **intra-party competition**. Because each voter casts only one vote and multiple candidates from the same party are running, candidates within the same party compete directly against each other for individual votes.

This creates a structural tension. The party wants its candidates to divide the vote evenly -- perfect vote management maximizes the party's seat count. But individual candidates have an incentive to attract as many personal votes as possible, even at the expense of their co-partisans.

### SNTV and the Coordination Problem

SNTV reveals the coordination problem in its starkest form. The party must decide how many candidates to nominate -- too many splits the vote, too few wastes it. Then it must find a way to distribute its supporters roughly evenly across those candidates. Unlike cumulative voting, where voters can self-coordinate by concentrating votes, SNTV requires that different voters go to different candidates. This party-level coordination challenge is what political scientists call **vote management**.

---

## Section 6: Bloc STAR

The four methods examined so far all use simple ballots: choose one or more candidates, no further information required. Bloc STAR uses the more expressive score ballot introduced in the previous series -- voters rate each candidate on a 0-5 scale -- and applies the single-winner STAR procedure (Score Then Automatic Runoff) seat by seat.

### Currently Used / Proposed Use

**Currently Used:** The Python Software Foundation adopted Bloc STAR for its Steering Council elections in 2024, replacing Approval Voting. The community concluded that Approval Voting could not distinguish between strong support and weak acceptance, and that a method capturing preference intensity was needed to reflect the community's genuine judgments about candidate quality.

**Proposed Use:** The Federal Judicial Balance and Accountability Act (FJBAA) proposes using Bloc STAR for Senate confirmation of Supreme Court nominees from a presidential slate.

### How It Works

In a Bloc STAR election with K seats:

1. Each voter assigns a score (0-5) to each candidate.
2. For the first seat, the two candidates with the highest total scores advance to an automatic runoff. The runoff winner is determined by which of the two is scored higher on more ballots -- a head-to-head comparison using the scores already on the ballot. That candidate is elected.
3. The process repeats for subsequent seats. Elected candidates are removed, and the scoring and runoff steps are applied again among the remaining candidates.

### What Bloc STAR Is Designed to Do

STAR voting was designed to find consensus winners -- candidates who are not only highly rated but broadly acceptable. The two-phase structure serves this purpose directly.

The scoring phase captures preference intensity across the full field. A voter who strongly supports one candidate and moderately accepts another can express that distinction through their scores. This is information that simpler ballots -- choose one, choose up to K, approve or not -- cannot collect.

The automatic runoff phase provides a majority-preference check on the scoring results. The two highest-scoring candidates advance, but the winner is determined by which of the two more voters actually prefer in a head-to-head comparison. This means a candidate who accumulates a high total score from a narrow faction can lose the runoff to a candidate who draws moderate support from a broader cross-section of the electorate.

This two-phase structure is what distinguishes STAR from pure Score Voting. Under pure Score Voting, the highest total score wins outright. Under STAR, a high total score earns a finalist position, but winning requires majority preference in the head-to-head comparison. The runoff phase resists a dynamic that pure Score Voting is vulnerable to: strategic bullet voting, where voters give maximum scores to their preferred candidates and minimum scores to everyone else. A voter who bullet votes under STAR sacrifices influence over which of the two finalists wins, because they have provided no information distinguishing between them.

In a multi-winner context, Bloc STAR applies this consensus-seeking process iteratively. Each seat is filled by a candidate who survives both the scoring phase and the runoff phase. The result is a set of winners who each commanded broad support from the electorate -- not merely the candidates most intensely preferred by a numerical majority.

### Bloc STAR and the Sweep Effect

Bloc STAR shares a structural property with all the other methods examined in this article: it does not contain a mechanism to reduce a voter's influence after one of their preferred candidates has been elected. There is no reweighting, no allocation, and no removal of satisfied voters from subsequent rounds. Every voter participates at full strength in every round.

This means that a cohesive majority can still capture every seat under Bloc STAR. If a group constituting 60% of the electorate scores its candidates at 5, scores all others at 0, and votes as a unified bloc, it will dominate both the scoring rounds and the automatic runoffs for every seat. The sweep effect is structurally possible.

This is the reason Bloc STAR is examined here, alongside the other bloc methods, rather than alongside the proportional score-based systems examined later in the series. The ballot format is not what determines whether a system produces proportional outcomes. The counting logic is. Proportional score-based methods -- covered in later articles -- use reweighting or allocation mechanisms that reduce the influence of voters whose preferred candidates have already been elected. Bloc STAR does not.

### What This Distinction Means

The precise claim is not that the expressive ballot adds nothing. It is that the expressive ballot does not produce proportionality. These are different statements.

Bloc STAR's scoring phase and automatic runoff produce winners who are broadly acceptable, not merely plurality-preferred. Among the bloc methods examined in this article, that is a meaningful structural difference. Bloc voting selects the candidates with the most supporters. Bloc STAR selects the candidates who score both highly and broadly, then confirms each through a majority-preference check. The quality of the majoritarian outcome is different even though the majoritarian structure -- a cohesive majority can sweep -- is the same.

The question of when a majoritarian outcome is appropriate, and whether Bloc STAR's consensus orientation makes it the stronger choice within that category, is addressed in Section 8.

---

## Section 7: The Spectrum

The five methods examined in this article share a common foundation: they all extend single-winner logic to fill multiple seats. What distinguishes them is how many votes each voter receives, whether those votes can be concentrated, and what ballot information is collected.

This creates a spectrum:

| Method | Votes Per Voter | Can Cumulate? | Ballot Type | Proportionality |
|---|---|---|---|---|
| Bloc Voting | K (seats) | No | Choose up to K | None (majoritarian) |
| Bloc STAR | Score (0-5) all | N/A | Score all candidates | None (majoritarian) |
| Limited Voting | L (less than K) | No | Choose up to L | Semi-proportional |
| Cumulative Voting | K (seats) | Yes | Distribute K votes | Semi-proportional |
| SNTV | 1 | N/A | Choose exactly 1 | Semi-proportional |

At one end, bloc voting and Bloc STAR are majoritarian: a cohesive majority can capture every seat. Both produce the sweep effect, though Bloc STAR's consensus-seeking mechanism produces qualitatively different winners than plurality-based bloc voting.

At the other end, SNTV gives each voter exactly one vote, creating natural vote division across candidates and structural space for minority representation -- but only through strategic coordination.

Limited voting and cumulative voting occupy intermediate positions. Limited voting reduces the number of votes, softening the sweep effect. Cumulative voting preserves the number of votes but allows concentration, giving minorities a self-help mechanism.

What all five methods have in common is that **proportionality, where it occurs, depends on strategic behavior rather than institutional design**. No counting rule within these methods adjusts the outcome to reflect the distribution of voter support. If minorities achieve representation, it is because they coordinated effectively -- not because the system guaranteed it.

---

## Section 8: When Is the Sweep Effect Appropriate?

The sweep effect is a structural property shared by all bloc methods. Whether it is desirable depends on the election's goal.

### Elections Where the Sweep Effect Serves the Purpose

There are contexts in which the sweep effect is the intended outcome. A primary election that advances the top candidates to a general election may reasonably want the majority's preferred candidates to advance. A steering committee seeking members who reflect broad organizational consensus may want every seat filled by someone who commands majority support. A small community where geographic subdivision is impractical may prefer at-large elections that give every voter a say in every seat. A deliberative body selecting members from a pre-screened slate -- where the goal is to identify the most broadly acceptable candidates rather than to represent distinct factions -- may want majoritarian selection by design.

In these contexts, the sweep effect is not a structural flaw. It is the system working as intended: the electorate expresses preferences, and the candidates with the broadest support fill the available seats.

### Not All Majoritarian Outcomes Are Equal

When the sweep effect is the intended outcome, the choice of bloc method still matters. The methods examined in this article produce different kinds of majoritarian winners.

Bloc voting selects the candidates who receive the most individual votes. A candidate who is intensely supported by a majority faction wins, regardless of whether the broader electorate finds that candidate acceptable. The sweep produces winners who are majority-preferred, but not necessarily broadly preferred.

Bloc STAR selects differently. The scoring phase surfaces candidates who accumulate high total scores -- which rewards broad acceptability, not just intense factional support. The automatic runoff phase then confirms each winner through a head-to-head majority-preference check. A candidate who scores moderately across both factions can outscore a candidate who scores at the maximum from one faction and at zero from everyone else. The sweep still occurs -- the majority still fills every seat -- but the winners are consensus-oriented rather than narrowly faction-preferred.

This distinction matters in practice. The Python Software Foundation replaced Approval Voting with Bloc STAR specifically because it needed a method that could distinguish between strong support and weak acceptance among a field of qualified candidates. The Federal Judicial Balance and Accountability Act proposes Bloc STAR for Supreme Court confirmations because the goal is to select the most broadly acceptable nominees from a presidential slate -- not to allocate confirmation slots to competing factions. In both cases, the sweep effect is structurally appropriate because the election's purpose is consensus selection, not proportional representation. And in both cases, the consensus-seeking properties of STAR's two-phase process are what make Bloc STAR the stronger choice among the available bloc methods.

### Elections Where the Sweep Effect Is Problematic

There are also contexts in which the sweep effect undermines the election's purpose. When a legislative body is meant to represent a diverse electorate, a system that gives one faction all the seats and shuts out everyone else has structural consequences for representation. When a jurisdiction has geographically concentrated minority communities, bloc voting can systematically prevent those communities from electing any representatives -- even when they constitute a substantial share of the population. This is not a theoretical concern. It is the pattern documented in decades of Voting Rights Act litigation, from *Thornburg v. Gingles* through the *Dillard* settlements and beyond.

In these contexts, no bloc method -- regardless of ballot expressiveness -- is structurally adequate. The problem is not the quality of the majoritarian outcome. The problem is that a majoritarian outcome is the wrong goal for the election. True proportional representation, where the distribution of seats reflects the distribution of voter support, requires a fundamentally different counting mechanism: one that reduces the influence of voters whose preferred candidates have already been elected.

The Equal Vote Coalition, which developed both Bloc STAR and Proportional STAR, draws this same distinction explicitly: Bloc STAR is designed for elections where consensus-oriented majoritarian selection is the goal, while Proportional STAR is designed for elections where proportional representation is the goal. The ballot format is the same; the counting logic is what determines whether the system produces majoritarian or proportional outcomes.

### The Prior Question

This distinction -- between the election's goal and the system's structural properties -- is a principle that recurs throughout this series. The previous series asked how different systems process the same ballots differently. This series adds a prior question: what is this election trying to accomplish?

A system's structural properties are desirable or problematic only relative to the answer. The sweep effect is appropriate for consensus selection and problematic for proportional representation. Among bloc methods deployed where the sweep is appropriate, Bloc STAR's consensus-seeking mechanism produces qualitatively different winners than simple plurality-based bloc methods. And when proportional representation is the goal, none of the methods examined in this article -- including Bloc STAR -- can deliver it. That requires the conceptual tools built in the next two articles and the systems examined in Movement 3.

---

## Comparison Table

| Dimension | Bloc Voting | Limited Voting | Cumulative Voting | SNTV | Bloc STAR |
|---|---|---|---|---|---|
| Ballot type | Vote for up to K | Vote for up to L (L < K) | Distribute K votes freely | Vote for exactly 1 | Score all candidates 0-5 |
| Winner selection basis | Most individual votes | Most individual votes | Most vote-points | Most individual votes | Highest scores + majority-preference runoff |
| Proportionality | None | Semi-proportional | Semi-proportional | Semi-proportional | None |
| Proportionality source | N/A | Strategic coordination | Self-help (concentration) | Vote management | N/A |
| Majority sweep possible? | Yes (by design) | Reduced but possible | Reduced but possible | Reduced but possible | Yes (by design) |
| Strategic complexity (voters) | Low | Moderate | Moderate-High | Low (party strategy high) | Moderate |
| Administrative simplicity | Very high | Very high | High | Very high | Moderate |
| Intra-party competition | Low | Low-Moderate | Moderate | High | Low |

---

## Conclusion

This article examined five methods that extend single-winner logic to fill multiple seats.

We began with bloc voting, the most common multi-winner method in American elections, and observed the sweep effect -- a cohesive majority can capture all available seats, leaving a substantial minority entirely unrepresented.

We then examined three modifications that create varying degrees of space for minority representation. Limited voting reduces the number of votes per voter, making it harder for a majority to cover all seats. Cumulative voting allows vote concentration, giving minorities a mathematical guarantee of proportional representation -- conditional on effective coordination. SNTV gives each voter a single vote, creating natural vote division but introducing intense coordination demands on parties.

We concluded with Bloc STAR, which collects far more information than a simple plurality ballot and uses it to identify consensus-oriented winners through a scoring phase and automatic runoff. Bloc STAR's expressive ballot and two-phase process produce qualitatively different majoritarian outcomes than simple bloc voting -- winners who are broadly acceptable, not merely plurality-preferred. But the sweep effect remains structurally possible because Bloc STAR, like the other methods examined here, contains no mechanism to reduce a voter's influence after their preferred candidate has been elected. Proportionality requires counting logic that the ballot format alone cannot provide.

Across all five methods, one pattern held: proportionality, where it occurred, was a product of strategy, not structure. None of these methods contains a mechanism that adjusts seat allocation to match the distribution of voter support.

The systems examined in the rest of this series each attempt to build such a mechanism -- guaranteeing proportional representation through institutional design rather than relying on strategic behavior. But those systems require conceptual tools that single-winner methods did not: algorithms, quotas, surplus handling, and ballot reweighting. Before examining the proportional systems themselves, the next two articles build that toolkit.
