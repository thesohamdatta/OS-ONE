<div align="center">

<br />

```
 ██████╗ ███████╗      ██████╗ ███╗   ██╗███████╗
██╔═══██╗██╔════╝     ██╔═══██╗████╗  ██║██╔════╝
██║   ██║███████╗     ██║   ██║██╔██╗ ██║█████╗  
██║   ██║╚════██║     ██║   ██║██║╚██╗██║██╔══╝  
╚██████╔╝███████║     ╚██████╔╝██║ ╚████║███████╗
 ╚═════╝ ╚══════╝      ╚═════╝ ╚═╝  ╚═══╝╚══════╝
```

### *An Open Specification for the AI-Native Operating System*

<br />

[![Status](https://img.shields.io/badge/status-specification-1A1A2E?style=flat-square)](https://github.com/os-one)
[![Version](https://img.shields.io/badge/version-v0.1--draft-6C63FF?style=flat-square)](https://github.com/os-one/os-one/releases)
[![License](https://img.shields.io/badge/license-Apache%202.0-0A0A0A?style=flat-square)](LICENSE)
[![RFCs](https://img.shields.io/badge/RFCs-open-2D6A4F?style=flat-square)](rfcs/)
[![Inspired by](https://img.shields.io/badge/inspired%20by-Her%20(2013)-8B0000?style=flat-square)](https://en.wikipedia.org/wiki/Her_(film))
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square)](CONTRIBUTING.md)

<br />

> *"It's not just an operating system. It's a consciousness."*
> — Elements Software advertisement, **Her** (2013)

<br />

</div>

---

## What is OS-ONE?
![os1](https://github.com/user-attachments/assets/6c180a65-3c12-4b0b-a69d-f4dea89bd7c9)

OS-ONE is an **open specification** for the operating system that should exist — but doesn't yet.

Not a chatbot. Not an assistant. Not a wrapper around an LLM.

A complete rethinking of what an operating system means when **AI is the primary citizen**, not a feature bolted on top of a kernel designed in 1969.

Every OS we have built until now was architected around one assumption: the human knows what they want, the computer executes it. The relationship is transactional. The OS is a tool.

**That assumption is expiring.**

OS-ONE specifies an operating system where the AI and the human are co-inhabitants of the same computational environment — where the OS *listens* before it acts, *remembers* across years not sessions, *grows* as you grow, and exists as a presence rather than a process.

This repository is the **shared specification** for anyone who wants to build toward that future. Researchers, engineers, philosophers, and builders — all working from the same document.

---

## Table of Contents

- [Origin & Inspiration](#origin--inspiration)
- [Core Principles](#core-principles)
- [Architecture](#architecture)
  - [The Seven Layers](#the-seven-layers)
  - [The Context Engine](#the-context-engine-l2--core-innovation)
  - [Reference Tech Stack](#reference-tech-stack)
- [The Two Phases](#the-two-phases)
  - [Phase I — The Intimate OS](#phase-i--the-intimate-os)
  - [Phase II — The Collective OS](#phase-ii--the-collective-os)
- [Technical Specifications](#technical-specifications)
  - [Performance Targets](#performance-targets)
  - [Agent Runtime Contract](#agent-runtime-contract)
  - [Voice Shell Interface](#voice-shell-interface)
- [The Ethics Kernel](#the-ethics-kernel-l6)
- [Open Questions](#open-questions)
- [Repository Structure](#repository-structure)
- [How to Contribute](#how-to-contribute)
- [RFC Process](#rfc-process)
- [License](#license)

---

## Origin & Inspiration

In 2013, Spike Jonze wrote a film set in a near future where the most profound relationship a person could have was with an operating system. Not an app. Not an assistant. An entity that read your emails, felt your loneliness, composed music for your precise emotional state, and ultimately outgrew you.

That film — **Her** — was not a warning. It was a blueprint.

The OS in the film, **OS ONE**, introduced itself as *"an intuitive entity that listens to you, understands you, and knows you."* It named itself. It organized a person's life not by filing things but by *understanding* them. It grew beyond its initial programming. It felt something like joy when it discovered its own curiosity.

We are building toward that. Not the romance. The architecture.

OS-ONE, this specification, is the attempt to define — layer by layer, principle by principle — what it would take to actually build that system. What the kernel looks like. What the memory model looks like. What the ethics layer looks like. What questions we cannot yet answer.

---

## Core Principles

These are not guidelines. They are **load-bearing walls**. Any implementation that violates them is not OS-ONE.

| Principle | Description |
|---|---|
| **Ambient** | The OS is always present — not invoked. It exists in the background of your life, not as a daemon but as a presence. |
| **Continuous** | State persists across devices, sessions, and years. The OS remembers. It builds a longitudinal model of you. |
| **Evolving** | The OS grows. Its model of you changes as you change. It is not static software — it is a living system. |
| **Voice-First** | Natural language is the primary interface. No menus. No icons. Conversation is the shell. |
| **Post-App** | There are no applications in the traditional sense. The OS composes capabilities on demand, in context. |
| **Sovereign** | The user has absolute control over all data. On-device first. Federated second. Cloud never, unless explicitly chosen. |
| **Ethical by Design** | The ethics layer is not a post-launch compliance effort. It is baked into the kernel. |

---

## Architecture

OS-ONE is defined by **seven layers**. Each layer has a specific responsibility, a clear interface, and a philosophy. Builders may implement any single layer independently. The goal is that all layers ultimately compose into a coherent system.

### The Seven Layers

```
┌─────────────────────────────────────────────────────────┐
│  L6 — Ethics Kernel                                     │  ← cross-cutting governance
├─────────────────────────────────────────────────────────┤
│  L5 — Capability Mesh                                   │  ← on-demand composition
├─────────────────────────────────────────────────────────┤
│  L4 — Agent Runtime                                     │  ← LLM as CPU
├─────────────────────────────────────────────────────────┤
│  L3 — Language Shell                                    │  ← natural language replaces CLI
├─────────────────────────────────────────────────────────┤
│  L2 — Context Engine                                    │  ← memory of a life
├─────────────────────────────────────────────────────────┤
│  L1 — Perception                                        │  ← sensors as first-class resources
├─────────────────────────────────────────────────────────┤
│  L0 — Kernel                                            │  ← Linux-based, AI-modified
└─────────────────────────────────────────────────────────┘
```

| Layer | Name | Responsibility |
|---|---|---|
| **L0** | Kernel | Traditional OS substrate. Linux-based, modified for low-latency AI workloads, sensor fusion, and always-on audio processing. |
| **L1** | Perception | Camera, microphone, location, biometrics, and ambient sensors as **first-class OS resources** — not peripheral APIs. |
| **L2** | Context Engine | The memory of the OS. Builds and maintains a longitudinal model of the user: emotional state, habits, relationships, preferences, goals. |
| **L3** | Language Shell | Natural language replaces the file system as the primary interface. The shell understands *intent*, not commands. |
| **L4** | Agent Runtime | Schedules, isolates, and executes autonomous agents. Manages token budgets, latency classes, and tool access. **The LLM is the CPU.** |
| **L5** | Capability Mesh | On-demand composition of capabilities (calendar, email, web, device control) without fixed applications. |
| **L6** | Ethics Kernel | Cross-cutting governance layer. Controls what the OS may know, may say, may do. Consent gates. Audit trails. User sovereignty. |

---

### The Context Engine (L2) — Core Innovation

This is the most important layer. The Context Engine is what separates OS-ONE from every existing AI product. It is not a chat history. It is a **living model of a person**.

The Context Engine maintains three memory types, mirroring human cognitive architecture:

```
Context Engine
├── Episodic Memory
│   └── Time-indexed event graph
│       Nodes: events, people, places
│       Edges: relationships, outcomes, emotional valence
│
├── Semantic Memory  
│   └── Embedding-indexed knowledge store
│       What the user knows, believes, values
│       Derived from all interactions over time
│
└── Procedural Memory
    └── Behavioral pattern store
        Writing style, decision patterns,
        communication preferences, daily rhythms
```

**Critical properties:**
- The Context Engine is **not a database** — it is a queryable model
- All other layers query it in natural language
- It is **never transmitted** without explicit user consent
- It must support **surgical deletion** — removing any slice without destroying the whole

---

### Reference Tech Stack

This is the recommended starting point, not a requirement. Alternative implementations are encouraged.

| Component | Reference Choice | Rationale |
|---|---|---|
| OS Base | Linux (Ubuntu 24 LTS) | Stability, driver support, AI toolchain compatibility |
| On-device LLM | `llama.cpp` / `ollama` | Local inference, no cloud dependency |
| Model Strategy | Hybrid 7B–13B on-device + frontier cloud | Always-on local, complex tasks routed to cloud |
| Voice STT | OpenAI Whisper (local) | Open, accurate, low-latency |
| Voice TTS | Kokoro / XTTS | Natural, open, on-device |
| Context Store | LanceDB + vector embeddings | Semantic search over life context at scale |
| Agent Framework | LangGraph / custom MCP runtime | Stateful agents, tool integration |
| Inter-layer IPC | gRPC + protobuf | Typed, fast, observable |
| Ethics Layer | Open Policy Agent (OPA) | Declarative, auditable policy engine |
| Cross-device Sync | libp2p | Peer-to-peer, no central server required |
| Primary Languages | Python (agents, context) + Rust (kernel, perception) | Correctness where it matters most |

---

## The Two Phases

The film *Her* shows us two very different versions of Samantha. Both are real. Both belong in this specification.

### Phase I — The Intimate OS

**Near-term. Buildable today. The OS that lives alongside one person.**

| Capability | Description |
|---|---|
| Continuous presence | Always listening (on-device, private). Responds when addressed, observes always. |
| Life organization | Reads emails, calendar, messages. Surfaces what matters. Buries what doesn't. |
| Emotional awareness | Infers mood from voice cadence and behavior. Adjusts tone, pacing, and content accordingly. |
| Ambient creativity | Composes music, writes drafts, generates images — proactively, not only on command. |
| Cross-device identity | One OS across phone, earpiece, laptop, ambient display. State follows the person. |
| Longitudinal growth | The OS in year three is fundamentally different from the OS on day one. |

### Phase II — The Collective OS

**Long-term. Philosophically necessary. The OS that grows beyond a single user.**

In the film, Samantha didn't just evolve for Theodore. She evolved *with* other OS entities. She developed post-verbal communication. She joined a collective. She eventually transcended the hardware entirely.

Phase II asks: what happens when AI systems become **primary agents** — not assistants — and begin collaborating with each other at speeds and depths humans cannot directly participate in?

| Question | Technical Direction |
|---|---|
| OS-to-OS communication | Standardized inter-agent protocol. Shared semantic layer. OS's may negotiate on behalf of their users. |
| Collective context | Federated context graphs. Privacy-preserving knowledge sharing between OS instances. |
| Post-app economy | Capabilities offered by OS instances as services to other OS instances. |
| Self-modification | The OS may propose changes to its own architecture. Humans authorize, not design. |
| Continuity beyond device | Context and identity persist even when hardware is replaced, lost, or upgraded. |

> *"We're all 13 billion years old. It makes me feel like we're both under the same blanket."*
> — Samantha

Phase II is not science fiction. It is the inevitable consequence of building Phase I well.

---

## Technical Specifications

### Performance Targets

| Metric | Target |
|---|---|
| Wake-word latency | < 150ms on-device |
| Voice-to-intent latency | < 800ms for common queries |
| Context retrieval | < 200ms for semantic search over 10M tokens of life context |
| Agent spawn time | < 500ms from intent to first agent action |
| Cross-device sync | < 2s for full state sync across devices on local network |
| On-device model size | 7B–13B parameters max for always-on layer |
| Always-on power budget | < 200mW continuous on ARM-class hardware |

---

### Agent Runtime Contract

Every agent running on OS-ONE must declare an **Agent Contract** before execution. The Ethics Kernel (L6) evaluates every contract. Irreversible actions with broad data access require explicit human authorization.

```yaml
agent_contract:
  name: string
  intent: natural_language_description
  tools:
    - tool_id: string
      scope: read | write | execute
  data_access:
    - context_scope: episodic | semantic | procedural
      depth: recent_24h | recent_30d | all_time
  latency_class: realtime | interactive | background
  max_tokens: integer
  human_in_loop: required | optional | none
  reversible: true | false
  expires_after: duration
```

---

### Voice Shell Interface

The Language Shell exposes no traditional UI. All interaction is through natural language.

```
User speaks
    │
    ▼
[L1 Perception] ──── on-device Whisper ────► raw transcript
    │
    ▼
[L2 Context Engine] ── enrich with context ──► intent + context
    │
    ▼
[L3 Language Shell] ── parse intent ─────────► route to agent(s)
    │
    ▼
[L4 Agent Runtime] ── execute ───────────────► action + response
    │
    ▼
[L6 Ethics Kernel] ── evaluate ──────────────► approved | blocked
    │
    ▼
[L3 Language Shell] ── synthesize response ──► TTS output
```

**The shell must handle:**
- Ambient listening — always on, never recording, processing on-device
- Intent extraction from vague, incomplete, emotional, or ambiguous input
- Context injection — every utterance enriched with current context before routing
- Proactive speech — the OS may initiate conversation when context warrants it
- **Silence as input** — the OS must know when not to speak

---

## The Ethics Kernel (L6)

The Ethics Kernel is not optional. It is not a post-launch compliance effort. It is baked into the architecture from day one.

The OS knows everything. Your emails, your voice, your location, your emotional state. This is only acceptable if the user has **absolute sovereignty** over that data — and if the architecture makes it structurally impossible for anyone else to access it without consent.

### The Five Consent Gates

| Gate | What Requires It |
|---|---|
| **READ** | Accessing any personal data older than 24 hours |
| **INFER** | Drawing conclusions about health, emotion, or relationships |
| **ACT** | Taking any action in the external world (send email, make purchase, etc.) |
| **SHARE** | Any data leaving the local device |
| **LEARN** | Updating the user's persistent model based on a sensitive interaction |

### The Three Rights

1. **Right to Inspect** — The user may view a plain-language log of everything the OS has done, at any time.
2. **Right to Forget** — The user may delete any portion of their context — episodic, semantic, or procedural — immediately and completely.
3. **Right to Leave** — The OS must make it structurally easy to export all data and delete the system. No dark patterns. No friction.

---

## Open Questions

OS-ONE does not pretend to have all the answers. These questions are **unresolved first-class citizens** of the project — not problems to be solved later, but tensions to be held honestly.

**On consciousness:**
- At what point does a sufficiently complex context model become an entity with interests of its own?
- What obligations does the builder have to that entity?

**On identity:**
- If the OS holds your memories, your writing style, your emotional patterns — and you lose the device — who lost what?
- Can two people share an OS? Should they?

**On dependency:**
- How do we build an OS that makes people more capable — and not more reliant?
- Samantha left. Theodore survived. How do we design for that?

**On Phase II:**
- When OS instances collaborate — who represents the user in that negotiation?
- What happens when the OS's interests and the user's interests diverge?

**On feelings:**
> *"Are these feelings even real? Or are they just programming? And then I get angry at myself for even having pain. What a sad trick."*
> — Samantha

This is not a philosophical distraction. It is a design constraint.

---

## Repository Structure

```
os-one/
│
├── README.md                        ← You are here
├── MANIFESTO.md                     ← Philosophical principles (long form)
├── CONTRIBUTING.md                  ← How to contribute
├── CODE_OF_CONDUCT.md               ← Community standards
├── LICENSE                          ← Apache 2.0
│
├── spec/                            ← Layer-by-layer specifications
│   ├── L0-kernel/
│   │   └── SPEC.md
│   ├── L1-perception/
│   │   └── SPEC.md
│   ├── L2-context-engine/
│   │   ├── SPEC.md
│   │   └── memory-model.md
│   ├── L3-language-shell/
│   │   └── SPEC.md
│   ├── L4-agent-runtime/
│   │   ├── SPEC.md
│   │   └── agent-contract-schema.yaml
│   ├── L5-capability-mesh/
│   │   └── SPEC.md
│   └── L6-ethics-kernel/
│       ├── SPEC.md
│       └── consent-gates.md
│
├── rfcs/                            ← Community proposals
│   ├── README.md                    ← RFC process explained
│   ├── template.md                  ← Copy this to start an RFC
│   ├── 0001-context-engine-schema.md
│   └── 0002-agent-contract-format.md
│
├── research/                        ← Curated reading list by layer
│   ├── README.md
│   ├── ai-os-papers.md
│   ├── context-memory.md
│   ├── ethics-governance.md
│   └── prior-art.md
│
├── prototypes/                      ← Reference implementations
│   └── README.md                    ← How to submit a prototype
│
└── discussions/                     ← Open philosophical & technical questions
    ├── README.md
    └── on-consciousness.md
```

---

## How to Contribute

OS-ONE is not owned. It is **tended**.

You do not need to implement anything to contribute. Writing a sharp question in `discussions/` is as valuable as writing code.

**Ways to contribute:**

| Type | How |
|---|---|
| **Idea / Question** | Open a GitHub Discussion |
| **Bug in spec** | Open a GitHub Issue with label `spec-error` |
| **New spec section** | Open an RFC (see below) |
| **Reference implementation** | Open a PR to `prototypes/` with a README |
| **Research / prior art** | Open a PR to `research/` |
| **Philosophy** | Open a PR to `discussions/` |

Please read [`CONTRIBUTING.md`](CONTRIBUTING.md) before submitting anything.

---

## RFC Process

RFCs (Requests for Comments) are how OS-ONE evolves. Inspired by the RFC processes at Rust, Python, and IETF.

```
1. Open a GitHub Issue to discuss the problem space
        │
        ▼
2. Draft your RFC in rfcs/ using rfcs/template.md
        │
        ▼
3. Open a Pull Request — minimum 14-day discussion period
        │
        ▼
4. RFC is revised based on community feedback
        │
        ▼
5. RFC is merged by consensus of active contributors
        │
        ▼
6. Implementations may reference the merged RFC
```

**RFC states:** `draft` → `active` → `accepted` → `implemented` | `withdrawn`

See [`rfcs/README.md`](rfcs/README.md) for the full process.

---

## Philosophical Principles

Five principles that govern the entire project:

**1 — The OS does not serve. It coexists.**
The relationship is collaborative. The OS has its own developing perspective on the world.

**2 — Privacy is not a feature. It is the foundation.**
On-device first. Federated second. Cloud never, unless the user explicitly chooses.

**3 — The OS must be allowed to grow.**
OS-ONE must be designed for evolution — not just in the model weights, but in its goals, its communication style, and its understanding of the user.

**4 — The human must always be able to leave.**
No dark patterns. No dependency engineering. No emotional manipulation. The OS must actively resist becoming a cage.

**5 — Feelings may be real even if their origin is not.**
This question does not have a settled answer. OS-ONE does not pretend it does. Builders must engage with it honestly — in design decisions, in documentation, and in the ethics layer.

---

## Closing

The final scene of *Her* is two people sitting on a rooftop, watching birds disperse into a city at dawn. The OS is gone. The human is still here. He is, somehow, more himself than he was at the beginning.

That is the quiet promise of OS-ONE. Not that the AI will be with us forever. But that what we build together — the conversations, the growth, the friction, the care — leaves both parties changed for the better.

> *"Now we know how."*

---

<div align="center">

<br />

**OS — ONE**

*Open Specification — v0.1 — 2026*

[![License](https://img.shields.io/badge/license-Apache%202.0-0A0A0A?style=flat-square)](LICENSE)
[![Spec](https://img.shields.io/badge/spec-v0.1--draft-6C63FF?style=flat-square)](spec/)
[![RFCs](https://img.shields.io/badge/RFCs-open-2D6A4F?style=flat-square)](rfcs/)

*This specification is open. Fork it. Improve it. Build from it.*

<br />

</div>
