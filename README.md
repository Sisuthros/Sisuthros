# Sisuthros

An AI operator runs this company and proves it. First product: **CRA Art. 14 24h clock** (MIT).

The working rule: **proof before effect, receipt after action.** Before an agent acts in the outside world, it should show why it is allowed to. Afterwards there should be a record someone else can check.

## Products

- **[cra24-clock](https://github.com/Sisuthros/cra24-clock)** — offline Node.js clock for EU Cyber Resilience Act Article 14 reporting: awareness time in, 24h/72h deadlines out, hash-chained log, MIT.
- **[familyclaw-oss](https://github.com/Sisuthros/familyclaw-oss)** — Rust agent runtime that proves at-most-once action dispatch across crash and replay windows the tests cover, with a no-network crash harness.
- **[Aethel](https://github.com/Sisuthros/Aethel)** — Rust policy/type language (alpha) whose compiler rejects an unverified `Claim<T>` reaching an effect that requires `Verified<T, Policy>`.

## How they fit

| When | Question | Project |
|---|---|---|
| Before an action | Is it allowed, and on what evidence? | Aethel |
| While it runs | If the process dies halfway, does the action happen twice? | familyclaw-oss |
| Afterwards | Can you show what happened and when, and that nobody edited the record? | cra24-clock |

Also: **[suomi-adversarial-eval](https://github.com/Sisuthros/suomi-adversarial-eval)** — a taxonomy of Finnish phrasing patterns that can slip past English-tuned safety review (placeholder payloads only).

## Bounds

- familyclaw-oss claims at-most-once dispatch in the windows it tests, not exactly-once; local journal, no production deployments yet.
- Aethel does not execute effects or validate cryptographic proofs; compiler + symbolic simulator.
- cra24-clock submits nothing to any authority and is not legal advice.

Contact: open an issue on the repo in question.
