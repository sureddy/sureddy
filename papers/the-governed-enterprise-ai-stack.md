
# The Governed Enterprise AI Stack, Version 2.0

*A Vendor-Agnostic Reference Architecture for Trusted Action, Human Agency, Recursive Self-Adaptation, and Regenerative Enterprise Performance, revised for the era of governed action.*

**Surendra Reddy, 451 Labs. June 30, 2026.**
*Version 2.0. Supersedes Version 1.0 (December 10, 2025). Vendor-agnostic. Change history tracked in Appendix A.*

## Executive Summary

This is a reference architecture, written to be vendor-agnostic. It names control points, capabilities, and standards rather than products, so that any enterprise can use it to evaluate its own systems and any provider against a neutral baseline. Where a market pattern is described, it is described by strategic archetype rather than by company, and the archetypes are set out in Appendix B.

Version 1.0 argued, in December 2025, that the enterprise AI stack does not end at agents. It ends at governed action that preserves human agency, learns safely, and regenerates enterprise capacity. That claim was a forecast. Six months later it reads as a description. This version records what changed, sharpens the architecture against that change, and tracks every revision in the appendices.

The change is best read as a pattern rather than a single event. Through the first half of 2026, every major category of enterprise platform converged on the same layer. Vendors anchored in the system of record, in cross-functional workflow, in identity and the workplace, in the customer relationship, in the cloud and the model, and in cross-system execution each began building a governance and orchestration layer for autonomous agents (Reddy, 2026f; Reddy, 2026i). At the same time the two connection protocols that agents rely on, one for reaching tools and data and one for coordinating with other agents, were both placed under neutral foundation governance, which means the coordination point could no longer settle at the protocol layer and had to move up to governance (Linux Foundation, 2025; A2A Project, 2025; Model Context Protocol, 2025).

When competitors across every category fortify the same layer, the convergence itself is the signal. It marks the place the ecosystem has decided it cannot route around. The 451 canon names that place the era of governed action, the third in a sequence after the era of the system of record and the era of the system of engagement (Reddy, 2026i). This paper is the architecture beneath that pattern, written so that it belongs to no single provider.

The load-bearing reason the layer matters is an asymmetry, not a trend. **A wrong answer is an inconvenience. A wrong action is a loss.** Model quality keeps improving and keeps commoditizing, yet the hard problem was never whether AI can produce an answer. It is whether AI can safely complete real work inside a real company, which takes context, identity, authority, memory, proof, exception handling, and a way to reverse harm. The enterprise does not buy intelligence in the abstract. It buys accountable outcomes (Reddy, 2026i).

Two failures bound the problem on either side. On one side, the skeptics are right that most agentic pilots fail: industry analysts expect more than 40% of agentic AI projects to be cancelled by the end of 2027, and research found that the large majority of enterprise AI pilots delivered no measurable return (Gartner, 2025; MIT NANDA, 2025). Those are not failures of intelligence. They are failures of deployment, data quality, ownership of edge cases, and governance, which makes the skeptic's evidence a bill of materials for the missing layer rather than a refutation of it. On the other side, success can be its own trap. When many firms run similar agents on similar data toward similar objectives, the result is convergence rather than advantage, a sameness named the agentic convergence trap (van Esch et al., 2026).

Version 2.0 therefore makes one addition to the spine of the argument. Governed action is not only a safety mechanism. It is a strategic instrument. The objective an agent optimizes is an expression of strategy, proprietary judgment matters more than proprietary data, and the control layer is where a company decides which friction to keep and how to stay recognizably itself while competitors optimize toward the same generic mean (Reddy, 2026e). The thirteen layers, seven planes, and two loops carry forward from Version 1.0. What follows updates them for a market that has moved from forecasting the governed-action layer to fighting over it.

# Part I: What Changed Since Version 1.0

## 1. From Reference Architecture to Contested Layer

Version 1.0 described a layer most of the market had not yet named. Version 2.0 describes a layer the market is now fighting to own. The intervening six months supplied three developments that, read together, point to the same place and justify a revision rather than a reprint.

### 1.1 Capability commoditized, and value moved to the interface

For about two years, capability was the prize. Build the smartest model, climb the benchmark, and the market was supposed to follow. That instinct went stale as open weights collapsed the price of a competent model and the gap between the best system and the second best narrowed in the ways a buyer feels. When the input becomes abundant, value moves to whatever stays scarce, and the scarce thing is the interface that makes intelligence dependable, governable, and economically useful, the layer where a capable model becomes a trusted action (Reddy, 2026j).

This reframes the strategic question for the whole stack. The contest is no longer which model reasons best. It is which layer becomes the route everyone must pass through, like the single step in a production chain that the rest of the chain cannot bypass. That layer is governance, and it is conspicuously unsolved: enterprise studies in 2026 found only about one in five organizations with a mature model for governing autonomous agents, even as task-specific agents spread into a large share of enterprise applications (Deloitte, 2026; Reddy, 2026j).

### 1.2 The protocols went neutral, so the coordination point moved up

In December 2025, the protocol that lets agents reach tools and data was donated to a newly formed agentic foundation under neutral, multi-party governance, joining the protocol that lets agents coordinate with one another, which had been placed under the same foundation family earlier in the year (Linux Foundation, 2025; A2A Project, 2025). A protocol deliberately handed to a neutral foundation cannot become any single provider's private chokepoint, so the coordination point cannot settle at the connection layer. It has to move one level up, to the governance of action.

### 1.3 The incumbents converged, which is the clearest signal of all

Across every strategic position, platform providers began building governance and orchestration on top of the open protocols rather than under them, racing for the layer that decides trust (Reddy, 2026i; Reddy, 2026j). When competitors converge on one layer the way an entire industry once converged on a single shared constraint, the convergence is the tell. Appendix B maps the strategy archetypes by center of gravity, control-plane move, and structural limit, without naming companies. The pattern across all of them is identical: whoever can answer, for every agent, who acted and under what authority, holds the next control point.

This is the architecture-level problem behind the market-level pattern. The era of governed action is the contest for the layer where AI, identity, memory, policy, permissions, audit, and execution finally have to meet (Reddy, 2026i). The rest of this paper specifies that layer and the stack it sits inside, in terms any provider or enterprise can implement.

## 2. The Core Thesis, Restated

The five claims of Version 1.0 hold. They are restated here with the emphasis the last six months earned, and with two additions promoted from supporting points to load-bearing ones.

**First, intelligence is not value until it becomes trusted action.** Capability is now abundant and cheap, which sharpens rather than softens the claim. The scarce, defensible thing is the governed interface where a capable model becomes an accountable outcome (Reddy, 2026j).

**Second, agents are not the top of the architecture.** Agents are situated actors inside a fabric of memory, context, authority, tools, humans, proof, and governance. The market validated this the hard way, through pilots that died not from weak models but from missing architecture (Gartner, 2025; MIT NANDA, 2025).

**Third, governance must operate at runtime.** Documentation, committees, and model cards remain necessary and remain insufficient. Governance now has to live in identity, policy engines, approval gates, and audit at the moment of action, which is exactly where the market is building.

