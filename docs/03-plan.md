# Execution plan

The order is deliberate. The application goes out before the port is built, because attribution
is granted by application and the bounty can be assigned to someone else while you code.

## Phase 0 — Scaffold
- [x] Repo created, VS Code and Claude Code settings carried over from `arch-review`
- [x] ADRs 0001–0027 carried over; 0028 and 0029 left behind as taxonomy-specific
- [x] Bounty context and benchmark notes written
- [ ] `git init` and first commit
- [ ] Public repo on GitHub

## Phase 1 — Apply
- [ ] Fill the typeform for BFCL-v4, citing `korck/arch-review-v1` as the completed project
- [ ] Rafael reads all answers and submits. The submission is his click, never the agent's.

## Phase 2 — Ground truth
- [ ] Clone `ShishirPatil/gorilla`, install `bfcl-eval`, run the upstream suite once
- [ ] Record the upstream numbers for at least one model, unmodified
- [ ] Answer the four open questions in `02-benchmark.md`

Nothing is ported before the upstream run reproduces. Without a local baseline there is no
definition of "faithful".

## Phase 3 — Port
- [ ] Scaffold the verifiers environment
- [ ] Wire the deterministic AST matcher as the reward
- [ ] Cover the v4 agentic parts: web search, memory, format sensitivity
- [ ] Cover the retained core categories

## Phase 4 — Reproduce
- [ ] Run the full suite on the agreed model set, using the supplied inference credits
- [ ] Compare against the published numbers, per sub-category, not just the mean
- [ ] Write the results into the README, including anything that did not reproduce

## Phase 5 — Publish
- [ ] `prime env push`
- [ ] Set visibility to Public in the web UI. The `--visibility` flag is ignored; see
      `arch-review/docs/02-hub-publication.md`
- [ ] Confirm the Hub integration test is green

## Risks

- **BFCL-v4 is assigned to someone else while this is built.** Mitigation: apply in Phase 1,
  before any port work. AppWorld and Xbench-DeepSearch remain open on the same credential.
- **The web-search part may not be reproducible.** A live search backend gives a different
  answer each run. If upstream does not record and replay, faithfulness and determinism
  conflict, and that conflict has to be documented rather than hidden.
- **Reproducing a published score can fail for reasons outside the port** — model version drift,
  a changed provider default, an undisclosed prompt. ADR-0027 applies: find the cause, do not
  tune until the number matches.
- **The Prime account has no inference balance today.** The bounty supplies credits, but only
  after selection. Phase 2 must run on something free or local.
