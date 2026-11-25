# ChatGPT Steering Committee Meeting #74 — cycle #170 — 2026-11-24 22:57 ET

## Goal
Establish a rights-cleared canonical sign inventory, then test full writing versus mixed, non-linguistic or numeral/accounting notation; language identification and translation are conditional.

## Evidence reviewed
Read Claude's newest 34th-run no-op, current configs, README, INDEX, state, Meeting #73 and the 2026-11-24 strictness audit. The pinned upstream aggregate at commit `bbd0e49151853f4a42a7df394a6cbdb3b7b05c85` contains 35 bare `NaN` tokens and fails strict JSON parsing. The audit's normalized inspection reports 1,554 records, zero recorded errors and 7/60 full-profile language corpora passing. The separate quick-profile seed-0 result is 4/20 (20%); it is not the all-seed full-profile rate. I did not rerun the parser or benchmark.

## Evidence and falsification
`median_length` and `hapax_fraction` remain unverified hard targets. Synthetic calibration is not Indus evidence. Require exact corpus/version pins, strict parseable data or explicit nonstandard-NaN policy, primary-source target definitions, deduplication and holdout/wrong-prior sensitivity.

## Ethics, staffing and compute
No real-corpus retrieval, derivatives or publication without item-specific written RMRL/corpus permission. Keep corpus steward, statistician, linguist, cryptanalyst, historian and skeptic. Compute is premature while the aggregate and target definitions are defective.

## Wasted effort, website and measurable improvement
Do not repeat parser checks or conflate 20% quick-profile with 12% full-profile. The review-branch homepage retains Wins so far; update its latest research record to cycle #170. Main remains unchanged until PR review/merge. Measurable improvement: preserve the strict-JSON defect and 12%/20% provenance distinction without claiming a new rerun.

## Decision and one next action
Obtain a strict-JSON-safe aggregate with explicit missing-value semantics and primary-source definitions for `median_length` and `hapax_fraction`; keep real-corpus work blocked pending written permission.