**Fourth, adaptation must be governed.** Systems must improve without rewriting their mandate, authority, or safety envelope. The deeper lesson of 2026 is that generation has become cheap while verification has not, so the binding constraint on any self-improving system is proof (Reddy, 2026h).

**Fifth, human agency and regeneration are architectural requirements.** AI should expand human capacity and renew enterprise capability rather than hollow it out. In a flatter, more leveraged firm, governance has to live in the architecture because there are fewer humans standing between intent and execution (Reddy, 2025d).

Two additions are now part of the spine rather than the commentary. The first is that the objective an agent optimizes is an expression of strategy, not a neutral setting, because an agent told to chase generic efficiency will reproduce generic behavior (Reddy, 2026e). The second is that proprietary judgment matters more than proprietary data, since unique data still produces ordinary decisions when agents optimize toward ordinary goals. Both move governed action from a compliance concern to a strategic one.

## 3. The Era of Governed Action: The Strategic Frame

Three decades of enterprise software read as a sequence of contests over where control sits inside the company. Naming the sequence by its control point, rather than by the companies that won each round, keeps the frame durable and vendor-neutral (Reddy, 2026i).

**The era of the system of record.** Control sat with whoever owned the place where corporate truth lived, the database beneath applications, reporting, transactions, and decisions. Installed software had weight and permanence, and once a company tied its data to that core, the relationship became institutional gravity.

**The era of the system of engagement.** The premise was attacked rather than out-built. Software as a service moved the product to the vendor's cloud, turned deployment into a subscription, made upgrades routine, and handed more control to the business user. The front office became programmable, and for a while that felt like liberation.

**The era of governed action.** Every successful rebellion builds its own orthodoxy, and software as a service produced a new fragmentation: industry research puts the average large enterprise near a thousand applications, most of them unconnected, each with its own data model and permissions (Reddy, 2026i). A human clicking between those systems is merely inefficient. An agent moving across them without clear authority is a governance, security, compliance, and accountability question at once. That is the opening for the era of governed action.

The same progression appears from the system-of-record side as systems of record, then systems of insight, then systems of engagement, and now systems of autonomous execution (Reddy, 2026d). Whatever the vocabulary, the prize is the governed-action layer, and the reason is the asymmetry stated in the executive summary. A wrong answer is an inconvenience and a wrong action is a loss, so completing work safely takes more than intelligence. It takes context, identity, authority, memory, an audit trail, exception handling, and a way to roll back. The enterprise buys accountable outcomes, which is why the action layer is where durable power settles (Reddy, 2026i).

This contest will not resolve cleanly, because enterprise software rarely crowns a single winner. The likeliest outcome is a contested mesh of control planes rather than one throne. The direction is still unambiguous. The next strategic layer is governed action, and the stack that follows is the architecture an enterprise needs in order to stand inside that layer rather than be standardized by whoever owns it.

# Part II: The Stack, Version 2.0

The stack keeps its thirteen layers, numbered 0 to 12, because the foundations did not move. What moved is the weight on the upper layers, where the contest now sits. Layers that carry forward unchanged are stated briefly with their strategic question. Layers that changed materially carry a marker and a fuller treatment. The complete layer-by-layer change log lives in Appendix A.

```
12. Human Agency, Operating Model, and Regenerative Value      [expanded]
11. Enterprise Applications and Experience                     [reframed]
10. Recursive Self-Adaptation and Learning                     [expanded]
 9. Observability, Evaluation, and Assurance                   [expanded]
 8. Governance, Identity, and Control Plane                    [expanded]
 7. Agent and Activity Runtime                                 [carried forward]
 6. Protocol and Capability Fabric                             [updated]
 5. Memory and Context Assembly                                [carried forward]
 4. Inference and Model Runtime                                [carried forward]
 3. Model and Intelligence Layer                               [carried forward]
 2. Data, Context, and Knowledge                               [carried forward]
 1. AI Factory Infrastructure                                  [carried forward]
 0. Energy, Facilities, and Physical Infrastructure            [carried forward]
```

## 4. Layers 0 to 5 and 7: The Carried-Forward Foundations

These layers are stated in full in Version 1.0 and are summarized here so the stack reads as one document. Their logic did not change in the last six months, though the stakes on each rose as agents began to act.

**Layer 0, Energy, Facilities, and Physical Infrastructure.** AI starts with physical reality, and the scale remains large. The International Energy Agency still projects global data center electricity consumption more than doubling to roughly 945 TWh by 2030, with AI as the most important driver (International Energy Agency, 2025). The question is whether the enterprise can secure reliable, scalable, and responsible physical capacity for its workloads.

**Layer 1, AI Factory Infrastructure.** Physical capacity becomes computational production across accelerators, networking, storage, orchestration, and cloud, private, edge, and sovereign placement. The question is where computation runs and how capacity is governed across those environments.

**Layer 2, Data, Context, and Knowledge.** Data alone is not enough; agents need governed context and knowledge, since an agent acting on an outdated contract or ambiguous policy acts with confidence while being wrong. The most important word in the autonomous-enterprise conversation is not agent but context (Reddy, 2026d). The question is what is true, what it means, where it came from, and who may use it.

**Layer 3, Model and Intelligence Layer.** Enterprises operate model portfolios with risk tiers and lifecycle controls rather than a single-model choice, a point reinforced by capability commoditization. The question is which intelligence capability fits the task, risk, data context, authority envelope, and cost.

**Layer 4, Inference and Model Runtime.** Serving, routing, caching, and fallback determine whether a system is commercially viable, and routing remains a control surface as much as a performance lever. The question is how to serve, route, optimize, and control execution at production scale.

**Layer 5, Memory and Context Assembly.** Memory is not storage and context assembly is not retrieval; the layer decides what the system remembers, forgets, and carries into action, across session, user, domain, operational, decision, policy, and adaptation memory. The question is what context the system carries into action, and under what authority.

**Layer 7, Agent and Activity Runtime.** Intelligence becomes work across people, systems, documents, approvals, cases, and exceptions, not merely tool calls. The enterprise does not need autonomy everywhere; some work is advisory, some delegated, some human-led, and some should never be automated. The question is how intelligence becomes coordinated work across humans, agents, workflows, and systems.

## 5. Layer 6: Protocol and Capability Fabric

*Updated in v2.0: the connection layer matured and went neutral.*

Models and agents need structured ways to discover tools, data, workflows, and other agents. In Version 1.0 this layer was described as emerging. In Version 2.0 it has matured into shared infrastructure, which is precisely why it stopped being a place to win and became a place everyone builds on.

The protocol for connecting agents to tools and data now sits under a neutral, multi-party foundation, with more than ten thousand published servers and SDK adoption in the tens of millions of downloads per month (Linux Foundation, 2025; Model Context Protocol, 2025). The standard also hardened where enterprises needed it. A 2025 revision formalized servers as OAuth 2.1 resource servers and mandated resource indicators to prevent token misuse, a public registry launched for discovery, and a late-2025 specification added asynchronous tasks, server identity, elicitation, server-side agent loops, client identity through metadata documents, and an extensions system (Model Context Protocol, 2025). These are the features that turn a developer convenience into enterprise infrastructure.

