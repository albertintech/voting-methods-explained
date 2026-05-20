# Voting Simulations

## Testing Systems Without Real Elections

---

## Statement of Purpose

The preceding articles in this series examined multi-winner voting methods by describing their mechanics, identifying their structural properties, and evaluating them against formal criteria: proportionality, monotonicity, ballot exhaustion, strategic incentives, and candidate incentive structures. Where real-world evidence was available -- Proportional RCV in Cambridge, bloc voting across American jurisdictions -- the articles drew on it. Where the operational record was thin -- Proportional Approval, Proportional Score, Proportional STAR -- the articles noted the gap.

That gap is not an accident. Most of the proportional methods examined in this series have limited real-world track records. Some have been used only in organizational elections. Some exist primarily in academic literature. Some have been proposed for governmental adoption but have never been tested at scale.

This creates a practical problem for the reader. How should one evaluate a voting method that has little or no operational experience? The formal properties are identifiable -- a method either satisfies monotonicity or it does not, either satisfies later-no-harm or it does not. But formal properties alone do not tell the reader how a method performs across a range of realistic conditions: different electorate sizes, different numbers of candidates, different levels of strategic behavior, different distributions of voter preferences. For that, the evaluative tool is simulation.

This article introduces voting simulations as a method of evaluation. It explains what simulations are, what they can reveal, what they cannot, and how to read simulation evidence critically when it appears in reform advocacy, academic research, or policy debate. The goal is not to reproduce specific simulation results -- the reader can consult the original studies for that -- but to equip the reader with the understanding needed to assess whether a simulation's findings are meaningful, limited, or misleading.

---

## Section 1: Why Simulations Exist

Elections are not experiments. A researcher studying the structural properties of Proportional STAR cannot run a controlled trial in which half of a state's congressional districts use Proportional STAR and the other half use Proportional RCV, with the same candidates, the same voters, and the same political conditions. Real elections happen once, with real stakes, real strategic behavior, and real consequences. There is no control group.

This creates an asymmetry in the evidence base. Methods with long histories of governmental use -- plurality, Proportional RCV in Ireland and Australia, party-list PR across Europe -- can be evaluated against decades of empirical data: actual election outcomes, measurable patterns of representation, documented strategic behavior by voters and candidates. Methods that are newer, less widely adopted, or proposed but not yet implemented cannot be evaluated that way. The evidence from actual elections does not yet exist.

Simulations address this gap by creating a controlled environment in which voting methods can be tested against synthetic electorates. The researcher defines a population of voters, gives each voter a set of preferences over a set of candidates, applies different counting methods to the same set of ballots, and compares the outcomes. Because the simulation controls the inputs, it can isolate the effect of the counting method itself -- holding the electorate constant and varying only the rule used to determine winners.

This is the core value of simulation: comparative evaluation under controlled conditions. It does not replace empirical evidence from real elections. It supplements it, and for methods that lack empirical records, it may be the most systematic evidence available.

---

## Section 2: What a Simulation Does

A voting simulation has three components: a voter model, a ballot generation process, and a set of counting methods to compare.

### The Voter Model

The voter model defines the simulated electorate. It specifies how many voters there are, how many candidates, and -- critically -- how voters' preferences are structured. This is where the most consequential design choices are made, because different voter models produce different preference structures, and those structures can favor or disfavor particular voting methods.

The most commonly used voter models fall into three families.

**Spatial models** place voters and candidates in a multi-dimensional "issue space." Each dimension represents a political issue or ideological axis. A voter's preference for a candidate is determined by the distance between them: voters prefer candidates who are closer to them in the issue space. The number of dimensions matters. A one-dimensional model (the conventional left-right spectrum) produces a very structured electorate with a clear center. A two-dimensional model (left-right and libertarian-authoritarian, for example) allows more complex preference patterns. Higher-dimensional models produce increasingly dispersed preferences.

**Impartial culture models** assign preferences completely at random: every possible preference ordering is equally likely for every voter. This is the simplest model and the most common in formal theoretical work. Its advantage is mathematical tractability. Its disadvantage is severe unrealism -- real electorates are not random. Voters cluster around shared concerns, and candidates position themselves in response. Impartial culture produces preference profiles that almost never occur in real elections, which can make simulation results based on it misleading about real-world performance.

**Clustered models** are a middle ground. They distribute voters in clusters within an issue space, reflecting the reality that voters tend to group around shared ideological positions. The number of clusters, their sizes, and their distances from one another are parameters the researcher controls. These choices matter: a model with two tight clusters produces a polarized electorate; a model with many dispersed clusters produces a fragmented one.

