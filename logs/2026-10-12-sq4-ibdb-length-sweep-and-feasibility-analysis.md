# SQ-4/SQ-3 — reading IBDB's own length-sweep and feasibility-region sections

## Precommitment self-review (written before analysis)

**Known:** last cycle unpacked IBDB's Task A section (sections 1-2 of the already-reproduced
`results.md`). The same report has at least five further sections (6-9: size sweep, length
sweep, "smallest corpus where a method beats chance," and a 16-scenario feasibility region)
that have never been read or synthesized by this project — only Task D's single headline
"2.1-14.6%" figure and Task A's "UNRESOLVED" label have been cited from this file so far.

**Not done yet:** no analysis of the length-sweep, the "smallest corpus" table, or the
feasibility-region section has been performed. These are already-reproduced, already-committed
numbers — this is a pure-analysis pass, not a new run.

**Design and why it's non-circular:** read the already-committed sections in full and report
exactly what they show, connecting them explicitly to SQ-3's and SQ-4's own stated purposes
rather than leaving them as unexamined tables.

**Honesty precommitment:** report the full picture, including results unfavorable to any
method's own credibility, rather than citing only the more flattering numbers.

## What the already-reproduced data shows

**Section 7 (length sweep, corpus size fixed at 2,906 texts) — Indus's own extreme brevity is
quantifiably, not just qualitatively, a handicap**: Task D "candidates"-tier mean token
accuracy (Knight-style EM, revised rule) rises sharply with mean signs/text: **7.4% at 3.0
signs/text → 15.1% at 4.6 (the real, verified Indus figure) → 36.1% at 10.0 signs/text**. This
is a precise, reproduced sensitivity curve, not a vague "short texts are hard" claim — recovery
accuracy roughly doubles for roughly double the text length in this range, consistent with the
real Indus corpus's own extreme brevity (mean 4.6 signs) being a specific, quantified, major
handicap for decipherment, independent of whatever the Indus script's actual linguistic status
turns out to be.

**Section 8 ("smallest corpus where a method beats chance") — a stronger, more specific
statement than "decipherment is hard"**: at the real Indus corpus size (2,906 texts) or even
far beyond it (up to the sweep's 50,000-text ceiling), **every Task C (sign-value/family
identification) method tested, at every tier relevant to the real Indus situation
(`candidates` and `none`), never reaches even a bare non-chance result** except one
(Knight-style EM revised rule reaches a "strong result," defined as accuracy ≥0.5, exactly at
2,906 texts in the `candidates` tier only). Every Task D method, at every tier relevant to the
real Indus situation, is marked "never" for both the baseline-beating threshold and the
"half the corpora reach ≥50% token accuracy" threshold — the only Task D method/tier
combinations that ever cross these thresholds use the `related` tier, which section 9's own
header explicitly calls "not the Indus situation... treat as an upper bound." **Translated
plainly: by this benchmark's own measure, no tested sign-value-recovery method is expected to
work reliably on a corpus shaped like the real Indus one, regardless of corpus size, unless the
Indus script turns out to have a closely related sister language already in hand** — which is
exactly the kind of external crib this project's own standing skepticism already treats as
unavailable.

**Section 9 (16 random perturbations around the calibrated Indus point) — the degradation is
not an artifact of one specific calibration choice**: across 16 independently-drawn scenarios
perturbing allograph rates, homophony, polyvalence, determinatives, word dividers, and
direction around the calibrated Indus point, **every Task D method's success share for "at
least half the corpora reach ≥50% token accuracy" is exactly 0.00 across all 16 scenarios**,
for every tier relevant to the real Indus situation (`candidates`, `none`) — not "rare," but
literally zero across this entire perturbation sweep. This rules out the possibility that the
Section 8 "never" results are a fragile artifact of one single, possibly-unlucky calibration —
the same failure holds robustly across a spread of nearby plausible scenarios.

## What this means for SQ-3 and SQ-4

This substantially strengthens, with specific quantified evidence rather than general caution,
this project's own standing skepticism toward any future claimed "statistical decipherment" of
Indus sign values or language family: **IBDB's own calibrated benchmark says no tested method
family is expected to reliably recover sign values or identify the correct language family at
Indus-realistic scale and brevity, and this conclusion is robust across a spread of nearby
calibration scenarios, not just the single central estimate.** This doesn't bear on Task A
(does the script encode language at all) directly — that's last cycle's separate finding — but
it gives SQ-4's own "historical recovery benchmark" purpose a much more specific, already-
quantified answer than "decipherment is hard in general."

## Outcome

No new experiment was run. This is a disclosed re-read of already-reproduced, already-committed
numbers from three further sections of the same results file this project has already verified
and cited, surfacing substantial, specific content that had never been examined.

## Limitation disclosed

This is this project's own reading of IBDB's own already-generated report tables, not an
independent re-derivation from IBDB's raw per-corpus data.