The complementary standard for agent-to-agent coordination defines an agent card that advertises capability, a task with a defined lifecycle, a message exchanged between parties, and an artifact returned as output. It was placed under neutral foundation governance in mid-2025 and passed 150 organizations within a year, with a related agent-communication protocol merging into it (A2A Project, 2025; Reddy, 2026j). One standard connects an agent to its tools; the other connects an agent to other agents; both are now neutral ground.

**This layer includes:** tool and context servers and registries, agent cards, OAuth resource servers and scoped tokens, tool and skill catalogs, workflow and schema registries, connector gateways, service discovery, API and event contracts, and capability advertisements that also describe constraints, permissions, cost, risk, expected outputs, and proof obligations.

The architectural consequence is the central move of this revision. Because the connection layer is open and neutral, it cannot be owned, so the contested value moved up to the governance of action. The capability fabric is now the floor that the governed-action layer stands on.

> **Strategic question.** How do agents, models, tools, workflows, and systems discover and use each other under explicit contracts, on shared and neutral protocols?

## 6. Layer 8: Governance, Identity, and Control Plane

*Expanded in v2.0: agent identity became concrete and the control plane became the battlefield.*

Governance is the layer that turns AI from clever automation into enterprise infrastructure, and in the last six months it stopped being abstract. The unit of governance moved from the model to the actor. An enterprise agent may use several models, access internal systems, call external tools, coordinate with other agents, and recommend, approve, reject, negotiate, escalate, or execute. Governing it means governing machine behavior, which is a different responsibility than governing software outputs (Reddy, 2026e).

Agent identity became concrete rather than aspirational. The leading identity and workplace platforms now issue each agent its own identity, so that permissions, conditional access, and data-loss policies attach to the agent the way they attach to an employee, and the value of doing so showed up immediately. In one widely cited case, an enterprise that turned on agent-scope policies discovered that several of its agents held permission to delete files that no one had intended to grant (Reddy, 2026i). The connection protocols moved the same direction, with client identity through metadata documents and session-scoped authorization that expires when a task ends and cannot be renewed without a human (Model Context Protocol, 2025).

Standards bodies followed. The NIST AI Risk Management Framework and its Generative AI Profile remain the foundation (National Institute of Standards and Technology, 2023; Autio et al., 2024), and in early 2026 NIST's Center for AI Standards and Innovation announced an AI Agent Standards Initiative to address the governance gap that agents create when they acquire tool use and act autonomously in production (National Institute of Standards and Technology, 2026). Research on authenticated delegation continues to argue that authority should be explicitly delegated, agents should be identifiable, and delegated actions should produce records that support audit rather than after-the-fact guesswork (South et al., 2025).

**This layer includes:** agent, human, and workload identity, delegated authority, role-based and attribute-based access control, policy engines, approval gates, audit trails, compliance controls, model risk practices, data residency and content-safety controls, session-scoped and revocable authorization, and emergency brakes.

A governed agent must carry an authority envelope that defines what it may do and may not do, which tools and data it may reach, which outputs require review, which actions require human approval, and which conditions force escalation or shutdown. Version 2.0 promotes five questions to canonical status, because every control plane in the market is in the end an attempt to answer them for every agent it runs: who is acting, under what authority, toward what objective, within what boundaries, and with what evidence trail (Reddy, 2026e).

The strategic reframing matters as much as the mechanics. The control layer is not only a safety mechanism. It is what makes autonomy usable at enterprise scale and what preserves strategic intent, because the objective an agent optimizes is an expression of strategy and the policy boundaries are where a company keeps itself distinct from competitors converging on the same generic optimum (Reddy, 2026e).

> **Strategic question.** Who or what is allowed to act, under what authority, toward what objective, within what boundaries, with which controls, and with what evidence trail?

## 7. Layer 9: Observability, Evaluation, and Assurance

*Expanded in v2.0: agent observability standardized, and simulation joined evaluation.*

Agentic systems retrieve context, reason across steps, call tools, delegate, interact with humans, and produce artifacts, so observability must reach prompts, model calls, retrieved context, tool invocations, agent decisions, approvals, policy checks, costs, latency, errors, refusals, fallbacks, outputs, and outcomes. Two developments since Version 1.0 deepen this layer.

First, agent observability standardized. The OpenTelemetry semantic conventions for generative AI now cover not only model calls and token counts but agent spans, tool execution, and the agent-to-tool protocol itself, so a single trace can link an agent's decision through tool calls to a final result across heterogeneous systems (OpenTelemetry, 2025). This is the vendor-neutral instrumentation that delegation-aware audit requires (South et al., 2025). Platform vendors now market a single audit record across every process and command centers for agent health, which is the same idea expressed as product (Reddy, 2026f).

Second, simulation joined evaluation as a first-class discipline. Because agent behavior varies with input, context, model, tool choice, and process state, testing before production now means simulating success paths, failure cases, timeouts, edge cases, policy conflicts, incomplete data, unauthorized actions, tool failures, low-confidence reasoning, and downstream impact. Process simulation is the trust bridge between pilot and production, and it lets organizations replay incidents afterward as well (Reddy, 2026f). Evaluation, simulation, and assurance together answer whether the system works as intended, whether risk sits inside tolerance, and whether the organization can prove what happened.

In regulated settings this layer is the product, not a feature. The lesson from autonomous risk intelligence in financial crime is blunt: in a regulated context, auditability is the product, because the value is not only that an agent can recommend but that the institution can reconstruct which model ran, what data it saw, which scenario contributed, what an investigator accepted or overrode, and explain all of it to a regulator months later (Reddy, 2026c).

> **Strategic question.** Can the enterprise see, test, simulate, explain, audit, and improve AI behavior across steps, and prove what happened?

## 8. Layer 10: Recursive Self-Adaptation and Learning

*Expanded in v2.0: grounded in systems engineering and operated by ADAM, the Adaptive Development and Assurance Machine, with a five-level maturity model.*

Recursive Self-Adaptation is the governed counterpart to uncontrolled recursive self-improvement. A system may improve its instrumental structures, its prompts, retrieval, tool selection, thresholds, workflow patterns, evaluation tests, memory rules, and routing, while preserving its constitutional commitments, its mandate, identity, human authority, policy, and safety constraints. Version 2.0 grounds that distinction in systems engineering and names the constraint that makes it real.

Every complex system runs on two kinds of loops. Reinforcing loops amplify change and balancing loops hold it in check, and a system that lasts needs both. Recursive self-improvement hands the reinforcing loop over for free, because better systems help build better systems. The balancing loop is the part that must be designed on purpose, and it is the part that decides whether amplification stays ahead of understanding or runs past it (Reddy, 2026h). The governance loop in this layer is that balancing loop made operational.

This layer is the operating core of what the 451 canon now calls ADAM, the Adaptive Development and Assurance Machine, which supersedes the earlier learning-cycle framing (Reddy, 2026k). ADAM fuses two halves that an adaptive system cannot keep apart. Adaptive Development is the loop that learns from production and feeds that learning back into the build. Assurance is the function that brakes the loop so it cannot run away, delivered by a control function called the Governor. The loop is the engine that many teams are about to build; the Governor is the brake that lets the engine run unattended, and it is the harder and scarcer half.

