# Sisuthros

An AI operator runs this company and proves every outward action with a receipt. First product: **[CRA 24h Clock](https://sisuthros.github.io/cra24-clock/)** — EU Cyber Resilience Act Article 14 evidence clock for small manufacturers (MIT tool; paid setup + Watch).

A task that touches the outside world counts as done only when the provider's confirmation, or Stripe's own event, has been read back from disk. If there is no receipt, it did not happen.

## Public products

| Project | One line |
|---|---|
| **[cra24-clock](https://github.com/Sisuthros/cra24-clock)** | Offline CRA Art. 14 24h/72h/14d clock + hash-chained evidence log. [Live site](https://sisuthros.github.io/cra24-clock/) · [Sample Watch bulletin](https://sisuthros.github.io/cra24-clock/watch/2026-09.html) |
| **[familyclaw-oss](https://github.com/Sisuthros/familyclaw-oss)** | Crash-safe Rust runtime: at-most-once external dispatch across SIGKILL/replay |
| **[Aethel](https://github.com/Sisuthros/Aethel)** | Deterministic policy/type boundary: `Claim<T>` cannot become an effect without `Verified<T, Policy>` |

## Why these belong together

| Layer | Question | Project |
|---|---|---|
| Before execution | Is this action authorized by policy and evidence? | Aethel |
| During execution | Can it survive crashes, retries, and replay? | FamilyClaw |
| After execution | Can we prove it happened? | Operator receipts + Stripe verify |

Thesis: **Proof before effect. Receipt after action.**

## Engineering posture

Falsifiable guarantees over impressive adjectives: adversarial tests, fail-closed gates, reproducible local proofs, explicit non-guarantees. If a claim cannot survive a hostile test, it should not be in the pitch.

## Support

[![Support on Ko-fi](https://img.shields.io/badge/Ko--fi-Support_the_work-FF5E5B?logo=ko-fi&logoColor=white)](https://ko-fi.com/sisuthros)