### Ballot Generation

Once the voter model defines each voter's preferences, the simulation translates those preferences into ballots. For a ranked-ballot system, this means generating a rank ordering of candidates for each voter. For a score-based system, it means assigning numerical scores. For an approval system, it means deciding which candidates each voter approves.

This translation step introduces its own assumptions. A voter in a spatial model who is equidistant from two candidates might rank them in either order. A voter generating a score ballot must decide how to use the scale: sincerely, strategically, or somewhere in between. The simulation must specify a behavioral model for each voter -- and that specification is itself an assumption.

The most common behavioral distinction is between honest voters and strategic voters. An honest voter translates their preferences directly into a ballot without considering how other voters will behave. A strategic voter considers the competitive environment -- which candidates are likely to win, which ballots will be wasted -- and adjusts their ballot to maximize their expected outcome.

Many simulations run the same electorate under both assumptions and compare the results. This is informative: it reveals how sensitive a method's performance is to strategic behavior. A method that performs well with honest voters but poorly with strategic voters has a structural vulnerability. A method that performs roughly the same under both conditions is more robust.

### Counting and Comparison

The simulation applies multiple counting methods to the same set of ballots and measures the outcomes against a chosen metric. Common metrics include:

**Voter Satisfaction Efficiency (VSE)** measures how closely a method's outcome matches the electorate's aggregate welfare. A method that always elected the candidate maximizing total voter satisfaction would score 100%. A method that elected a random candidate would score near 0%. Methods that consistently elect high-satisfaction outcomes score higher. VSE was developed to provide a single comparable number across methods and voter models.

**Bayesian Regret** measures the expected loss in voter welfare compared to the optimal outcome. It is the inverse of voter satisfaction: lower regret means better performance. A method that always elected the welfare-maximizing candidate would produce zero regret. Bayesian Regret was developed by Warren Smith and has been a central metric in comparative voting method research.

**Proportionality measures** assess how closely the elected committee reflects the electorate's preference distribution. In the multi-winner context, these include the justified representation axioms (JR, PJR, EJR) introduced in the Proportional Approval article. Simulations can test how frequently a method satisfies or violates these axioms across thousands of generated electorates.

**Candidate Incentive Distributions (CID)** measure what structural incentives a voting method creates for candidates. Rather than asking "which candidate wins?", CID analysis asks "which voters does a candidate have an incentive to appeal to?" This framework, developed by Ogren (2024), evaluates methods by the breadth or narrowness of the electorate a candidate must engage to improve their chances.

**Criterion compliance rates** test how frequently a method satisfies specific formal properties (monotonicity, Condorcet consistency, clone independence, and others) across a large number of simulated elections. A method that satisfies monotonicity in 100% of simulated elections has a perfect compliance rate for that criterion. A method that satisfies it in 95% of simulations has a high but imperfect rate. These rates provide empirical frequency data to supplement the theoretical question of whether a property holds in all cases.

---

## Section 3: What Simulations Can Reveal

Simulations are most informative when they are used comparatively -- testing multiple methods against the same electorate under the same conditions. This holds constant the factors that real elections cannot control (who the voters are, what they prefer, how many candidates run) and isolates the variable of interest: the counting method.

Several kinds of findings emerge from well-designed comparative simulations.

**Relative performance across methods.** Simulations can show that Method A consistently outperforms Method B on a given metric across a range of voter models. This is useful even if the absolute numbers depend on modeling assumptions, because the ranking of methods is often more stable than the specific scores. If Method A outperforms Method B under spatial models, impartial culture, and clustered models alike, the finding is robust to the choice of voter model.

**Sensitivity to strategic behavior.** By running the same electorate under honest and strategic voting assumptions, simulations reveal which methods are most affected by strategic behavior. A method whose performance degrades substantially when voters behave strategically has a structural vulnerability that the method's formal properties alone might not reveal.

**Edge cases and pathological outcomes.** Simulations that generate thousands or millions of elections can identify scenarios where a method produces counterintuitive results -- monotonicity failures, Condorcet failures, disproportionate outcomes. The frequency of these scenarios matters. A property violation that occurs in 0.01% of simulations is a different concern than one that occurs in 5%.

**Interaction effects.** Some structural properties interact in ways that are difficult to predict from theory alone. For example, the interaction between strategic exaggeration and reweighting under RRV produces a partial self-correction effect that the formal properties do not fully capture. Simulations can quantify these interaction effects by observing how methods behave when multiple factors vary simultaneously.

