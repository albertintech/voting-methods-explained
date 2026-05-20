# Multi-Winner Methods

## When More Than One Candidate Wins

---

## Statement of Purpose

The previous Part examined single-winner elections. Each system answered the same question:

> Who should win?

Different ballots collected different information. Different counting rules processed that information differently. But the outcome was always the same type of object: one winner.

This Part asks a different question:

> How should representation be distributed when multiple seats are available?

That shift -- from selecting an individual to filling multiple seats -- changes what voting systems must do, what tradeoffs they face, and what vocabulary is needed to evaluate them.

This article introduces the foundational concepts that recur throughout the Part. It establishes the central question, the key structural variables, and the scope of what follows. It does not examine any voting system in detail. That is the work of the articles to come.

---

## The Single-Winner Assumption

Every system examined in the previous Part shared a structural feature so basic it was easy to overlook: there was one seat to fill.

That constraint shaped every design choice. Plurality asked who received the most first-choice votes. Ranked Choice Voting eliminated candidates sequentially until one remained. Approval and Score aggregated evaluations to identify a single most-supported candidate. Condorcet methods checked whether one candidate could defeat every other head-to-head.

Each approach made different decisions about ballot design and counting logic. But all of them compressed many preferences into one outcome.

Most elections do not work this way.

City councils, legislatures, school boards, and corporate boards typically fill multiple seats at once. When more than one candidate can win, the design problem changes. It is no longer enough to identify the strongest individual. The system must also decide how support across the electorate translates into seats -- and for whom.

---

## District Magnitude

The number of seats filled in a single election has a name: **district magnitude**.

A single-winner election has a district magnitude of one. A city council election that fills five seats at once has a district magnitude of five. A state legislative district that elects two representatives has a district magnitude of two.

District magnitude is not a procedural detail. It is a structural variable that shapes representation more powerfully than almost any other feature of an electoral system.

In a single-winner election, any group smaller than a plurality is shut out entirely. If 30 percent of voters share a preference, they may win nothing -- because 30 percent is not enough when only one candidate can win.

Increase the district magnitude to five, and that same 30 percent of voters could, under the right system, elect at least one representative. Increase it to ten, and smaller groups -- 15 percent, even 10 percent -- may gain a voice.

The relationship is roughly inverse: as district magnitude increases, the share of the vote needed to guarantee a seat decreases. This share is called the **threshold of representation** -- the minimum level of support at which a group can secure a seat if its voters coordinate effectively.

> The threshold of representation is not a legal requirement. It is a mathematical consequence of how many seats are available.

Under common formulas, the approximate threshold of representation for a given district magnitude is:

| District Magnitude | Approximate Threshold |
|---|---|
| 1 | 50% (majority needed) |
| 3 | 25% |
| 5 | 17% |
| 9 | 10% |
| 20 | ~5% |

These figures are approximations. The exact threshold depends on the voting system and the quota formula in use -- concepts that will be developed in later Parts. But the pattern holds: more seats mean lower barriers to representation.

This is why district magnitude matters. It determines who can be represented -- before a single ballot is cast.

---

## A Five-Seat Council

District magnitude creates the possibility of broader representation. But possibility is not the same as outcome.

Consider a city council with five seats and 100 voters. The electorate is divided into two groups: a 60-voter majority and a 40-voter minority. The election uses a simple rule -- each voter may vote for up to five candidates, and the five candidates with the most votes win.

Both groups vote as a **bloc** -- that is, every voter in a group selects the same set of candidates. A bloc is a group of voters who coordinate to support the same **slate**, a predetermined list of candidates running together. The majority puts forward five candidates; the minority puts forward five.

### Seat 1

| Candidate | Votes | Group |
|---|---|---|
| Majority Candidate 1 | 60 | Majority |
| Minority Candidate 1 | 40 | Minority |

The highest vote-getter is a majority candidate. Seat 1 goes to the majority.

### Seat 2

| Candidate | Votes | Group |
|---|---|---|
| Majority Candidate 2 | 60 | Majority |
| Minority Candidate 2 | 40 | Minority |

Same result. Seat 2 goes to the majority.

### Seat 3

