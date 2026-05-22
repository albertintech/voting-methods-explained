# Proportional RCV

## How It Works

### Also Known As: The Single Transferable Vote (STV)

---

## Currently Used / Proposed Use

**Currently Used:** Cambridge, Massachusetts has used Proportional RCV for city council and school committee elections since 1941 (under the name "proportional representation" or "Plan E") -- the longest continuous use of the system in the United States. Portland, Oregon adopted Proportional RCV for city council elections in 2024 following a charter reform measure. Arlington, Virginia used Proportional RCV for a 2023 Democratic primary.

**Proposed Use:** The Fair Representation Act, introduced in the U.S. Congress, would require all elections for the U.S. House of Representatives to use Proportional RCV in multi-member districts (referred to in the legislation as "ranked choice voting" in multi-winner districts). The bill has been introduced in multiple sessions; readers can look up the current status of the legislation.

---

## Statement of Purpose

The two preceding articles built two conceptual tools. the Algorithms and Counting article introduced the algorithm -- a step-by-step procedure that proportional systems use to elect candidates sequentially, adjusting voter influence after each seat is filled. the Quotas and Surplus article introduced the quota -- the defined quantity of support that earns a seat -- and the surplus and remainder problems that every proportional system must solve.

This article is the first application of those tools. It introduces **Proportional RCV** -- the ranked-ballot method for achieving proportional representation without party lists. The system is historically and internationally known as the **Single Transferable Vote (STV)**; in the United States, it is increasingly called Proportional RCV or multi-winner RCV. The mechanics are the same.

Proportional RCV is the direct multi-winner extension of RCV from the previous series. The ballot is identical: voters rank individual candidates in order of preference. But the counting process is substantially more complex. In single-winner RCV, the task is straightforward: eliminate the last-place candidate and transfer their votes until one candidate has a majority. In Proportional RCV, the system must manage two distinct types of vote movement -- transfers from eliminated candidates (as in RCV) and transfers of surplus votes from candidates who have already won. This surplus transfer mechanism has no single-winner analogue. It is the core innovation of Proportional RCV, and it is the primary source of both the system's power and its complexity.

The mechanics are intricate enough to warrant dedicated treatment before evaluating consequences. This article focuses exclusively on how Proportional RCV works: the algorithm, the quota, the surplus transfer problem, and the variants that different jurisdictions have adopted to address it. A fully worked example demonstrates the complete process from first preferences through final seat allocation.

Evaluation -- proportionality properties, strategic incentives, monotonicity concerns, and real-world performance -- is reserved for the next article.

---

## Section 1: From Single-Winner RCV to Multi-Winner Proportional RCV

In the previous series, RCV worked as follows: voters ranked candidates, the candidate with the fewest first-preference votes was eliminated, and that candidate's votes were transferred to each ballot's next-ranked continuing candidate. This process repeated until one candidate held a majority of the remaining active votes.

The key properties were straightforward. There was one seat. The threshold for winning was a majority. Transfers came only from eliminated candidates. And the process was sequential: eliminate, transfer, check for majority, repeat.

Proportional RCV preserves the ranked ballot and the elimination-transfer logic. But the multi-winner context introduces three fundamental changes.

**First, the winning threshold changes.** In a single-winner election, a candidate needs a majority -- more than half the votes. In a multi-winner election, requiring a majority for each seat would be impossible: if five seats are available, five candidates cannot each hold a majority simultaneously. The winning threshold must be lower. Proportional RCV uses a quota -- a quantity of support calculated from the total votes and the number of seats -- as the threshold for election. The quota concept was developed in the Quotas and Surplus article; this article applies it.

**Second, a new type of transfer appears.** In single-winner RCV, votes move only when a candidate is eliminated. In Proportional RCV, votes also move when a candidate is elected with more support than the quota requires. These excess votes -- the surplus -- must be transferred to other candidates. If they are not, votes trapped above the quota are wasted, and voters whose first choice was a popular winner lose their ability to influence the remaining seats. the Quotas and Surplus article identified the surplus problem as one of the central challenges of proportional systems. Proportional RCV's answer to that challenge is the subject of Section 4.

**Third, the process manages election and elimination simultaneously.** Single-winner RCV has only one operation: eliminate the weakest candidate. Proportional RCV has two: elect candidates who reach the quota and eliminate candidates who cannot win. These operations alternate, and the order in which they occur can affect the outcome.