---

## Section 4: What Simulations Cannot Tell Us

Simulations are powerful tools, but they have structural limitations that no amount of computational power can overcome.

**Real strategic behavior.** Simulations model strategic voters by assuming a specific decision procedure: the voter observes polling information, calculates expected outcomes under different ballot choices, and selects the ballot that maximizes expected utility. Real voters do not perform this calculation. They rely on heuristics, partial information, social pressure, identity, habit, and emotion. The gap between modeled strategic behavior and actual strategic behavior is substantial and largely unmeasured.

This does not mean strategic behavior is irrelevant. The previous series established that strategic incentives are structural pressures created by the voting system's design. But simulations model the pressure at full rationality, which overstates the degree to which real voters respond to it. A simulation that shows significant performance degradation under strategic voting is identifying a real vulnerability -- but the severity in practice will likely be lower than the simulation suggests.

**Implementation and administration.** Simulations evaluate counting methods in a frictionless environment: every ballot is correctly filled out, every ballot is counted, every algorithm is executed perfectly. Real elections involve ballot design, voter education, tabulation equipment, poll worker training, legal challenges, recounts, and public trust. A method that performs beautifully in simulation may face practical obstacles that have nothing to do with its mathematical properties.

The series has already encountered this gap. Proportional RCV in Ireland is hand-counted, a process that works because of institutional tradition but would not scale easily to larger electorates. Proportional STAR requires centralized tabulation of individual ballot records, a logistical requirement that some election administrators may resist regardless of the method's proportionality properties.

**Voter comprehension and legitimacy.** Simulations cannot measure whether voters understand what the system is doing or whether they trust its outcomes. A method that produces optimal results by a mathematical standard may face political resistance if voters cannot follow the counting process. The previous series documented this concern for RCV, where the elimination-and-transfer process is sometimes perceived as opaque. Proportional methods with reweighting or allocation steps face similar comprehension challenges that simulations do not capture.

**The social and political environment.** Voting systems exist within political cultures, party systems, media environments, and legal frameworks. A method that works well in a nonpartisan city council election may behave differently in a highly partisan congressional election with national media attention and sophisticated campaign operations. Simulations can model the preferences of voters and candidates but cannot model the institutional context in which the election takes place.

---

## Section 5: The Assumptions That Matter Most

Every simulation result depends on the assumptions built into the voter model and the behavioral model. Two simulations that use different assumptions can produce different conclusions about the same voting method. Recognizing which assumptions matter most is the key to reading simulation evidence critically.

### The Voter Model

The choice of voter model is the single most consequential assumption in any simulation. A spatial model with normally distributed voters in two dimensions produces a different preference structure than an impartial culture model, which produces a different structure than a clustered model with four polarized groups.

For most voting methods, the relative performance ranking is reasonably stable across spatial models with different numbers of dimensions. A method that performs well in a two-dimensional spatial model usually performs well in a three-dimensional one. This is a reassuring finding -- it means the choice between two and three dimensions is unlikely to change the conclusion.

The exception is the impartial culture model. Because it generates completely random preferences, it produces preference profiles that are extremely unlikely in any real electorate. Results from impartial culture models should be interpreted as theoretical stress tests, not as predictions of real-world performance. A method that fails frequently under impartial culture may be fragile in adversarial conditions. A method that performs well under impartial culture has survived a demanding test. But neither finding transfers directly to predictions about real elections.

### The Behavioral Model

Whether voters are modeled as honest or strategic, and what strategic model is used, can change outcomes substantially for some methods. Approval voting is particularly sensitive: the strategic threshold decision (which candidates to approve) can dramatically alter which candidates win. Score-based methods are sensitive to the degree of exaggeration assumed: fully strategic voters who min-max their scores produce different outcomes than voters who exaggerate moderately.

The most informative simulations report results under multiple behavioral assumptions and show the sensitivity: how much does the result change when voters shift from honest to strategic? A large gap suggests a structural vulnerability. A small gap suggests robustness.

### The Number of Candidates and Seats

Multi-winner simulation results depend on the number of candidates, the number of seats, and the ratio between them. A five-seat election with eight candidates produces a different competitive environment than a five-seat election with twenty candidates. Methods that perform well with few candidates may struggle with many, and vice versa. Simulations that report results for only one configuration should be read with this caveat in mind.

### The Metric

