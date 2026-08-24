# Context: Prime Intellect bounty — BFCL-v4

## The target

- **BFCL-v4** — US$1,500, status **Open**, section "Search + Tool Use" of the Application-Only sheet.
  Read from the master spreadsheet on 24/Aug/2026. The row carries no organization, no source
  link, no PR and no assignee.
- Attribution is 1 person per bounty, granted through an application, not through a direct PR.
  The sheet is explicit: "BOUNTIES ARE CLOSED, DO NOT SUBMIT PRs FOR THESE DIRECTLY."

## What the sheet demands

BFCL-v4 sits under **Flagship Benchmarks**. That section sets the acceptance bar:

- The port must be **fully faithful to the original benchmark**.
- Completion means **reproducing the source or publicly reported scores over the full suite**,
  for a suitable set of models.
- **Inference credits are supplied by Prime Intellect.** Reproduction is not paid out of pocket.

Two further rules from the Application-Only header apply:

- The applicant must show prior work — a finished open-access bounty, an original environment on
  the Hub, or an independent agent/eval/RL project. One completed project must be linked.
- Submissions that "smell 'fully vibecoded'" are rejected.

## The qualifying credential

The application evidence is **[korck/arch-review-v1](https://app.primeintellect.ai/dashboard/environments/korck/arch-review-v1)**,
published on the Environments Hub on 24/Aug/2026, public, Hub integration test green.
Repo: https://github.com/Korck-lab/arch-review

That project is a credential, not a code base. Nothing in it is reusable here beyond method:
hand-written taxonomy, judge separated from gold, decisions recorded as ADRs, determinism
stated honestly.

## Status of the sibling application

The SWE-Swiss (Full Pipeline) application, US$3,500, was submitted on 24/Aug/2026 with the same
credential. BFCL-v4 is a **second, independent** application, not a fallback. Attribution is per
bounty, so both can be held at once.

Still Open on the same sheet, same credential: AppWorld US$1,000, Xbench-DeepSearch US$600.

## References

- Master spreadsheet: https://docs.google.com/spreadsheets/d/13UDfRDjgIZXsMI2s9-Lmn8KSMMsgk2_zsfju6cx_pNU
  - gid 650541192 = Application-Only, the sheet that counts
  - gid 1235730607 = Open-Access, all closed as of 20/Aug/2026
  - gid 1178381510 = LEGACY, stale status, ignore
- Application typeform: https://form.typeform.com/to/jLfT7v7o
  (draft answers are kept outside this repo; they carry an e-mail address)
- Hub: https://app.primeintellect.ai/dashboard/environments
