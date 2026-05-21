# Proportional Representation

## When Structure Guarantees What Strategy Cannot

---

## Statement of Purpose

The previous Part examined multi-winner elections in which familiar ballot formats and straightforward counting rules were applied to fill multiple seats. It revealed a consistent pattern: proportionality, where it emerged at all, depended on strategic behavior by voters and parties -- not on the counting rule itself. Bloc voting produced sweeps. Limited voting, cumulative voting, and SNTV created structural space for minority representation, but only when minority factions coordinated their votes effectively. Multi-Seat STAR sought consensus winners through an expressive ballot, but did not alter the majoritarian structure. Across all five methods, the counting rule did not guarantee proportional outcomes. It permitted them, under favorable conditions.

This Part examines a different family of methods -- systems in which proportional outcomes are built into the counting rule itself.

These are candidate-centered proportional systems: methods in which voters evaluate individual candidates, and the counting rule distributes seats to reflect the distribution of voter support. A faction with 30 percent of the vote receives approximately 30 percent of the seats -- not because its voters coordinated skillfully, but because the system's mechanics produce that result by design.

This article introduces the proportional design space. It explains what distinguishes proportional systems from the multi-winner methods already examined, previews the conceptual tools the reader will need before encountering proportional mechanics, and maps the structure of the Part to come.

---

## What Changed

The multi-winner methods examined in the previous Part shared a structural feature: every voter participated at full strength in every round. When a seat was filled, no adjustment followed. The same voters who helped elect the first winner carried equal influence into the next round -- and the next, and the next. This is why a cohesive majority could sweep every seat. No mechanism existed to recognize that some voters had already been represented and to create space for those who had not.

Proportional systems break this pattern.

After each seat is filled, the system identifies which voters contributed to that winner and reduces their influence on subsequent seats. The specific mechanisms vary -- some transfer surplus votes, others reduce ballot weights, others allocate a quota's worth of voters to the winner and remove them from the count -- but the structural logic is the same: voters who have already helped elect a representative carry less weight in filling the remaining seats, creating space for groups that have not yet been represented.

This adjustment step is the defining feature of proportional representation. It is what the multi-winner methods lacked, and it is what makes proportional outcomes a product of institutional design rather than strategic behavior.

---

## The Proportional Design Question

The previous Part asked:

> How should representation be distributed when multiple seats are available?

This Part narrows that question:

> How should a counting rule distribute seats to reflect the distribution of voter support?

The difference is not merely verbal. The multi-winner question admits majoritarian answers -- and as the previous Part demonstrated, many multi-winner methods give exactly those answers. The proportional question presupposes a design commitment: seats should be distributed roughly in proportion to voter support, and the counting rule should produce that result mechanically.

That commitment introduces new design problems. When a candidate wins with more support than needed, what happens to the excess? When no candidate has enough support to win, who is eliminated and how are their voters' preferences redirected? How is "enough support" defined in the first place? These questions have no single-winner analogue. They arise because proportional systems must track and manage voter influence across multiple rounds, and the answers to them shape the kind of proportionality the system produces.

---

## Why Prerequisites Come First

Proportional systems require conceptual tools that earlier Parts did not need.

Single-winner systems could be taught with a worked example: present the ballots, apply the counting rule, announce the winner. Even multi-winner systems followed this pattern -- the counting rule was simple enough to describe in a sentence or two, and the structural consequences emerged from the example itself.

Proportional systems are different. Their counting rules are sequential, multi-round processes that involve conditional logic, fractional ballot values, surplus transfers, and threshold calculations. A reader encountering these mechanics for the first time inside a system article would be learning two things at once -- what the system does and the mathematical framework it depends on -- and the conceptual load would be excessive.

This Part addresses that problem directly. Before any proportional system is presented, two Foundation articles build the tools the reader will need.

The first, **Algorithms and Counting**, introduces the concept of an algorithm in the electoral context -- a step-by-step procedure that takes ballots as input, applies a defined sequence of operations, and produces a set of winners as output. It explains why proportional systems require sequential, multi-round algorithms where single-winner and multi-winner systems needed only a single pass. It also establishes the spectrum from methods simple enough to count by hand to methods that require a computer.

The second, **Quotas and the Price of a Seat**, introduces three interconnected concepts. The quota is the defined quantity of voter support that earns a seat. The surplus problem arises when a candidate receives more support than the quota -- those excess votes represent voters whose full preferences have not been used. The remainder problem arises when votes do not divide evenly into seats, and rules are needed to allocate seats at the margin. Together, these concepts form the arithmetic foundation of every proportional system that follows.

