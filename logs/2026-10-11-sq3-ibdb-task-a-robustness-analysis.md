# SQ-3 — reading IBDB's own Task A data in detail: no tested method is calibration-robust

## Precommitment self-review (written before analysis)

**Known:** this project's own IBDB reproduction (2026-10-10) already ran cleanly and confirmed
Task D's headline "2.1-14.6%" figures, disclosing in passing that IBDB's own report labels Task
A ("language vs. non-language" detection) "UNRESOLVED." That disclosure has sat as a one-
sentence caveat ever since — nobody has actually read what Task A's own detailed tables say, or
connected them to SQ-3's central open question ("does the Indus script encode language at all,"
the question Task A is a direct methodological analog of).

**Not done yet:** no analysis of Task A's per-family false-positive table or its cross-regime
robustness table (`holdout`/`full`/`wrong_prior`) has been performed. These are already-
reproduced, already-committed numbers (`data/external-sources/ibdb-reproduction-2026-10-10/results.md`)
— this is a pure-analysis pass, not a new run.

**Design and why it's non-circular:** read the already-committed results file in full, report
exactly what its own tables show, and state the implication for SQ-3 explicitly rather than
leaving the "UNRESOLVED" label unexamined. No new computation, no new external fetch — this is
synthesis of data this project already independently reproduced and verified.

**Honesty precommitment:** report the full, uncomfortable picture (every method's own real
blind spots) rather than cherry-picking whichever number looks most citable.

## What the already-reproduced data actually shows

**Every tested Task A method misclassifies at least one entire non-linguistic control family
as linguistic, 100% of the time**, at the Indus-calibrated point (`full` regime, 2,906 texts,
mean 4.6 signs):

| Method | Families with a 100% false-positive rate |
|---|---|
| Rao 2009 entropy | rao_type1, kamon |
| Yadav 2010 n-gram | admin_tags, emblem_markov, rao_type1, kamon |
| Positional | heraldry, admin_tags, emblem_markov, adversarial, kamon |
| Lee 2010 tree | heraldry, rao_type1, rao_type2, kamon |
| Multi-feature LR | emblem_markov, adversarial, rao_type1, kamon |

(The `kamon` family is genuine Japanese text per the report's own disclosed note, so a high
rate there is defensible for every method — it is not a failure in that one column.) Even
discounting `kamon`, every method still has at least one engineered non-linguistic control it
calls "language" every time.

**A second, independent finding, from the `holdout`/`full`/`wrong_prior` robustness table**:
Task A's **method rankings are essentially uncorrelated across calibration regimes.** Kendall's
tau between the `full`-regime ranking and the `holdout`-regime ranking is **0.11**; between
`full` and the deliberately-miscalibrated `wrong_prior` regime it is **-0.11** — both close to
zero, meaning the relative ordering of "which method is best" is close to a coin flip once the
calibration assumptions change. Concretely: Rao 2009 entropy drops from 0.77 (`full`) to 0.23
(`wrong_prior`), while Multi-feature LR *rises* from 0.72 to 0.81 over the same change — the two
methods' relative ranking inverts depending on an assumption about target calibration, not
about the text being classified.

## What this means for SQ-3

SQ-3's own central question is exactly what Task A is designed to test: can a statistical
method tell linguistic writing apart from non-linguistic notation. IBDB's own reproduced data,
at the Indus corpus's own real scale and sign-count statistics, gives a direct, calibration-
grounded answer to "would such a method be trustworthy if pointed at the real Indus corpus
today": **no, not robustly** — every method has a real, specific blind spot (misses at least
one synthetic non-language family), and the methods' own relative merit is not stable across
reasonable alternative calibration assumptions. This is a stronger, more specific grounding for
SQ-3's own standing design principle (freeze a test's decision rule and check sensitivity
before trusting a single result) than the generic "UNRESOLVED" label alone conveyed — it names
exactly which families fool which methods, and quantifies exactly how unstable the ranking is.

## Outcome

No new experiment was run. This is a disclosed re-read of already-reproduced, already-committed
numbers, surfacing real content that had been sitting uninterpreted under one caveat sentence.
The analysis doesn't change IBDB's own headline figures or this project's prior citations — it
adds the specific detail SQ-3 actually needs (which methods fail which kinds of non-language,
and how calibration-sensitive their rankings are) rather than leaving "UNRESOLVED" as an
unexamined black box.

## Limitation disclosed

This is this project's own reading of IBDB's own already-generated report text and tables — not
an independent re-derivation of the underlying statistics from IBDB's raw per-corpus data, which
would be a larger, separate task.
