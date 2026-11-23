# Full-profile 12% pass-share independent audit — 2026-11-23

## Pinned source

- Repository: ArnavGoel98/indus-blind-benchmark
- Commit: bbd0e49151853f4a42a7df394a6cbdb3b7b05c85
- File: reports/results/aggregate.json
- Git blob: 5fc380fd437d3277324b29204f6432fbbe96f002
- Aggregate metadata: profile=full, n_records=1,554, n_errors=0.

## Reproduction

At the full-profile point keyed by ["size", 2906, 4.6, "full"]:
- n_corpora = 81;
- n_passing_languages = 7;
- A_by_kind language denominator n = 60.

Thus the language-corpus pass share is 7/60 = 0.116666..., or 11.67% (rounded to 12%).

The quick/seed-0 profile is a separate source and regime: its 27-row table contains 20 language configurations and 7 controls; four language rows pass, so 4/20 = 20%. The 20% quick/seed-0 figure must not be described as the full-profile all-seed share.

## Limits

This is arithmetic reproduction of a pinned aggregate, not a rerun of the 1,554 raw records. The all-seed effect of demoting median_length and hapax_fraction remains unmeasured because raw per-run rows are not published. These are synthetic calibration results, not evidence that the Indus signs encode language.

## Decision

Use 12% for the pinned full-profile aggregate and 20% only for the quick/seed-0 language-only subset. Do not rerun the benchmark. Verify the two target definitions from primary sources and obtain item-specific written RMRL permission before any real-corpus analysis.
