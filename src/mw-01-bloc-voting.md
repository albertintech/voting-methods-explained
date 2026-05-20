# Bloc Voting

## The Multi-Winner Baseline

---

## Statement of Purpose

Bloc voting is the most common multi-winner election format in American government. It is also the simplest: take the counting rule of single-winner plurality -- most votes wins -- and apply it to fill multiple seats.

This article examines how bloc voting works, where it is used, and what structural consequences follow from extending plurality logic to multi-winner elections. The Introduction established the sweep effect as a general concept. This article demonstrates how that effect operates mechanically in bloc voting, documents its real-world consequences, and identifies what bloc voting optimizes for and what it does not guarantee.

Bloc voting is not a reform proposal. It is the existing baseline from which reforms depart. Understanding its structure is essential before examining the modifications that follow.

---

## Currently Used

Bloc voting operates at every level of American government.

At the state level, several legislative chambers currently use multi-member districts with bloc voting. Arizona's House of Representatives elects two representatives at large from each of 30 legislative districts. Maryland's House of Delegates elects up to three delegates from multi-member districts, with 41 of 71 districts being multi-member. New Hampshire's House of Representatives uses multi-member districts electing up to 10 representatives, with over half of its 203 districts being multi-member. New Jersey's General Assembly elects two members at large from each of 40 Senate districts. North Dakota, South Dakota, Vermont, and other states also use multi-member bloc-voting districts.

At the local level, thousands of jurisdictions use at-large elections for city councils, school boards, and county commissions. At-large bloc voting has been the subject of extensive Voting Rights Act Section 2 litigation, a history examined later in this article.

---

## Section 1: How Bloc Voting Works

Bloc voting -- also called **plurality-at-large** -- is the most direct extension of plurality voting to multi-seat elections. If plurality voting lets each voter choose one candidate for one seat, bloc voting lets each voter choose as many candidates as there are seats.

In a bloc voting election with K seats:

1. Each voter may vote for up to K candidates. Each vote goes to a different candidate -- no voter can give two votes to the same person.
2. All votes are tallied. Each candidate's total is the number of voters who selected them.
3. The K candidates with the highest vote totals are elected.

There is no transfer of votes, no elimination rounds, and no reweighting. The counting rule is identical to single-winner plurality -- most votes wins -- applied K times.

### What the Ballot Looks Like

A bloc voting ballot resembles a familiar plurality ballot, except the instructions say "vote for up to" a number greater than one. In a three-seat election, the voter sees a list of candidates and may mark up to three. In a five-seat election, up to five. Each mark goes to a different candidate. Casting fewer than K votes is permitted -- a voter who supports only two candidates in a three-seat race may vote for two and leave the third blank.

The simplicity is real. Any voter who has cast a plurality ballot already understands how to cast a bloc voting ballot.

---

## Section 2: A Worked Example

Consider a city council election with three seats and 100 voters. Six candidates are running. The electorate is divided into two groups:

- **Group A** (60 voters) supports candidates Adams, Allen, and Ayers.
- **Group B** (40 voters) supports candidates Brooks, Bailey, and Burns.

Under bloc voting, each voter may vote for up to three candidates. If both groups vote as blocs -- each voter selecting their group's full slate -- the results are:

| Candidate | Votes | Group |
|---|---|---|
| Adams | 60 | A |
| Allen | 60 | A |
| Ayers | 60 | A |
| Brooks | 40 | B |
| Bailey | 40 | B |
| Burns | 40 | B |

The three highest vote-getters are Adams, Allen, and Ayers. Group A wins all three seats. Group B, despite constituting 40 percent of the electorate, wins nothing.

### Why This Happens

The outcome follows directly from the counting rule. Each Group A candidate receives a vote from every Group A voter. Each Group B candidate receives a vote from every Group B voter. Because Group A has more voters than Group B, every Group A candidate finishes ahead of every Group B candidate.

The Introduction demonstrated this pattern with a generic five-seat council. Here the same structure produces the same result: a cohesive majority wins every available seat. The sweep effect is not a property of any particular candidate configuration or any particular number of seats. It follows from the combination of bloc voting and a majority that votes as a bloc.

### What If Voters Cross Lines?

The example above assumes perfect bloc voting -- every voter in each group selects exactly that group's slate. In practice, some voters may support candidates from both groups. If 10 of Group A's voters vote for Brooks instead of Ayers, the result changes:

| Candidate | Votes | Group |
|---|---|---|
| Adams | 60 | A |
| Allen | 60 | A |
| Brooks | 50 | B |
| Ayers | 50 | A |
| Bailey | 40 | B |
| Burns | 40 | B |

The top three are Adams (60), Allen (60), and Brooks or Ayers (50 each, requiring a tiebreaker or further calculation). Crossover voting can break the sweep -- but only when the majority is not fully cohesive. The sweep effect is a structural possibility whenever a cohesive majority exists. Whether the majority actually is cohesive is an empirical question that varies by election.

