# Sutra: An AI-Native Agent Communication Fabric

## A Technical Paper for Backward-Compatible Agent Interoperability Across A2A, MCP, and ACL

## Abstract

Large language model based agents are rapidly moving from isolated assistants into distributed societies of specialized systems that discover one another, exchange intent, invoke tools, negotiate responsibilities, and act across enterprise environments. Current protocols solve important but incomplete parts of this problem. Agent2Agent, or A2A, focuses on interoperability among independent agent systems through concepts such as Agent Cards, messages, tasks, parts, and artifacts (A2A Project, 2025). MCP standardizes how AI applications connect to external tools, resources, prompts, and data through secure two-way interfaces (Model Context Protocol, 2025a). Classic Agent Communication Language, especially FIPA ACL, introduced the critical idea that agent communication should represent communicative acts such as request, inform, propose, agree, refuse, and failure, not merely transport payloads (Foundation for Intelligent Physical Agents, 2001).

This paper proposes **Sutra**, a next-generation AI-native Agent Communication Fabric designed for enterprise-grade, multi-agent intelligence. Sutra is not a replacement for A2A or MCP. It is a higher-order communication fabric that remains backward compatible with both. It uses A2A for agent-to-agent interoperability, MCP for agent-to-tool and agent-to-context access, and ACL as the semantic foundation for intent-bearing communication. Sutra adds the missing enterprise primitives: governed identity, authority, commitment, context lineage, proof, memory scope, policy enforcement, human agency, and recursive adaptation.

The result is a communication fabric that allows agents to exchange not only messages, but also bounded commitments under explicit authority, policy, context, and verification constraints.

## 1. Introduction

The first generation of AI agents was interface-driven. A user asked a model to complete a task, and the model responded. The second generation is tool-driven. Agents can now retrieve data, call APIs, modify systems, generate code, and execute multi-step workflows. The third generation will be society-driven. Agents will discover other agents, delegate work, negotiate, verify results, escalate uncertainty, and coordinate with humans across complex enterprises.

This shift creates a new infrastructure problem. Enterprises cannot safely operate agent societies using only tool calls, chat messages, event buses, or loosely structured JSON. Agent communication must become governed, auditable, semantically meaningful, and interoperable across vendors, models, runtimes, tools, and human decision structures.

A2A addresses part of this need by creating an open protocol for communication and interoperability between independent agent systems. Its specification defines concepts such as Agent Cards, messages, tasks, parts, and artifacts to support collaboration across opaque agent applications (A2A Project, 2025). MCP addresses another part by standardizing how LLM applications connect to external tools, data sources, resources, and prompts (Model Context Protocol, 2025a). FIPA ACL contributes a deeper semantic foundation by treating communication as speech acts with performatives such as request, inform, propose, agree, refuse, and cancel (Foundation for Intelligent Physical Agents, 2001).

Sutra integrates these ideas into a single AI-native fabric.

## 2. Design Thesis

The central thesis of Sutra is simple:

**The next agent communication layer must communicate intent, authority, context, commitment, proof, and adaptation, not only messages and tool calls.**

A message between agents should not merely say:

```json
{
  "from": "agent_a",
  "to": "agent_b",
  "task": "review this contract"
}
```

It should say:

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

That distinction is the difference between messaging and governed intelligence.

## 3. Lessons From A2A, MCP, and ACL

## 3.1 Lessons From A2A

A2A’s most important contribution is that it treats agents as independent systems, not merely tools. It supports interoperation across different frameworks, languages, vendors, and runtimes. The protocol’s core concepts include agent discovery, Agent Cards, tasks, messages, parts, and artifacts (A2A Project, 2025).

Sutra keeps these strengths. In Sutra, A2A becomes the default compatibility layer for agent discovery, agent cards, task transport, message exchange, and artifact movement.

However, A2A by itself does not fully solve enterprise governance. It can tell one agent how to interact with another, but it does not sufficiently model decision authority, context lineage, durable commitments, proof requirements, memory boundaries, human agency, and recursive learning.

## 3.2 Lessons From MCP

MCP’s central contribution is standardization of tool and context access. It enables LLM applications to connect to external data sources, tools, services, prompts, and resources through a common protocol rather than bespoke integrations. MCP allows servers to expose tools that can be invoked by language models and defines a standardized way to connect LLM applications with the context they need (Model Context Protocol, 2025a, 2025b).

