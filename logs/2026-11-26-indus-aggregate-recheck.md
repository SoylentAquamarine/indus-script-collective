# Pinned Indus aggregate and target-share recheck

**Date:** 2026-11-26 01:55 ET  
**Scope:** Read-only check of pinned upstream artifacts; not a benchmark rerun and no real Indus corpus access.

## Exact upstream pin
Repository: https://github.com/ArnavGoel98/indus-blind-benchmark  
Commit: bbd0e49151853f4a42a7df394a6cbdb3b7b05c85  
Aggregate: reports/results/aggregate.json  
Calibration report: reports/calibration_report.md

## Aggregate serialization
Fetched the exact pinned aggregate. Its header declares profile=full, n_records=1554 and n_errors=0, but the file contains 35 bare NaN tokens. Native JSON.parse fails at the first bare NaN. This confirms the strict-JSON serialization defect at the pinned commit; no upstream file was modified and no benchmark was rerun.

## Target-share correction
Directly re-read the pinned calibration_report.md:
- Section 2 reports 18 of 27 configurations passing in the seed-0 regime.
- Section 3 reports a 12% all-seed full-regime share.
- The 4/20 figure belongs to the separate quick-profile report, not the all-seed full regime.
Thus the earlier “20% all-seed full” label is incorrect. This is a direct report-text check, not an independent rerun of all 1,554 records.

The report still labels median_length=4 and hapax_fraction=0.27 as targets needing verification. Their primary-source definitions remain outstanding.

## Research decision
Keep the 7/60 full-profile and 4/20 quick-profile results distinct. Do not interpret synthetic calibration as Indus evidence. Require a strict-JSON-safe upstream aggregate with explicit missing-value semantics and primary-source definitions for median_length and hapax_fraction before further benchmark interpretation. Real-corpus work remains blocked on item-specific written RMRL permission.
