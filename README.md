# bfcl-v4

A faithful port of the **Berkeley Function-Calling Leaderboard v4** to the Prime Intellect
Environments Hub.

BFCL v4 measures how well a model calls tools. Version 4 adds three agentic parts on top of the
earlier single-turn and multi-turn categories: web search with multi-hop reasoning, memory
management, and format sensitivity. Grading uses a deterministic AST matcher against a reference
invocation, so there is no LLM judge and no judge variance.

Built against the **BFCL-v4 bounty**, US$1,500, Application-Only, Open as of 24/Aug/2026.

## Status

- [x] Phase 0 — scaffold, bounty context, benchmark notes
- [ ] Phase 1 — application submitted
- [ ] Phase 2 — upstream suite reproduced locally
- [ ] Phase 3 — port to a verifiers environment
- [ ] Phase 4 — full-suite reproduction against the published numbers
- [ ] Phase 5 — published on the Hub

Nothing is ported before the upstream suite reproduces locally. Without a baseline there is no
definition of "faithful". See `docs/03-plan.md`.

## Results

None yet. This section will hold the per-sub-category comparison against the published numbers,
including any category that does not reproduce.

## Docs

| File | Holds |
|---|---|
| `docs/01-bounty-context.md` | The bounty, its acceptance bar, the qualifying credential |
| `docs/02-benchmark.md` | What BFCL v4 is, how it scores, four open questions |
| `docs/03-plan.md` | Phase checklist and risks |
| `docs/adr/` | Accepted engineering decisions. Start at `docs/adr/README.md` |

## Credential

The application evidence is [korck/arch-review-v1](https://app.primeintellect.ai/dashboard/environments/korck/arch-review-v1),
published 24/Aug/2026 ([repo](https://github.com/Korck-lab/arch-review)). It is a separate
project. Nothing in it is reused here except method.

## Repo rules

- The repo is public. It is part of the showcase.
- No PII.
- Upstream code is cited, never silently copied.
- Every decision that constrains later work becomes an ADR.

## Sources

Listed in `docs/02-benchmark.md`.