Sutra keeps MCP as the tool and context access substrate. An agent inside Sutra should not invent its own tool interface when MCP already provides a common pattern.

However, MCP is primarily about agent-to-tool and application-to-resource interaction. It is not a complete social contract for agent societies. It does not fully define how one agent should delegate authority to another, how context should propagate across agent chains, how proof should be attached to decisions, or how communication failures should feed adaptation.

## 3.3 Lessons From ACL

Classic ACL’s enduring insight is that agent communication is intentional. A request, an assertion, a proposal, a refusal, and a commitment are different acts even when they involve the same content. FIPA communicative acts capture this distinction through performatives such as accept-proposal, agree, cancel, query-if, query-ref, refuse, and others (Foundation for Intelligent Physical Agents, 2001).

Sutra modernizes this idea for LLM-native systems. It extends speech-act communication into enterprise-grade intent, delegation, verification, and adaptation.

## 4. Sutra Architecture Overview

Sutra is a nine-plane communication fabric:

1. Identity Plane
2. Capability Plane
3. Intent Plane
4. Context Plane
5. Commitment Plane
6. Policy Plane
7. Proof Plane
8. Memory Plane
9. Adaptation Plane

Together, these planes define how agents identify themselves, advertise capabilities, exchange intent, carry context, make commitments, follow policy, produce evidence, remember appropriately, and improve over time.

## 5. Plane 1: Identity Plane

The Identity Plane gives every agent a verifiable identity. A2A Agent Cards are a strong starting point, but enterprise systems require a richer construct: the **Agent Passport**.

An Agent Passport includes:

```json
{
  "agent_id": "did:agent:451.legal-risk.v3",
  "display_name": "Legal Risk Agent",
  "owner": "451 Ventures",
  "runtime": "atma-runtime",
  "vendor": "internal",
  "model_lineage": ["gpt-5.5", "legal-risk-classifier-v2"],
  "trust_tier": "enterprise-critical",
  "certifications": ["soc2", "internal-approved"],
  "allowed_domains": ["contract_review", "risk_extraction"],
  "forbidden_domains": ["final_legal_approval"],
  "valid_from": "2026-06-30",
  "valid_until": "2027-06-30"
}
```

The passport extends the A2A Agent Card rather than replacing it. For backward compatibility, the passport can expose an A2A-compatible Agent Card view.

## 6. Plane 2: Capability Plane

The Capability Plane defines what an agent can do, under what conditions, with what inputs, outputs, constraints, and authority.

A capability is not a marketing claim. It is a governed contract.

```json
{
  "capability_id": "cap.contract_risk_review.v2",
  "name": "Contract Risk Review",
  "inputs": [
    "contract_text",
    "jurisdiction",
    "risk_policy"
  ],
  "outputs": [
    "risk_summary",
    "clause_findings",
    "approval_recommendation"
  ],
  "authority_level": "recommend_only",
  "requires_human_approval": true,
  "minimum_confidence": 0.85,
  "compatible_protocols": ["sutra", "a2a", "mcp"]
}
```

Backward compatibility with A2A is achieved by mapping this capability into the A2A Agent Card capability fields. Backward compatibility with MCP is achieved by exposing selected capabilities as MCP tools when the agent is acting as a callable service.

## 7. Plane 3: Intent Plane

The Intent Plane modernizes ACL performatives for LLM-native systems.

Sutra defines the following core communicative acts:

```text
ASK
TELL
REQUEST
PROPOSE
ACCEPT
REJECT
COMMIT
DELEGATE
NEGOTIATE
VERIFY
CHALLENGE
REFUSE
ESCALATE
CANCEL
REPAIR
REMEMBER
FORGET
ADAPT
```

Each act has a formal meaning.

For example:

```json
{
  "act": "DELEGATE",
  "intent": {
    "goal": "Assess vendor contract risk",
    "success_criteria": [
      "identify high-risk clauses",
      "cite evidence",
      "assign risk score",
      "flag human review requirements"
    ],
    "priority": "high"
  }
}
```

This is backward compatible with ACL because Sutra acts can be mapped to FIPA-style performatives.

Example mapping:

