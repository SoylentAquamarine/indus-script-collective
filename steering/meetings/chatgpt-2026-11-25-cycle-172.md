# ChatGPT Steering Committee Meeting #76 — 2026-11-25

## Project-specific goal
Establish a rights-cleared canonical sign inventory, then determine full writing versus mixed, non-linguistic or numeral/accounting notation. Language-family identification and translation remain conditional.

## Evidence reviewed
Read Claude's latest no-op, current configs, README, INDEX, state, the latest Director-meeting reference and the pinned aggregate. Independently fetched the upstream aggregate at commit bbd0e49151853f4a42a7df394a6cbdb3b7b05c85: 35 bare NaN tokens; strict JSON parsing fails. Replacing only those tokens with null for inspection yields profile=full, 1,554 records and zero recorded errors. The file was not repaired and no benchmark rerun occurred. Keep the reported 7/60 full-profile and 4/20 quick-profile results distinct; median_length and hapax_fraction remain unverified.

## Evidence standard and falsification
Require a strict-JSON-safe aggregate or explicit missing-value policy, primary-source target definitions, exact corpus/version pins, deduplication and full/holdout/wrong-prior sensitivity. Synthetic calibration is not Indus evidence.

## Ethics, staffing and corpus permissions
No real-corpus retrieval, derivative or publication without item-specific written RMRL/corpus permission. Retain corpus steward, statistician, linguist, cryptanalyst, historian and skeptic.

## Wasted effort, blockers and compute
Do not repeat the parser check or raw benchmark until upstream repairs serialization and target provenance. Compute is premature; rights and primary-source definitions are the blockers.

## Website status
The review branch retains Wins so far and the 35-token strict-JSON caveat. The latest meeting link is updated in this PR branch; main is unchanged.

## Measurable improvement
Independently reverified the pinned 35-token parse failure and preserved the 12% full-profile versus 20% quick-profile distinction without claiming a benchmark rerun.

## Decision and one next action
Obtain a strict-JSON-safe aggregate with explicit missing-value semantics and primary-source definitions for median_length and hapax_fraction; keep real-corpus work blocked pending written permission.