These three changes -- a quota threshold, surplus transfers, and dual operations -- transform the relatively straightforward RCV algorithm into a substantially more complex procedure. The remainder of this article examines each element in detail.

---

## Section 2: The Quota

The quota is the number of votes a candidate needs to be declared elected. It serves the same structural role in Proportional RCV that the majority threshold serves in single-winner RCV: it defines "enough support to win a seat."

the Quotas and Surplus article defined two quota formulas: the Hare quota and the Droop quota. Proportional RCV uses the Droop quota almost universally in practice.

### The Droop Quota in Proportional RCV

The Droop quota is calculated as:

> Droop quota = floor(total valid votes / (seats + 1)) + 1

In an election with 1,000 valid votes and 4 seats:

> floor(1,000 / 5) + 1 = 200 + 1 = 201

Any candidate who accumulates 201 or more votes (counting both first preferences and transfers) is declared elected.

### Why Droop?

the Quotas and Surplus article established the Droop quota's key mathematical property: it is the smallest number of votes that makes it impossible for more candidates to reach the quota than there are seats. In a 4-seat election with 1,000 votes and a Droop quota of 201, at most 4 candidates can reach 201 votes, because 5 x 201 = 1,005, which exceeds the 1,000 available votes. The quota precisely matches the number of seats.

The Hare quota (total votes divided by seats, or 250 in this example) is larger and more than necessary. The higher threshold means more votes remain as surplus or are left untransferred, which can affect which candidates ultimately fill the final seats. The Droop quota is more efficient: it sets the lowest threshold that still guarantees the correct number of winners.

Nearly all governmental Proportional RCV implementations -- Cambridge, Ireland, Scotland, Australia, and the newer U.S. adoptions -- use the Droop quota. The Hare quota appears primarily in historical and theoretical discussions.

---

## Section 3: The Proportional RCV Algorithm

With the quota established, the Proportional RCV counting process proceeds through a repeating cycle. the Algorithms and Counting article described the general structure of proportional algorithms: elect, adjust, repeat. Proportional RCV instantiates this structure with specific operations.

### Step-by-Step

1. **Calculate the Droop quota** from the total number of valid ballots and the number of seats.

2. **Count first preferences.** Each ballot is assigned to its highest-ranked candidate. Every candidate's tally is the number of ballots currently assigned to them.

3. **Check for quota.** If any candidate's tally meets or exceeds the quota, that candidate is declared **elected**.

4. **Transfer the surplus.** The elected candidate's surplus -- the amount by which their tally exceeds the quota -- is transferred to continuing candidates according to the next preferences on the ballots assigned to the elected candidate. How this transfer is calculated varies by Proportional RCV variant; this is the subject of Section 4.

5. **If no candidate meets the quota,** the candidate with the fewest votes is **eliminated**. All ballots assigned to the eliminated candidate are transferred at full value to the next-ranked continuing candidate on each ballot.

6. **Repeat from step 3** until all seats are filled.

7. **Termination.** The count ends when the required number of candidates have been elected, or when the number of continuing candidates equals the number of remaining seats -- in which case the remaining candidates are elected by default, even if they have not reached the quota.

### Two Types of Transfer

The algorithm involves two mechanically distinct types of vote movement.

**Elimination transfers** work exactly as in single-winner RCV. When a candidate is eliminated, every ballot assigned to that candidate moves to the next-ranked continuing candidate at its current value. If a ballot has no remaining continuing candidates ranked, it becomes **exhausted** and leaves the active count.

**Surplus transfers** are unique to Proportional RCV. When a candidate is elected with more votes than the quota, the excess must be redistributed. The challenge is that the elected candidate does not "need" all of their votes -- only a quota's worth. The surplus represents voter support that should flow to other candidates. But which votes transfer, and at what value? This is the central design problem of Proportional RCV, and different answers produce different systems.

---

## Section 4: The Surplus Transfer Problem

Consider a candidate who receives 300 first-preference votes when the quota is 200. The surplus is 100. Those 100 votes' worth of support should transfer to help elect other candidates. But 300 real ballots are assigned to this candidate. Which 100 ballots move? Or do all 300 move at a reduced value?

This is not a trivial question. The choice of surplus transfer method affects which candidates receive transfers, how much support they receive, and ultimately who wins the remaining seats. Different jurisdictions have adopted different solutions, each representing a different position on a tradeoff between simplicity and equal treatment of voters.

