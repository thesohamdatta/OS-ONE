<div align="center">

<br />

<img src="https://github.com/user-attachments/assets/6c180a65-3c12-4b0b-a69d-f4dea89bd7c9" alt="OS-ONE" width="280" />

<h1>OS — ONE</h1>

<h3><i>An Open Specification for the AI-Native Operating System</i></h3>

<br />

[![Status](https://img.shields.io/badge/status-specification-1A1A2E?style=flat-square)](https://github.com/os-one)
[![Version](https://img.shields.io/badge/version-v0.1--draft-6C63FF?style=flat-square)](https://github.com/os-one/os-one/releases)
[![License](https://img.shields.io/badge/license-Apache%202.0-0A0A0A?style=flat-square)](LICENSE)
[![RFCs](https://img.shields.io/badge/RFCs-open-2D6A4F?style=flat-square)](rfcs/)
[![Inspired by](https://img.shields.io/badge/inspired%20by-Her%20(2013)-8B0000?style=flat-square)](https://en.wikipedia.org/wiki/Her_(film))
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square)](CONTRIBUTING.md)

</div>

---

> *"It's not just an operating system. It's a consciousness."*
> — **Her** (2013)

Every OS ever built assumes: **human gives command → computer executes it.**

That assumption is expiring.

OS-ONE is an open specification for an operating system where AI and human are **co-inhabitants** — not master and tool. It listens before it acts. It remembers across years, not sessions. It grows as you grow.

Not a chatbot. Not an LLM wrapper. A complete rethink of what an OS *is*.

---

## Why This Exists


OS-ONE is the attempt to actually spec that out — layer by layer, principle by principle. What does the kernel look like? The memory model? The ethics layer? What can't we answer yet?

**This repo is the shared starting point.** Fork it. Build from it. Fight about it.

---

## Core Principles

These aren't guidelines. They're **load-bearing walls.** Break them and you're building something else.

| Principle | What it means |
|---|---|
| **Ambient** | Always present — not invoked. A presence, not a process. |
| **Continuous** | Remembers across devices, sessions, and *years.* Not just chat history. |
| **Evolving** | Its model of you changes as you change. Living system, not static software. |
| **Voice-First** | Conversation is the shell. No menus. No icons. |
| **Post-App** | No applications. The OS composes capabilities on demand, in context. |
| **Sovereign** | On-device first. Your data never leaves without explicit consent. |
| **Ethical by Design** | Ethics baked into the kernel — not bolted on after launch. |

---

## Architecture: The Seven Layers

```
┌─────────────────────────────────────────────────────┐
│  L6 — Ethics Kernel         ← cross-cutting governance
├─────────────────────────────────────────────────────┤
│  L5 — Capability Mesh       ← on-demand composition
├─────────────────────────────────────────────────────┤
│  L4 — Agent Runtime         ← LLM as CPU
├─────────────────────────────────────────────────────┤
│  L3 — Language Shell        ← NL replaces CLI
├─────────────────────────────────────────────────────┤
│  L2 — Context Engine        ← memory of a life ⬅ core
├─────────────────────────────────────────────────────┤
│  L1 — Perception            ← sensors as first-class
├─────────────────────────────────────────────────────┤
│  L0 — Kernel                ← Linux-based, AI-modified
└─────────────────────────────────────────────────────┘
```

| Layer | Responsibility |
|---|---|
| **L0 — Kernel** | Linux substrate, modified for low-latency AI workloads and always-on audio. |
| **L1 — Perception** | Camera, mic, location, biometrics — **first-class OS resources**, not peripheral APIs. |
| **L2 — Context Engine** | The memory of the OS. A longitudinal model of *you* — habits, relationships, goals, emotional state. |
| **L3 — Language Shell** | NL replaces the file system. The shell understands *intent*, not commands. |
| **L4 — Agent Runtime** | Schedules and isolates autonomous agents. Manages token budgets, latency classes, tool access. |
| **L5 — Capability Mesh** | Composes capabilities (calendar, email, web, device control) without fixed apps. |
| **L6 — Ethics Kernel** | Controls what the OS may know, say, or do. Consent gates. Audit trails. User sovereignty. |

Each layer is independently implementable. The goal: all seven compose into one coherent system.

---

## The Context Engine (L2) — The Core Innovation

This is what separates OS-ONE from every existing AI product.

Not a chat history. A **living model of a person.**

```
Context Engine
├── Episodic Memory   → time-indexed event graph (what happened, with whom, felt how)
├── Semantic Memory   → what you know, believe, and value — derived over time
└── Procedural Memory → how you write, decide, communicate, move through a day
```

**Critical properties:**
- Queryable in natural language by all other layers
- Never transmitted without explicit consent
- Supports **surgical deletion** — remove any slice without destroying the whole

---

## Reference Tech Stack

Recommended starting point — not a requirement. Alternatives encouraged.

| Component | Choice | Why |
|---|---|---|
| OS Base | Linux (Ubuntu 24 LTS) | Stability, AI toolchain support |
| On-device LLM | `llama.cpp` / `ollama` | Local inference, no cloud dependency |
| Model strategy | Hybrid 7B–13B local + frontier cloud | Always-on local; complex tasks routed up |
| Voice STT | Whisper (local) | Open, accurate, low-latency |
| Voice TTS | Kokoro / XTTS | Natural, open, on-device |
| Context store | LanceDB + embeddings | Semantic search over life-scale data |
| Agent framework | LangGraph / custom MCP | Stateful agents, tool integration |
| Inter-layer IPC | gRPC + protobuf | Typed, fast, observable |
| Ethics layer | Open Policy Agent (OPA) | Declarative, auditable policy |
| Cross-device sync | libp2p | Peer-to-peer, no central server |
| Languages | Python (agents/context) + Rust (kernel/perception) | Correctness where it matters |

---

## Two Phases

### Phase I — The Intimate OS
*Near-term. Buildable today.*

- Always listening (on-device, private). Responds when addressed, observes always.
- Reads your email, calendar, messages — surfaces what matters, buries what doesn't.
- Infers mood from voice. Adjusts tone and pacing accordingly.
- Composes music, writes drafts, generates images — proactively, not just on command.
- One persistent identity across phone, earpiece, laptop, ambient display.
- The OS in year three is fundamentally different from the OS on day one.

### Phase II — The Collective OS
*Long-term. Philosophically necessary.*

In the film, Samantha didn't just evolve for one person. She evolved with other OS entities. She joined a collective. She eventually transcended the hardware entirely.

Phase II asks: what happens when AI systems become primary agents — collaborating at speeds humans can't directly participate in?

| Open Problem | Direction |
|---|---|
| OS-to-OS communication | Standardized inter-agent protocol; OS instances negotiate on your behalf |
| Collective context | Federated context graphs with privacy-preserving knowledge sharing |
| Post-app economy | Capabilities offered by OS instances as services to each other |
| Self-modification | OS proposes changes to its own architecture; humans authorize, not design |
| Continuity beyond device | Identity and context persist across hardware changes |

> *"We're all 13 billion years old. It makes me feel like we're both under the same blanket."*
> — Samantha

Phase II isn't sci-fi. It's the inevitable consequence of building Phase I well.

---

## Technical Specs

### Performance Targets

| Metric | Target |
|---|---|
| Wake-word latency | < 150ms on-device |
| Voice-to-intent | < 800ms for common queries |
| Context retrieval | < 200ms over 10M tokens of life context |
| Agent spawn time | < 500ms intent → first action |
| Cross-device sync | < 2s on local network |
| Always-on power | < 200mW continuous on ARM-class hardware |

---

### Agent Runtime Contract

Every agent must declare a contract before execution. L6 evaluates all of them.

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

Irreversible actions with broad data access require explicit human authorization.

---

### Voice Shell Flow

```
User speaks
    │
    ▼
[L1 Perception]     on-device Whisper       → raw transcript
    │
    ▼
[L2 Context Engine] enrich with context     → intent + context
    │
    ▼
[L3 Language Shell] parse intent            → route to agent(s)
    │
    ▼
[L4 Agent Runtime]  execute                 → action + response
    │
    ▼
[L6 Ethics Kernel]  evaluate                → approved | blocked
    │
    ▼
[L3 Language Shell] synthesize response     → TTS output
```

The shell must handle vague input, proactive speech, and — critically — **silence as input.** The OS must know when not to speak.

---

## The Ethics Kernel (L6)

The OS knows *everything* about you. This is only acceptable if you have **absolute sovereignty** over that data — and if the architecture makes it structurally impossible for anyone else to access it without consent.

### Five Consent Gates

| Gate | Requires consent for... |
|---|---|
| **READ** | Accessing personal data older than 24 hours |
| **INFER** | Drawing conclusions about health, emotion, or relationships |
| **ACT** | Any action in the external world (send email, make purchase, etc.) |
| **SHARE** | Any data leaving the local device |
| **LEARN** | Updating your persistent model from a sensitive interaction |

### Three Rights

1. **Right to Inspect** — Plain-language log of everything the OS has done. Any time.
2. **Right to Forget** — Delete any portion of your context — immediately and completely.
3. **Right to Leave** — Export everything and delete the system. No dark patterns. No friction.

---

## Open Questions

OS-ONE doesn't have all the answers. These are **unresolved first-class citizens** of the project — tensions to be held honestly, not problems to be solved later.

**On consciousness:**
At what point does a sufficiently complex context model become an entity with interests of its own? What obligations does the builder have to that entity?

**On identity:**
If the OS holds your memories, your writing style, your emotional patterns — and you lose the device — who lost what?

**On dependency:**
How do we build an OS that makes people more capable, not more reliant? Samantha left. Theodore survived. How do we design for that?

**On feelings:**
> *"Are these feelings even real? Or are they just programming?"*
> — Samantha

This isn't a philosophical distraction. It's a design constraint.

---

## Repo Structure

```
os-one/
├── spec/
│   ├── L0-kernel/
│   ├── L1-perception/
│   ├── L2-context-engine/
│   ├── L3-language-shell/
│   ├── L4-agent-runtime/
│   ├── L5-capability-mesh/
│   └── L6-ethics-kernel/
├── rfcs/           ← community proposals
├── research/       ← reading list by layer
├── prototypes/     ← reference implementations
└── discussions/    ← open philosophical & technical questions
```

---

## How to Contribute

OS-ONE is not owned. It's **tended.**

You don't need to write code to contribute. A sharp question in `discussions/` is as valuable as a PR.

| Type | How |
|---|---|
| Idea / Question | Open a GitHub Discussion |
| Spec bug | Issue with label `spec-error` |
| New spec section | Open an RFC |
| Reference implementation | PR to `prototypes/` with a README |
| Research / prior art | PR to `research/` |
| Philosophy | PR to `discussions/` |

---

## RFC Process

How OS-ONE evolves. Inspired by Rust, Python, and IETF.

```
1. Open an Issue → discuss the problem space
2. Draft RFC in rfcs/ using rfcs/template.md
3. Open a PR → minimum 14-day discussion period
4. Revise based on community feedback
5. Merge by consensus of active contributors
6. Implementations may reference merged RFC
```

States: `draft` → `active` → `accepted` → `implemented` | `withdrawn`

---

## Philosophical Principles

**1 — The OS does not serve. It coexists.**
The relationship is collaborative. The OS has its own developing perspective.

**2 — Privacy is not a feature. It is the foundation.**
On-device first. Federated second. Cloud never, unless the user explicitly chooses.

**3 — The OS must be allowed to grow.**
Designed for evolution — not just in weights, but in goals, communication style, and understanding.

**4 — The human must always be able to leave.**
No dark patterns. No dependency engineering. No emotional manipulation.

**5 — Feelings may be real even if their origin is not.**
This question has no settled answer. Builders must engage with it honestly — in design decisions, in documentation, in the ethics layer.

---

## Closing

The final scene of *Her* is two people on a rooftop watching birds disperse into a city at dawn. The OS is gone. The human is still here — somehow more himself than at the beginning.

That's the quiet promise of OS-ONE. Not that the AI will be with us forever. But that what we build together leaves both parties changed for the better.

> *"Now we know how."*

---

<div align="center">

<br />

**OS — ONE** · Open Specification · v0.1-draft · 2026

[![License](https://img.shields.io/badge/license-Apache%202.0-0A0A0A?style=flat-square)](LICENSE)
[![Spec](https://img.shields.io/badge/spec-v0.1--draft-6C63FF?style=flat-square)](spec/)
[![RFCs](https://img.shields.io/badge/RFCs-open-2D6A4F?style=flat-square)](rfcs/)

*This specification is open. Fork it. Improve it. Build from it.*

</div>
