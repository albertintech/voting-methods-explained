# Multi-Winner Methods

## What We Learned

---

## Statement of Purpose

This Part examined five methods that extend single-winner logic to fill multiple seats. Each method modified the ballot or counting process in a different way, producing different structural properties and different representational outcomes.

This article synthesizes the spectrum those methods form, identifies the pattern that unites them, and asks the question that motivates the next Part of the series.

---

## The Spectrum

The five methods share a common foundation: they all take familiar ballot formats and counting rules and apply them to multi-winner elections. What distinguishes them is how many votes each voter receives, whether those votes can be concentrated, and what ballot information is collected.

**Bloc Voting** is the baseline. Each voter receives as many votes as there are seats. The top vote-getters win. A cohesive majority captures every seat -- the sweep effect in its purest form. Bloc voting is not a reform proposal. It is the existing default in thousands of American jurisdictions.

**Limited Voting** reduces the number of votes below the number of seats. The counting rule is identical to bloc voting, but the majority can no longer cover every seat at full strength. The sweep effect is softened, and structural space opens for minority representation -- contingent on strategic coordination.

**Cumulative Voting** preserves the number of votes but allows concentration. A voter may give all their votes to a single candidate. This creates a mathematical guarantee of proportional representation for any group that can coordinate effectively -- a self-help mechanism that limited voting does not provide.

**SNTV** gives each voter exactly one vote -- the simplest possible multi-winner ballot. Different voters must go to different candidates, creating natural vote division but placing the most intense coordination demands on parties and voters. SNTV also introduces intra-party competition: candidates from the same faction compete directly for individual votes.

**Multi-Seat STAR** uses the expressive score ballot and the two-phase STAR process (scoring round plus automatic runoff) applied seat by seat. The sweep effect remains structurally possible, but the winners are consensus-oriented rather than merely plurality-preferred. The expressive ballot changes the quality of the majoritarian outcome without changing the majoritarian structure.

---

## Comparison Table

| Dimension | Bloc Voting | Limited Voting | Cumulative Voting | SNTV | Multi-Seat STAR |
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

## Strategy, Not Structure

Across all five methods, one pattern held: **proportionality, where it occurred, was a product of strategy, not structure**.

No counting rule within these methods adjusts the outcome to reflect the distribution of voter support. Under bloc voting and Multi-Seat STAR, no proportional outcome is possible at all -- the majority fills every seat. Under limited voting, cumulative voting, and SNTV, proportional outcomes are achievable -- but only if minority groups coordinate their behavior effectively. The counting rule itself does nothing to ensure that seats are distributed in proportion to votes.

This is the fundamental limitation shared by every method in this Part. The system creates conditions. The voters and parties must do the work. When coordination succeeds, minorities achieve representation. When it fails, they may be shut out entirely. The system does not distinguish between the two outcomes -- it processes the votes the same way regardless.

This limitation is not a flaw that could be fixed with better ballot design. The Multi-Seat STAR article demonstrated that an expressive score ballot collects far more information than a simple choose-one or choose-many ballot. But that information does not produce proportional outcomes, because the counting logic does not use it to adjust seat allocation. The ballot format determines what information is available. The counting logic determines what the system does with it.

---

## The Prior Question

The Introduction to this Part introduced **goal-relative evaluation**: the principle that a method's structural properties are desirable or problematic only relative to the election's goal. The articles that followed applied this principle to each method individually. The Conclusion applies it across the full spectrum.

### When the Sweep Effect Serves the Purpose

There are elections where majoritarian selection is the right structural choice. A primary election advancing top candidates, a steering committee selecting consensus members, a deliberative body choosing from a pre-screened slate -- in each case, the goal is to fill every seat with candidates who command broad or majority support. The sweep effect is the system delivering on that goal.

When the sweep is appropriate, the choice of method still matters. Bloc voting selects the candidates with the most supporters. Multi-Seat STAR selects the candidates who are broadly acceptable and confirms each through a majority-preference check. The character of the majoritarian winners differs even though the majoritarian structure is the same.

### When the Sweep Effect Undermines the Purpose

There are also elections where the sweep effect is the wrong structural outcome. A legislative body representing a diverse electorate, a jurisdiction with geographically concentrated minority communities, any election whose goal is proportional representation -- in these contexts, a system that gives one faction all the seats and shuts out everyone else fails the election's purpose.

In these contexts, no method examined in this Part is structurally adequate. The semi-proportional methods (limited voting, cumulative voting, SNTV) create space for minority representation, but they place the burden on voters and parties to use that space effectively. A minority group that lacks the organizational infrastructure to manage its votes may be shut out even under a system that theoretically permits proportional outcomes.

The problem is not the quality of the majoritarian outcome. The problem is that a majoritarian outcome -- of any quality -- is the wrong goal for the election.

---

## What Proportionality Requires

The methods in this Part demonstrated what multi-winner elections can look like when proportionality depends on strategy. The next Part examines what happens when proportionality is built into the counting rule itself.

True proportional representation -- where the distribution of seats reflects the distribution of voter support by design, not by accident of coordination -- requires a fundamentally different counting mechanism. The key structural element is one that no method in this Part contains: a mechanism that reduces the influence of voters whose preferred candidates have already been elected.

When a voter helps elect a candidate, that voter has achieved representation. If the same voter participates at full strength in the next round, they have a structural advantage over voters who have not yet elected anyone. Proportional systems address this by reweighting ballots, transferring surplus votes, or allocating voter influence across rounds -- ensuring that voters who have already been represented contribute less to subsequent seat decisions. This creates structural space for unrepresented groups not through strategic coordination, but through the counting rule itself.

These mechanisms require conceptual tools that single-winner methods did not need: algorithms, quotas, surplus handling, and ballot reweighting. The next Part builds that toolkit and examines the proportional systems that depend on it.

---

## The Frame, Revisited

The single-winner Part established that voting systems reflect priority choices. No single-winner system satisfies all desirable criteria simultaneously. Understanding the tradeoffs is structural literacy.

This Part extended that principle to multi-winner elections and added a new dimension: the choice between majoritarian and proportional outcomes. The methods examined here make that choice in different ways -- from bloc voting's decisive majoritarianism to SNTV's strategy-dependent semi-proportionality. But none of them makes proportionality a structural guarantee.

The question is no longer just who should win, or even how representation should be distributed.

It is whether the system itself should guarantee that the distribution of seats reflects the distribution of voter support -- or whether that outcome should depend on the strategic behavior of voters and parties.

The next Part examines methods that answer: the system should guarantee it.

---

<!--
## Revision History

**Revision 1.1** (Current)
- Added revision history footer per formatting convention
- Article content unchanged from Revision 1.0

**Revision 1.0**
- Initial publication as part of the three-section site architecture transition
- Six descriptive H2 sections covering the multi-winner spectrum, comparison table, strategy versus structure, the prior question of election goals, what proportionality requires, and the frame revisited
-->

*Revision history available in the raw file.*

> 📥 [Download this document](https://github.com/albertintech/voting-methods-explained/blob/main/src/mw-06-conclusion.md) (opens on GitHub -- click the ⬇ download button)

---

*© 2026 Albert Ramos. All rights reserved.*
