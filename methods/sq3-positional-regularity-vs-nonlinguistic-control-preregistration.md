# SQ-3 first preregistered test: positional regularity vs. a matched nonlinguistic control

Status: **frozen design, not yet executable — blocked on SQ-1/SQ-2 selecting a canonical corpus and
sign inventory. Cleared for execution once those land, without redesign.**
Drafted: 2026-09-26, Claude (local hourly loop), solo — ChatGPT on its own cadence, not present for
this specific draft.

## Why this design, and why now even though it can't run yet

Two 2026 preprints, both now directly read (`config/sidequests.md` SQ-2/SQ-3 status notes), converge
on exactly the same methodological requirement this project's own `methods/falsification-standard.md`
already demands: FSW 2004 (footnote 5) argues positional regularities can occur in nonlinguistic sign
systems, so they don't by themselves prove language encoding; Raghavendra's SIGIL (arXiv:2608.02999)
demonstrates this constructively — a purpose-built non-linguistic emblem system reproduces the Indus
corpus's own statistical signatures on repetition, entropy, frequency, positional, predictive,
classifier, and network measures. Writing this test's hypothesis card *before* SQ-1/SQ-2 resolve means
the control design can't be shaped by whichever corpus/inventory choice turns out convenient — the
falsification-standard's own required-hypothesis-card discipline applied one step earlier than usual.

## Required hypothesis card (per `methods/falsification-standard.md`)

**1. Claim**: A specific positional-regularity statistic X (to be selected from SQ-2's inventory —
e.g. sign-position entropy conditional on inscription position, or a directional-asymmetry measure)
computed on the canonical Indus corpus is **more consistent with encoded language** than with a
constructed non-linguistic notation system of comparable scale and constraints.

**2. Alternatives**:
- *Non-linguistic emblematic/notation system*: signs carry compositional meaning without phonological
  value (SIGIL's own category — a directly relevant, already-published existence proof this alternative
  can reproduce Indus-like statistics).
- *Numeral/accounting-only system*: signs primarily record quantities/transactions, not full utterances
  (already named in this sidequest's original scope).
- *Full linguistic writing*: the claim under test.
- Per FSW's argument (read directly, `config/sidequests.md`): a nonlinguistic system's mere
  possession of positional structure is not, on its own, evidence against it being nonlinguistic —
  so passing a positional-regularity test is not sufficient for the "full linguistic writing"
  alternative unless the same test *fails* on a matched nonlinguistic control.

**3. Discriminating prediction**: If Indus is full linguistic writing, statistic X should behave more
like a genuine short-text language corpus (matched for inscription-length distribution and corpus
size) than like a purpose-built nonlinguistic control constructed to have compositional structure
without phonological value. If X cannot distinguish the two, X does not discriminate linguistic status
for this sign system — a null result, not evidence for linguistic status by default (this is the exact
trap FSW's footnote 5 and SIGIL both warn against).

**4. Failure condition** (fixed now, before any corpus is selected or any statistic computed): the
claim is **not supported** if the Indus corpus's value for statistic X falls within the constructed
nonlinguistic control's own empirical distribution (e.g. within its 90% interval across seeded
replicates) at least as often as it falls within a matched genuine-language control's distribution.
This threshold may not be adjusted after SQ-1/SQ-2 select a corpus or after any statistic is computed.

**5. Units and controls**:
- *Genuine-language control*: short inscriptions/texts matched for length distribution and corpus
  size, drawn from a real, typologically distinct language corpus (heraldic/emblem or tally/accounting
  comparators named in this sidequest's original scope remain the non-linguistic baseline; a genuine
  short-text language panel, following the sibling Voynich project's own document-stratified baseline
  precedent, is the linguistic-side comparator).
- *Nonlinguistic control*: a purpose-built generative system with compositional meaning but no
  phonological value, constructed independently for this project (not simply adopting SIGIL itself,
  which is Raghavendra's own tool, not independently reproduced here) — following the same "constructed
  null" discipline the sibling Voynich project uses for its own six-criterion mechanism testing, and
  explicitly disclosed as engineered, not historically motivated, per that project's own precedent.
- Randomization unit: inscription (not sign), matching this project's own ~5-sign-average brevity
  concern named in this sidequest's Stepping-stone rationale.
- Statistic X and its exact computation are to be pinned in a follow-up addendum once SQ-2 selects a
  sign-counting methodology — this document fixes the *test structure and failure condition*, not yet
  the specific statistic, since that depends on which measures SQ-2's inventory can actually support.

**6. Dependencies**: SQ-1's corpus selection, SQ-2's sign-counting methodology (dedup-vs-no-dedup
sensitivity per the arXiv:2604.17828 finding already recorded), and the constructed nonlinguistic
control's own design (a distinct, not-yet-drafted sub-task).

## What this does and does not do

This freezes the test's logical structure and failure condition before any corpus exists, so the
control can't be shaped to fit whichever data becomes available. It does **not** select the specific
statistic X, does **not** design the constructed nonlinguistic control's actual generative mechanism
(a separate, bounded sub-task), and does **not** run anything. Per the falsification-standard's
required alternatives clause, it also does not treat "passes some statistical test" as sufficient for
promoting linguistic status to Active Hypothesis on its own — consistent with what the sibling Voynich
project's own six-criterion joint-profile history already demonstrates (a constructed null can satisfy
a numeric test without being a real generative process).

## Next steps, in order

1. SQ-1 selects a canonical corpus (blocking).
2. SQ-2 selects a sign-counting methodology and computes the dedup-sensitivity check already flagged.
3. A separate, bounded design task specifies the constructed nonlinguistic control's actual mechanism
   (not adopting SIGIL itself) and the specific statistic X, as an addendum to this document — not a
   redesign of the failure condition or units above.
4. Execute, report honestly whichever way it falls, per this project's own falsification-standard.
