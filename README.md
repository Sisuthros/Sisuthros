# Sisuthros

Finnish, living in Cyprus. I build tools for AI agents that take real actions, like sending an email or charging a card, and then I try to make them fail.

The rule I work by: **proof before effect, receipt after action.** Before an agent does something in the outside world, it should be able to show why it is allowed to. Afterwards there should be a record that someone else can check.

## Projects

- **[suomi-adversarial-eval](https://github.com/Sisuthros/suomi-adversarial-eval)**: ten ways Finnish phrasing can carry a harmful request past a safety review that was built and tuned in English. A case ending hides the act, a compound word hides the concept, the passive removes the actor, and there are seven more. Each pattern has a detection cue and a scoring note for people who rate model outputs. It is written as a taxonomy, not an attack kit: every example uses `[KOHDE]` in place of a payload.
- **[familyclaw-oss](https://github.com/Sisuthros/familyclaw-oss)** (Rust): a runtime for AI agents. Kill the process after an action has fired but before it was recorded, restart it, and the action does not fire again, within the crash and replay windows the tests cover. `bash scripts/crash-proof.sh` runs the proof with no API keys and no network. [![Crash Matrix](https://github.com/Sisuthros/familyclaw-oss/actions/workflows/crash-matrix.yml/badge.svg)](https://github.com/Sisuthros/familyclaw-oss/actions/workflows/crash-matrix.yml)
- **[cra24-clock](https://github.com/Sisuthros/cra24-clock)** (Node.js): a command-line clock for EU Cyber Resilience Act Article 14 reporting. It records when you became aware of a vulnerability, computes the 24 h and 72 h deadlines, and keeps a hash-chained log. Offline, MIT.
- **[Aethel](https://github.com/Sisuthros/Aethel)** (Rust, alpha): a policy and type language for agent actions. The compiler rejects a program where an unverified `Claim<T>` reaches an effect that requires `Verified<T, Policy>`. [![Aethel CI](https://github.com/Sisuthros/Aethel/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/Sisuthros/Aethel/actions/workflows/ci.yml)

## How they fit together

| When | Question | Project |
|---|---|---|
| Before an action | Is it allowed, and on what evidence? | Aethel |
| While it runs | If the process dies halfway, does the action happen twice? | FamilyClaw |
| Afterwards | Can you show what happened and when, and that nobody edited the record? | cra24-clock, for CRA reporting deadlines |

suomi-adversarial-eval comes one step earlier. It asks whether a safety reviewer is judging the Finnish sentence the model actually saw, or an English translation that reads differently.

## How I test

I want to see a test fail before I trust it when it passes.

- FamilyClaw's crash harness can also run the pre-fix code path (`--mode old`). There the same crash makes the action fire twice, so a pass on the current code is measuring the fix. A scheduled workflow rebuilds and reruns the crash matrix every day, and it fails unless the duplicate count is zero.
- An Aethel breaker test counts only if the compiler rejects the program with the exact diagnostic code the test expects. A parser crash does not count.
- cra24-clock will not give a final report deadline until you record a fix, because that 14-day clock starts from the fix. Its `verify` command recomputes the hash chain and names any line edited afterwards, including edits made by the tool's authors.

## What these do not claim

- FamilyClaw claims at-most-once dispatch across the crash and replay windows it tests, not exactly-once. It runs as a single process with a local journal and has no production deployments yet.
- Aethel does not execute effects, resume after a crash or validate cryptographic proofs. It is a compiler and a symbolic simulator.
- cra24-clock submits nothing to any authority and is not legal advice.
- suomi-adversarial-eval tested no model, has one author and has no inter-rater agreement data.

Each README lists the rest.

## About me

My day job is technical customer support. Before that I helped start a food truck, and sold cars and did IT support at a car dealership in Finland.

I taught myself to build software with AI. I work with AI coding agents, including a family of agents that I run myself. I decide what gets built and read what they produce. A task that touches the outside world counts as done only when the other side's own confirmation has been read back.

Languages: Finnish (native), English (professional working level).

Contact: open an issue on the repo in question.

Suomeksi: olen suomalainen ja asun Kyproksella. Päivätyöni on teknistä asiakastukea. Sen lisäksi rakennan tekoälyagentteja ja testaan, missä kohdassa ne pettävät.