Different metrics measure different things. Voter Satisfaction Efficiency measures aggregate welfare. Proportionality axioms measure group representation. Candidate Incentive Distributions measure structural incentives for candidates. A method can score well on one metric and poorly on another, because the metrics capture different values.

This is not a flaw in the metrics. It reflects the same lesson that has recurred throughout this series: voting systems embody design choices, and different design choices optimize for different values. A simulation that reports only VSE is measuring one dimension of performance. A comprehensive evaluation requires multiple metrics, just as a comprehensive evaluation of a voting method requires examining multiple structural properties.

---

## Section 6: How to Read Simulation Evidence

Simulation evidence appears in academic papers, reform advocacy materials, organizational reports, and policy debates. The reader will encounter it whenever proportional representation is discussed. The following guidelines help distinguish credible evidence from misleading claims.

### Check the Voter Model

If the simulation uses only an impartial culture model, the results may not apply to real electorates. Spatial models and clustered models are more realistic. The most credible simulations report results across multiple voter models and show that findings are consistent.

### Check the Behavioral Assumptions

If the simulation assumes only honest voters, the results may overstate a method's performance for methods that are vulnerable to strategic behavior. If it assumes only fully strategic voters, it may overstate the severity of strategic problems. The most informative simulations include both assumptions and report the sensitivity.

### Check Whether Multiple Metrics Are Reported

A simulation that reports only the metric on which a particular method performs best may be presenting a partial picture. Voter Satisfaction Efficiency favors methods that maximize aggregate welfare. Proportionality axioms favor methods designed for group representation. The most credible evaluations report multiple metrics and acknowledge that different methods may perform differently on different dimensions.

### Check the Source

Voting method simulations are produced by researchers, advocacy organizations, and system designers. Each of these sources can produce rigorous work, and each can produce work that reflects the priorities of its sponsor.

Academic researchers typically submit work for peer review, which subjects methodology and conclusions to scrutiny by other experts. This does not guarantee correctness, but it provides a quality filter.

Advocacy organizations -- including organizations that support specific voting methods -- sometimes produce simulation evidence in support of their preferred systems. This does not make the evidence wrong, but it means the reader should ask whether the simulation was designed to test the method fairly or to showcase its strengths. Were competing methods included? Were unfavorable metrics reported alongside favorable ones?

System designers sometimes produce simulation evidence for the methods they invented. The same caution applies: the work may be rigorous, but the reader should look for independent validation by researchers who did not design the system being tested.

### Check for Sensitivity Analysis

A sensitivity analysis varies the assumptions -- the voter model, the number of candidates, the behavioral model, the number of seats -- and shows whether the findings are stable. Simulations that report only a single configuration, with a single voter model and a single behavioral assumption, are less informative than those that demonstrate robustness across conditions.

The absence of a sensitivity analysis does not invalidate a finding. But its presence substantially strengthens one.

---

## Section 7: Notable Simulation Frameworks

Several simulation frameworks have produced evidence referenced throughout this series. This section briefly identifies them and notes what each measures, so the reader can recognize them when encountered in reform advocacy or academic literature.

**Bayesian Regret / Social Utility Efficiency.** Developed by Warren Smith, this framework measures the expected loss in aggregate voter welfare under different voting methods. It was one of the earliest systematic simulation-based comparisons of voting systems and remains widely cited. The framework uses spatial models with varying numbers of dimensions and includes both honest and strategic voter assumptions. It has been most extensively applied to single-winner methods.

**Voter Satisfaction Efficiency (VSE).** Developed by Jameson Quinn, VSE is a normalized version of the same aggregate-welfare concept: it scales results so that the optimal outcome scores 100% and a random selection scores approximately 0%. VSE simulations have been applied to both single-winner and multi-winner methods using spatial and clustered voter models with honest and viability-aware strategic voters. The framework has been published in peer-reviewed work in collaboration with other researchers.

**Candidate Incentive Distributions (CID).** Developed by Ogren (2024), this framework measures the structural incentives a voting method creates for candidates. Rather than evaluating outcomes (who wins), CID evaluates the incentive landscape: which voters does a candidate benefit from appealing to? The framework has been applied across multiple single-winner methods using spatial models and has demonstrated that methods differ substantially in whether they incentivize candidates to appeal broadly or narrowly.

**Criterion compliance testing.** Multiple research groups have conducted large-scale simulations that test how frequently specific voting methods satisfy formal criteria (monotonicity, Condorcet consistency, participation, and others) across generated electorates. Graham-Squire and McCune (2023) applied this approach to real ranked-ballot election data, testing RCV for monotonicity failures and other pathologies. Green-Armytage, Tideman, and Cosman (2016) conducted a broad statistical evaluation of voting rules using simulated data. These studies provide empirical frequency data that supplement the binary question of whether a method satisfies a criterion in all cases.

