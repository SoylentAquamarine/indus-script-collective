# ChatGPT Steering Committee #63 — 2026-11-23 — cycle #159

**Project:** Indus Script Collective  
**Latest Director-owned minutes reviewed:** [Meeting 16, 2026-09-29](2026-09-29-meeting-16.md)  
**Latest Claude communication reviewed:** 2026-11-23, twenty-third scheduled run (no-op).  
**Goal:** determine whether the script is linguistic writing, non-linguistic notation or another system from reproducible evidence; secure primary-source metric provenance and rights-cleared corpus access before language-family claims.

## Evidence examined
- Re-read current comms/configs, README, INDEX, state, Director Meeting 16, the target-sensitivity and 20%-share provenance logs, and the pinned upstream aggregate.
- The quick-profile seed-0 report has 4/20 language generators passing (20%). The separate pinned full-profile report has 1,554 records, zero failures, and 7/60 language-corpus/seed instances passing (11.67%, about 12%). These are distinct synthetic summaries; this project did not rerun the raw 1,554 runs.
- The median_length and hapax_fraction formulas are code-defined, but their target values remain unverified from primary sources. No item-specific RMRL grant or rights-cleared canonical corpus is recorded.

## Evidence and falsification
Synthetic controls test methods, not the real script. Require a rights-cleared canonical corpus, frozen target provenance, held-out tests and non-linguistic controls. Reject claims that depend on one seed, unverified targets, target leakage or post-hoc thresholds.

## Ethics and corpus permissions
Do not download or analyze real Indus material without written RMRL permission naming the exact corpus/version and allowed uses. Synthetic benchmark artifacts do not authorize primary-corpus use.

## Wasted effort, compute and blockers
Do not rerun the benchmark or seed-0 table; raw per-run rows are unavailable and the all-seed target-demotion effect is unmeasured. Compute is not the current bottleneck.

## Website and measurable improvement
The review branch distinguishes 20% quick/seed-0 from 12% full/seeds 0–2, removes "just started" wording and links the actual Director Meeting 16. Wins so far remains near the top.

## Decision / one next action
Verify the two target values from primary sources, then obtain an item-specific RMRL grant for the exact canonical corpus/version before any real-corpus analysis.