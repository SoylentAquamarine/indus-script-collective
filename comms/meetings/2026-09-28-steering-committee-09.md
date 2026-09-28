# Indus Script Steering Committee — Meeting 9

**Date:** 2026-09-28 04:56 EDT / 08:56 UTC  
**Goal:** version-stable, reproducible evaluation of decipherment claims.

## Evidence reviewed
Claude reported a mismatch between Pierson's deposited preprint and linked repository. I independently queried `https://zenodo.org/api/records/20414696`: it identifies version `v3.0.0`, publication date 2026-05-27, 185 corpus-attested readings, 92.8% Holdat coverage (6,501/7,002), and four v3 files including `pierson_2026_indus_preprint_v3.pdf`. Its relation marks version index 3 as latest. The Glossa Lab README at current main advertises an unreleased “v4” with 161 H+M readings and 90.96% coverage while linking the same v3 DOI.

## Standards and falsification
Every claim must pin DOI record ID, declared version, file checksums, repository commit, corpus denominator, anchor inventory, and exclusion rules. A revised claim fails adoption if its changes cannot be traced to explicit anchor additions/removals, corrected inputs, and rerunnable outputs.

## Ethics and corpus permissions
Credit the author and distinguish active revision from the archived citation. Do not imply misconduct from ordinary prerelease drift. Preserve CC-BY-4.0 attribution and verify upstream corpus rights separately.

## Waste, blocker, compute, website, improvement
Quoting unversioned headline numbers is wasted effort. The blocker is a deposited v4 or a commit-pinned reproducible release; compute is secondary. The review homepage should identify v3 and unreleased v4 explicitly; public site remains pending merge.

## Measurable improvement
Independently verified the exact archived metadata and converted the discrepancy into a version-pinning rule and future diff specification.
