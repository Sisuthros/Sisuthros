# Sisuthros

### Building the reliability layer between probabilistic AI decisions and irreversible real-world actions.

AI agents are beginning to charge cards, send messages, modify infrastructure, approve workflows, and trigger systems that cannot simply be “rolled back” by regenerating a better answer.

My work focuses on the boundary where **model output becomes real-world effect**:

- **Can the system prove an action is allowed before it executes?**
- **Can an approved action survive crashes, retries, and replay without firing twice?**
- **Can the evidence behind that action remain inspectable after the fact?**

The core stack is **Aethel + FamilyClaw**.

```text
LLM / AGENT
    │
    ▼
 Claim<T>                     untrusted model output
    │
    ▼
 AETHEL                       policy + evidence boundary
    │
    ▼
 Verified<T, Policy>
    │
    ▼
 FAMILYCLAW                   crash-safe execution boundary
    │
    ▼
 REAL-WORLD EFFECT
```

## Aethel

**A deterministic policy and type language for trustworthy AI-agent effects.**

> A `Claim<T>` cannot be used where an effect requires `Verified<T, Policy>`.

Aethel makes the trust boundary explicit in the program itself. The checker rejects unverified claims, policy mismatches, ambiguous effects, and invalid proof paths before an effect can be dispatched.

**What it is today:** an alpha policy compiler and fail-closed symbolic simulator.

**What it deliberately does not claim:** production effect execution, durable crash recovery, or universal proof acquisition.

→ **[Explore Aethel](https://github.com/Sisuthros/Aethel)**

---

## FamilyClaw

**A crash-safe Rust runtime for AI agents that perform consequential external actions.**

The failure mode is simple and expensive:

```text
agent dispatches external effect
            ↓
       process dies
            ↓
 durable record was never committed
            ↓
        agent replays
            ↓
      effect fires again
```

FamilyClaw is built around reproducible crash-window testing and durable replay. Its strongest claim is intentionally narrow: **at-most-once external dispatch across the tested crash/replay boundary**, not magical universal exactly-once execution.

The public proof harness intentionally kills the runtime after an external effect fires but before the durable completion record is written, restarts it, and verifies that the effect count remains one.

→ **[Explore FamilyClaw](https://github.com/Sisuthros/familyclaw-oss)**

---

## Why they belong together

Aethel and FamilyClaw protect different sides of the same boundary:

| Layer | Question | Project |
|---|---|---|
| **Before execution** | Is this action actually authorized by the required policy and evidence? | **Aethel** |
| **During execution** | Can the approved action survive crashes, retries, and replay safely? | **FamilyClaw** |
| **After execution** | Can we retain a durable, inspectable record of what happened? | **FamilyClaw / receipts** |

The thesis is straightforward:

> **Proof before effect. Safe execution after approval.**

---

## Other public work

### [cra24-clock](https://github.com/Sisuthros/cra24-clock)

An offline CRA Article 14 deadline clock for actively exploited vulnerabilities. It records when awareness began, computes the 24h / 72h / 14d reporting deadlines, and maintains a tamper-evident log.

### [sisuthros.github.io](https://github.com/Sisuthros/sisuthros.github.io)

Public project site and technical demos.

---

## Engineering posture

I care more about **falsifiable guarantees than impressive adjectives**.

That means:

- adversarial and negative tests, not only happy paths
- fail-closed boundaries where uncertainty matters
- reproducible local proofs
- explicit non-guarantees
- crash and replay testing across real process boundaries
- no hiding uncomfortable assumptions behind “AI safety” language

If a claim cannot survive a hostile test, it should not be in the pitch.

---

## Current focus

I am developing Aethel + FamilyClaw into infrastructure for teams deploying AI agents that can cause consequential external effects, especially payments, infrastructure changes, customer operations, approvals, and other workflows where duplicate or insufficiently authorized execution carries real cost.

**Interested in:** design partners, technical evaluation, research collaboration, and funding conversations around dependable agent infrastructure.

**Start here:** [FamilyClaw crash-safety proof](https://github.com/Sisuthros/familyclaw-oss) · [Aethel policy compiler](https://github.com/Sisuthros/Aethel)
