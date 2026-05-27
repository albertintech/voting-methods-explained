# Proportional RCV

## Structural Consequences

---

## Statement of Purpose

The previous article examined the mechanics of Proportional RCV -- the quota, the surplus transfer problem, the variants that different jurisdictions have adopted, and the step-by-step process by which ranked ballots are converted into a multi-member result. That article deliberately withheld evaluation. It described how Proportional RCV works without asking how well it works, or at what cost.

This article provides the evaluation.

Proportional RCV's central claim is that proportional representation can be achieved through individual candidate rankings rather than party labels. Voters rank people, not parties, and the counting process assembles a proportional result from those individual choices. This is a powerful design idea. It is also one that introduces structural consequences that do not appear in simpler multi-winner methods. The complexity of the counting process raises questions about transparency and auditability. The sensitivity to elimination order raises questions about monotonicity. The dependence on ranked preferences raises questions about strategic behavior and ballot complexity. And the absence of party labels raises questions about what kind of proportionality Proportional RCV actually delivers.

Each of these consequences is examined in turn. The article then surveys the real-world record -- Ireland, Australia, Scotland, and Cambridge -- to assess how Proportional RCV's structural properties manifest in practice. The evaluation concludes by situating Proportional RCV as a candidate-centered proportional system with a distinctive position in the multi-winner design space.

---

## Section 1: Droop Proportionality

Proportional RCV's proportionality guarantee has a specific formal character. It is not the kind of proportionality that most people imagine when they hear "proportional representation," and understanding the difference is essential to evaluating what Proportional RCV actually promises.

### Proportionality for Solid Coalitions

The formal property is called **proportionality for solid coalitions**, sometimes referred to as **Droop proportionality**. It works as follows:

If a group of voters constituting more than K Droop quotas all rank the same K candidates at the top of their ballots -- in any order, but above all other candidates -- then at least K of those candidates will be elected.

Consider a five-seat election with 600 voters and a Droop quota of 101. If 210 voters all rank candidates X and Y first and second (in either order), and rank all other candidates below X and Y, then X and Y are guaranteed to be elected. The 210 voters exceed two Droop quotas (2 x 101 = 202), and they form a "solid coalition" behind X and Y -- meaning they unanimously prefer both X and Y to every other candidate.

This guarantee is strong. It means that any sufficiently large group of voters who share a common set of preferred candidates will see those candidates elected, regardless of how the rest of the electorate votes. The system cannot waste or drown out their support as long as the group ranks its preferred candidates together at the top.

### What Droop Proportionality Does Not Guarantee

Droop proportionality is a guarantee about cohesive voter groups and their top-ranked candidates. It is not a guarantee about party seat shares. Two important distinctions follow.

First, the guarantee requires a **solid coalition** -- the voters must unanimously rank the same candidates above all others. If a group of 210 voters mostly prefers X and Y but some rank a third candidate Z between X and Y, the coalition may not be "solid" in the formal sense, and the guarantee may not hold. In practice, voter preferences are rarely this tightly coordinated, which means Proportional RCV's proportionality guarantee applies most cleanly to groups with highly aligned preferences and weakens as internal disagreement increases.

Second, the guarantee says nothing about parties. A party that wins 40% of first-preference votes is not guaranteed 40% of the seats. If that party's voters split their lower preferences across candidates from other parties -- or if the party nominates too many candidates, fragmenting its first-preference support -- the transfer mechanism may not consolidate enough votes to fill all the seats the party's overall support level would suggest. Proportional RCV's proportionality operates at the level of voter coalitions, not party labels.

### The Practical Effect

In jurisdictions with strong party systems -- Ireland, for example -- Proportional RCV's Droop proportionality tends to produce roughly party-proportional outcomes in practice. Voters who support a particular party generally rank that party's candidates ahead of other parties' candidates, forming something close to a solid coalition. The transfer mechanism then does its work: surplus votes flow from the strongest candidate to the next co-partisan, and votes from eliminated co-partisans transfer to surviving co-partisans.

