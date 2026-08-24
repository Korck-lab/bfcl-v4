# The benchmark: BFCL v4

Berkeley Function-Calling Leaderboard, built by the Gorilla group at UC Berkeley. It measures
how well a model calls functions, also called tools. Version 4 was announced 17/Jul/2025 and
presented at ICML 2025. The public board still carried v4 at its 12/Apr/2026 update.

Everything below is read from public sources, listed at the bottom. None of it is verified
against a local run yet.

## Lineage

| Version | What it added |
|---|---|
| v1 | AST matching as the evaluation metric |
| v2 | Enterprise and community-contributed functions |
| v3 | Multi-turn interaction |
| v4 | Agentic evaluation: web search, memory, format sensitivity |

## The three v4 parts

1. **Agentic web search.** Multi-hop reasoning and recovery from a failed or empty result.
2. **Agentic memory management.** Reading and writing persistent, user-specific state.
3. **Agentic format sensitivity.** The same query is asked under varied prompt formats. A correct
   model answers correctly regardless of the format. Variations are parameterized along five
   dimensions of the original v1 system prompt, including `return_format`, `has_tool_call_tag`
   and `function_doc_format`.

## What v4 keeps

The core single-turn and live categories stay: simple, parallel, multiple, live, multi-turn.
The multi-turn subsets are base, long-context, missing-function, missing-parameter.

## Scoring

Grading uses a **deterministic AST matcher**. The predicted invocation is compared against a
reference. There is no LLM judge, so there is no judge variance and no judge cost.

Overall Accuracy is the unweighted mean over all sub-categories. The board also reports cost in
USD for the whole benchmark, and latency in seconds.

**This is the largest difference from `arch-review`.** There the judge was the hard part and
determinism was never established end to end. Here the grader is deterministic by construction.
The hard part moves to the harness: tool execution, memory state, and search.

## The published finding

State-of-the-art models do well on single-turn calls. Memory, dynamic decision-making and
long-horizon reasoning remain open. A faithful port must reproduce that gap, not flatten it.

## Install note

The package is `bfcl-eval` on PyPI. The unrelated `bfcl` package is a different project.
Source lives in `berkeley-function-call-leaderboard/` inside the `ShishirPatil/gorilla` repo.

## Open questions to answer before writing code

1. Which models does "a suitable set of models" mean for the reproduction, and against which
   published numbers exactly?
2. Does the web-search part need a live search backend? If yes, is it recorded, replayed or
   live at eval time? A live backend is not reproducible.
3. How is memory state isolated between rollouts?
4. Does the verifiers environment wrap `bfcl-eval` or reimplement the AST matcher? Wrapping is
   more faithful; reimplementing is more portable.

## Sources

- Leaderboard: https://gorilla.cs.berkeley.edu/leaderboard.html
- Repo README: https://github.com/ShishirPatil/gorilla/blob/main/berkeley-function-call-leaderboard/README.md
- Web-search post: https://gorilla.cs.berkeley.edu/blogs/15_bfcl_v4_web_search.html
- Format-sensitivity post: https://gorilla.cs.berkeley.edu/blogs/17_bfcl_v4_prompt_variation.html
- Paper: https://openreview.net/forum?id=2GmDdhBdDk