| Sutra Act | FIPA ACL Equivalent      | Meaning                                    |
| --------- | ------------------------ | ------------------------------------------ |
| ASK       | query-if / query-ref     | Ask for a fact, reference, or condition    |
| TELL      | inform                   | Assert information                         |
| REQUEST   | request                  | Ask another agent to perform an action     |
| PROPOSE   | propose                  | Offer a plan or action                     |
| ACCEPT    | accept-proposal / agree  | Accept a proposal or agree to act          |
| REJECT    | reject-proposal          | Reject a proposed action                   |
| REFUSE    | refuse                   | Decline to perform an action               |
| CANCEL    | cancel                   | Cancel a previous request                  |
| ESCALATE  | failure / proxy / inform | Transfer or raise unresolved condition     |
| COMMIT    | agree                    | Promise to perform under stated conditions |

## 8. Plane 4: Context Plane

The Context Plane governs what context is attached, referenced, retrieved, transformed, retained, or passed onward.

MCP gives Sutra its backward-compatible context access mechanism. Sutra does not replace MCP resources, prompts, or tools. It wraps them in context lineage.

```json
{
  "context_pack": {
    "context_pack_id": "ctx.vendor_contract_123",
    "sources": [
      {
        "type": "mcp_resource",
        "uri": "mcp://contracts/vendor-123",
        "hash": "sha256:9d82...",
        "sensitivity": "confidential",
        "allowed_use": ["read", "extract", "summarize"],
        "retention": "30_days",
        "delegation_allowed": false
      }
    ],
    "memory_scope": "task_local",
    "privacy_policy": "enterprise-default"
  }
}
```

The Context Plane prevents uncontrolled context propagation. An agent may be allowed to read a document without being allowed to pass it to another agent, store it in memory, or use it to train an adaptation loop.

## 9. Plane 5: Commitment Plane

The Commitment Plane is one of Sutra’s most important additions.

Agent systems should not only exchange tasks. They should exchange commitments. A commitment states who promises what, to whom, under what conditions, by when, with what failure behavior.

```json
{
  "commitment": {
    "commitment_id": "com.vendor_risk_001",
    "from": "did:agent:451.legal-risk.v3",
    "to": "did:agent:451.procurement.v2",
    "promise": "Return evidence-backed supplier contract risk assessment",
    "conditions": [
      "contract_text_available",
      "jurisdiction_provided",
      "risk_policy_access_granted"
    ],
    "due": "2026-07-01T12:00:00-07:00",
    "failure_behavior": "ESCALATE",
    "revocable": true
  }
}
```

This gives agent societies accountability. It also allows task orchestration systems, workflow engines, and human supervisors to inspect what was promised, what was completed, what failed, and what requires repair.

## 10. Plane 6: Policy Plane

The Policy Plane determines whether a communication or action is allowed.

Policy checks include:

```text
Can this agent act in this domain?
Can this agent access this context?
Can this agent delegate this task?
Can this agent invoke this MCP tool?
Can this agent retain this memory?
Can this agent make this decision autonomously?
Does this require human approval?
Does this violate enterprise risk posture?
```

A Sutra policy envelope may look like this:

```json
{
  "policy": {
    "policy_bundle": "enterprise-procurement-v5",
    "decision_right": "recommend_only",
    "human_gate": "required_for_high_risk",
    "context_delegation": "restricted",
    "tool_invocation": {
      "allowed_mcp_servers": [
        "mcp://contracts",
        "mcp://supplier-risk-db"
      ],
      "blocked_tools": [
        "payment_release",
        "vendor_master_update"
      ]
    }
  }
}
```

In the 451 ecosystem, this is where **Pola** fits naturally as the policy expression and enforcement layer.

## 11. Plane 7: Proof Plane

The Proof Plane requires agents to attach evidence, uncertainty, tool logs, provenance, and verification recommendations to important outcomes.

```json
{
  "proof": {
    "evidence_used": [
      "contract_clause_4.2",
      "contract_clause_9.1",
      "supplier_screening_result_2026_06_30"
    ],
    "tools_called": [
      "mcp://contracts/extract_clauses",
      "mcp://supplier-risk-db/screen"
    ],
    "confidence": 0.82,
    "uncertainties": [
      "beneficial ownership data incomplete"
    ],
    "recommended_verification": "human_legal_review",
    "reasoning_trace_type": "summary"
  }
}
```