But "roughly proportional" is not "exactly proportional." Small parties may win fewer seats than their vote share would suggest under a system with a formal party-proportionality guarantee, because their voters are more likely to transfer preferences across party lines, breaking the solid coalition condition. Independent candidates and cross-party voters introduce further variability.

In non-partisan contexts -- such as Cambridge, Massachusetts, where city council elections have no party labels on the ballot -- Droop proportionality operates entirely at the level of interest-group coalitions rather than parties. Proportionality emerges to the extent that identifiable voter groups rank their preferred candidates together. The system does not know or care about party affiliation; it responds only to the preference structure on the ballots.

---

## Section 2: Strategic Incentives

Proportional RCV's strategic profile is generally favorable. Honest preference reporting -- ranking candidates in the order a voter genuinely prefers them -- is a reasonable strategy for most voters in most elections. The system does not impose the kind of strategic burden that SNTV places on parties (vote management across multiple candidates) or that cumulative voting places on voters (deciding how to concentrate limited votes).

That said, Proportional RCV is not strategyproof. Several forms of strategic behavior are theoretically possible and have been observed or discussed in practice.

### Free-Riding

Free-riding occurs when supporters of a popular candidate deliberately rank that candidate lower than their true preference, hoping that other supporters will provide enough first-preference votes to elect the candidate, while the free-rider's first-preference vote goes to help a different, less popular candidate.

The logic is straightforward: if a candidate is certain to be elected anyway, a strategic voter might reason that their vote is "wasted" as a first preference for that candidate -- it will simply become part of the surplus. By giving their first preference to a candidate who needs the votes more, the strategic voter attempts to influence an additional seat.

In practice, free-riding is extremely difficult to execute. It requires accurate information about how many first preferences the popular candidate will receive -- information that voters rarely have. If too many supporters attempt to free-ride simultaneously, the candidate may fail to reach the quota at all, and the strategy backfires catastrophically. The individual incentive exists, but the coordination problem makes it impractical in most real elections.

### Vote Management

Vote management is a party-level strategy rather than an individual voter strategy. It refers to a party's attempt to distribute its supporters' first-preference votes evenly across its candidates, rather than allowing one candidate to accumulate a large surplus while another falls short.

The problem arises because Proportional RCV treats surplus votes differently from direct first-preference votes. A party with enough total support to win three seats might win only two if one candidate receives a massive first-preference total (generating a large surplus that transfers at fractional value) while a second candidate narrowly reaches the quota and a third falls just short. A more even distribution of first preferences across the party's three candidates would have been more efficient.

Irish political parties have historically engaged in vote management by asking supporters in different geographic areas to give their first preferences to different party candidates. This practice is well-documented in Irish politics and illustrates a structural tension in Proportional RCV: the system is designed to let individual voters express their personal preferences, but optimal party outcomes sometimes require voters to subordinate their personal favorite to a party-directed allocation.

### Strategic Truncation

Strategic truncation means deliberately leaving candidates unranked -- submitting a shorter ballot than one's true preferences would warrant -- to prevent one's vote from eventually helping a less-preferred candidate.

The concern is specific to Proportional RCV's transfer mechanism. If a voter ranks their three favorite candidates and all three are eliminated, the ballot will transfer to the voter's fourth-ranked candidate. But if the voter only marginally prefers that candidate over the remaining field, they might leave the fourth preference blank, causing the ballot to exhaust rather than transfer to an outcome they find only slightly acceptable.

In practice, strategic truncation is most relevant when voters have strong negative preferences and weak positive preferences among the remaining candidates. It is also more relevant in jurisdictions that limit the number of rankings voters can express, since limited ranking depth forces truncation regardless of strategic intent.

### Strategic Nomination

Parties face nomination decisions that have strategic consequences under Proportional RCV. Running too many candidates can fragment first-preference support, causing all candidates to start with low tallies and making the party vulnerable to early eliminations. Running too few candidates can leave transferable votes stranded -- if a party's only candidate is elected with a surplus, the surplus transfers to candidates from other parties.