These are not optional background articles. Every proportional method examined in this Part depends on the vocabulary and structural understanding they establish. The reader who completes them will find the system articles substantially more accessible. The reader who skips them will encounter unfamiliar concepts -- quotas, surplus transfers, ballot reweighting, fractional vote values -- embedded in system mechanics, without the preparation needed to understand them.

---

## Four Families

With the Foundation articles in place, the Part examines four families of proportional systems, organized by ballot type.

**Proportional RCV** uses a ranked ballot -- the same ballot format the reader encountered in the Single-Winner Part. Voters rank candidates in order of preference. The counting rule fills seats through a combination of quota-based election and surplus transfer: when a candidate reaches the quota, the excess support transfers to voters' next-ranked candidates at a reduced value. When no candidate reaches the quota, the lowest-ranked candidate is eliminated and those voters' preferences transfer. This method has a long track record under the name Single Transferable Vote (STV) and is currently used in Cambridge, Massachusetts and proposed at the federal level through the Fair Representation Act.

**Proportional Approval** uses a binary ballot -- approve or do not approve each candidate. The counting rule adjusts voter influence after each seat is filled, typically through harmonic reweighting: a voter whose approved candidates have already won carries less weight than a voter with no elected representation. This family includes several methods that differ in their reweighting formulas and the proportionality guarantees they provide.

**Proportional Score** uses a cardinal ballot -- rate each candidate on a numerical scale. As with the move from single-winner Score to multi-winner Score, the ballot and basic aggregation remain familiar. The proportional version adds ballot reweighting after each seat is filled, reducing the influence of voters whose high-rated candidates have already won.

**Proportional STAR** uses the same score ballot and adds the automatic runoff from single-winner STAR, combined with a quota-based allocation mechanism. After each seat is filled, a quota's worth of voter influence is allocated to the winner and spent. This method is currently used by DSA-LA for internal elections and has been proposed through the CEMA proposal for U.S. House elections.

Each system article opens with where the method is currently used or has been formally proposed in the United States -- establishing stakes before mechanics. Where American usage is thin or nonexistent, the article says so.

---

## Evaluating Systems With Thin Records

Most proportional systems examined in this Part have limited real-world track records -- particularly the approval-based, score-based, and STAR-based families. Proportional RCV has decades of empirical evidence from Cambridge, Ireland, and Australia. The cardinal-ballot families have been adopted in organizational contexts but have little data from governmental elections.

This creates an evaluative challenge. How should a reader assess a system that has strong theoretical properties but thin empirical evidence?

The Part addresses this challenge with a dedicated article on **voting simulations** -- computational models that test voting systems under controlled conditions. Simulations allow analysts to evaluate systems whose real-world performance data is insufficient for confident empirical claims. But simulations also involve simplifying assumptions, and those assumptions shape the results. The article equips the reader to evaluate simulation evidence critically: to understand what simulations can reveal, what they cannot, and what questions to ask about any simulation result.

---

## How This Part Is Organized

The sequence follows the logic outlined above:

1. This Introduction establishes the design space and previews the structure.
2. Two Foundation articles build the prerequisite tools: algorithms and counting, then quotas, surplus handling, and ballot reweighting.
3. Four system families follow in order of ballot complexity: ranked, approval, score, then score with automatic runoff. Each system article covers mechanics, worked examples, structural consequences, and tradeoffs. Proportional RCV receives two articles (mechanics and consequences) due to the complexity of its counting process and the depth of its empirical record.
4. A Voting Simulations article equips the reader to evaluate systems with limited empirical data.
5. A Conclusion synthesizes across design dimensions rather than by system, providing a comparative framework.

---

## The Frame

The previous Parts established a principle that carries forward unchanged:

> Voting systems reflect priority choices.

Every system examined so far collected certain information, processed it in a particular way, guaranteed some outcomes, and left others unguaranteed. No single-winner system satisfied all desirable criteria simultaneously. No multi-winner system resolved the tension between majoritarian efficiency and proportional inclusion on its own terms.

The same principle applies here -- but the design space is more demanding. Proportional systems introduce new tradeoffs that simpler methods did not face: complexity against transparency, mathematical rigor against hand-count feasibility, strong proportionality guarantees against sensitivity to strategic behavior. Every proportional system makes choices along these dimensions, and those choices have consequences for who is represented and how.

The goal of this Part is the same as the Parts that came before: not to determine which system is best, but to develop the structural understanding needed to evaluate any proportional system one encounters.

The question is no longer whether representation should be distributed proportionally.

It is how -- and at what cost.