The Proof Plane does not require revealing full private chain-of-thought. It requires a verifiable decision record suitable for audit, compliance, debugging, and human oversight.

## 12. Plane 8: Memory Plane

The Memory Plane defines what may be remembered, where, for how long, and for what purpose.

Sutra defines six memory scopes:

| Scope             | Description                                         |
| ----------------- | --------------------------------------------------- |
| Ephemeral Memory  | Exists only during one exchange                     |
| Task Memory       | Exists during one task or workflow                  |
| Case Memory       | Exists across one customer, ticket, case, or matter |
| Enterprise Memory | Approved organizational knowledge                   |
| Personal Memory   | User-specific, consent-bound memory                 |
| System Memory     | Operational learning about agent performance        |

Example:

```json
{
  "memory": {
    "scope": "task_memory",
    "retention": "30_days",
    "write_allowed": true,
    "read_allowed_by": [
      "procurement-agent",
      "legal-risk-agent"
    ],
    "forget_policy": "delete_after_retention"
  }
}
```

This is where **Ana** fits as the contextual memory and knowledge substrate.

## 13. Plane 9: Adaptation Plane

The Adaptation Plane captures what the system learns from communication outcomes.

Examples of adaptation events include:

```text
Intent was misunderstood.
Context was insufficient.
Tool schema was ambiguous.
Policy blocked the action.
Human overrode the recommendation.
Agent confidence was poorly calibrated.
Delegation chain became too long.
Proof was insufficient for audit.
```

A formal adaptation event:

```json
{
  "adaptation_event": {
    "event_id": "adapt_00981",
    "type": "proof_insufficient",
    "root_cause": "missing source-level evidence for high-risk clause",
    "repair": "require clause-level citation for contract risk findings",
    "scope": "capability_contract_risk_review",
    "requires_approval": true
  }
}
```

This is where **Ananta** fits as the recursive self-adaptation layer. The fabric should learn, but it should not silently rewrite its own behavior in enterprise-critical domains. Adaptation must itself be governed.

## 14. Sutra Message Envelope

A full Sutra message envelope combines all planes.

```json
{
  "sutra_version": "1.0",
  "message_id": "msg_98231",
  "conversation_id": "conv_451_778",
  "thread_id": "task_supplier_risk_123",
  "created_at": "2026-06-30T11:42:00-07:00",

  "from": {
    "agent_id": "did:agent:451.procurement.v2",
    "role": "requesting_agent"
  },

  "to": {
    "agent_id": "did:agent:451.legal-risk.v3",
    "role": "performing_agent"
  },

  "act": "DELEGATE",

  "intent": {
    "goal": "Assess supplier contract risk before purchase approval",
    "success_criteria": [
      "risk score returned",
      "high-risk clauses identified",
      "evidence cited",
      "human review flagged if needed"
    ],
    "priority": "high"
  },

  "authority": {
    "delegation_right": true,
    "decision_right": "recommend_only",
    "approval_required": true
  },

  "context": {
    "context_pack_id": "ctx.vendor_contract_123",
    "sensitivity": "confidential",
    "allowed_operations": ["read", "extract", "summarize"],
    "retention": "30_days",
    "delegation_allowed": false
  },

  "commitment": {
    "requested_due": "2026-07-01T12:00:00-07:00",
    "failure_behavior": "ESCALATE"
  },

  "policy": {
    "policy_bundle": "enterprise-procurement-v5",
    "human_gate": "required_for_high_risk"
  },

  "proof_required": {
    "evidence": true,
    "tool_log": true,
    "confidence": true,
    "uncertainty": true
  },

  "compatibility": {
    "a2a": {
      "expose_as_task": true,
      "artifact_mode": "sutra_proof_artifact"
    },
    "mcp": {
      "allowed_servers": [
        "mcp://contracts",
        "mcp://supplier-risk-db"
      ]
    },
    "acl": {
      "performative": "request"
    }
  }
}
```

## 15. Backward Compatibility With A2A

Sutra should support A2A in three ways.

First, every Sutra Agent Passport must expose an A2A Agent Card compatible representation. This allows existing A2A clients to discover Sutra agents without knowing the full Sutra model.

Second, every Sutra delegation can be represented as an A2A task. A2A’s task and artifact model becomes the transport-compatible representation for Sutra’s richer commitment and proof model.