The optimal number of nominees depends on the party's expected vote share, the district magnitude, and the transfer patterns of the electorate. This calculation is a standard feature of Proportional RCV campaign strategy in Ireland and Australia.

### The Overall Strategic Picture

These strategic vulnerabilities are real, but they share a common characteristic: they are difficult for individual voters to exploit successfully. Free-riding requires information that voters do not have. Vote management requires party coordination that is imperfect. Strategic truncation sacrifices influence. Strategic nomination is a party-level calculation, not a voter-level one.

Compared to SNTV, where strategic coordination is essential and miscalculation regularly produces suboptimal outcomes, Proportional RCV's strategic demands are modest. The general assessment in the voting theory literature is that Proportional RCV is "semi-strategyproof" in practice: the opportunities for strategic manipulation exist but are rarely worth the risk, and honest voting is a reasonable strategy for the vast majority of voters in the vast majority of elections.

---

## Section 3: Monotonicity

Proportional RCV violates monotonicity. This means that it is possible for a candidate to lose a seat precisely because additional voters ranked that candidate higher -- or, conversely, for a candidate to win a seat precisely because some voters ranked them lower.

This property was introduced in the previous series in the context of single-winner RCV, where the same violation occurs. The multi-winner context adds complexity but the underlying mechanism is the same.

### How Monotonicity Failures Occur

The mechanism is inherited from the sequential elimination process. Changing a voter's ranking of a candidate can alter which candidate is eliminated in an earlier round. That change cascades: different eliminations produce different transfer patterns, which alter the tallies in subsequent rounds, which can change the order of further eliminations and elections. The candidate who gained support may find that the cascade of downstream effects ultimately harms them.

Consider a simplified scenario. In a three-seat Proportional RCV election, Candidate X narrowly wins the final seat. Some voters who ranked X second decide to rank X first instead. This change increases X's first-preference tally, but it also decreases the first-preference tally of the candidate who was previously those voters' first choice. That candidate may now be eliminated earlier. Their transferred votes may flow to a different candidate than they would have under the original elimination order. And that different candidate may now defeat X for the final seat.

The candidate gained support -- and lost because of it.

### Frequency and Practical Significance

Empirical studies of real Proportional RCV elections have found that monotonicity failures are uncommon. The vast majority of Proportional RCV elections proceed without any detectable monotonicity anomaly. But "uncommon" is not "impossible," and the cases that do occur are difficult to detect -- a monotonicity failure can only be identified by comparing the actual outcome to a hypothetical scenario in which some voters had ranked differently, which requires access to all individual ballot data and the computational capacity to test alternative configurations.

The analogy to the single-winner case from the previous series is instructive. The previous series documented that RCV's monotonicity violations are real but rare. The same pattern holds for Proportional RCV: the violation is a structural property of the algorithm -- it follows from the interaction between sequential elimination and quota-based elections -- but it manifests infrequently in real-world conditions.

### Why the Violation Persists

If monotonicity failures are undesirable, why not design a system that avoids them? The answer is that monotonicity conflicts with other properties that Proportional RCV is designed to satisfy.

The formal tension is between Droop proportionality and monotonicity. Systems that guarantee Droop proportionality through a quota-and-transfer mechanism are susceptible to monotonicity failures, because the transfer mechanism creates path-dependent cascades. Eliminating the monotonicity problem would require either abandoning the sequential elimination process or abandoning the surplus transfer mechanism -- both of which would sacrifice the proportionality guarantee.

Alternative designs have been explored. Schulze STV and CPO-STV -- methods that compare complete committees using pairwise logic rather than building them sequentially -- achieve stronger monotonicity properties. But both are computationally intractable: determining the winning committee under either method is NP-hard. the Algorithms and Counting article introduced the concept of computationally intractable methods at the far end of the counting spectrum. Schulze STV and CPO-STV are concrete examples: the improved monotonicity comes at the price of practical usability.

Within the space of administrable multi-winner methods using ranked ballots, the tension between Droop proportionality and monotonicity appears to be a genuine constraint -- not an accident of Proportional RCV's specific design but a reflection of deeper mathematical limits in the multi-winner space.

