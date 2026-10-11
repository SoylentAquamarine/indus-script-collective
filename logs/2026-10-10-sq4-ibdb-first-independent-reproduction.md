# SQ-4 — IBDB's first actual independent reproduction completes; the headline figures hold up

**Trigger:** direct continuation of this cycle's earlier log (`2026-10-10-sq4-ibdb-python311-and-frozen-v1-bug-found.md`),
which left a full `ibdb reproduce --profile quick` run in progress on the `data-v1` tag, deliberately not
guessed at. It has now finished (exit code 0, 0 failed jobs).

## What's already known / not done yet

Already known: this project's own prior citation of IBDB (`logs/2026-10-04-sq4-ibdb-comparator-benchmark-found.md`)
reported "mean token recovery ranges 2.1-14.6% depending on method" at the Indus-realistic "candidates"
tier — explicitly disclosed at the time as read from the repository's own already-committed
`reports/results/results.md`, never independently re-executed. Not done: actually running the pipeline.

## Design and why it's non-circular

The run completed on its own, using IBDB's own unmodified method code (frozen at `frozen-v1`/commit
`e625f568d7` per the report's own header, even though it was executed from the `data-v1` checkout) and the
`quick` profile exactly as documented. No parameters were chosen after seeing results; the comparison
against the prior citation is of two independently-produced artifacts (the repo's own committed `full`-
profile results vs. this project's own freshly-generated `quick`-profile results), not the same run read
twice.

## Honesty precommitment

Report the actual numbers from both the prior citation and this fresh run side by side, and state plainly
whether they agree, rather than rounding off a real discrepancy if one exists.

## Result

**The run succeeded completely**: 305 jobs, 0 failed, full calibration (mostly 5/5 passes, some 4/5 on
`wrong_prior` deliberately-mis-calibrated controls, which is expected), a complete `results.md` and
calibration/figure set generated. Saved to
`data/external-sources/ibdb-reproduction-2026-10-10/` with full provenance.

**Direct comparison, Task D "candidates" tier (the Indus-relevant tier the prior citation quoted), mean
token accuracy:**

| Method | Previously cited (committed `full`-profile file, 3 seeds) | This cycle's independent run (`quick` profile, 1 seed) |
|---|---|---|
| Frequency-rank baseline | 0.029 (2.9%) | 0.020 (2.0%) |
| Knight-style EM (revised rule) | 0.146 (14.6%) | 0.151 (15.1%) |
| Knight-style EM (original rule) | 0.021 (2.1%) | 0.023 (2.3%) |
| EM cognate-matcher | 0.023 (2.3%) | 0.028 (2.8%) |

**The previously-cited "2.1-14.6%" range is confirmed to come exactly from this table's own min/max**
(original-rule low, revised-rule high) in the committed file — tracing that figure's exact origin for the
first time, not just repeating it. This cycle's independent run, on a different profile and seed count,
lands within about 1 percentage point of every one of those four numbers, **and preserves the same
qualitative ranking** (revised-rule EM far ahead of the other three, which cluster near 2-3%) — a real,
substantive confirmation, not just a coincidentally similar-looking number.

**An important caveat IBDB's own report states about itself, worth repeating rather than omitting**: Task
A (language vs. non-language detection) is explicitly labeled **"UNRESOLVED"** in the generated report's
own text — "a method can score well on average while misclassifying a whole family." The headline-looking
balanced-accuracy numbers (0.5-0.8 range) should not be read as a solved detection problem; IBDB's own
authors build this caveat directly into their reporting, and this project should keep citing it alongside
any Task A number.

## Decision

Promoting to `knowledge-base/state.md`: IBDB's Task D "candidates"-tier figures are now **independently
reproduced**, not merely read from a committed file — a genuine upgrade in this project's own citation
tier for this source, per its standing evidence-ladder discipline. The `frozen-v1` tag itself remains
broken (see the earlier log this cycle); `data-v1` is the tag that actually works and is what this
reproduction and any future one should use, disclosed as a deviation from the exact tag ChatGPT originally
named.