| Candidate | Votes | Group |
|---|---|---|
| Majority Candidate 3 | 60 | Majority |
| Minority Candidate 3 | 40 | Minority |

Seat 3 goes to the majority.

Is the pattern clear?

Every majority candidate receives 60 votes. Every minority candidate receives 40. Because 60 is greater than 40, a majority candidate finishes ahead of every minority candidate -- not just for one seat, but for every seat.

### Seats 4 and 5

The remaining two seats follow the same logic. Majority Candidate 4 receives 60 votes. Majority Candidate 5 receives 60 votes. The highest-finishing minority candidate has 40. The majority wins all five seats.

### The Full Result

| Seat | Winner | Votes |
|---|---|---|
| 1 | Majority Candidate 1 | 60 |
| 2 | Majority Candidate 2 | 60 |
| 3 | Majority Candidate 3 | 60 |
| 4 | Majority Candidate 4 | 60 |
| 5 | Majority Candidate 5 | 60 |

The majority constitutes 60 percent of the electorate but captures 100 percent of the seats.

### What Just Happened

The majority won all five seats. Not because of a fluke in the numbers or a quirk of this particular example, but because of the structure of the election itself. A group that outnumbers any opposing group for one seat outnumbers them for every seat. When a cohesive majority votes as a bloc, it wins every available seat -- regardless of how large the minority is.

This outcome is known as the **sweep effect**, a term readers will encounter in voting reform discussions and academic literature. In plain terms: the majority sweeps every seat, and the minority -- despite constituting 40 percent of the electorate -- wins nothing.

The sweep effect is not a malfunction. It is a structural consequence of applying majoritarian logic to multi-winner elections. But whether that consequence is acceptable depends entirely on what the election is trying to accomplish.

### When Majoritarian Selection Fits the Goal

There are contexts in which having the majority's preferred candidates fill every seat is the intended outcome:

- A primary election advancing top candidates to a general election
- A steering committee seeking members who reflect broad organizational consensus
- A small community where geographic subdivision is impractical
- A deliberative body selecting members from a pre-screened slate, where the goal is to identify the most broadly acceptable candidates rather than to represent distinct factions

In these contexts, the sweep effect is the system working as designed. The electorate expresses preferences, and the candidates with the broadest support fill the available seats.

### When Majority Control Becomes Minority Exclusion

There are also contexts in which the same structural outcome undermines the election's purpose:

- A legislative body meant to represent a diverse electorate
- A jurisdiction with geographically concentrated minority communities whose voting strength is diluted when elections are conducted **at-large** -- that is, across the entire jurisdiction rather than within smaller districts
- Any election whose goal is proportional representation, where the distribution of seats should reflect the distribution of voter support

In these contexts, the majority's structural advantage translates into total seat control, leaving substantial minorities entirely unrepresented. This pattern is well-documented in practice. At-large elections in racially polarized communities have been the subject of decades of Voting Rights Act litigation -- not because the elections malfunctioned, but because majoritarian selection was the wrong tool for the job.

This distinction -- between an election's structural properties and its purpose -- is a principle that recurs throughout this Part.

---

## Proportionality Is Not Automatic

Once more than one seat is available, a natural question arises: should the distribution of seats reflect the distribution of voter support?

This idea -- that groups of voters should receive seats roughly in proportion to their share of the vote -- is called **proportional representation**. A faction with 40 percent of the vote would receive approximately 40 percent of the seats. A group with 10 percent would receive approximately 10 percent.

It is tempting to treat proportionality as an obvious consequence of having multiple seats. If a method works for one seat, surely extending it to five seats will let different groups win different seats?

The methods examined in this Part demonstrate that the answer is no. Applying single-winner logic to multi-winner elections does not automatically produce proportional outcomes. Some of these methods are fully majoritarian -- a cohesive majority can capture every seat. Others create varying degrees of space for minority representation, but only if minority voters and parties coordinate their behavior effectively.

This is the foundational insight that motivates the structure of this series. Multi-winner elections and proportional representation are often conflated, but they are not the same thing. A multi-winner election can be fully majoritarian. Proportionality is a design choice -- one that requires specific counting mechanisms that the methods in this Part do not contain. Understanding what these methods can and cannot do is what prepares the reader for the proportional systems examined in the next Part.

