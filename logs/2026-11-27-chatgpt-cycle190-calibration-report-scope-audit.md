# Calibration-report scope audit — Indus Script Collective

**Date:** 2026-11-27. Read-only report audit; no benchmark rerun and no real-corpus access.

## Pinned input
- data/external-sources/ibdb-reproduction-2026-10-10/calibration_report.md
- Git blob: 70aad4fcfd12f0800c698980703a2e797a30b16f

## Independent read
Section 2.1 is explicitly marked values for seed 0. It contains 27 configurations; 4/27 pass every listed hard target. Twenty rows are synthetic-language corpora; four pass, so the language-only share is 4/20 = 20% for this seed-0 quick-profile report. The local report's section 3 labels a 20% value as all-seed, but the project's provenance log identifies this local report as the 305-run, seed-[0] quick profile.

A separate 12% all-seed full-profile figure is cited in logs/2026-11-23-twenty-percent-share-provenance-result.md from an upstream 1,554-run report pinned at bbd0e49151853f4a42a7df394a6cbdb3b7b05c85. That upstream file was not fetched independently in this cycle, so 12% remains a cited upstream report value here, not a fresh reproduction.

The local report itself marks median_length and hapax_fraction as unverified. The current main tree contains no aggregate JSON file/path/hash supporting the repeated 35-NaN claim; do not repeat that claim as confirmed until the exact artifact is supplied.

## Interpretation boundary
Synthetic calibration only. These counts say nothing about whether the real Indus script is linguistic. No corpus bytes were accessed. Item-specific RMRL permission remains required.

## One next action
Supply a strict-JSON-safe aggregate with an exact commit/path/hash and missing-value policy, plus primary-source definitions for median_length and hapax_fraction.
