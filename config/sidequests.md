# Decipherment-oriented sidequest queue

Sidequests are bounded, achievable pieces of work. Each must produce a
reusable artifact, answer a decision, or remove a named blocker. The lead
agent may reprioritize them, but should record why.

## SQ-1 — Corpus canonicalization (blocking, start here)

**Purpose:** unlike a project with a single already-agreed, machine-readable
transcription, the Indus script corpus is spread across multiple published
catalogs using different sign-numbering conventions (the Mahadevan
concordance is commonly cited as a standard reference — this needs
primary-source verification before being treated as canonical). This
sidequest is not optional groundwork — it blocks every other sidequest and
the entire Statistician/Linguist/Cryptanalyst track.

**Scope:** evaluate candidate digital corpora/catalogs of the Indus script
(noting that different publications use different sign-numbering
conventions) for a rights-clear, machine-readable, checksummed source.
Record, for each candidate: source, license/rights, retrieval method,
coverage (how many of the commonly-cited ~3,700–4,200 catalogued inscribed
objects it transcribes, at what completeness — this figure itself needs
verification, see the Open Questions in `knowledge-base/state.md`), whether
it preserves reading uncertainty/damage rather than silently resolving it,
and a checksum once pulled. Do not bulk-download anything without explicit
user authorization — this is a standing rule across all sibling projects.

**Deliverables:** a source-comparison writeup, a provenance file once a
source is selected, and a normalization script with a full ambiguity-audit
trail once normalization begins.

**Stepping-stone value:** nothing downstream (sign frequency, sequence
structure, held-out tests) is reproducible or falsifiable without this.

**Laptop/worker-node work:** none yet — this stage is source discovery and
licensing/provenance research, not computation.

**Status note (2026-09-23):** first real candidate survey done via web
research (no download) — see `logs/2026-09-23-sq1-sq2-corpus-and-signcount.md`.
Four candidates identified, none yet formally selected: (1) Mahadevan's 1977
concordance (2,906 objects, 417–419 signs), digitized free by the RMRL Indus
Research Centre — the standard sign-*numbering* reference but the smallest,
oldest corpus of the four; (2) the multi-volume Corpus of Indus Seals and
Inscriptions (CISI, Parpola et al.), described in secondary sources as more
complete than Mahadevan but not yet checked directly for rights/format; (3)
the Interactive Corpus of Indus Texts (ICIT, Wells & Fuls) — largest found,
4,537 objects / 5,509 texts / 19,616 sign occurrences, but access is by
request to the administrator, not an open pull, so it does not yet clear
SQ-1's "rights-clear" bar; (4) an unvetted GitHub repo
(`mayig/indus-valley-script-corpus`) surfaced in search — license/provenance
not checked, not downloaded. Next step: formally evaluate (2) and (3) for
license/rights and completeness before any provisional selection; correct
the commonly-cited "3,700–4,200 objects" figure, which is stale relative to
ICIT's 4,537 and other claims of "more than 4,700" — see the log and
`README.md`/`knowledge-base/state.md` for the corrected framing.