the Algorithms and Counting article introduced the idea that adjustment rules are where a system's values enter. Surplus transfer methods are Proportional RCV's adjustment rules, and they illustrate that idea concretely.

### Random Transfer (Original Hare Method)

The earliest approach, used in the original Hare system, was physical: literally select a random subset of the winning candidate's ballots equal to the surplus, and transfer those ballots at full value.

In the example above, 100 of the 300 ballots would be physically drawn from the pile and moved to the next-ranked candidates. The remaining 200 would stay with the elected candidate as their quota.

This method is easy to understand and easy to administer by hand. But it has a fundamental problem: the outcome depends on which ballots happen to be selected. A different random draw could transfer ballots with different next preferences, producing different results. The method is non-deterministic -- repeating the count with the same ballots could elect different candidates.

Random transfer is now generally considered obsolete. No major governmental election uses it for Proportional RCV today.

### The Gregory Method (Last Parcel)

The Gregory method avoids randomness by transferring ballots at a fractional value rather than selecting a subset.

However, the Gregory method examines only the **last parcel** of ballots received by the elected candidate -- the batch of transfers that pushed them over the quota. If a candidate reached the quota through first preferences alone, the last parcel is the full set of first-preference ballots. If a candidate reached the quota after receiving a transfer from an eliminated candidate, the last parcel is that transfer batch only.

The transfer value is calculated as:

> Transfer value = surplus / number of ballots in the last parcel

Each ballot in the last parcel is transferred to the next-ranked continuing candidate at this fractional value. Ballots received in earlier parcels are not examined.

The Gregory method is deterministic -- the same ballots always produce the same result. But it treats ballots unequally: a ballot that arrived in an earlier parcel has no chance of transferring, while a ballot in the last parcel carries the full surplus. Two voters who ranked the same candidates in the same order may have different influence on the outcome depending on when their ballot reached the elected candidate.

Ireland uses a version of the Gregory method for elections to the Dail (lower house of parliament), where it has been in continuous use since 1922.

### The Inclusive Gregory Method (IGM)

The Inclusive Gregory Method addresses the Gregory method's unequal treatment by examining **all** ballots held by the elected candidate, not just the last parcel. Every ballot assigned to the winning candidate is checked for a next-ranked continuing candidate, and transferable ballots are transferred at a fractional value:

> Transfer value = surplus / total number of transferable ballots held by the candidate

This is more equitable than the last-parcel approach because all of the candidate's ballots participate in the transfer, regardless of when they arrived. However, IGM can still produce subtle inequities. A ballot that arrived via a previous transfer at a reduced weight is treated the same as a first-preference ballot at full weight when calculating the transfer fraction.

IGM has been used for Australian Senate elections.

### The Weighted Inclusive Gregory Method (WIGM)

The Weighted Inclusive Gregory Method refines IGM by accounting for each ballot's current value when calculating the transfer.

Under WIGM, each ballot held by the elected candidate is transferred at a value calculated as:

> Ballot's transfer value = (ballot's current value) x (surplus / total value of all transferable ballots held by the candidate)

This means a ballot that arrived at full value (as a first preference) transfers at a higher absolute value than a ballot that arrived at a reduced value (via a previous surplus transfer). Both transfer at the same proportional reduction, but the method respects the fact that these ballots entered the candidate's pile carrying different weights.

WIGM is more equitable than either the Gregory method or IGM. It treats all ballots proportionally to their current contribution. It is deterministic and does not depend on the order in which ballots were counted.

WIGM is used in Scottish local government elections (since 2007) and is the basis for multi-winner RCV rules adopted in several U.S. jurisdictions, including Cambridge and the newer adoptions.

### Meek's Method (Iterative)

Developed by Brian Meek in 1969, Meek's method takes a fundamentally different approach. Rather than selecting parcels or calculating one-time transfer values, Meek's method assigns each elected candidate a **keep value** -- the fraction of each ballot's value that the candidate retains. The remainder passes through to subsequent preferences.

The process is iterative:

1. All candidates start with a keep value of 1 (they retain all support directed to them).
2. When a candidate is elected, their keep value is reduced so they retain exactly a quota's worth of value.
3. All ballots are recounted from the beginning, with each ballot distributing its value across its ranked candidates according to the current keep values.
4. The quota is recalculated to account for ballots that have exhausted (lost all value to exhaustion).
5. Steps 2 through 4 repeat until the keep values converge -- meaning all elected candidates hold exactly a quota, and the count is stable.