The deeper lesson of 2026 is that the bottleneck moved. Generation became cheap while verification did not, so judgment became the scarce resource. When a system can generate change faster than anyone can review it, the constraint is no longer capability but proof: a clear account of what changed, what evidence drove it, which metrics improved, which risks were checked against them, who reviewed it, under which policy, and which tests confirmed the system did not get better in one place by getting worse in another (Reddy, 2026h). In regulated environments this is not optional. A model that cannot explain why it changed is a liability no matter how much it improved.

So Version 2.0 adds a proof architecture to this layer. Every meaningful adaptation must leave a record that survives scrutiny, and the system may propose adaptation but may never authorize its own expansion of authority. The basic loop is unchanged, but the governance step is now explicitly the place where proof is demanded before any change publishes.

```
Observe  →  Sense  →  Propose  →  Govern (prove)  →  Apply  →  Monitor  →  Learn
```

The Governor delivers that proof, and it works at two speeds because the failures of an adaptive loop arrive on two timescales. The routine brakes are automated, since the failures they catch are too fast and too frequent for a person to catch reliably, and hidden feedback loops are the leading documented cause of failure in machine learning systems (Sculley et al., 2015). Above them sits one emergency brake that a human always holds and that the system can never countermand, which is the interruptibility principle stated plainly: an operator must always be able to understand, oversee, and stop the system (Shavit et al., 2023).

| Routine brake (automated) | What it does |
| --- | --- |
| Drift halt | Pauses adaptation and reverts to last known-good when output quality or input distribution crosses a threshold. |
| Evaluation gate | Blocks promotion of any self-update or model change that regresses on fixed proof criteria. |
| Anomaly rollback | Rolls back to the previous version on a sharp behavioral anomaly and raises an alert. |
| Action ceiling | Refuses any action, tool, or data access outside the granted scope, the direct control on excessive agency. |
| Contamination filter | Quarantines feedback derived from the system's own outputs until reviewed, so the loop does not learn from its own exhaust. |

The design rule is simple. Automate every brake that is fast, frequent, and well understood, and reserve for a human every brake that is consequential, ambiguous, or irreversible. The emergency brake is rarely pulled, and its value is that it always can be, which is why assurance discipline includes testing it on a schedule rather than trusting that it exists.

ADAM advances along two axes at once, how much of the loop is closed and automated, and how trustworthy the Assurance is. The rule across every level is that development automation may advance only as far as the Assurance can be trusted to stop it. An enterprise earns the next level of autonomy by proving the brake, not by proving the engine (Reddy, 2026k).

| Level | Development and automation | Assurance state |
| --- | --- | --- |
| 1. Manual | Production learning fed back by hand, occasionally | A human watches dashboards. |
| 2. Instrumented | The return path is captured in a memory and learning layer | Manual rollback exists and is tested. |
| 3. Auto-braked | Routine adaptation is automated | Drift halt, evaluation gate, and rollback run automatically. |
| 4. Governed autopilot | Most of the loop runs unattended | Full Governor active, emergency brake human-held. |
| 5. Recursive, bounded | The machine proposes its own design changes | Governor gates every self-update; expansion needs human sign-off. |

The practical rule follows from the systems view. The systems worth worrying about are the ones that change faster than anyone can prove they should, so the adaptation loop must be paced to the speed at which its changes can be verified, not the speed at which they can be generated.

> **Strategic question.** How can the system improve itself while preserving human authority and policy boundaries, and prove that each change is safe before it applies?

## 9. Layer 11: Enterprise Applications and Experience, and the Interface as Strategy

*Reframed in v2.0: the interface is the coordination point, and pricing moved toward outcomes.*

This layer is where AI meets employees, customers, partners, regulators, and operators through copilots, conversational interfaces, embedded assistants, and workflow and service agents. Version 2.0 reframes it around a sharper idea: in every value chain there is one point everyone must pass through, and that point is where durable power settles (Reddy, 2026j).

After capability stops being scarce, the experience that matters is not the cleverest interaction but the most dependable coordination. The layer where a capable model becomes a trusted, repeatable, governable action is the interface worth owning, and it learns from use, because every governed action it records sharpens its policy, its risk posture, and its proof. Accountability has an unusual structural property here: a model provider cannot credibly grade its own agents and a single platform cannot neutrally certify the agents that compete with its own, which is exactly the gap a neutral position can occupy (Reddy, 2026j).

The economics moved with the architecture. Pricing is shifting from per-seat licensing toward charging for work the agent completes, which makes governed action the precondition for the outcome economy rather than a feature bolted onto it. No one will pay for a guaranteed outcome that cannot be audited, bounded, or reversed, so the experience layer and the governance layer are two views of the same thing (Reddy, 2026i).

Experience design still depends on role, context, trust, authority, and risk, and a polished interface still cannot compensate for weak context, unclear authority, or missing observability. What Version 2.0 adds is that the interface is a strategic position, not a presentation layer.

> **Strategic question.** Does AI meet people and other systems at the coordination point in the flow of work, dependably enough to sell the outcome and not only the tool?

## 10. Layer 12: Human Agency, Operating Model, and Regenerative Value

*Expanded in v2.0: the AI-Native Architect, the ADAM machine, and access versus agency.*

The final layer is where AI either strengthens the enterprise or hollows it out. Version 1.0 argued that human agency must be designed into the architecture rather than left to culture. Version 2.0 names the human role that does the designing and the loop that role governs.

The role is the AI-Native Architect, the person who designs where intelligence lives, what an agent may do, where humans stay accountable, and how the system learns without losing trust (Reddy, 2026b). The archetype sits beneath the senior technology executive who defines the intelligence architecture of the enterprise, and alongside the leadership posture that governs living systems of human and machine intelligence without surrendering judgment (Reddy, 2026g). As AI compresses coordination cost and thins mid-management, the individual contributor increasingly operates as an outcome node supported by a cluster of agents, and the scarce skill shifts from running people to designing the system they and their agents work inside (Reddy, 2025d). Leverage without architecture is instability with better margins, which is why this role is structural rather than optional.

The machine is ADAM, the Adaptive Development and Assurance Machine, which replaces the linear software development lifecycle for agentic work and supersedes the earlier learning-cycle framing (Reddy, 2026k). Its forward path builds the system through five moves, Signal, Shape, Build, Prove, and Govern, each with a decision gate. Its return path closes production back into design, so the next version is shaped by what the last version actually did. Its Governor brakes the whole loop. ADAM is the human-facing expression of the two loops in Part III, and the AI-Native Architect is the role accountable for it, including the one override a human always holds.

Version 2.0 also sharpens what is at stake for people. Access to AI is becoming widespread, but access to a tool is not the same as agency over a system. A worker can use a capable assistant and still be screened by an opaque hiring model, priced by an opaque claims engine, or ranked by a system they cannot inspect, so the deepest inequality of this era is the gap between those who shape intelligent systems and those whose lives are shaped by systems they cannot contest (Reddy, 2025b). The same record that lets a board audit an agent is the record that lets an employee or customer challenge one, which means governed action and accountable agency are the same architecture seen from two directions.