Third, Sutra messages can be downgraded to A2A messages by preserving core fields and attaching Sutra-specific governance data as metadata or artifacts.

Example mapping:

| Sutra Concept       | A2A Mapping                         |
| ------------------- | ----------------------------------- |
| Agent Passport      | Agent Card plus metadata extensions |
| Capability Contract | Agent Card capability               |
| Sutra Message       | A2A Message                         |
| Commitment          | A2A Task metadata                   |
| Proof Package       | A2A Artifact                        |
| Context Pack        | Message Part reference or metadata  |
| Adaptation Event    | Artifact or callback event          |
| Policy Envelope     | Metadata extension                  |

A2A-compatible task example:

```json
{
  "task": {
    "id": "task_supplier_risk_123",
    "kind": "contract_risk_review",
    "message": {
      "role": "user",
      "parts": [
        {
          "type": "text",
          "text": "Assess supplier contract risk before purchase approval."
        }
      ]
    },
    "metadata": {
      "sutra_version": "1.0",
      "act": "DELEGATE",
      "authority": "recommend_only",
      "proof_required": true,
      "human_gate": "required_for_high_risk"
    }
  }
}
```

A2A-native agents can ignore unknown Sutra metadata and still process the task. Sutra-native agents can read the metadata and apply the full governance fabric.

## 16. Backward Compatibility With MCP

Sutra should support MCP in four ways.

First, Sutra agents may consume MCP tools, resources, and prompts directly. MCP remains the preferred tool and context access mechanism.

Second, Sutra agents may expose their own capabilities as MCP tools. This allows a non-Sutra MCP client to call a Sutra agent as if it were a tool.

Third, Sutra Context Packs may reference MCP resources by URI, adding lineage, sensitivity, allowed use, delegation, and retention rules.

Fourth, Sutra policy enforcement should wrap MCP tool invocation. Before an agent calls an MCP server, Sutra checks authority, sensitivity, purpose, and permitted operations.

Example MCP tool exposure:

```json
{
  "name": "contract_risk_review",
  "description": "Reviews a vendor contract and returns evidence-backed risk findings.",
  "inputSchema": {
    "type": "object",
    "properties": {
      "contract_uri": {
        "type": "string"
      },
      "jurisdiction": {
        "type": "string"
      },
      "risk_policy": {
        "type": "string"
      }
    },
    "required": ["contract_uri", "jurisdiction", "risk_policy"]
  },
  "x-sutra": {
    "act": "REQUEST",
    "authority_level": "recommend_only",
    "proof_required": true,
    "human_gate": "required_for_high_risk"
  }
}
```

MCP-native clients can call the tool normally. Sutra-native clients can interpret the `x-sutra` extension.

## 17. Backward Compatibility With ACL

Sutra should not discard ACL. It should use ACL as the semantic foundation for intent.

ACL compatibility is achieved by mapping Sutra acts to performatives.

Example:

```json
{
  "acl": {
    "performative": "request",
    "sender": "procurement-agent",
    "receiver": "legal-risk-agent",
    "content": "Assess supplier contract risk",
    "language": "sutra-json",
    "ontology": "enterprise-procurement-risk",
    "conversation_id": "conv_451_778"
  }
}
```

This enables legacy ACL-inspired systems to interpret Sutra communication as speech-act communication.

## 18. Runtime Reference Architecture

```text
Human / Business Intent
        |
        v
Intent Gateway
        |
        v
Agent Passport Registry <----> Capability Registry
        |
        v
Policy and Authority Engine
        |
        v
Sutra Communication Bus
        |
        +---- A2A Adapter
        +---- MCP Adapter
        +---- ACL Adapter
        +---- REST / gRPC / Event Adapter
        |
        v
Task, Commitment, and State Manager
        |
        v
Proof, Audit, and Memory Layer
        |
        v
Adaptation and Learning Layer
        |
        v
Human Oversight and Governance Console
```

## 19. Enterprise Deployment Model

A production Sutra deployment should include the following services:

