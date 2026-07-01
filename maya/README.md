# Sutra

**An AI-native Agent Communication Fabric for governed enterprise intelligence**

Sutra is a communication layer for agent societies, built for the moment when AI stops being a single assistant answering a prompt and becomes a network of specialized agents discovering each other, delegating work, negotiating responsibility, and acting inside real enterprise systems.

It is not a replacement for A2A or MCP. It sits above both, backward compatible with each, and adds what neither fully provides: governed identity, authority, commitment, context lineage, proof, memory scope, policy enforcement, human agency, and recursive adaptation.

## Why this exists

Agent-to-agent (A2A) solves interoperability between independent agent systems: discovery, agent cards, tasks, messages, artifacts. MCP solves tool and context access: how an agent reaches external data, tools, and prompts through a standard interface. Classic Agent Communication Language, especially FIPA ACL, contributed something older and still correct: communication between agents is intentional. A request, an assertion, a proposal, and a refusal are different acts, not interchangeable payloads.

Each protocol solves a real piece of the problem. None of them, alone or together, gives an enterprise what it needs to let agent societies act with accountability. That gap is what Sutra is for.

## The core thesis

The next agent communication layer has to carry intent, authority, context, commitment, proof, and adaptation, not just messages and tool calls.

A message between agents shouldn't just say *"review this contract."* It should say who is asking, under what authority, with what context boundaries, promising what in return, with what evidence required, and whether a human has to sign off before anything final happens. That distinction, a bare task versus a governed commitment, is the difference between messaging and governed intelligence.

## Architecture: nine planes

Sutra organizes agent communication into nine planes. Together they define how agents identify themselves, advertise what they can do, exchange intent, carry context, make commitments, follow policy, produce evidence, remember appropriately, and improve over time.

| Plane | Governs |
|---|---|
| **Identity** | Verifiable agent identity via an Agent Passport (extends A2A's Agent Card with owner, runtime, trust tier, certifications, and domain boundaries) |
| **Capability** | What an agent can do, as a governed contract, not a marketing claim: inputs, outputs, authority level, confidence thresholds |
| **Intent** | Communicative acts modernized from ACL performatives (ASK, TELL, DELEGATE, COMMIT, NEGOTIATE, ESCALATE, REPAIR, and more) |
| **Context** | Context lineage: what's attached, where it came from, who's allowed to read it, delegate it, or retain it |
| **Commitment** | Who promises what, to whom, under what conditions, by when, with what happens on failure |
| **Policy** | Whether a communication or action is allowed at all: domain rights, delegation limits, tool access, human gates |
| **Proof** | Evidence, tool logs, confidence, uncertainty, and verification recommendations attached to outcomes |
| **Memory** | Six scopes from ephemeral to enterprise, defining what may be remembered, where, and for how long |
| **Adaptation** | How communication failures and human overrides feed back into governed, approved improvement, not silent self-rewriting |

## What a Sutra message actually carries

Compare a plain task handoff to a Sutra envelope:

```json
{ "from": "agent_a", "to": "agent_b", "task": "review this contract" }
```

against:

```json
{
  "from": "procurement-agent",
  "to": "legal-risk-agent",
  "act": "DELEGATE",
  "intent": "Assess contract risk before vendor approval",
  "authority": "recommend_only",
  "context_scope": "confidential_contract_review",
  "commitment": "return evidence-backed risk assessment",
  "proof_required": true,
  "human_gate": "required_before_final_approval"
}
```

The full envelope combines identity, intent, authority, context, commitment, policy, and proof requirements into a single portable message, one that degrades gracefully to a plain A2A task or MCP tool call for systems that don't speak Sutra natively.

## Backward compatibility

Sutra doesn't ask the ecosystem to replace anything.

- **A2A**: every Sutra Agent Passport exposes an A2A-compatible Agent Card. Every delegation can be represented as an A2A task, with Sutra's governance data riding along as metadata or artifacts. A2A-native agents can ignore what they don't understand and still process the task.
- **MCP**: Sutra agents consume MCP tools, resources, and prompts directly, and can expose their own capabilities as MCP tools so non-Sutra clients can call them. Context Packs reference MCP resources by URI with lineage, sensitivity, and retention rules layered on top.
- **ACL**: Sutra acts map cleanly onto FIPA performatives (DELEGATE to request, COMMIT to agree, REFUSE to refuse), so ACL-inspired systems can interpret Sutra communication as the speech acts it actually is.

Nothing has to choose Sutra to talk to a Sutra agent. Sutra just has more to say when the other side is listening.

## Human agency

Sutra treats human intervention as a first-class communicative act, not a UI bolt-on. Requester, approver, reviewer, steward, exception handler, domain oracle, policy owner, auditor, teacher: these are roles the protocol itself understands. A human override is a structured message with a reason, and it can trigger a governed adaptation event rather than disappearing into a log.

## Relationship to the 451 architecture

Sutra is the thread that connects the rest of the stack:

| Component | Role |
|---|---|
| **Atma** | Agentic core and execution intelligence |
| **Ana** | Memory, context, and knowledge substrate |
| **Pola** | Policy language and governance rules |
| **Actra** | Governed autonomy operating plane |
| **Astra** | Strategic reasoning and thesis generation |
| **Ananta** | Recursive self-adaptation layer |
| **Sutra** | Communication fabric connecting all of the above |

Atma acts. Ana remembers. Pola governs. Actra controls autonomy. Astra reasons. Ananta adapts. Sutra is what lets them talk to each other with meaning, proof, and responsibility, instead of just passing JSON back and forth.

## Roadmap

1. **Compatibility layer** — adapters for A2A Agent Cards, task/message/artifact mapping, MCP tool invocation, ACL performative mapping
2. **Sutra envelope** — the core message format: identity, act, intent, authority, context, commitment, policy, proof, memory
3. **Registries** — Agent Passport Registry, Capability Registry, Context Pack Registry, Policy Bundle Registry, Proof Ledger, Commitment Store
4. **Governance runtime** — policy enforcement, delegation control, human approval gates, memory scope enforcement, audit trails
5. **Adaptation layer** — failure capture, override capture, proof quality scoring, governed learning loops, Ananta integration

## Status

Sutra is a working design, not a shipped protocol. It's the specification for how agent societies should communicate once they're doing more than answering prompts, developed as part of the governed AI architecture work under 451 Labs.

---

*Sutra: An AI-Native Agent Communication Fabric, backward compatible with A2A and MCP, semantically grounded in ACL, and designed for the next era of enterprise agent societies.*