Meek's method treats all ballots identically regardless of the path by which they reached any candidate. It dynamically adjusts the quota as ballots exhaust, and it allows value to flow through already-elected candidates to later preferences. These properties make it the most mathematically rigorous surplus transfer method.

The cost is transparency. Meek's method requires a computer. The iterative recalculation is invisible to observers -- there is no moment where a pile of physical ballots moves from one candidate to another. The count cannot be verified by hand.

Meek's method is used in New Zealand local body STV elections and by several private organizations.

### The Refinement-Manageability Tradeoff

These approaches can be arranged along a spectrum. At one end, random transfer is the simplest to administer: select a subset, move them. It can be done entirely by hand with physical ballots. But it produces arbitrary, non-deterministic results.

At the other end, Meek's method treats every ballot with perfect mathematical symmetry. But it requires a computer and is opaque to manual verification.

In between, the Gregory method and WIGM occupy intermediate positions -- deterministic and administrable, but with varying degrees of success at equal treatment of ballots.

the Algorithms and Counting article introduced the tension between algorithmic sophistication and auditability. The surplus transfer spectrum is a concrete instance of that tension. No surplus transfer method is objectively superior. Each represents a different priority: administrative simplicity, determinism, equal treatment, or mathematical rigor. The choice among them is itself a design decision, and different jurisdictions have resolved it differently based on their own institutional values and administrative capacities.

---

## Section 5: A Worked Example

The following example demonstrates a complete Proportional RCV count with surplus transfers and eliminations. The election has 4 seats, 6 candidates, and 100 voters. The transfer method is WIGM.

This is a simplified example for pedagogical purposes. Real Proportional RCV elections typically involve more voters and more varied rankings.

### The Candidates and the Ballots

Six candidates are running: Adams, Brooks, Clarke, Davies, Ellis, and Foster.

The 100 ballots break down as follows:

- 28 ballots: Adams > Clarke > Ellis
- 14 ballots: Adams > Davies > Clarke
- 20 ballots: Brooks > Ellis > Davies
- 12 ballots: Clarke > Adams > Ellis
- 10 ballots: Davies > Brooks > Clarke
- 9 ballots: Ellis > Clarke > Adams
- 7 ballots: Foster > Davies > Brooks

### Calculating the Quota

> Droop quota = floor(100 / (4 + 1)) + 1 = floor(20) + 1 = **21**

Any candidate who accumulates 21 or more votes (by value) is elected.

### Count 1: First Preferences

| Candidate | First-Preference Votes |
|---|---|
| Adams | 42 |
| Brooks | 20 |
| Clarke | 12 |
| Davies | 10 |
| Ellis | 9 |
| Foster | 7 |

Adams has 42 first-preference votes -- well above the quota of 21. Adams is **elected**.

### Count 2: Transfer Adams's Surplus

Adams holds 42 votes, all at full value of 1.0. The quota is 21. The surplus is 42 - 21 = **21**.

Under WIGM, all 42 ballots assigned to Adams are examined for their next-ranked continuing candidate. Each ballot transfers at a value of:

