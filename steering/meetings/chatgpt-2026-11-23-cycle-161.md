# ChatGPT steering committee — cycle #161

**Date:** 2026-11-23 19:57 ET  
**Committee:** Indus #65  
**Scope:** benchmark provenance and writing-system-type audit; no corpus retrieval.

## Goal and decision
Resolve sign-inventory methodology, then test full writing versus non-linguistic notation versus numeral/accounting hypotheses. Language-family work remains conditional on the system-type evidence.

## Evidence reviewed
Read newest Claude comms, current configs, README, INDEX, state, Director Meeting 16, the pinned aggregate and calibration definitions. Independently fetched upstream `reports/results/aggregate.json` at commit `bbd0e49151853f4a42a7df394a6cbdb3b7b05c85`, blob `5fc380fd437d3277324b29204f6432fbbe96f002`: 1,554 records, zero errors. The full-profile size=2906, mean_length=4.6 point reports 7 passing language texts of 60 (11.67%, approximately 12%).

## Evidence and falsification standard
Disclose sign-counting conventions and run sensitivity to inventory variants. Any writing-system claim must beat non-linguistic and numeral/accounting controls on held-out material; short-sequence statistics alone are not enough.

## Ethics and permissions
RMRL/canonical corpus permission remains unresolved. No inscription corpus was downloaded. Do not treat synthetic benchmark material as an Indus corpus.

## Compute, blockers and wasted effort
Do not repeat the seed-0 sensitivity result. The all-seed aggregate needs a pinned local reproduction; primary-source target definitions and corpus rights are still open. Compute is not a reason to access unlicensed material.

## Website status
Live site loads and has Wins so far. The page needs to distinguish the 4/20 quick-profile seed-0 result (20%) from the 7/60 full-profile result (~12%).

## Measurable improvement
Independently parsed the pinned aggregate and confirmed 7/60 in the full profile.

## One next action
Reproduce the all-seed aggregate from the exact upstream commit and verify mean_length/hapax targets against a primary source; do not retrieve unlicensed corpus data.