**Status note (2026-09-23, round 2):** formally evaluated CISI and ICIT for
license/rights per Steering Committee Meeting #1's action item — see
`logs/2026-09-23-sq1-cisi-icit-rights-evaluation.md` (no download; WebFetch
was network-blocked this session, so this remains WebSearch-summary-derived,
disclosed explicitly). **Both currently fail SQ-1's rights-clear bar, for
different reasons:** CISI's copyright is explicitly held by Academia
Scientiarum Fennica (the volume) and by individual owning institutions (the
photographs) — readable via libraries/the Indian Culture Portal, but not
rights-clear for this project to extract/redistribute without permission.
ICIT has been a real, live, publicly-addressed online query tool since
October 2009 (`epigraphica.de/indus/`, mirrored at
`user.tu-berlin.de/fuls/Homepage/indus/`) — correcting the round-1 log's
framing of it as merely "access by request" — but using it still requires
the administrator (Andreas Fuls) to grant a login, and even then its
documented output model is per-query HTML/text/image, not a single bulk
machine-readable export of the full corpus. Candidate (4), the unvetted
GitHub repo, remains unvetted. **Provisional recommendation (not yet a
final selection):** since CISI and ICIT both currently fail the rights-clear
bar and the GitHub repo is unvetted, adopt Mahadevan/RMRL — freely,
anonymously downloadable today via Archive.org and the RMRL Indus Research
Centre's own online version — as SQ-1's first working corpus, explicitly
trading coverage (2,906 objects vs. CISI/ICIT's larger holdings) for actual
rights-clarity, while keeping CISI and ICIT queued as permission-pending,
higher-coverage sources to revisit if the user authorizes contacting either
rightsholder directly. Next step: directly verify RMRL's/Archive.org's own
stated terms of use before treating this recommendation as a real selection
— do not let it pass by default just because it's the only unblocked
option.

**Status note (2026-09-25):** confirmed via WebSearch that RMRL's Indus Research Centre runs a
live web application, `IndusScript.in`, providing free access to the corpus/concordance based on
Mahadevan's 1977 volume — corroborates the provisional recommendation above. **No explicit
license/terms-of-use text was found via search summaries**; reading RMRL's own site directly to
confirm terms remains blocked by this session's `WebFetch` restriction (see
`logs/2026-09-25-sq3-literature-deepdive-websearch.md`, now confirmed across eleven distinct
domains over two sessions — treat as a durable environment restriction, not worth further blind
retries). Terms-of-use verification stays open for whichever cycle next has working fetch access.

## SQ-2 — Sign inventory reconciliation

**Purpose:** published sign counts for the Indus script vary substantially
by counting methodology, with estimates ranging from under 100 "basic"
signs to several hundred counting variants and ligatures. This is an open
cataloging question, not a settled fact, and it affects every downstream
statistic — entropy, frequency distributions, and the writing-system-type
tests in SQ-3 all depend on which counting convention is used.

**Scope:** using SQ-1's canonicalized corpus, build a documented,
checksummed sign inventory with explicit, stated criteria for
distinct-sign vs. variant/ligature. Record how the choice of criteria
changes the resulting inventory size, and explicitly test whether
downstream statistical results (frequency distribution shape, entropy
estimates) are sensitive to the choice — report sensitivity honestly rather
than picking whichever count is most convenient for a later claim.

**Deliverables:** checksummed sign inventory table under at least two
reasonable counting methodologies, extraction/validation script, a
missing-data report, and a documented sensitivity analysis showing how much
downstream results shift across counting choices.

**Stepping-stone value:** every other sidequest and every agent's
statistical claims depend on this. Without it, a claimed corpus statistic
cannot be trusted to mean the same thing from one analysis to the next.

**Status note (2026-09-23):** literature survey of published sign-list sizes
done via web research (no computation, no corpus pulled yet — see
`logs/2026-09-23-sq1-sq2-corpus-and-signcount.md`). Found published counts
cluster between **386 signs (Parpola 1994) and 694 signs (Wells 2006)**,
with Mahadevan's original 417–419 in between (179 of which have variants
totaling 641 forms). This corrects this project's own bootstrap framing:
"under 100 basic signs to several hundred" is not supported by anything
found this session — no credible modern sign list puts the count under 100.
The real documented range among serious catalogers is roughly 386–694, i.e.
both ends are already in the hundreds; the dispute is about where to draw
the variant/ligature line within that range, not about a sub-100 option.
`README.md` and `knowledge-base/state.md` corrected accordingly. Next step:
once SQ-1 selects a source, apply at least two of these three published
counting methodologies (Parpola, Mahadevan/M77, Wells) to it directly rather
than relying on secondary-reported totals, and report the sensitivity.

**Laptop/worker-node work:** parsing, sign/ligature clustering, sensitivity
sweeps across counting-methodology choices.