---

## Section 3: The Sweep Effect in Practice

The sweep effect is not a theoretical curiosity. Its consequences have been documented extensively in American elections, particularly in the context of racial bloc voting.

### The Voting Rights Act and At-Large Elections

When a jurisdiction holds at-large elections and the electorate votes along racial or ethnic lines -- a pattern called **racial bloc voting** -- the sweep effect can systematically prevent minority communities from electing any representatives, even when those communities constitute a substantial share of the population.

This pattern gave rise to decades of Voting Rights Act litigation. The Supreme Court's 1986 decision in *Thornburg v. Gingles* established the legal framework for challenging at-large systems that dilute minority voting strength. Under *Gingles*, a plaintiff challenging an at-large system must demonstrate three preconditions: that the minority group is sufficiently large and geographically compact to constitute a majority in a single-member district, that the minority group is politically cohesive, and that the white majority votes sufficiently as a bloc to defeat the minority's preferred candidates.

The third precondition -- majority bloc voting -- is the structural mechanism this article has been examining. When a racial majority votes as a bloc in an at-large election, the sweep effect ensures that the majority's preferred candidates win every seat. The minority is shut out not because its candidates lack support, but because the counting rule treats each seat independently, and the majority outnumbers the minority for every one of them.

### Remedies and Departures

Numerous jurisdictions have been ordered to adopt alternative election methods as a result of VRA challenges. The most common remedy has been a shift from at-large elections to single-member districts, which allows geographically concentrated minorities to elect representatives from their own districts. Other remedies have included limited voting, cumulative voting, and the Single Non-Transferable Vote -- the methods examined in the articles that follow.

These alternatives do not eliminate the structural tension between majority and minority representation. They change the terms on which that tension plays out. Each method creates different degrees of space for minority representation, through different mechanisms, with different strategic demands.

---

## Section 4: Structural Properties

Bloc voting has clear structural properties. Identifying them precisely is what allows meaningful comparison with the methods that follow.

### What Bloc Voting Optimizes For

Bloc voting selects the candidates who receive the most individual votes. When the electorate votes in blocs, this means the majority's preferred slate wins every seat. The system optimizes for **majority preference**: the candidates supported by the largest group of voters fill the available seats.

This is the same property that single-winner plurality optimizes for -- largest faction wins -- extended to multiple seats. In a two-faction electorate, the result is decisive: the majority controls all seats.

### What Bloc Voting Does Not Guarantee

Bloc voting does not guarantee proportional representation. A group constituting 40 percent of the electorate may win zero seats. A group constituting 20 percent may win zero seats. The counting rule contains no mechanism to allocate seats in proportion to voter support.

Bloc voting also does not guarantee that winners have broad support beyond their own faction. A candidate who is intensely supported by the majority and actively opposed by the minority can win, because the counting rule tallies individual votes without considering how voters evaluate candidates they did not select.

### Candidate Incentives

While we cannot attribute all candidate and campaign behavior to the voting system, we can identify the structural incentives it puts in place.

Under bloc voting, the path to winning is clear: secure a position on the majority's slate. A candidate who is included on the slate that 60 percent of voters will select is virtually guaranteed a seat. A candidate excluded from that slate faces a structural ceiling set by the minority's size.

This creates incentives to align with the dominant faction rather than to build cross-factional coalitions. A candidate who appeals to voters in both groups may draw votes from each, but if neither group includes that candidate on its full slate, the cross-factional appeal may not translate into a seat. Bloc voting rewards factional loyalty over bridge-building -- a structural consequence of the counting rule, not a moral failing of voters or candidates.

### Administrative Properties

Bloc voting shares the administrative strengths of single-winner plurality:

- Simple ballot design (mark up to K names)
- Single-round counting (no eliminations, no transfers)
- Easy to audit (each candidate's total is a straightforward sum)
- Fast results (no sequential rounds to process)

These properties are not trivial. Simplicity, transparency, and speed are genuine virtues in election administration. The structural limitations of bloc voting exist alongside real administrative advantages.

---

## Conclusion

Bloc voting is the most widely used multi-winner election method in American government, and it is the simplest to understand: the candidates with the most votes win.

That simplicity comes with a structural consequence. When a cohesive majority votes as a bloc, it captures every available seat -- the sweep effect demonstrated in the Introduction and examined in detail here. Whether this outcome is appropriate depends on the election's goal. In contexts where majoritarian selection serves the purpose, bloc voting delivers it efficiently. In contexts where the goal is proportional representation, bloc voting cannot deliver it at all.

The real-world consequences of the sweep effect are not theoretical. Decades of Voting Rights Act litigation have documented the pattern: at-large bloc voting in racially polarized communities systematically prevents minority groups from electing representatives, even when those groups constitute a substantial share of the population.

The methods examined in the remaining articles of this Part each modify bloc voting's structure in a different way. The first modification is the simplest: keep the counting rule identical, but give voters fewer votes than there are seats.

This is limited voting.