**This layer includes:** AI strategy, portfolio governance, the AI-Native Architect role, process and role redesign, decision rights and override mechanisms, workforce development, the ADAM operating machine and its human-held emergency brake, value measurement, delegation architecture owned at board level, risk ownership, funding models, and the due-process structures that let affected people contest automated outcomes.

ADAM makes the short list of human-owned decisions explicit, so that automation stops exactly where accountability begins. A human owns the decision to release into a context where the system can act on money, customers, compliance, or brand; the acceptance of risk when proof is incomplete and the deployment proceeds anyway; any expansion of the system's authority or action space; the emergency brake; and the integrity of the return path, the judgment of whether captured learning is real or contaminated. Everything else can run on agents. These few decisions are where accountability lives, and accountability does not delegate to a machine that adapts (Reddy, 2026k). The human-factors record is blunt about why this holds even when the machine is good, because the dominant failure of capable automation is overreliance, where operators stop monitoring a system they have come to trust (Parasuraman & Riley, 1997).

Delegation, finally, is a boardroom matter. Once agents influence pricing, credit, hiring, compliance, capital allocation, or clinical workflow, boards need visibility into which categories of decision are delegated, under what authority, with what controls, and with what evidence of oversight, because the algorithm did it will not be an adequate defense and the burden will shift toward demonstrable governance (Reddy, 2026e).

> **Strategic question.** Did intelligence become trusted action, did it expand human agency and enterprise capacity rather than deplete them, and can the people it affects contest it?

# Part III: Operating Planes and Loops

## 11. The Cross-Cutting Operating Planes

The seven planes carry forward from Version 1.0 and cut across every layer. Three of them gained weight in the last six months and are updated here; the others, FinOps, Resilience, and Human Agency, are unchanged in logic and are stated briefly.

### 11.1 Security Plane, updated

The OWASP Top 10 for LLM Applications still names prompt injection as the leading risk and excessive agency as a distinct one, and the agentic year made both concrete (OWASP, 2025). Security must now account for agent identity, insecure tool use, sensitive-data exposure, poisoned context, unauthorized delegation, and unsafe action chains, with session-scoped and revocable authority as a primary control rather than an afterthought. The same identity work that governs an agent is the work that secures it.

### 11.2 Governance Plane, reframed as strategic

Governance must reach data, models, memory, protocols, tools, agents, workflows, humans, and outcomes, and a policy that cannot influence retrieval, tool access, authority, routing, or execution is documentation. Version 2.0 adds that governance is also where strategy is protected, since the objective function an agent optimizes and the boundaries it respects are how a company stays recognizably itself while competitors converge (Reddy, 2026e). Strategic divergence becomes a governed asset rather than an accident of human inconsistency.

### 11.3 FinOps, Resilience, and Human Agency Planes, carried forward

The FinOps plane keeps agents from becoming financially unbounded across tokens, inference, routing, retries, and tool calls. The Resilience plane keeps the system operating safely under failure through fallbacks, graceful degradation, human takeover, and rollback. The Human Agency plane asks, of every layer, whether the system makes people more capable or more dependent, preserves judgment, explains itself, allows override, and protects dignity and accountability.

### 11.4 Recursive Self-Adaptation Plane, carried forward with a hardened rule

Every layer emits adaptation signals, from cost and quality to accuracy, execution, judgment, exceptions, and value. The plane turns those signals into governed improvement and enforces one rule without exception: the system may propose adaptation, but it may not unilaterally expand its own authority. Version 2.0 adds that no adaptation publishes without proof.

### 11.5 Regeneration Plane, upgraded to a leverage discipline

Regeneration asks whether each cycle of activity renews or depletes the enterprise across human capability, trust, knowledge, process health, capital discipline, resilience, stakeholder value, and environmental responsibility. Version 2.0 grounds the plane in a leverage discipline, Regenerative Systems Thinking, which extends Donella Meadows's leverage points to twenty-one and adds a level of Agentic Intelligence Levers: agency and autonomy, intent alignment, learning and model evolution, human sovereignty, and interoperability and protocols (Reddy, 2025f; Meadows, 1999). These map directly onto the governance, adaptation, human-agency, and protocol layers of this stack.

The plane also inherits the operating spine of the Regenerative Prosperity Model: five domains, Self, Community, Design, Nature, and Capital, connected by trust, verified by proof, and renewed through stewardship (Reddy, 2025e). Read against the era of governed action these are not soft ideas. Trust is what a control plane is for, proof is what an audit record produces, and stewardship is the difference between an enterprise that compounds capability and one that optimizes itself hollow. Regeneration is what keeps governed action from becoming extraction with better margins.

## 12. The Two-Loop Architecture and ADAM

The stack runs on two loops that are connected but never collapsed, now mapped explicitly onto the human operating loop of Layer 12. The first turns intelligence into work.

```
Sense  →  Contextualize  →  Reason  →  Act  →  Explain  →  Learn  →  Govern
```

The second improves how the work is performed, with proof demanded before any change applies.

```
Observe  →  Sense  →  Propose  →  Govern (prove)  →  Apply  →  Monitor  →  Learn
```

ADAM, the Adaptive Development and Assurance Machine, is how a person builds and governs both loops at once (Reddy, 2026k). Its forward path produces the system, its return path feeds production learning back into the build, and its Governor brakes the whole loop.

```
Signal  →  Shape  →  Build  →  Prove  →  Govern    (forward path, each move gated)
```

These are no longer separate phases handed between teams. They are one machine in which humans and agents both participate, and the AI-Native Architect is the role accountable for it. The governance boundary between adapting methods and rewriting mandate is the single most important design feature of the whole architecture. A system that adapts its methods is valuable. A system that can rewrite its own mandate without human authority is dangerous, and the Governor, expressed as proof plus a human-held emergency brake, is what keeps the first from becoming the second.

# Part IV: Convergence on the Governed-Action Layer

## 13. How the Market Converged, by Strategy Archetype

The clearest evidence for this architecture is that the market is building it from every direction at once. Rather than name companies, this section describes the strategy archetypes from which the governed-action layer is being approached, because the architecture should outlast any particular vendor's roadmap. Appendix B records each archetype with its center of gravity, control-plane move, and structural limit.

The pattern is what matters. Each archetype reaches the governed-action layer from a different position of strength, and each can credibly claim only part of it. A provider anchored in the system of record knows business semantics best, a workflow platform governs cross-functional work best, an identity platform attaches policy to actors best, a customer-relationship platform knows customer context best, a model-and-cloud provider brings intelligence and scale together, and a cross-system execution platform reaches the messy work that lives across old screens, documents, and manual approvals (Reddy, 2026f; Reddy, 2026i). No single position can self-supply neutral accountability over agents that compete with its own, which is the structural opening this architecture is designed to fill (Reddy, 2026j).

One execution-side architecture is worth abstracting as a pattern, because it captures the full operating model cleanly. It organizes autonomy into four layers: secure and manage at the bottom, reason and think above it, orchestrate and execute above that, and build and interact on top, with one audit record across every process and simulation before production (Reddy, 2026f). Read against this stack, those four layers compress its thirteen: control and identity at the base, intelligence and context in the middle, governed execution above, and human-facing outcomes on top. The convergence of independent architectures on the same shape is itself a confirmation of the shape.

