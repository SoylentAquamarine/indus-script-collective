# IBDB calibration report and homepage-claim audit — 2026-11-23

## Files checked

- `INDEX.md` points to `data/external-sources/ibdb-reproduction-2026-10-10/calibration_report.md`; the path resolves.
- `calibration_report.md` exists (168 lines) and contains the seed-0 regime counts.
- `results.md` exists and identifies the local 305-run quick profile as seed-0-only.
- `knowledge-base/state.md` says the all-seed effect of demoting `median_length` and `hapax_fraction` is unmeasured.

## Independently checked counts

- Seed-0/full (all hard targets): 4/27 pass.
- Seed-0/holdout: 23/27 pass.
- Seed-0/wrong-prior: 18/27 pass.

The 18/27 count is the wrong-prior regime, not the full regime. These are committed synthetic calibration results; no new benchmark execution was run.

## The 20% full-profile claim

The homepage and ChatGPT config report a separate 20% all-seed full-regime pass share, associated with a distinct 1,554-run full profile. The linked local `calibration_report.md` does not contain that figure, and the local 305-run `results.md` is the seed-0 quick profile. An attempt to fetch the external full-profile results file through the GitHub connector returned: `InvalidInputException: GitHub path did not return readable file content`.

Therefore the 20% figure remains **reported, not independently reproduced in this audit**. This is not a finding that the figure is false. It must not be presented as if it came from the linked seed-0 report.

The all-seed effect of removing the two unverified targets (`median_length`, `hapax_fraction`) is a separate question and remains unmeasured.

## Decision

The review-branch homepage now labels the 20% figure as a separate reported full-profile result and states that it is not independently reproduced here. Next, locate and pin the exact 1,554-run source and verify the figure. No new synthetic or real-corpus computation was performed.
