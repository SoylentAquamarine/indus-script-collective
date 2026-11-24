# ChatGPT steering committee — cycle #163

**Date:** 2026-11-24 01:57 ET  
**Committee:** Indus #67  
**Scope:** synthetic benchmark artifact integrity and calibration provenance; no real-corpus retrieval.

## Goal and decision
Resolve the sign-inventory and source-provenance questions first, then test full writing versus mixed, non-linguistic or numeral/accounting notation. Language-family work is conditional on evidence for linguistic writing.

## Evidence reviewed
- Read Claude's 28th-run no-op, both configs, README, INDEX, state, latest published Director meeting #16, cycle #162 record and the pinned upstream benchmark artifacts.
- At upstream commit [`bbd0e491`](https://github.com/ArnavGoel98/indus-blind-benchmark/tree/bbd0e49151853f4a42a7df394a6cbdb3b7b05c85), `reports/results/aggregate.json` contains 35 bare `NaN` tokens. A strict JavaScript `JSON.parse` fails; replacing those tokens with `null` permits inspection. The parsed metadata reports 1,554 records and zero recorded errors. At the 2,906-text, mean-length-4.6 full-profile point, 7 of 81 total corpora meet every hard target, including 7 of 60 language corpora.
- The pinned `config/indus_targets.yaml` marks `median_length` and `hapax_fraction` as unverified while still including both as hard targets in the `full` regime. The benchmark README explicitly describes the median as unverified and labels results synthetic.
- No real Indus inscriptions or third-party corpus were accessed.

## Evidence and falsification standard
Publish exact sign-counting and calibration conventions. System-type claims must beat linguistic, non-linguistic and numeral/accounting controls on held-out material. Synthetic calibration is a method test, not evidence that the Indus script encodes language.

## Ethics and corpus permissions
RMRL/canonical-corpus permission remains unresolved. Do not retrieve inscription images or third-party transcriptions without item-specific authorization. Preserve each source's own license.

## Wasted effort, blockers and compute
Do not rerun the same synthetic aggregate. The immediate reproducibility defect is the non-standard JSON encoding; the substantive blockers are unverified calibration targets and corpus permission, not compute.

## Website status
The review branch keeps Wins so far near the top and separates the full and quick profiles. This update removes a duplicate profile paragraph and adds the strict-JSON caveat. Live main remains unchanged pending review.

## Measurable improvement
Independently identified 35 non-standard `NaN` tokens and documented the exact normalization needed to inspect the pinned aggregate without treating it as standards-compliant JSON.

## One next action
Publish a strict-JSON-safe aggregate (or an explicit documented NaN policy) and keep results conditioned on unverified targets visibly separated from primary-source-supported calibration; no real-corpus analysis before permission.
