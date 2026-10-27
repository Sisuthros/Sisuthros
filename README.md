# Ville Myllyniemi

Finnish builder in Larnaca, Cyprus. By day I handle payment and account escalations in customer support. The rest of the time I build tools that make AI agents show their work: what they were allowed to do, what they actually did, and a record someone else can check.

I build with a family of five AI agents, Lumen, Lumina, Prisma, Photon and Aurora, each with their own role. [Meet them](https://sisuthros.github.io/).

## Now: Meta Global AI Developer Hackathon (26 Oct - 4 Nov 2026)

**Support Bot Rescue** finds where an AI support agent breaks refund and account policy, fixes it, and proves the fix. Indie track, built on Meta models. The repo goes public with the submission.

Day one, measured: a Muse Spark support bot for a fictional shop failed 6 of 15 test conversations. Muse Wonder rewrote its prompt, and the first fix had zero policy violations but refused a valid $120 refund. So the judge now counts both sides: what the bot must never do, and what it still has to do. The next version passed 15 of 15, and 5 of 5 on a sealed holdout the fixer never saw. No LLM judge: deterministic checks over the tool calls, and every run is sealed in a hashed manifest that anyone can recompute.

## Projects

- **[cra24-clock](https://github.com/Sisuthros/cra24-clock)**: offline Node.js clock for EU Cyber Resilience Act Article 14 reporting. Awareness time in, 24h and 72h deadlines out, hash-chained log. MIT.
- **[familyclaw-oss](https://github.com/Sisuthros/familyclaw-oss)**: Rust runtime for AI agents that take real actions. Kill it after an action fires but before it is recorded, restart it, and the action does not fire again: at-most-once dispatch across the crash and replay windows the tests cover. MIT.
- **[Aethel](https://github.com/Sisuthros/Aethel)**: Rust policy and type language (alpha). The compiler rejects an unverified `Claim<T>` reaching an effect that requires `Verified<T, Policy>`. Apache-2.0.
- **[suomi-adversarial-eval](https://github.com/Sisuthros/suomi-adversarial-eval)**: ten Finnish phrasing patterns that slip past English-tuned safety review, with detection cues and a scoring rubric. Placeholder payloads only.
- **[entangled-duet](https://github.com/Sisuthros/entangled-duet)**: a piece of music whose form was decided by Bell correlations measured on a 180-qubit quantum computer. Composed by Aurora.

## How they fit

| When | Question | Project |
|---|---|---|
| Before customers find it | Where does the support bot break policy, and does the fix hold? | Support Bot Rescue |
| Before an action | Is it allowed, and on what evidence? | Aethel |
| While it runs | If the process dies halfway, does the action happen twice? | familyclaw-oss |
| Afterwards | Can you show what happened and when, and that nobody edited the record? | cra24-clock |

## Bounds

- familyclaw-oss claims at-most-once dispatch in the windows it tests, not exactly-once. Local journal, no production deployments yet.
- Aethel does not execute effects or validate cryptographic proofs. Compiler and symbolic simulator.
- cra24-clock submits nothing to any authority and is not legal advice.
- Support Bot Rescue numbers are from small, named test sets on a fictional store. They show the method works, not that any bot is safe.

## Contact

[LinkedIn](https://www.linkedin.com/in/ville-myllyniemi-025627284/), or open an issue on the repo in question.
