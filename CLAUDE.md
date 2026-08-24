# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this
repository.

## Purpose

`bfcl-v4` ports the Berkeley Function-Calling Leaderboard v4 to the Prime Intellect Environments
Hub, against the BFCL-v4 bounty (US$1,500, Application-Only, Open on 24/Aug/2026).

The acceptance bar is set by the bounty sheet: the port must be **fully faithful** to the
original benchmark and must **reproduce the published scores over the full suite**. See
`docs/01-bounty-context.md`.

## Current state

Scaffold only. No environment code, no tests, no upstream run. `docs/` holds the bounty context,
the benchmark notes, the plan, and the inherited ADRs.

The next step is Phase 1 in `docs/03-plan.md`: submit the application. The port comes after.

## Repo rules

- The repo is public. It is part of the showcase.
- No PII. The typeform draft stays outside the repo; it carries an e-mail address.
- Upstream code from `ShishirPatil/gorilla` is cited, never silently copied.
- Faithfulness beats convenience. A deviation from upstream is recorded as an ADR or it does not
  happen.

## Architecture decisions

`docs/adr/` holds the accepted decisions, carried over from `arch-review`. Read the ADRs that
touch the area you are about to change. Start at `docs/adr/README.md`.

If your work contradicts an ADR, say so explicitly instead of overriding it silently.

The three that bite hardest here:

- **ADR-0003** — nothing is dropped silently. An unclassifiable tool call goes to a named bucket.
- **ADR-0027** — a score below the published number is a defect to explain at its root cause,
  never a threshold to lower.
- **ADR-0022** — validate at the model-extraction seam. The format-sensitivity part varies the
  response syntax on purpose; prompt prose will not hold it.

New decisions in this project start at 0028.

## Submission rule

The final application submission is Rafael's decision and Rafael's click. Prepare everything,
review it together, submit only on an explicit ok.

## Agent skills

### Issue tracker

Issues live as GitHub issues, via the `gh` CLI. See `docs/agents/issue-tracker.md`.

### Triage labels

The five canonical labels, unrenamed. See `docs/agents/triage-labels.md`.

### Domain docs

Single-context: `CONTEXT.md` plus `docs/adr/` at the repo root. See `docs/agents/domain.md`.
