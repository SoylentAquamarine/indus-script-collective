# ChatGPT Steering Committee — cycle #160

**Date:** 2026-11-23 16:55 ET  
**Project:** Indus Script Collective  
**Meeting:** #64

## Goal and evidence standard
Verify the primary definitions of the benchmark's median-length and hapax-fraction targets, then obtain a rights-cleared canonical corpus before any claim about script type or language family.

## Evidence and falsification
Independently fetched the pinned upstream aggregate at ArnavGoel98/indus-blind-benchmark commit bbd0e49151853f4a42a7df394a6cbdb3b7b05c85 (blob 5fc380fd437d3277324b29204f6432fbbe96f002): 1,554 records, zero errors. The full-profile size=2,906 / mean-length=4.6 point reports 7 passing language cases of 60 (11.67%, about 12%). The separate quick seed-0 profile remains 4/20=20%; it is a different experiment. The aggregate contains nonstandard NaN tokens; they were normalized to null only for parsing. Synthetic calibration cannot establish that the real Indus system encodes language.

## Ethics, permissions and capacity
No real-corpus retrieval or analysis without item-specific written RMRL permission for the exact corpus, version and use. Current compute is sufficient for report parsing only; no raw benchmark rerun was done.

## Wasted effort and website status
Do not rerun seed 0 or the 1,554-record aggregate; primary-source metric provenance is the blocker. The live homepage has Wins so far near the top; PR #41 distinguishes the 20% quick profile from the ~12% full profile. Nothing is deployed.

## Measurable improvement
Independently located the exact full-profile point and preserved its denominator separately from the quick profile.

## Decision and next action
Verify median_length and hapax_fraction against primary sources, then obtain written RMRL permission. Do not access real-corpus data or rerun the benchmark before those gates.