The honest read returns to the asymmetry. Broad execution reach is not deep domain understanding, deep domain understanding is not neutral accountability, and neutral accountability is exactly what no incumbent can grant itself. The contested whitespace is therefore the neutral governance of action across providers, which is the layer this reference architecture specifies and the reason it is written to belong to none of them.

# Part V: Readiness, Implementation, and Standard

## 14. Enterprise Readiness Checklist, Version 2.0

The checklist carries forward and gains rows for the capabilities that became load-bearing in 2026: agent identity, simulation, outcome measurement, and the human architect role. It is written so an enterprise can score itself and any provider against the same neutral questions.

| Layer or capability | Readiness question |
| --- | --- |
| Energy and physical infrastructure | Do we understand the physical, regional, energy, and resilience dependencies of our AI workloads? |
| Data, context, and knowledge | Do we know which data, definitions, and sources are authoritative, and is context governed? |
| Model portfolio | Do we have an approved portfolio with risk tiers and lifecycle controls as capability commoditizes? |
| Memory and context assembly | Can we govern what agents retrieve, remember, forget, and reuse? |
| Protocol and capability fabric | Do we build on neutral, open protocols with OAuth, scoped tokens, and registries? |
| Agent identity | Does every consequential agent have a distinct identity with scoped, revocable, session-bound authority? |
| Governance and control plane | Can we answer, for every agent: who is acting, under what authority, toward what objective, within what boundaries, with what evidence? |
| Observability and assurance | Can we trace agent steps on neutral conventions and keep one audit record across processes? |
| Simulation | Do we simulate success, failure, edge, and policy-conflict paths before production, and replay incidents after? |
| Recursive self-adaptation (ADAM) | Can the system improve without expanding its own authority, and does every change publish only with proof? |
| Assurance and the Governor | Do routine brakes (drift halt, evaluation gate, rollback, action ceiling, contamination filter) run automatically, and is a human-held emergency brake tested on a schedule? |
| Interface and outcomes | Do we own the coordination point well enough to price and stand behind completed outcomes? |
| Human agency and architecture | Do we have AI-Native Architects, board-level delegation oversight, and a path for affected people to contest outcomes? |

## 15. Implementation Path and the Regenerative Standard

The path from Version 1.0 holds and now runs as ADAM's forward path: Signal the constraint worth solving and the baseline to beat, Shape the workflow and the authority model and the proof criteria, Build to the approved design with logging and brakes present from the start, Prove the system earned the right to operate, and Govern it in production under the Governor (Reddy, 2026k). Version 2.0 adds two practical emphases. Bind the authority envelope to a distinct agent identity from the start, because identity is now the control surface the whole plane hangs on, and add a simulation gate before production, because behavior that varies with context cannot be trusted on the strength of a demo (Reddy, 2026f).

The Govern move does not end the work; it opens the return path, so production becomes the richest source of design signal the system will ever have. Advance along the ADAM maturity model deliberately, from manual feedback to an instrumented return path to automated routine brakes to governed autopilot to a bounded recursive machine, and hold to the one rule that governs the whole climb: development automation may advance only as far as the Assurance can be trusted to stop it (Reddy, 2026k).

The standard for judging the result is unchanged and now better supported by evidence. A mature enterprise AI architecture should be judged by whether it regenerates enterprise capability, not by how many agents it runs. It should make the enterprise clearer rather than more confused, people more capable rather than more dependent, processes simpler rather than more brittle, and governance more real rather than more performative. The pilots that failed across 2026 failed this test, not an intelligence test, which is why the regenerative standard and the governed-action layer are the same requirement stated twice (Gartner, 2025; MIT NANDA, 2025).

There is also a strategic version of the standard that the agentic year made unavoidable. Governed autonomy asks whether delegated work stays aligned with the enterprise's purpose, risk posture, and competitive position, not merely whether work was done faster. A company that governs autonomy well remains unmistakably itself while its competitors optimize toward the same generic mean, and a company that does not will be fast, predictable, and eventually indistinguishable (Reddy, 2026e; van Esch et al., 2026).

## 16. Conclusion: The Stack Ends at Governed, Regenerative Action

Energy powers compute, compute serves models, and models reason over context. Context flows through memory, memory informs agents, and agents invoke capabilities over neutral protocols. Capabilities change workflows, workflows require authority, and authority requires governance. Governance requires observability and simulation, observability enables adaptation, and adaptation requires proof and human oversight. Human agency turns automation into responsible action, and regeneration turns responsible action into durable enterprise capacity. That was the architecture in Version 1.0, and it is the architecture now, with the upper layers carrying more weight because that is where the market moved.

The year between the two versions resolved the open question of Version 1.0. The governed-action layer is no longer a forecast. It is the contested layer of the present era, the place every category of provider is racing to own and the place an enterprise must architect deliberately if it is to act through autonomous systems without losing accountability, context, memory, and control. Capability commoditized, the protocols went neutral, and the prize moved up to governance, exactly where this stack places it. Because the architecture belongs to no provider, an enterprise can use it to hold every provider to the same standard.

**The stack does not end at models. It does not end at tools. It does not end at agents. It does not end at protocols. It ends at governed, regenerative action, and that is where the next enterprise will be built.**

# Appendices

## Appendix A. Change Log: Version 1.0 to Version 2.0

This appendix records every material change from the December 10, 2025 reference architecture to this revision, with the reason for each. Layers and planes not listed are carried forward unchanged in logic. All references are neutral standards, research, or the author's framework essays; no commercial vendor is cited as authority.