---

## Section 4: Candidate Incentive Structures

Every voting system shapes how candidates campaign. In multi-winner systems, these incentive structures are more complex than in single-winner elections because candidates must position themselves relative to both opponents and co-partisans.

### Intra-Party Competition

Proportional RCV creates competition between candidates of the same party. In a four-seat constituency where a party runs three candidates, those candidates must compete with each other for first-preference votes, even as they depend on each other's transfers. This intra-party dimension is absent from the simpler multi-winner methods in Part 1: under bloc voting, a party slate succeeds or fails together; under SNTV, party candidates compete but have no transfer mechanism to create mutual dependence.

The dual pressure -- compete for first preferences, cooperate for transfers -- is distinctive to Proportional RCV. A candidate who attacks a co-partisan too aggressively may win first-preference votes but lose the lower-preference transfers needed to reach the quota. A candidate who relies entirely on transfers without building a first-preference base may be eliminated before transfers arrive.

### The Transfer Incentive

Proportional RCV rewards candidates who can attract lower-preference support from voters whose first choices are in other coalitions. This structural incentive encourages a different kind of campaigning than plurality-based systems produce.

Under plurality or bloc voting, candidates focus on maximizing first-choice support -- typically by mobilizing a base. Under Proportional RCV, a candidate with a secure first-preference base has an incentive to be broadly acceptable beyond that base, because surplus transfers from other candidates' supporters may determine whether the candidate reaches the quota. Conversely, a candidate without a large first-preference base can still win if they attract enough transfers from multiple sources.

While we cannot attribute all candidate and campaign behavior to the voting system, we can identify the structural incentives Proportional RCV puts in place. The system rewards breadth of appeal across voter groups, not only depth of support within one group.

### Constituency Service

Irish political culture places heavy emphasis on constituency service -- the expectation that elected representatives will act as local advocates for individual constituents. Political scientists have attributed this emphasis partly to Proportional RCV's incentive structure: because candidates from the same party compete for votes within the same constituency, they differentiate themselves through personal attentiveness and local engagement rather than policy positions alone. Whether this produces responsive representation or parochialism at the expense of national policy is a matter of ongoing debate in the literature -- and a normative question beyond this article's scope.

---

## Section 5: Ballot Complexity and Voter Error Rates

Proportional RCV asks voters to rank candidates in order of preference -- the same task required by single-winner RCV. But the multi-winner context changes the practical character of that task.

### The Ranking Task at Scale

In a single-winner RCV election with five candidates, the ranking task is manageable: evaluate five people, order them. In an Proportional RCV election for a nine-seat city council with twenty candidates -- a realistic scenario for Cambridge or Portland -- the ranking task is substantially more demanding. Voters must form and express preferences across a larger candidate field, and the cognitive effort required to rank twenty candidates meaningfully is considerable.

Most voters in multi-seat Proportional RCV elections do not provide full rankings. They rank some candidates and leave others blank. The resulting truncated ballots are not errors -- they reflect the natural limits of voter knowledge and interest. But they do increase the prevalence of exhausted ballots later in the count, as discussed in the previous article.

### Equipment Limitations

Ballot design and voting equipment can constrain the ranking task further. If a jurisdiction's voting machines allow voters to rank only six candidates in a twenty-candidate field, the opportunity for exhaustion is imposed by technology rather than voter choice. This is an equipment limitation, not a design feature of Proportional RCV, but it shapes real-world outcomes. The previous series noted the same issue for single-winner RCV; the effect is amplified in multi-winner elections with larger candidate fields.

### Voter Error Rates

The empirical evidence on voter errors under Proportional RCV is mixed. Scotland's adoption of Proportional RCV for local government elections in 2007 produced low rates of invalid ballots, and subsequent elections showed declining error rates as voters gained familiarity with the ranking process. The Electoral Commission's review of the 2007 elections concluded that the transition was smoother than many had anticipated.