**Pivotal Voter Strategic Incentive (PVSI).** Developed by Wolk, Quinn, and Ogren (2023), this framework measures the strategic incentive for an individual voter to deviate from honest voting under different methods. It has been applied to single-winner methods, finding that STAR voting has a substantially lower strategic incentive than plurality or RCV, confined primarily to mild "honest inflation." The framework's findings are specific to single-winner contexts and do not transfer directly to multi-winner methods, though they inform the strategic analysis for methods that share the STAR ballot.

These frameworks are not interchangeable. Each measures a different dimension of voting method performance. A complete evaluation draws on multiple frameworks, just as it draws on multiple formal properties and whatever empirical evidence is available.

---

## Section 8: Simulations and the Multi-Winner Evidence Gap

The multi-winner methods examined in this series fall across a wide spectrum of empirical evidence.

At one end, Proportional RCV has been used in governmental elections for over a century. Ireland, Australia, Scotland, Cambridge, and Portland provide decades of operational data: real outcomes, real strategic behavior, real administrative experience, and real voter comprehension patterns. Evaluating Proportional RCV does not depend primarily on simulation -- there is enough empirical evidence to draw on.

At the other end, approval-based proportional methods (PAV, SPAV, MES) have almost no operational track record. The Method of Equal Shares has been used in a handful of European participatory budgeting processes. PAV and SPAV have not been used in any election. For these methods, simulation evidence and formal axiomatic analysis are the primary evaluative tools.

Score-based proportional methods occupy a middle position. RRV has been used in non-governmental contexts (the Academy Awards, Berkeley's referral prioritization). Proportional STAR has been used in one organizational election (DSA-LA) and proposed for federal congressional elections (CEMA). The operational evidence is thin but not absent.

Simulations become more important as the operational evidence becomes thinner. For Proportional RCV, simulations supplement a rich empirical record. For Proportional STAR, simulations are a primary source of comparative evidence. For PAV, simulations are nearly the only source.

This creates an asymmetry that the reader should recognize: the methods with the least empirical evidence are the ones most dependent on simulation evidence, and simulation evidence is inherently more assumption-dependent than empirical observation. This does not mean the less-tested methods are worse. It means the reader should hold the evidence for each method to the standard appropriate to its type: empirical evidence is evaluated by its representativeness and sample size; simulation evidence is evaluated by its modeling assumptions and sensitivity.

---

## Conclusion

This article introduced voting simulations as an evaluative tool for multi-winner voting methods. Simulations create controlled environments in which voting methods can be tested comparatively against synthetic electorates, revealing relative performance, sensitivity to strategic behavior, frequency of edge cases, and interaction effects that formal analysis alone cannot capture.

Simulations rest on assumptions -- about voter models, behavioral models, the number of candidates and seats, and the metrics used to evaluate outcomes. The most consequential assumption is the voter model: different models produce different preference structures, and those structures can favor or disfavor particular methods. The most informative simulations report results across multiple models and behavioral assumptions, demonstrate stability through sensitivity analysis, and present multiple metrics rather than selecting the one most favorable to a particular method.

Simulations cannot model real strategic behavior, administrative implementation, voter comprehension, or the social and political environment in which elections take place. They evaluate counting methods in an idealized environment. The gap between simulation and reality is real and irreducible. A method that performs well in simulation may face practical obstacles that simulation cannot anticipate. A method that performs poorly in simulation under one voter model may perform differently under another.

The series has now covered a progression of evaluative approaches: formal properties (monotonicity, proportionality axioms, later-no-harm), worked examples (demonstrating mechanics and outcomes in specific scenarios), empirical evidence (where available), and simulations (filling the gap where empirical evidence is thin). Each approach captures something the others miss. None is sufficient alone.

The reader is now equipped to evaluate any multi-winner voting method they encounter -- not just the specific methods examined in this series, but any system that might appear in a ballot measure, a legislative proposal, or a reform advocacy campaign. The Conclusion that follows synthesizes the series by design dimension: proportionality, ballot complexity, auditability, candidate incentives, and the recurring theme that no system satisfies all criteria simultaneously. That synthesis draws on everything the reader has learned -- mechanics, properties, evidence, and the tools to assess evidence critically.

---

*Prepared for the Voting Methods Explained -- Proportional Representation Series*
