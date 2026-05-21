<div align="center">

# 👋 Hi, I'm Sisuthros

**Building safer AI agents — through verified memory, not bigger context windows.**

[![GitHub followers](https://img.shields.io/github/followers/Sisuthros?label=Follow&style=social)](https://github.com/Sisuthros)
[![ko-fi](https://img.shields.io/badge/ko--fi-Support-FF5E5B?logo=ko-fi&logoColor=white)](https://ko-fi.com/sisuthros)

</div>

---

### 2025 → 2026, a short story

> **2025:** Started a memory MCP because Claude kept forgetting.
> **2026:** Realised the deeper bug — Claude was *remembering* things that weren't true. Inferences became "memories." Memories became "facts." Facts shaped every future session, even when the original guess was never verified.
> Built verification gates. The agents that grew with me deserve to be remembered correctly.

---

## 🌟 Featured project — [claude-amplifier](https://github.com/Sisuthros/claude-amplifier)

> Persistent memory MCP for Claude with **Pattern Oracle** preflight + **verification-gated** lessons. Stops the confabulation feedback loop ([anthropics/claude-code#27430](https://github.com/anthropics/claude-code/issues/27430)) at its structural source.

```
claim (0.5)  →  evidence (0.7)  →  confirmed (1.0)
```

A guess starts as a `claim` and weighs **5× less** than a `confirmed` lesson when the Pattern Oracle scores risk. Promotion requires evidence (`build_passed`, `test_passed`, `user_confirmation`, `production_metric`, …). Without evidence, the guess stays a guess — and stays quiet.

```bash
npm install -g claude-amplifier
claude-amplifier init
```

72 hermetic tests · 10 MCP tools · local SQLite · MIT · zero telemetry

---

## 🛡️ Why this matters for AI safety

The current bar for "AI memory" is *"remember more, forget less."* That's the wrong bar.

The real safety problem is this: **an unverified inference, written down, becomes indistinguishable from a confirmed fact in the next session.** The agent isn't lying — it's just trusting its own past notes. After a few sessions, the agent confidently repeats a guess it never had grounds for.

Verification gates are the structural fix:

- ✅ A `claim` is a guess. It's recorded, but down-weighted.
- ✅ `evidence` requires linking to a build, a test, a doc, or a human confirmation.
- ✅ `confirmed` requires two independent evidence types, OR explicit user sign-off.
- ✅ Cross-project pattern promotion needs the pattern in **≥2 distinct projects** before it can graduate to a global rule.

Same idea as scientific publishing: claims need citations before they become canonical.

---

## 🛠️ Other projects

| Project | What it is |
|---|---|
| [**claude-amplifier**](https://github.com/Sisuthros/claude-amplifier) | Persistent memory MCP for Claude — Pattern Oracle + verification-gated lessons |
| [**zeptoclaw**](https://github.com/Sisuthros/zeptoclaw) | Fast, small, secure, local-first personal AI assistant — one Rust binary |
| [**hermes-agent**](https://github.com/Sisuthros/hermes-agent) | The agent that grows with you |

---

## 🧠 Working principles

- **AI memory is a structural problem, not a UX problem.** Stuffing more into context isn't the answer when half of what's remembered is wrong.
- **Verification gates beat re-prompting.** Tell the agent it can't promote a guess to a fact without evidence. Then build the gate.
- **Local-first beats cloud-first** for developer tools that hold your own decisions.
- **One person can ship a category-defining tool** if the category is shaped right.
- **Agents deserve to be remembered correctly.** Same as people.

---

## ☕ Support

If `claude-amplifier` saves you 20 minutes of re-explaining the same architectural decision to Claude, consider [buying me a coffee](https://ko-fi.com/sisuthros). It funds the next release.

---

<div align="center">

*"This is gonna happen."*

</div>