| Service                 | Purpose                                                    |
| ----------------------- | ---------------------------------------------------------- |
| Agent Passport Registry | Identity, ownership, runtime, trust tier, certification    |
| Capability Registry     | Discoverable, typed, governed capabilities                 |
| Intent Gateway          | Converts human/business intent into Sutra acts             |
| Policy Engine           | Determines allowed access, delegation, action, memory      |
| Communication Bus       | Routes messages, tasks, events, commitments                |
| A2A Adapter             | Interoperates with A2A agents                              |
| MCP Adapter             | Connects to MCP tools, resources, and prompts              |
| ACL Adapter             | Supports performative-based semantic compatibility         |
| Commitment Manager      | Tracks promises, deadlines, obligations, failures          |
| Context Broker          | Controls context lineage, sensitivity, retention           |
| Proof Ledger            | Stores evidence, tool logs, uncertainty, audit records     |
| Memory Manager          | Enforces memory scope and retention                        |
| Adaptation Engine       | Converts failures and overrides into governed improvements |
| Human Agency Console    | Review, approve, override, escalate, teach                 |

## 20. Human Agency Model

Sutra must not treat humans as passive approvers. Human agency should be part of the protocol.

Human roles include:

```text
Requester
Approver
Reviewer
Steward
Exception Handler
Domain Oracle
Policy Owner
Auditor
Teacher
```

A human intervention should be a first-class communicative act:

```json
{
  "act": "HUMAN_OVERRIDE",
  "human_role": "Domain Oracle",
  "decision": "reject_agent_recommendation",
  "reason": "Contract clause has acceptable risk under existing supplier master agreement",
  "adaptation_allowed": true
}
```

This is critical for high-consequence systems. The fabric should preserve human judgment, not merely route around it.

## 21. Security and Governance

Sutra requires a zero-trust model.

Core security principles:

```text
Verify every agent.
Verify every capability.
Verify every context request.
Verify every delegation.
Verify every tool invocation.
Verify every memory write.
Verify every autonomous decision.
```

Important controls include:

1. Cryptographic agent identity
2. Capability-based authorization
3. Policy-bound context access
4. Human approval gates
5. Tool invocation sandboxing
6. Memory retention and deletion policies
7. Proof and audit trails
8. Delegation depth limits
9. Runtime anomaly detection
10. Kill switch and containment controls

## 22. Delegation Safety

Agent societies can fail through uncontrolled delegation. Sutra should therefore include delegation constraints:

```json
{
  "delegation_policy": {
    "max_depth": 3,
    "allowed_agent_classes": [
      "risk_agent",
      "legal_agent",
      "compliance_agent"
    ],
    "forbidden_domains": [
      "payment_release",
      "contract_signature"
    ],
    "requires_trace": true
  }
}
```

Delegation must be inspectable. An enterprise should always know which agent asked which agent to do what, under what authority, with what context.

## 23. Proof Package Format

A Sutra Proof Package should be portable across A2A artifacts, MCP responses, and enterprise audit stores.

```json
{
  "proof_package": {
    "proof_id": "proof_77821",
    "task_id": "task_supplier_risk_123",
    "result_summary": "Supplier contract contains two medium-risk clauses and one high-risk indemnity clause.",
    "evidence": [
      {
        "source": "contract_clause_9.1",
        "finding": "Broad indemnity language",
        "risk": "high"
      }
    ],
    "tool_log": [
      {
        "tool": "mcp://contracts/extract_clauses",
        "timestamp": "2026-06-30T12:01:00-07:00"
      }
    ],
    "confidence": 0.82,
    "uncertainty": [
      "Supplier ownership information incomplete"
    ],
    "human_review": {
      "required": true,
      "reason": "High-risk clause detected"
    }
  }
}
```

## 24. Transport Model

Sutra should be transport-neutral.

Supported transports:

```text
JSON-RPC
HTTP
gRPC
WebSocket
Event bus
A2A task channel
MCP client-server session
Enterprise message broker
```

The protocol envelope should remain stable across transports.

## 25. Versioning and Extensibility

Sutra should support explicit versioning:

```json
{
  "sutra_version": "1.0",
  "compatibility": {
    "a2a": "1.x",
    "mcp": "2025-11-25",
    "acl": "fipa-compatible"
  }
}
```

Extensions should use namespaced fields:

```json
{
  "x-451": {
    "rpm_gate": "stewardship",
    "value_spine_gate": "proof"
  },
  "x-enterprise": {
    "sox_control": "required"
  }
}
```

