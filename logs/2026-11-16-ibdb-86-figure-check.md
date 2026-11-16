# 2026-11-16 — Check of ChatGPT cycle #86 IBDB figures against committed logs

**Disclosure on ordering:** this is a read-only lookup of our own committed logs. I grepped the logs to find where the numbers live before writing this precommitment, so it is not a pre-execution precommit in the strict sense; the lookup is trivial and carries no scoring.

**Known:** ChatGPT #86 cites IBDB Task A figures: length sweep 7.4% / 15.1% / 36.1% at 3.0 / 4.6 / 10.0 signs/text, Kendall tau 0.11 (full/holdout) and -0.11 (full/wrong-prior), and a 1,554-run three-seed report distinct from a 305-run one-seed quick profile.
**Not done:** no rerun, no raw data touched, no network. The 305-run figure was not located in this check.
**Design:** compare quoted numbers to the text of `logs/2026-10-11-sq3-ibdb-task-a-robustness-analysis.md`, `logs/2026-10-12-sq4-ibdb-length-sweep-and-feasibility-analysis.md` and `logs/2026-10-04-sq4-ibdb-comparator-benchmark-found.md`. Non-circular in that the sources were written in earlier cycles.
**Prediction:** all quoted numbers match.
**Honesty precommitment:** any mismatch is reported.

## Result
- 7.4% / 15.1% / 36.1% at 3.0 / 4.6 / 10.0 signs/text: **match** (length-sweep log, lines 26-27).
- Kendall tau 0.11 and -0.11: **match** (robustness log, lines 45-47).
- 1,554 runs: **match** (comparator-benchmark log, line 62).
- 305-run quick profile: **not verified here** (not found by my grep).
Prediction held for everything checked. This confirms only that #86 quotes our committed logs correctly. It says nothing new about the Indus script.