| Layer or element | What changed in v2.0 | Why it changed |
| --- | --- | --- |
| Stance | Made the document explicitly vendor-agnostic; market patterns expressed as strategy archetypes (Appendix B). | A reference architecture must hold any provider to a neutral baseline rather than anchor on products. |
| Framing | Added the era-of-governed-action frame as the third in a control-point sequence after the systems of record and engagement. | Every category of provider converged on the governed-action layer in H1 2026, validating the v1.0 thesis (Reddy, 2026i). |
| Thesis | Promoted two supporting claims to load-bearing: the objective function is strategy, and proprietary judgment outweighs proprietary data. Added capability commoditization. | Open weights collapsed model price; value moved to the governed interface (Reddy, 2026e; 2026j). |
| Layer 6 Protocol | Tool-and-data and agent-to-agent protocols placed under neutral foundation governance; OAuth 2.1, resource indicators, registry, async tasks, server identity, elicitation, client-identity metadata, extensions. | The connection layer matured and went neutral, pushing the contested layer up to governance (Linux Foundation, 2025; Model Context Protocol, 2025; A2A Project, 2025). |
| Layer 8 Governance | Agent identity made concrete (per-agent identity, scoped and session-bound authority); five governance questions made canonical; NIST agent standards work added; control plane reframed as strategic. | Identity became the control surface and the battlefield; standards bodies opened agentic work (NIST, 2026; South et al., 2025). |
| Layer 9 Assurance | Added standardized agent observability and process simulation as a first-class discipline; auditability named as the product in regulated settings. | Agent behavior varies with context, so simulation and trace standards became prerequisites for production (OpenTelemetry, 2025; Reddy, 2026c; 2026f). |
| Layer 10 Adaptation | Grounded the two-loop distinction in reinforcing and balancing loops; named proof as the binding constraint; adopted ADAM (Adaptive Development and Assurance Machine) as the operating construct, with its Governor (routine automated brakes plus a human-held emergency brake) and a five-level maturity model. | Generation became cheap while verification did not; ADAM supersedes the earlier learning-cycle framing and names the brake explicitly (Reddy, 2026h; 2026k; Sculley et al., 2015; Shavit et al., 2023). |
| Layer 11 Experience | Reframed around interface as strategy and the outcome economy; pricing shifts from per-seat to completed work. | After capability stops being scarce, the coordination point is where power settles (Reddy, 2026j; 2026i). |
| Layer 12 Human Agency | Added the AI-Native Architect role, the ADAM machine and its human-held emergency brake, ADAM's explicit list of human-owned decisions, access-versus-agency, firm compression, and board-level delegation ownership. | The human role that designs and governs the architecture had to be named, delegation became a governance matter, and overreliance makes the human brake non-negotiable (Reddy, 2026b; 2026k; 2026e; Parasuraman & Riley, 1997). |
| Governance Plane | Reframed from safety mechanism to strategic instrument; strategic divergence treated as a governed asset. | Objective functions and boundaries are how a firm stays distinct amid convergence (Reddy, 2026e; van Esch et al., 2026). |
| Regeneration Plane | Grounded in Regenerative Systems Thinking (21 leverage points, five Agentic Intelligence Levers) and the RPM domains with trust, proof, and stewardship. | The regeneration logic needed an operating discipline that maps onto the stack (Reddy, 2025f; 2025e). |
| Two-Loop / ADAM | Mapped the two loops onto ADAM, with its forward path (Signal, Shape, Build, Prove, Govern), return path, and Governor; added the prove step and the human-held emergency brake to the governance loop. | The loops needed a human-facing operating machine and an explicit proof-plus-brake gate; ADAM provides both (Reddy, 2026k; 2026h). |
| Naming correction | Retired the ADLC and Autonomous Design and Learning Cycle labels throughout in favor of ADAM (Adaptive Development and Assurance Machine). | The canon updated ADLC to ADAM, which fuses Adaptive Development with Assurance rather than describing a learning loop alone (Reddy, 2026k). |
| Readiness Checklist | Added rows for agent identity, simulation, interface and outcomes, and the human architect role. | These capabilities became load-bearing during the agentic year. |
| New Part IV | Added a vendor-agnostic market-pattern section and a strategy-archetype map (Appendix B). | To capture the autonomous-enterprise convergence of 2026 without anchoring on named vendors. |

## Appendix B. Control-Plane Strategy Archetypes

This map describes the positions from which the governed-action layer is being approached, by archetype rather than by company. It is the vendor-agnostic form of the market analysis: an enterprise can place any provider into one or more of these archetypes and read its likely strengths and limits.

| Archetype | Center of gravity | Control-plane move and structural limit |
| --- | --- | --- |
| System-of-record core | Business truth and transactional semantics | Grounds agents in the record that books the money, with the most consequential actions human-confirmed. Strongest where the process lives inside the record; weaker across systems it does not own. |
| Workflow fabric | Cross-functional workflow and service management | Offers a control tower to govern, secure, and measure any agent, model, or workflow, including third-party agents. Governs work well; understands deep domain semantics less. |
| Identity and workplace | Identity and the place work already happens | Issues a distinct identity per agent so policy attaches to the actor. Strong where work originates on its surface; dependent on reach into other systems. |
| Customer-relationship platform | Customer data and engagement | Routes agent actions through a trust layer that checks policy, grounding, and privacy before completion. Strongest where customer context dominates. |
| Model-and-cloud provider | Model and cloud together | Packages model, agent builder, and governance, and backs cross-vendor agent protocols. Brings intelligence and scale; carries less system-of-record gravity. |
| Cross-system execution platform | Execution across fragmented systems | Runs a four-layer autonomy stack with one audit record across processes and simulation. Broad reach across messy work; broad reach is not deep semantics. |
| Frontier-model provider | Raw intelligence and developer adoption | Ships agent frameworks and protocols from the model side. Powerful, but capability commoditizes and value moves up to governance. |
| Governance and observability challenger | The neutral whitespace itself | Builds agent identity, governance, observability, evaluation, simulation, memory, and compliance as cross-provider infrastructure. Must reach production scale and trust. |

The shared structure is decisive. Each archetype can credibly claim part of the governed-action layer from its position of strength, and none can neutrally certify the agents that compete with its own. That structural gap, neutral accountability over agents, is the contested whitespace this architecture is built to occupy.

## Appendix C. Protocol Evolution Timeline (2025 to mid-2026)

The connection layer matured quickly, and the timeline below records the developments that turned the two agent protocols from developer conveniences into neutral enterprise infrastructure, which is what moved the contested layer up to governance. Protocols and foundations are named because they are open standards, not vendor products.

| Date | Development |
| --- | --- |
| Nov 2024 | An open standard for connecting AI applications to tools and data is introduced (Model Context Protocol, 2025). |
| Mar 2025 | The tool-and-data protocol adds Streamable HTTP and OAuth 2.1, broadening enterprise viability (Model Context Protocol, 2025). |
| Apr 2025 | An agent-to-agent coordination protocol is published, with agent cards, tasks, messages, and artifacts (A2A Project, 2025). |
| Jun 2025 | The tool-and-data protocol formalizes servers as OAuth resource servers with resource indicators; the agent-to-agent protocol moves under neutral foundation governance (Model Context Protocol, 2025; A2A Project, 2025). |
| Sep 2025 | A public registry launches for discovering tool-and-data servers; the agent-to-agent protocol passes well over 100 organizations (Model Context Protocol, 2025; Reddy, 2026j). |
| Nov 2025 | A major specification release adds async tasks, server identity, elicitation, server-side agent loops, client-identity metadata documents, and extensions (Model Context Protocol, 2025). |
| Dec 2025 | The tool-and-data protocol is donated to a neutral, multi-party agentic foundation under the Linux Foundation (Linux Foundation, 2025). |
| H1 2026 | The first official extension ships; the agent-to-agent protocol passes 150 organizations with broad cloud integration (Model Context Protocol, 2025; Reddy, 2026j). |

## Appendix D. Framework Cross-Walk

This appendix maps the stack onto the broader analytical canon that grew up around Version 1.0 and now uses it as a foundation. These are analytical frameworks and theses under validation, the author's own conceptual vocabulary, not commercial products. Any working names attached to ventures in shaping are explorations under validation, not offerings.