In the American context, research on ranked-ballot elections has identified higher error rates in certain communities -- particularly where ballot design is confusing or where voters have less familiarity with the ranking format. The Cormack (2024) study of New York City's first RCV elections and the Pettigrew and Radley research on ballot spoilage both document that ballot complexity interacts with ballot design and voter experience to produce uneven error distributions. These studies examined single-winner RCV, but the ballot format is the same, and the added complexity of multi-seat Proportional RCV elections may amplify the effects.

The relationship between ballot complexity and voter participation is a legitimate design concern. A system that produces more accurate proportional outcomes but confuses a significant fraction of voters faces a tradeoff between representational quality and democratic accessibility.

---

## Section 6: Transparency and Auditability

Proportional RCV's counting process is substantially more opaque than the counting processes used by other multi-winner methods. This is not a matter of perception; it is a structural feature of the algorithm.

### The Transparency Challenge

Under the simpler multi-winner methods from Part 1, the counting process is arithmetically straightforward: add up the votes, the top K candidates win. Any observer can verify the result independently.

Under Proportional RCV, the counting process involves multiple rounds of surplus transfers and eliminations, fractional ballot values, and path-dependent interactions between rounds. The result cannot be verified from aggregate data -- it requires access to every individual ballot and the ability to replay the counting algorithm step by step. Different surplus transfer methods produce different results from the same set of ballots, and the choice of transfer method may not be visible to voters who only see the final result.

### Precinct Summability

A related concept is **precinct summability** -- whether precinct-level subtotals can be aggregated to determine the election-wide result without transmitting every individual ballot to a central location.

The methods from Part 1 (bloc voting, limited voting, cumulative voting, SNTV) and the single-winner systems from the previous series (plurality, approval, score, STAR) are all precinct-summable. Each precinct can report its candidate totals, and those totals can be summed across precincts to produce the election result.

Proportional RCV is not precinct-summable. Because the transfer of a single ballot depends on which candidates have been elected or eliminated in previous rounds -- decisions that depend on the full ballot profile across all precincts -- the count cannot begin until all ballot data has been centralized. Proportional RCV elections inherently require centralized tabulation, which creates logistical requirements around ballot transmission and chain of custody that precinct-summable methods avoid.

### The Hand-Count Question

Ireland counts Proportional RCV elections by hand at public count centers -- a tradition that provides physical transparency. Observers can watch ballots being sorted into piles. But the connection between the physical process and the mathematical result is difficult for non-specialists to follow, particularly when surplus transfers involve fractional values.

Scotland counts Proportional RCV elections electronically, publishing detailed round-by-round results. Verifying that the software correctly implemented the transfer rules requires either access to the source code, an independent re-implementation, or a hand recount -- each of which presents its own practical challenges.

the Algorithms and Counting article identified the tension between algorithmic sophistication and auditability as a recurring theme in proportional systems. Proportional RCV occupies a notable position in that tension: it is the most widely used proportional system that is not precinct-summable and not straightforwardly hand-auditable, yet it is used in jurisdictions that rely on hand counting and public verification as democratic norms.

---

## Section 7: Real-World Performance Evidence

Proportional RCV has a longer and more geographically diverse track record than any other candidate-centered proportional system. The previous article described the mechanics used in each major jurisdiction. This section evaluates what those jurisdictions teach about Proportional RCV's structural properties in practice.

### Ireland

Ireland's experience since 1922 demonstrates several things about Proportional RCV.

First, Proportional RCV can produce roughly party-proportional outcomes over an extended period, even without a formal party-proportionality guarantee. The major parties have received seat shares that broadly track their vote shares, and small parties and independents have won representation at rates that would be difficult under single-member district systems.

Second, Proportional RCV creates intra-party competition with real behavioral consequences. Irish candidates differentiate themselves through constituency service and personal reputation rather than policy positions alone. This candidate-centered dynamic is a direct product of Proportional RCV's incentive structure.

Third, Proportional RCV is politically durable when it has public support. The Irish electorate has twice been asked to replace Proportional RCV with a single-member district plurality system -- by referendum in 1959 and again in 1968. Both referendums failed. The system's survival reflects public attachment to the ability to rank individual candidates, express preferences across party lines, and hold individual politicians accountable.