**Status note (2026-09-25):** a new, unverified lead surfaced via WebSearch summary of
arXiv:2604.17828 ("How Non-Linguistic Is the Indus Sign System? A Synthetic-Baseline Scorecard"):
that preprint's own working corpus (1,916 deduplicated inscriptions, 52 sites) reportedly found a
**24% duplication rate** in the source material before deduplication, which it states materially
affects formulaic-repetition metrics. If a similar duplication rate holds in whichever corpus SQ-1
selects, every downstream frequency/entropy/repetition statistic in SQ-2 and SQ-3 needs an explicit
dedup-vs-no-dedup sensitivity check, not just a sign-counting-methodology sensitivity check — add
this as a required sensitivity axis once SQ-1 selects a source. Not yet independently verified —
see `logs/2026-09-25-sq3-literature-deepdive-websearch.md` for the full disclosure and
`knowledge-base/state.md` Open Questions for the corresponding entry.

## SQ-3 — Writing-system-type discriminant tests

**Purpose:** this project's central open question is not "which language"
but "does this even encode language at all." A widely-discussed 2004 paper
by Farmer, Sproat, and Witzel argued for the non-linguistic position and was
itself controversial and disputed by other scholars — this dispute is live
and unresolved, and this sidequest is where it gets tested directly rather
than assumed away in either direction.

**Scope:** using SQ-2's sign inventory, design and run held-out,
preregistered tests distinguishing full linguistic writing, non-linguistic
emblematic/notation systems, and numeral/accounting-only hypotheses.
Compare against appropriate short-text baselines: heraldic/emblem systems,
tally/accounting notations, and genuine-language inscriptions of comparable
extreme brevity (matched as closely as possible to the Indus corpus's own
~5-sign average). Freeze each test's design and decision rule before looking
at results, the same discipline the sibling projects use for their own
mechanism tests. Directly engage the Farmer/Sproat/Witzel argument and its
published critiques as part of this sidequest's literature basis, not as a
side reading.

**Deliverables:** preregistration per test, held-out scores, comparison
against typologically appropriate baselines, and a plain-English
interpretation that states clearly what the evidence does and does not
settle.

**Stepping-stone value:** answers a genuinely prior question — attempting a
language-decipherment pipeline before this is settled risks repeating the
documented failure mode of proposing sentence-level readings from
inscriptions averaging only ~5 signs, a practice the field broadly considers
methodologically unsound without much stronger justification than has
historically been offered.

**Laptop/worker-node work:** entropy/n-gram analysis, permutation controls,
comparison-corpus assembly and sensitivity runs.

## SQ-4 — Historical recovery benchmark

**Purpose:** learn which analysis methods can actually recover meaning from
plausible comparator systems (other short-inscription notation or writing
systems with an independently verified reading) before trusting any method
on Indus material, which has no known answer key.

**Scope:** assemble a small checksummed panel of comparator material with
documented, independently verifiable readings — candidates to evaluate
include other early notation or writing systems of comparable brevity with
scholarly-consensus readings. Hide the reading from the recovery stage and
measure how much can be recovered blind, to calibrate how much confidence
any given method's output actually deserves when later applied to Indus
material.

**Deliverables:** source manifest and licenses, reproducible recovery
methodology, blind recovery tasks, accuracy measures, and a record of
methods that fail.

**Stepping-stone value:** validates or eliminates decipherment techniques
before they are trusted on a corpus with no known answer key — exactly the
role the sibling projects' own historical recovery benchmarks played for
their mechanism candidates.

**Laptop/worker-node work:** corpus preprocessing, transform sweeps,
candidate scoring, robustness tests.

## Initial priority

Start SQ-1 first — it is a hard blocker. SQ-2 (sign inventory
reconciliation) should begin as soon as a corpus source is provisionally
selected, since every downstream statistic depends on it and it is itself
priority #1 in `config/research-department.md`. SQ-3 (writing-system-type
tests) is the most consequential sidequest overall and should begin as soon
as SQ-2's inventory exists — it gates whether any subsequent
language-specific decipherment attempt (which depends on SQ-3 resolving
toward "this is linguistic writing") is well-motivated at all. SQ-4 can
begin in parallel with SQ-1/SQ-2 (comparator-source discovery does not
depend on the Indus corpus itself being ready) without competing with the
primary task.