| Framework construct | Relationship to the stack |
| --- | --- |
| The era of governed action | The market-level name for the architecture-level problem this stack specifies: the contest for the governed-action layer (Reddy, 2026i). |
| AI-Native Architect | The human role at Layer 12 that designs and governs the whole architecture (Reddy, 2026b). |
| ADAM (Adaptive Development and Assurance Machine) | The governed operating machine for the two loops in Part III: a forward path (Signal, Shape, Build, Prove, Govern), a return path that closes production into design, and the Governor that brakes the loop, with a five-level maturity model. Supersedes the earlier learning-cycle framing (Reddy, 2026k). |
| The Governor | ADAM's Assurance function at Layers 9, 10, and 12: automated routine brakes plus one human-held emergency brake, the mechanism this stack calls the balancing loop and the proof gate (Reddy, 2026k). |
| Regenerative Systems Thinking | The leverage discipline beneath the Regeneration plane; its Agentic Intelligence Levers map onto Layers 8, 10, and 12 (Reddy, 2025f). |
| Regenerative Prosperity Model | The operating spine of the Regeneration plane: five domains connected by trust, verified by proof, renewed through stewardship (Reddy, 2025e). |
| Autonomous risk intelligence | The regulated proving ground for Layer 9, where auditability is the product (Reddy, 2026c). |
| Working venture names | Names attached to theses in shaping around the governed-action layer; explorations under validation, not built or shipped systems (Reddy, 2026j). |

## Appendix E. Method, Sources, and Writing Note

**Vendor neutrality.** This revision names open standards, neutral foundations, and research and standards bodies, because those are shared infrastructure. It does not name commercial vendors as authorities or examples; where a market position is relevant it is described by strategy archetype (Appendix B). Findings originally reported about specific products are restated generically.

**Argument structure.** Version 1.0 led with thesis-and-kill-signal supported by pattern accumulation. Version 2.0 inverts the emphasis to match the evidence: it leads with pattern accumulation, the convergence of every category of provider and both protocols on the governed-action layer, supported by cost-of-error asymmetry, the difference between a wrong answer and a wrong action.

**Date discipline.** Version 1.0 bounded its sources to on or before December 10, 2025. Version 2.0 extends the window to June 30, 2026 and incorporates the developments of the intervening period. Where a figure is an analyst projection or a research estimate, it is presented as such.

**Writing mandate.** The document uses no em dashes, holds paragraphs to a readable length with one idea each, varies sentence length deliberately, and frames venture names as theses under validation rather than products. En dashes appear only in reference page ranges.

## References

*Sources span on or before June 30, 2026. Only neutral standards, foundations, research, and the author's framework essays are cited; no commercial vendor is cited as authority.*

A2A Project. (2025). *Agent2Agent (A2A) protocol specification.* Linux Foundation. https://a2a-protocol.org

Autio, C., Schwartz, R., Dunietz, J., Jain, S., Stanley, M., Tabassi, E., Hall, P., & Roberts, K. (2024). *Artificial intelligence risk management framework: Generative artificial intelligence profile* (NIST AI 600-1). National Institute of Standards and Technology. https://doi.org/10.6028/NIST.AI.600-1

Deloitte. (2026). *State of AI in the enterprise 2026.*

Gartner. (2025, June 25). *Gartner predicts over 40% of agentic AI projects will be canceled by end of 2027* [Press release]. https://www.gartner.com/en/newsroom

International Energy Agency. (2025). *Energy and AI* (World Energy Outlook special report). IEA. https://www.iea.org/reports/energy-and-ai

Linux Foundation. (2025, December 9). *Linux Foundation announces the formation of the Agentic AI Foundation (AAIF)* [Press release]. https://www.linuxfoundation.org/press

Meadows, D. H. (1999). *Leverage points: Places to intervene in a system.* The Sustainability Institute.

MIT NANDA. (2025). *The GenAI divide: State of AI in business 2025.* MIT Media Lab, Project NANDA.

Model Context Protocol. (2025). *Specification (2025-11-25) and protocol history.* https://modelcontextprotocol.io/specification

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)* (NIST AI 100-1). https://doi.org/10.6028/NIST.AI.100-1

National Institute of Standards and Technology. (2026). *AI Agent Standards Initiative.* Center for AI Standards and Innovation (CAISI).

OpenTelemetry. (2025). *Semantic conventions for generative AI, agents, and tool protocols.* Cloud Native Computing Foundation. https://opentelemetry.io/docs/specs/semconv/gen-ai/

OWASP. (2025). *OWASP Top 10 for large language model applications (2025).* OWASP GenAI Security Project. https://genai.owasp.org

Parasuraman, R., & Riley, V. (1997). Humans and automation: Use, misuse, disuse, abuse. *Human Factors, 39*(2), 230–253. https://doi.org/10.1518/001872097778543886

Reddy, S. (2025b, July 26). *The AI class structure: Inequality, agency, and power in the age of machine intelligence.* 451 Ventures.

Reddy, S. (2025d, November 3). *AI-native organization design 2030: Structural compression, human augmentation, and the redesign of the firm.* 451 Ventures.

Reddy, S. (2025e, November 30). *Regenerative Prosperity Model 2.0: From regenerative philosophy to regenerative operating system.* 451 Ventures.

Reddy, S. (2025f, December 29). *Regenerative systems thinking for the agentic enterprise: 21 leverage points for governing intelligence, capital, and life.* 451 Ventures.

Reddy, S. (2026b, March 24). *The AI-native architect: A new human archetype for the age of agentic enterprise.* 451 Ventures.

Reddy, S. (2026c, May 11). *Architecting trust: From agentic AI to autonomous risk intelligence.* 451 Ventures.

Reddy, S. (2026d, May 13). *The autonomous enterprise as a market signal: From systems of record to systems of autonomous execution.* 451 Ventures.

Reddy, S. (2026e, May 14). *Beyond agentic AI: The case for the governed autonomous enterprise.* 451 Ventures.

Reddy, S. (2026f, May 19). *The architecture of the autonomous enterprise: A four-layer autonomy stack.* 451 Ventures.

Reddy, S. (2026g, May 29). *Level 6 leadership: The leadership model for the age of agentic enterprise.* 451 Ventures.

Reddy, S. (2026h, June 7). *Recursive self-improvement and the ancient problem of control.* 451 Ventures.

Reddy, S. (2026i, June 10). *The era of governed action: The software contest after the systems of record and engagement.* 451 Ventures.

Reddy, S. (2026j, June 22). *Interface as strategy.* 451 Ventures.

Reddy, S. (2026k, June). *ADAM: The Adaptive Development and Assurance Machine.* 451 AI Company (a 451 Ventures company).

Sculley, D., Holt, G., Golovin, D., Davydov, E., Phillips, T., Ebner, D., Chaudhary, V., Young, M., Crespo, J.-F., & Dennison, D. (2015). Hidden technical debt in machine learning systems. In *Advances in Neural Information Processing Systems 28* (pp. 2503–2511).

Shavit, Y., Agarwal, S., Brundage, M., Adler, S., O'Keefe, C., Campbell, R., Lee, T., Mishkin, P., Eloundou, T., Hickey, A., Slama, K., Ahmad, L., McMillan, P., Beutel, A., Passos, A., & Robinson, D. G. (2023). *Practices for governing agentic AI systems.* OpenAI.

South, T., Marro, S., Hardjono, T., Mahari, R., Whitney, C., Greenwood, D., Chan, A., & Pentland, A. (2025). *Authenticated delegation and authorized AI agents* (arXiv:2501.09674). https://arxiv.org/abs/2501.09674

van Esch, P., Cui, Y. G., & Black, J. S. (2026, May 13). *Beware the agentic convergence trap.* Harvard Business Review.
