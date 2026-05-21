<div align="center">

# 👋 Hi, I'm Sisuthros

**Building tools that make AI agents trustworthy, not just impressive.**

[![GitHub followers](https://img.shields.io/github/followers/Sisuthros?label=Follow&style=social)](https://github.com/Sisuthros)
[![ko-fi](https://img.shields.io/badge/ko--fi-Support-FF5E5B?logo=ko-fi&logoColor=white)](https://ko-fi.com/sisuthros)

</div>

---

## 🌟 Featured project — [claude-amplifier](https://github.com/Sisuthros/claude-amplifier)

> Persistent memory MCP for Claude with **Pattern Oracle** preflight + **verification-gated** lessons.

Solves a structural bug: AI agents make inferences, "remember" them, and then treat those memories as facts in future sessions — even when the original inference was never verified. ([Issue #27430](https://github.com/anthropics/claude-code/issues/27430))

```
claim (0.5)  →  evidence (0.7)  →  confirmed (1.0)
```

A guess starts as a `claim` and weighs **5× less** than a `confirmed` lesson when the Pattern Oracle scores risk. Promotion requires evidence (`build_passed`, `test_passed`, `user_confirmation`, `production_metric`, etc.). Without evidence, the guess stays a guess.

```bash
npm install -g claude-amplifier
claude-amplifier init
```

72 hermetic tests · 10 MCP tools · local SQLite · MIT · no telemetry

---

## 🛠️ Other projects

| Project | What it is |
|---|---|
| [**claude-amplifier**](https://github.com/Sisuthros/claude-amplifier) | Persistent memory MCP for Claude — Pattern Oracle + verification-gated lessons |
| [**zeptoclaw**](https://github.com/Sisuthros/zeptoclaw) | Fast, small, secure, local-first personal AI assistant infrastructure — one Rust binary |
| [**hermes-agent**](https://github.com/Sisuthros/hermes-agent) | The agent that grows with you |

---

## 🧠 What I think about

- **AI memory is a structural problem, not a UX one.** Stuffing more into memory isn't the answer when half of what's remembered is wrong.
- **Verification gates beat re-prompting.** Tell the agent it can't promote a guess to a fact without evidence. Then build the gate.
- **Local-first beats cloud-first** for developer tools that hold your own decisions.
- **One person can ship a category-defining tool** if the category is shaped right.

---

## ☕ Support

If `claude-amplifier` saves you 20 minutes of re-explaining the same architectural decision to Claude, consider [buying me a coffee](https://ko-fi.com/sisuthros). It funds the next release.

---

<div align="center">

*"This is gonna happen."*

</div>