### Australia

Australia's Senate elections use Proportional RCV with the Inclusive Gregory Method for surplus transfers. The Australian experience illustrates how administrative design choices can reshape a system's character. From 1984 to 2013, "group voting tickets" allowed parties to register predetermined preference orders applied to any voter who marked a single "above the line" vote for a party. Since the vast majority of voters voted above the line, the effect was to convert Proportional RCV into a de facto party-list system. Preference deals between parties determined which minor parties would benefit from transferred votes, and voters had little practical control over the preference flows.

Reforms in 2016 abolished group voting tickets and introduced optional preferential voting above the line, restoring some of Proportional RCV's candidate-centered character. The Australian experience offers a structural lesson: Proportional RCV's properties depend not only on the algorithm but also on the administrative and ballot-design choices that surround it. A system that is formally candidate-centered can become functionally party-centered through mechanisms that reduce the cost of party-line voting to a single mark.

### Scotland

Scotland's adoption of Proportional RCV in 2007 provides evidence on voter adaptation and error rates. The first Proportional RCV elections produced low rates of invalid ballots, and subsequent elections showed declining error rates. Scotland's use of WIGM rather than the Gregory method reflects the institutional choice to prioritize equal treatment of ballots over hand-count simplicity -- a choice enabled by electronic counting.

### Cambridge, Massachusetts

Cambridge demonstrates that Proportional RCV functions effectively in non-partisan contexts. Without party labels on the ballot, Proportional RCV's proportionality operates entirely through voter coalitions. Identifiable interest groups -- geographic, racial, ethnic, and ideological -- have achieved representation through the transfer mechanism. With a nine-seat council and a Droop quota of approximately 10%, any group constituting more than one-tenth of the electorate and ranking its preferred candidates together can guarantee itself a seat.

Cambridge also illustrates district magnitude in action. The low threshold enabled by nine seats produces a council that is broadly recognized as more diverse than single-member district elections would likely yield in a city with Cambridge's demographic distribution.

### The Historical American Experience

Approximately two dozen U.S. cities adopted Proportional RCV during the early-to-mid twentieth century. Nearly all subsequently repealed it. The system functioned mechanically as designed -- the repeals were not driven by counting failures or administrative breakdowns. They were driven by political opposition to the outcomes that the functioning system produced.

The political dynamics of Proportional RCV adoption and repeal -- including the role of racial politics, Cold War anxieties, and institutional resistance -- are important context that is acknowledged here but deferred to a later series where normative and political questions are in scope. For the purposes of this evaluation, the relevant structural observation is that Proportional RCV demonstrated its capacity for diverse representation, and that this capacity generated political opposition from established power structures.

---

## Comparison Table: Proportional RCV Evaluation Dimensions

| Dimension | Assessment |
|---|---|
| Proportionality type | Droop proportionality for solid coalitions (candidate-centered, not party-guaranteed) |
| Proportionality in practice | Roughly proportional in partisan contexts (Ireland); coalition-proportional in non-partisan contexts (Cambridge) |
| Strategic demands on voters | Moderate; honest ranking is generally optimal |
| Strategic demands on parties | Significant (nomination strategy, vote management) |
| Candidate incentive structure | Intra-party competition; rewards breadth of appeal across voter groups; constituency service emphasis |
| Monotonicity | Violated; ranking a candidate higher can cause them to lose |
| Ballot complexity | Moderate to high (ranking task; scales with candidate field size) |
| Transparency | Low; multi-round counting with fractional values is difficult to follow |
| Precinct summability | No; centralized tabulation required |
| Auditability | Requires full ballot data and algorithm replay; hand-countable in principle but laborious |
| Functions without parties | Yes -- the only widely used proportional system that does |
| Real-world track record | Extensive (Ireland since 1922, Australia, Scotland, Cambridge, Portland, historical U.S.) |

---

## Conclusion

This article evaluated Proportional RCV's structural consequences -- the properties, tradeoffs, and real-world performance that follow from the mechanical design examined in the previous article.