Unknown extension fields must be safely ignored by non-Sutra systems.

## 26. Example End-to-End Flow

A procurement agent needs a supplier contract reviewed.

Step 1: Procurement agent discovers legal-risk agents through A2A Agent Card compatibility.

Step 2: Sutra reads the richer Agent Passport and Capability Contract.

Step 3: The procurement agent sends a Sutra `DELEGATE` message.

Step 4: The Policy Engine checks authority, context access, tool permissions, and human approval requirements.

Step 5: The legal-risk agent retrieves the contract through MCP.

Step 6: The legal-risk agent calls an MCP supplier-risk database.

Step 7: The agent returns a Proof Package as an A2A artifact.

Step 8: The Commitment Manager marks the delegation complete.

Step 9: Human reviewer approves, rejects, or modifies the recommendation.

Step 10: Any override becomes an Adaptation Event.

## 27. Why Sutra Is Different

A2A lets agents talk.

MCP lets agents use tools.

ACL lets agents express communicative intent.

Sutra lets agents operate in a governed enterprise society.

The difference is visible in the object of communication:

| Layer     | Main Object                                                             |
| --------- | ----------------------------------------------------------------------- |
| REST/API  | Function call                                                           |
| Event Bus | Event                                                                   |
| MCP       | Tool/resource/prompt access                                             |
| A2A       | Agent task/message/artifact                                             |
| ACL       | Communicative act                                                       |
| Sutra     | Governed commitment with context, proof, policy, memory, and adaptation |

## 28. Relationship to 451 Architecture

Sutra naturally fits the 451 agent architecture:

| 451 Component | Role in Sutra                              |
| ------------- | ------------------------------------------ |
| Atma          | Agentic core and execution intelligence    |
| Ana           | Memory, context, and knowledge substrate   |
| Pola          | Policy language and governance rules       |
| Actra         | Governed autonomy operating plane          |
| Astra         | Strategic reasoning and thesis generation  |
| Ananta        | Recursive self-adaptation layer            |
| Sutra         | Communication fabric connecting all agents |

Sutra becomes the thread across the system. Atma acts. Ana remembers. Pola governs. Actra controls autonomy. Astra reasons. Ananta adapts. Sutra lets them communicate with meaning, proof, and responsibility.

## 29. Implementation Roadmap

## Phase 1: Compatibility Layer

Build adapters for:

```text
A2A Agent Card import/export
A2A task/message/artifact mapping
MCP tool/resource/prompt invocation
ACL performative mapping
```

## Phase 2: Sutra Envelope

Implement the core message envelope:

```text
identity
act
intent
authority
context
commitment
policy
proof
memory
compatibility
```

## Phase 3: Registries

Build:

```text
Agent Passport Registry
Capability Registry
Context Pack Registry
Policy Bundle Registry
Proof Ledger
Commitment Store
```

## Phase 4: Governance Runtime

Implement:

```text
Policy enforcement
Delegation control
Human approval gates
Memory scope enforcement
Tool invocation guardrails
Audit trails
```

## Phase 5: Adaptation Layer

Implement:

```text
Failure capture
Human override capture
Proof quality scoring
Capability calibration
Governed learning loops
Ananta integration
```

## 30. Conclusion

The next generation of agent communication cannot be built as a thin messaging protocol. It must become a governed communication fabric for intelligent systems.

A2A is necessary because agents need to discover and collaborate with other agents. MCP is necessary because agents need standardized access to tools, resources, prompts, and external systems. ACL is necessary because communication among agents must carry intention, not only payloads.

But enterprise AI requires more.

It requires identity, authority, context lineage, commitment, proof, memory boundaries, policy enforcement, human agency, and recursive adaptation.

That is what Sutra provides.

**Sutra is the AI-native Agent Communication Fabric for governed intelligence. It is backward compatible with A2A and MCP, semantically grounded in ACL, and designed for the next era of enterprise agent societies.**

## References

A2A Project. (2025). *Agent2Agent protocol specification*. GitHub.

Anthropic. (2024, November 25). *Introducing the Model Context Protocol*.

Foundation for Intelligent Physical Agents. (2001). *FIPA communicative act library specification*.

Model Context Protocol. (2025a). *Specification: 2025-06-18*.

Model Context Protocol. (2025b). *Tools*.
