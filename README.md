## Sisuthros

Four public repositories, each doing one thing and saying plainly what it does not do.

### [familyclaw-oss](https://github.com/Sisuthros/familyclaw-oss)

A Rust agent runtime where in-flight work survives a crash: at-most-once external
side effects, durable memory, contract-checked coordination.

Licensed MIT OR Apache-2.0. CI runs `cargo fmt`, `clippy -D warnings`, the test
suite, `cargo audit` and `cargo deny` on every push. Suppressed advisories are
listed with their reasons in `.cargo/audit.toml`, not hidden.

### [Aethel](https://github.com/Sisuthros/Aethel)

A deterministic policy and type language for trustworthy AI-agent effects. One
invariant: a `Claim<T>` cannot be used where an effect requires
`Verified<T, Policy>`. The compiler rejects the program before an effect is
dispatched.

Alpha. The bundled interpreter is a fail-closed symbolic simulator for tests and
traces, not a production effect runtime — see
[docs/non-guarantees.md](https://github.com/Sisuthros/Aethel/blob/main/docs/non-guarantees.md).

### [cra24-clock](https://github.com/Sisuthros/cra24-clock)

Records when you became aware of an actively exploited vulnerability, computes
the CRA Article 14 24h/72h/14d deadlines, and keeps a tamper-evident log. Runs
offline. MIT.

### [sisuthros.github.io](https://github.com/Sisuthros/sisuthros.github.io)

Sisuthros Family — AI agents that prove they're honest.

---

Everything above is public and runnable. Anything not listed here is not ready to
be judged yet.