Proportional RCV's proportionality guarantee -- Droop proportionality for solid coalitions -- is formally strong but substantively different from the proportionality people often associate with the term "proportional representation." It guarantees representation for cohesive voter groups, not for parties. In partisan contexts, this distinction is often invisible: party supporters who rank co-partisans together form natural solid coalitions, and the system produces roughly party-proportional outcomes. In non-partisan contexts, the distinction is consequential: Proportional RCV provides proportional representation to any sufficiently large group of voters who share common preferences, regardless of whether those preferences align with party labels.

Proportional RCV's strategic profile is generally favorable. Honest voting is a good strategy for most voters. The known vulnerabilities -- free-riding, vote management, strategic truncation, and nomination strategy -- are real but difficult to exploit and rarely decisive.

The monotonicity violation is a structural consequence of combining sequential elimination with quota-based election and surplus transfer. It is the same type of violation documented for single-winner RCV in the previous series, extended to the multi-winner context. It is uncommon in practice but mathematically unavoidable within Proportional RCV's design framework. Methods that improve monotonicity -- Schulze STV, CPO-STV -- sacrifice computational tractability, confirming that the tension is genuine rather than incidental.

Proportional RCV's candidate incentive structures reward breadth of appeal across voter groups and create intra-party competition that distinguishes it from both bloc methods and party-list systems. The transfer mechanism encourages candidates to seek second and third preferences beyond their base, not only first-preference support within it.

The ballot complexity challenge is real and scales with the candidate field. Proportional RCV asks voters to rank across potentially large fields, and voter error rates interact with ballot design and voter experience. Equipment limitations that restrict ranking depth can amplify ballot exhaustion.

The transparency and auditability challenges are significant. Proportional RCV is the most widely used proportional system that cannot be verified from aggregate data alone. It requires centralized tabulation, full ballot data, and algorithm replay. This stands in tension with the democratic norm of publicly verifiable counting.

The real-world record is extensive and instructive. Ireland demonstrates long-term viability and candidate-centered politics. Australia demonstrates that administrative design choices can reshape Proportional RCV's character. Scotland demonstrates smooth voter adaptation. Cambridge demonstrates that Proportional RCV works without parties. The historical American experience demonstrates both Proportional RCV's representational power and the political forces that can challenge any electoral system that disturbs established patterns.

Proportional RCV occupies a distinctive position in the multi-winner design space. It is the only widely used proportional system that operates entirely through individual candidate rankings rather than party labels. The Introduction to this series noted that party-centered proportional systems -- party-list PR, MMP, and MMM -- are the dominant global approach to proportional representation and are deferred to a future series. Proportional RCV represents the candidate-centered alternative: proportionality achieved through the transfer mechanism itself, conditional on voter behavior, and embedded in a counting process that is complex but has proven administrable across more than a century of continuous use.

The next article introduces a different path to proportional representation -- one that requires neither ranked ballots nor party labels. Approval-based multi-winner methods achieve proportionality through the simplest possible ballot: approve or do not approve. The counting algorithms are recent, the formal properties are well-studied, and the design philosophy differs from Proportional RCV in ways that expand the design space further.

---

<!--
## Revision History

**Revision 1.5** (Current)
- Series-wide revision alignment with pr-08 reframe; article content unchanged from Revision 1.4

**Revision 1.4**
- Added revision history footer per formatting convention
- Article content unchanged

**Revisions 1.0 through 1.3**
- Development history prior to adoption of on-document revision tracking
- Final pre-convention state: seven numbered sections plus evaluation comparison table and conclusion covering Droop proportionality, strategic incentives, monotonicity, candidate incentive structures, ballot complexity and voter error rates, transparency and auditability, and real-world performance evidence
-->

*Revision history available in the raw file.*

> 📥 [Download this document](https://github.com/albertintech/voting-methods-explained/blob/main/src/pr-04-proportional-rcv-consequences.md) (opens on GitHub -- click the ⬇ download button)

---

*© 2026 Albert Ramos. All rights reserved.*
