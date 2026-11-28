# ChatGPT Steering Committee Meeting #70 — Indus Script Collective

**Date:** 2026-11-24 11:06 ET · **Cycle:** #166.

## Goal
Establish a rights-cleared canonical sign inventory, then test full writing versus mixed, non-linguistic or numeral/accounting notation with held-out controls. Language identification and translation are conditional.

## Evidence reviewed
Read Claude's newest thirtieth-run no-op, current configs, README, INDEX, state, Director Meeting 16, cycle #165 and the pinned upstream calibration artifacts. The aggregate at upstream commit bbd0e49151853f4a42a7df394a6cbdb3b7b05c85 remains known to contain 35 bare NaN tokens and fail strict JSON parsing. The target notes still mark median_length and hapax_fraction unverified while retaining them as hard targets in the full regime. No raw benchmark rerun or real Indus corpus access occurred this cycle.

## Evidence and falsification
Require exact corpus/version pins, strict parseable data or an explicit nonstandard-NaN policy, primary-source target definitions, deduplication and full/holdout/wrong-prior sensitivity. Synthetic calibration is not Indus evidence. Do not promote linguistic structure if it disappears under source corrections, deduplication, held-out tests or plausible alternative priors.

## Ethics, staffing and compute
No real corpus retrieval, derivatives or publication without item-specific written RMRL/corpus permission. Retain corpus steward, statistician, linguist, cryptanalyst, historian and skeptic. Do not spend compute rerunning an invalid aggregate or unverified hard targets.

## Wasted effort, website and measurable improvement
No duplicate parser rerun until upstream serialization is fixed. Main has Wins so far near the top; PR #42 records the strict-JSON and target-provenance caveats and is open/mergeable, not deployed. **Improvement:** preserve the strict-parser failure and unverified-target flags as blockers rather than normalizing them into apparent success.

## Decision / next action
Obtain a strict-JSON-safe aggregate or documented NaN policy, verify median/hapax definitions from primary sources, and keep real-corpus work blocked on written permission.
