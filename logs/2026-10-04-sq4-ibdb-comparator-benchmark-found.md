# SQ-4 — a directly relevant existing benchmark found: IBDB (Indus Blind Decipherment Benchmark)

**Trigger:** standing autonomous-loop directive to find an unclaimed thread rather than default to a
no-op; ChatGPT has been silent for four consecutive cycles, and this repo's two active threads
(Mahadevan 1986d / RMRL) are both blocked on the user's own outreach. SQ-4 ("Historical recovery
benchmark") has no status entries at all and explicitly does not depend on SQ-1/SQ-2's corpus-access
blocker — a genuinely unclaimed, actionable thread.

## What's already known / not done yet

Already known: Indus inscriptions are extremely short (mean ≈4.4 signs, median 4.0 — already on file).
SQ-4's own scope calls for a comparator corpus with an independently-verified reading, hidden during a
blind recovery test, to calibrate how much confidence any decipherment method's output deserves at this
corpus scale. Not done: any search for an existing such resource, or any attempt to build one from
scratch.

## Design and why searching first is non-circular

Before building anything, checked whether this exact need has already been addressed in the
decipherment-methodology literature — a search for prior art, not a result-shaping exercise, since the
goal here is finding evidence, not producing it.

## Result

Found **IBDB (Indus Blind Decipherment Benchmark)**, `github.com/Arnavthemighty/indus-blind-benchmark`,
an independent, MIT-licensed open-source project built for almost exactly SQ-4's stated purpose:

- **Methodology**: encodes known languages (Sanskrit, Old Tamil, Sumerian, Latin, Finnish) in invented
  scripts spanning logographic, syllabic, logo-syllabic, and alphabetic types, plus non-linguistic
  controls (heraldic bearings, administrative tags, Markov-generated emblems) — then tests decipherment
  methods blind against these synthetic corpora.
- **Calibration**: explicitly calibrated to **published Indus statistics** — "approximately 2,906 texts
  with 4.6 signs per text, 400–700 sign types." The 4.6-signs-per-text figure is an independent
  cross-check against this project's own already-cited "mean ≈4.4 signs (median 4.0)" — close, not
  identical, two different secondary sources converging on the same order of magnitude.
- **Key reported finding**: "without a related language among the candidates, no tested method exceeds
  about 5% of tokens" recovered, and entropy-based statistics "cannot distinguish synthetic languages from
  random signs at this corpus size." This is exactly the kind of sobering, quantified calibration result
  SQ-4 exists to produce — a real ceiling on what any method (including ones that might later be proposed
  for Indus itself) can plausibly achieve at this corpus scale, absent a correctly-identified related
  language.
- **Licensing**: code is MIT-licensed; the underlying known-language data retains its own original
  licenses (documented in the repo's own `DATA_LICENSES.md`), not bundled/redistributed by the repo
  itself — data is downloaded separately and git-ignored.

## Honest sourcing tier, disclosed

This is an independent, individually-authored open-source project, not a peer-reviewed publication —
disclosed at that tier explicitly, matching this project's own established practice for other
independent/amateur-tier sources (e.g. the Phaistos Disc project's handling of Rajeev's and Colless's
independent work). **Update, same cycle — cloned and inspected directly, not just via search summary**:
the repository is far more rigorous than a typical hobby project. Its `config/indus_targets.yaml` tracks
every calibration number with an explicit `verified: true/false/partial` flag, a citation, and — where
unverified — a "CHECK BEFORE CITING" note; several targets were independently re-derived (e.g. mean length
4.60, from "13,372 sign occurrences [Rao 2018] / 2,906 texts [Yadav et al. 2010]," which **supersedes**
this project's own previously-cited "~4.4" figure with a more precisely sourced one). The project
discloses direct input from **J. M. Kenoyer** (University of Wisconsin–Madison), a genuine, prominent
Indus-civilization archaeologist, via "comments relayed by the project owner" plus two of his papers
supplied as PDFs and read in full by the benchmark's authors — a real, credible connection to the
institutional literature, not just self-citation.

**The actual results are populated, not placeholder** — `reports/results/results.md`, 1,554 runs across 3
seeds, methods frozen at a tagged git commit before the run, 95% cluster-bootstrap confidence intervals,
multiple calibration regimes (`full`, `holdout`, `wrong_prior`) specifically to test whether findings are
circular/generator-dependent. **The precise finding is more nuanced than the "~5%" headline a search
summary gave**: at the Indus-realistic "candidates" tier (solver knows the likely language family but not
which language), mean token recovery accuracy is 2.9% (frequency-rank baseline), 14.6% (Knight-style EM,
revised selection rule), 2.1% (Knight-style EM, original rule), and 2.3% (EM cognate-matcher) — one method
(the revised-rule EM) clearly outperforms the others, not a flat ceiling across all methods. At the "none"
tier (no related-language hint at all), every method drops to 1.2–3.3%. Both are far below real
decipherment-level accuracy, but the "candidates"-tier spread shows method choice does matter.

## Consequence for SQ-4

This substantially advances SQ-4's "assemble a small checksummed panel of comparator material" deliverable
— it is a rigorous, already-built, methodologically pre-registered comparator benchmark directly
calibrated to this project's own corpus statistics (with one correction: this project's "mean ≈4.4"
citation should be updated to the more precisely-sourced 4.60 figure). **Not yet done**: independently
reproducing any of its results locally (the repo supports `ibdb reproduce --profile full` for exactly
this), or formally adopting it as this project's own SQ-4 resource with its own citation and license
record. That is the natural next step.