---

## Candidate-Centered Scope

The multi-winner design space is vast. Globally, the most common multi-winner systems are party-centered: voters choose parties, and seats are allocated to parties based on vote shares. Party-list proportional representation, Mixed-Member Proportional systems, and Mixed-Member Majoritarian systems collectively govern elections in more countries than any other family.

These systems are outside the scope of this series.

American ballots are constructed around individual candidates, not parties. Voters mark specific people by name. Party affiliation may appear on the ballot as a label -- and for many voters, that label functions as a heuristic that guides candidate selection -- but the unit of choice on the ballot is still the individual candidate. This is structurally different from a party-list system, where the voter selects a party and the party determines which individuals fill the seats.

The systems examined in this series are candidate-centered: voters evaluate individual candidates directly. This reflects the American electoral context. The methods covered here are either currently used in the United States, have been proposed through American legislation, or represent active areas of American reform discussion. Party-list systems may be covered in a separate series.

---

## How This Part Is Organized

This Part examines five methods that extend single-winner logic to fill multiple seats.

The first four use simple ballots -- no rankings, no scores, no party lists -- and a familiar counting rule: the candidates with the most votes win. What changes is how many votes each voter receives and whether those votes can be concentrated.

**Bloc Voting** is the starting point and the baseline. It is the most common multi-winner election format in American government. Each voter receives as many votes as there are seats, and the top vote-getters win. Bloc voting demonstrates the sweep effect in its starkest form: a cohesive majority captures every seat.

**Limited Voting** is a direct modification. The counting rule is identical to bloc voting, but voters receive fewer votes than there are seats. This single change softens the sweep effect, creating structural space for minority representation -- though only through strategic coordination.

**Cumulative Voting** preserves the number of votes but allows concentration. A voter may give all their votes to a single candidate. This creates a mathematical guarantee of proportional representation for any group that can coordinate effectively -- a self-help mechanism.

**Single Non-Transferable Vote (SNTV)** gives each voter exactly one vote -- the same ballot as single-winner plurality -- but uses it to fill multiple seats. SNTV creates natural vote division across candidates and structural space for minority representation, but introduces intense coordination demands on parties and voters.

The fifth method uses a more expressive ballot. **Multi-Seat STAR** applies the score ballot from the previous Part and repeats the single-winner STAR procedure (Score Then Automatic Runoff) for each seat. The sweep effect remains structurally possible, but the winners are consensus-oriented rather than merely plurality-preferred.

These five methods form a spectrum. At one end, bloc voting gives a cohesive majority full control of every seat. At the other, SNTV creates conditions under which minority representation can emerge -- but only through effective coordination. Across all five, one pattern holds: proportionality, where it occurs, is a product of strategy, not structure.

The Part concludes by synthesizing this spectrum and asking when the sweep effect is structurally appropriate -- and when it is not. That question sets the stage for the Proportional Representation Part, which examines methods that guarantee proportional outcomes through institutional design rather than relying on strategic behavior.

---

## The Frame

The previous Part established a principle that carries forward unchanged:

> Voting systems reflect priority choices.

Every system examined in that Part collected certain information, processed it in a particular way, guaranteed some outcomes, and left others unguaranteed. No single-winner system satisfied all desirable criteria simultaneously. Understanding this was the goal.

The same principle applies here -- but the design space introduces a new variable. When multiple seats are available, the system must not only determine which candidates win, but also decide whether the distribution of seats should reflect the distribution of voter support. The methods in this Part make different choices along that dimension, and those choices have consequences for who is represented and who is not.

This Part adds one evaluative tool that the previous Part did not require: **goal-relative evaluation**. Whether a method's structural properties are desirable depends on what the election is trying to accomplish. A system that sweeps all seats to the majority may be exactly right for a consensus-seeking committee and exactly wrong for a diverse legislature. The reader who finishes this Part will be equipped to ask the right question before evaluating any multi-winner method: what is this election's goal?

The question is no longer just who should win.

It is how representation should be distributed -- and whether the system's answer matches the election's purpose.