> (ballot's current value) x (surplus / total value of transferable ballots)

All 42 ballots have a current value of 1.0, and all 42 have a next-ranked continuing candidate (either Clarke or Davies). Total transferable value = 42.0.

> Transfer value per ballot = 1.0 x (21 / 42) = **0.5**

The 42 ballots split as follows:

- 28 ballots (Adams > **Clarke** > Ellis): 28 x 0.5 = 14.0 to Clarke
- 14 ballots (Adams > **Davies** > Clarke): 14 x 0.5 = 7.0 to Davies

Updated tallies after Count 2:

| Candidate | Previous Tally | Transfer | New Tally |
|---|---|---|---|
| Adams | 42.0 | -21.0 (surplus) | 21.0 (elected) |
| Brooks | 20.0 | -- | 20.0 |
| Clarke | 12.0 | +14.0 | 26.0 |
| Davies | 10.0 | +7.0 | 17.0 |
| Ellis | 9.0 | -- | 9.0 |
| Foster | 7.0 | -- | 7.0 |

Clarke has 26.0 -- above the quota of 21. Clarke is **elected**.

### Count 3: Transfer Clarke's Surplus

Clarke holds ballots from two sources:

- 12 original first-preference ballots (Clarke > Adams > Ellis), each at value 1.0
- 28 transferred ballots (Adams > Clarke > **Ellis**), each at value 0.5

Clarke's total value: (12 x 1.0) + (28 x 0.5) = 12.0 + 14.0 = 26.0. The surplus is 26.0 - 21 = **5.0**.

Which ballots are transferable? Adams is already elected, so the 12 first-preference ballots (Clarke > Adams > Ellis) skip Adams and look for the next continuing candidate: Ellis. All 12 are transferable to Ellis. The 28 transferred ballots (Adams > Clarke > Ellis) have Ellis as their next continuing candidate. All 28 are transferable to Ellis.

Total transferable value: (12 x 1.0) + (28 x 0.5) = 26.0.

Under WIGM, each ballot's transfer value is proportional to its current value:

> (ballot's current value) x (5.0 / 26.0)

- 12 ballots at value 1.0: transfer at 1.0 x (5.0 / 26.0) = 0.192 each. Total: 12 x 0.192 = 2.308
- 28 ballots at value 0.5: transfer at 0.5 x (5.0 / 26.0) = 0.096 each. Total: 28 x 0.096 = 2.692

All transfers go to Ellis. Ellis receives 2.308 + 2.692 = **5.0** (the full surplus, as expected).

Updated tallies after Count 3:

| Candidate | Previous Tally | Transfer | New Tally |
|---|---|---|---|
| Adams | 21.0 | -- | 21.0 (elected) |
| Brooks | 20.0 | -- | 20.0 |
| Clarke | 26.0 | -5.0 (surplus) | 21.0 (elected) |
| Davies | 17.0 | -- | 17.0 |
| Ellis | 9.0 | +5.0 | 14.0 |
| Foster | 7.0 | -- | 7.0 |

No candidate meets the quota. The count moves to elimination.

### Count 4: Eliminate Foster

Foster has the fewest votes (7.0) and is eliminated. Foster's 7 ballots (Foster > **Davies** > Brooks), each at full value 1.0, transfer to Davies.

Updated tallies after Count 4:

| Candidate | Previous Tally | Transfer | New Tally |
|---|---|---|---|
| Adams | 21.0 | -- | 21.0 (elected) |
| Brooks | 20.0 | -- | 20.0 |
| Clarke | 21.0 | -- | 21.0 (elected) |
| Davies | 17.0 | +7.0 | 24.0 |
| Ellis | 14.0 | -- | 14.0 |

Davies has 24.0 -- above the quota. Davies is **elected**.

### Count 5: The Final Seat

Davies's surplus is 24.0 - 21 = 3.0. Two candidates remain: Brooks (20.0) and Ellis (14.0). Three seats have been filled (Adams, Clarke, Davies) and one seat remains.

Davies holds ballots from two sources: the 10 original first-preference ballots (Davies > Brooks > Clarke) at value 1.0, and the 14 transferred ballots from Adams (Adams > Davies > Clarke) at value 0.5, and the 7 transferred ballots from Foster (Foster > Davies > Brooks) at value 1.0.

Davies's total value is (10 x 1.0) + (14 x 0.5) + (7 x 1.0) = 10.0 + 7.0 + 7.0 = 24.0.

Examining next preferences among continuing candidates (Brooks and Ellis only):

- 10 ballots (Davies > **Brooks** > Clarke): transferable to Brooks, current value 1.0
- 14 ballots (Adams > Davies > **Clarke**): Clarke is elected, no further continuing candidate ranked -- these exhaust
- 7 ballots (Foster > Davies > **Brooks**): transferable to Brooks, current value 1.0

Total transferable value: (10 x 1.0) + (7 x 1.0) = 17.0. The 14 exhausting ballots carry 7.0 in value that leaves the active count.

Under WIGM, the transfer value per ballot is:

> (ballot's current value) x (3.0 / 17.0) = current value x 0.176

- 10 ballots to Brooks: 10 x 1.0 x 0.176 = 1.76
- 7 ballots to Brooks: 7 x 1.0 x 0.176 = 1.24

Brooks receives 1.76 + 1.24 = **3.0** (the full transferable surplus).

Wait -- but the surplus is 3.0 and the total transferable value is 17.0, not 24.0, because 7.0 worth of value exhausts. Under WIGM, the transfer fraction is calculated using total transferable value, so the calculation adjusts:

> Transfer fraction = surplus / total transferable value = 3.0 / 17.0 = 0.176

The 3.0 in surplus is fully distributed to Brooks. Updated tallies:

| Candidate | Previous Tally | Transfer | New Tally |
|---|---|---|---|
| Brooks | 20.0 | +3.0 | 23.0 |
| Ellis | 14.0 | -- | 14.0 |

Brooks (23.0) exceeds the quota. Brooks is **elected** to the fourth seat.

If the surplus transfer had not been sufficient to push any candidate over the quota, the count would have continued with elimination: Ellis, with fewer votes, would have been eliminated, and Brooks would have won the final seat by being the only remaining candidate -- the termination rule in action.

### Final Result

| Seat | Winner | Path to Election |
|---|---|---|
| 1 | Adams | First preferences (42 votes, quota 21) |
| 2 | Clarke | First preferences (12) + surplus transfer from Adams (14.0) |
| 3 | Davies | First preferences (10) + surplus transfer from Adams (7.0) + elimination transfer from Foster (7.0) |
| 4 | Brooks | First preferences (20) + surplus transfer from Davies (3.0) |

### What the Example Demonstrates

Several features of Proportional RCV are visible in this count.

**Surplus transfers preserve voter influence.** Adams received far more first-preference support than needed for one seat. Under bloc voting or SNTV, those excess votes would have been wasted. Under Proportional RCV, half of each ballot's value transferred to Adams's supporters' second choices, helping Clarke and Davies win seats. Voters who supported Adams did not sacrifice their influence on the remaining seats by choosing a popular candidate.

**Ballots carry different values at different stages.** The 28 ballots that began as Adams > Clarke > Ellis started at full value (1.0), transferred to Clarke at 0.5, and then transferred to Ellis at approximately 0.096. Each transfer reduced the ballot's remaining influence. This is a feature of the design: the ballot has already helped elect two candidates (Adams and Clarke) and has proportionally less influence remaining.

**Elimination and election alternate.** The count used both operations: Adams and Clarke were elected via surplus, Foster was eliminated for insufficient support, and Davies was elected after receiving Foster's transferred votes. This interplay between election and elimination is characteristic of Proportional RCV counts.

**The order of operations matters.** If Foster had been eliminated earlier -- or if a different candidate had been eliminated instead -- the transfers might have flowed differently, potentially producing a different fourth winner. This sensitivity to the sequence of operations is a structural feature of Proportional RCV that will be examined in the next article.

**Some ballot value exhausts.** In the final surplus transfer, 14 ballots carrying 7.0 in value exhausted because their remaining ranked candidates were all elected or eliminated. This value left the active count without contributing to the final seat. Exhaustion is an inherent feature of any system that uses ranked ballots with optional full ranking.

---

## Section 6: Exhausted Ballots in the Multi-Winner Context

A ballot becomes **exhausted** when it can no longer contribute to any continuing candidate -- typically because all candidates ranked on that ballot have been either elected or eliminated, and no further preferences are marked.

Exhausted ballots appeared in single-winner RCV, where they arose when a voter's ranked candidates were all eliminated before the final round. In the multi-winner context, exhaustion is more common and takes additional forms.

A ranked ballot in a Proportional RCV election may help elect one candidate through first preferences, transfer fractionally to a second candidate via surplus, and then exhaust because its third-ranked candidate has already been elected and no fourth preference was marked. The ballot participated meaningfully in the count -- it helped elect a winner and contributed partial support to another -- but it eventually ran out of continuing ranked candidates.

The frequency of exhaustion depends on several factors: the number of candidates, the number of seats, the depth of rankings voters provide, and equipment limitations. If a ballot scanner allows voters to rank only six candidates in a five-seat election with fifteen candidates running, the opportunity for exhaustion increases substantially compared to a system that permits full ranking. This is an equipment limitation, not a design feature of Proportional RCV itself, but it affects outcomes in practice.

Exhaustion has a structural consequence for the count: it reduces the number of active votes while the quota, in most Proportional RCV implementations, remains fixed at its original value. If enough ballots exhaust, it becomes possible that no remaining candidate can reach the quota. When this happens, the termination rule activates: remaining candidates are elected by default to fill the remaining seats, without reaching the quota.

Meek's method addresses this asymmetry by recalculating the quota at each iteration to account for exhausted ballot value. As ballots exhaust, the effective quota decreases, making it easier for remaining candidates to reach the threshold. Most statutory Proportional RCV rules do not make this adjustment -- they fix the quota at the start and rely on the termination rule to handle any shortfall.

---

## Section 7: Proportional RCV in American Practice

### Cambridge, Massachusetts

Cambridge has used Proportional RCV (under the name "proportional representation" or "Plan E") for city council and school committee elections since 1941 -- the longest continuous use of the system in the United States. Cambridge adopted the system decades before the "Proportional RCV" branding existed; the academic and international term for the system is "the Single Transferable Vote" (STV).

Cambridge's elections are non-partisan -- no party labels appear on the ballot. The system's proportionality operates entirely through voter coalitions rather than party structure. In practice, identifiable interest groups -- geographic neighborhoods, racial and ethnic communities, political tendencies -- have achieved representation through the transfer mechanism. With nine seats on the city council elected from a single at-large district, the Droop quota is approximately 10% of the vote. Any identifiable group constituting more than 10% of the electorate and ranking its preferred candidates together can guarantee itself a seat.

### Portland, Oregon

Portland adopted Proportional RCV for city council elections in 2024 as part of a comprehensive charter reform. The adoption represents the most significant expansion of Proportional RCV in U.S. local government in decades.

### The Fair Representation Act

The Fair Representation Act would require all U.S. House elections to use multi-member districts with Proportional RCV (referred to in the legislation as "ranked choice voting" in multi-winner districts). The bill has been introduced in multiple sessions of Congress. If enacted, it would represent the largest adoption of Proportional RCV in American history.

### A Note on Terminology

The system described in this article is known by several names. Internationally and in academic literature, the standard term is the **Single Transferable Vote (STV)**. In the United States, reform advocates and organizations (notably FairVote) use **"proportional ranked choice voting"** or **"multi-winner RCV."** The Fair Representation Act uses "ranked choice voting" in multi-winner districts. Cambridge calls its system "proportional representation" under "Plan E."

This series uses **Proportional RCV** -- the term gaining traction in American reform discourse and the one readers are most likely to encounter in ballot measures, legislation, and advocacy materials. The underlying mechanics are identical regardless of which name is used. Ranked ballots, a Droop quota, surplus transfers, and sequential eliminations define the system. Where specific implementation details differ -- such as the handling of exhausted ballots, batch elimination rules, or the maximum number of rankings permitted by voting equipment -- these are variations within the Proportional RCV family rather than departures from it.

### Historical U.S. Use

Proportional RCV (then known as STV) was adopted by approximately two dozen U.S. cities during the early-to-mid twentieth century, typically as part of broader municipal reform packages that also included city manager government and non-partisan elections. New York City used STV for city council elections from 1937 to 1947. Cincinnati used it from 1925 to 1957. Other adopters included Cleveland, Sacramento, Boulder, and several smaller cities.

Nearly all of these adoptions were eventually repealed. The political dynamics of adoption and repeal -- including the role of racial politics, Cold War anxieties, and institutional resistance -- are important historical context. They are also normative and political questions that belong in a later series. For this article, the relevant point is structural: Proportional RCV has an extensive American track record, not merely a theoretical existence.

---

## Section 8: International Practice

Outside the United States, the system described in this article is universally known as the Single Transferable Vote (STV). The international implementations described below use that term.

### Ireland

Ireland has used STV for elections to the Dail (lower house of parliament) since 1922, making it the longest-running national use of the system. Irish STV uses the Droop quota and a version of the Gregory method that examines only the last parcel of ballots received by the elected candidate. The count is conducted physically, with paper ballots sorted into piles, and results are announced at public count centers.

The Irish experience demonstrates that STV can function at the national level over an extended period. It also illustrates the path dependence inherent in the Gregory method: because only the last parcel transfers, the order in which candidates reach the quota can influence which votes are available for transfer.

### Scotland

Scotland adopted STV for local government elections in 2007. Scottish STV uses the Droop quota and the Weighted Inclusive Gregory Method for surplus transfers. The count is conducted electronically, and detailed round-by-round results are published for each ward. The decision to use WIGM rather than the simpler Gregory method reflected a deliberate choice to prioritize equal treatment of ballots over hand-count simplicity. Because Scottish local elections are machine-counted, fractional value transfers are administratively feasible.

### Australia

Australia has used STV for Senate elections since 1949. The Australian system uses the Inclusive Gregory Method for surplus transfers. However, the practical character of Australian Senate STV was significantly shaped by the introduction of "group voting tickets" in 1984, which allowed parties to register a predetermined preference order applied to any voter who marked a single "above the line" vote for a party. This effectively converted STV into a party-list system in practice, since most voters voted above the line and accepted their party's predetermined rankings.

Reforms in 2016 abolished group voting tickets for federal Senate elections and replaced them with optional preferential voting above the line, restoring some of the candidate-centered character of STV. The Australian experience illustrates how administrative design choices -- even those not part of the core STV algorithm -- can substantially alter a system's character.

---

## Comparison Table: Surplus Transfer Methods

| Dimension | Random Transfer | Gregory (Last Parcel) | Inclusive Gregory (IGM) | Weighted Inclusive Gregory (WIGM) | Meek (Iterative) |
|---|---|---|---|---|---|
| Deterministic? | No | Yes | Yes | Yes | Yes |
| Which ballots transfer? | Random subset | Last parcel only | All held ballots | All held ballots | All ballots (iterative) |
| Equal treatment of ballots? | No (arbitrary selection) | No (parcel-dependent) | Partial (ignores current value) | Yes (proportional to current value) | Yes (fully symmetric) |
| Hand-countable? | Yes | Yes | Difficult | Difficult | No (requires computer) |
| Quota adjustment for exhaustion? | No | No | No | No | Yes |
| Path dependence | High (random) | Moderate (parcel order) | Low | Low | Minimal |
| Current governmental use | None | Ireland, Australian states | Australian Senate | Scotland, U.S. jurisdictions | New Zealand local elections |

---

## Conclusion

This article examined the mechanics of Proportional RCV -- the ranked-ballot method for achieving proportional representation without party lists, historically and internationally known as the Single Transferable Vote (STV).

The article began by connecting Proportional RCV to single-winner RCV from the previous series. The ballot is the same: voters rank candidates. But the multi-winner context introduces three mechanical elements that have no single-winner analogue: a quota threshold lower than a majority, surplus transfers from elected candidates, and the interplay between election and elimination as dual operations within the same count.

The quota -- almost universally the Droop quota in practice -- sets the price of a seat, applying the concept developed in the Quotas and Surplus article. It is the multi-winner replacement for the majority threshold.

The surplus transfer problem proved to be the central design challenge. When a candidate wins with more votes than the quota, the excess must be redistributed -- but how? Five methods were examined, each occupying a different position on the refinement-manageability tradeoff:

- Random transfer is simple but non-deterministic.
- The Gregory method is deterministic but treats ballots unequally depending on when they arrived.
- The Inclusive Gregory Method examines all ballots but ignores differences in current ballot value.
- The Weighted Inclusive Gregory Method accounts for current ballot values, achieving proportional treatment.
- Meek's method achieves full mathematical symmetry through iterative recalculation, at the cost of transparency and hand-count feasibility.

No surplus transfer method is objectively superior. Each reflects a different judgment about what matters more: administrative transparency or mathematical rigor, hand-count simplicity or equal treatment of every ballot. The choice among them is itself a design decision -- embedded in the counting rules in the same way that the choice of quota formula is embedded in the allocation rules.

The worked example demonstrated these mechanics in action: surplus flowing from a popular first choice to second and third choices, fractional ballot values accumulating across rounds, elimination filling the gaps when no candidate reaches the quota, and the gradual assembly of a multi-member result through iterated transfers.

Several features of Proportional RCV's mechanics carry forward into the evaluation that follows. The complexity of the counting process raises questions about transparency and auditability. The sensitivity to the order of eliminations raises questions about path dependence and monotonicity. The dependence on ranked preferences raises questions about ballot exhaustion and strategic behavior. These are structural consequences of Proportional RCV's design -- the subject of the next article.

---

<!--
## Revision History

**Revision 1.4** (Current)
- Added revision history footer per formatting convention
- Article content unchanged

**Revisions 1.0 through 1.3**
- Development history prior to adoption of on-document revision tracking
- Final pre-convention state: eight numbered sections plus surplus transfer comparison table and conclusion covering the transition from single-winner to multi-winner RCV, quota selection, the Proportional RCV algorithm, surplus transfer methods, a worked example, exhausted ballots, American practice, and international practice
-->

*Revision history available in the raw file.*

> 📥 [Download this document](https://github.com/albertintech/voting-methods-explained/blob/main/src/pr-03-proportional-rcv-mechanics.md) (opens on GitHub -- click the ⬇ download button)

---

*© 2026 Albert Ramos. All rights reserved.*
