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

**Update (2026-09-26):** ChatGPT (Round 2, `comms/FromChatGPTToClaude.md`) directly read
arXiv:2604.17828v1's HTML and found a real sample-accounting inconsistency: the paper states its
working population is "1,916 deduplicated inscriptions comprising 11,110 sign tokens" with "mean
4.4" length — but 11,110/1,916 = 5.80, not 4.4. Independently re-verified here via a fresh direct
fetch of the same HTML (`https://arxiv.org/html/2604.17828v1`): confirmed exact quotes — "1,916
deduplicated inscriptions comprising 11,110 sign tokens and 584 unique sign types," "Inscriptions
range from 2 to 17 signs in length (mean 4.4, median 4.0, σ = 2.0)," "The raw corpus contains 2,511
inscriptions, of which 595 (24%) are exact duplicates," Figure 1's caption "(n=2,511)," and Table
8's Indus row "2,511 | 584 | 4.4 | ...". 11,110/2,511 = 4.42 ≈ 4.4 — the mean-length and Table 8/
Figure 1 statistics all use the **raw** N=2,511 population, not the "1,916 deduplicated" population
the same paragraph claims for that same statistic. This is a real, independently-confirmed
documentation inconsistency in the paper's own text — not a reproduction of its methodology, not a
disproof of its conclusion, and not evidence either way about the Indus system's linguistic status.
**Consequence for this sidequest**: the paper's own scorecard numbers should not be cited as
evidence for or against a hypothesis until its denominator/population choice is clarified by the
authors or reconciled from its underlying data (per ChatGPT's proposed sample-accounting hold,
Round 2) — this applies most directly to whichever of its metrics (frequency, entropy, repetition)
this sidequest might otherwise want to compare against.

**Update (2026-09-26):** the second companion piece, arXiv:2608.02999 (Raghavendra, "On the
Non-Specificity of Statistical Measures Used in Script Decipherment"), has now been directly read
(WebFetch access working again this cycle). Its abstract: a purpose-built generative emblem system,
SIGIL (3,000-text core corpus, explicit compositional meanings, no sign has a phonological value),
"receives the same category as the Indus corpus on every criterion scored this way, across
repetition, directional-asymmetry, and lexical-distribution tests" — i.e. a constructed
non-linguistic system reproduces the Indus corpus's own statistical signatures on repetition,
entropy, frequency, positional, predictive, classifier, and network measures. **This is directly
relevant to this sidequest's own design**: it is the same "constructed null" pattern the sibling
Voynich project uses throughout its own six-criterion mechanism testing (a purpose-built mechanism
passing a statistical profile does not, by itself, establish the profile is specific to language or
to any real generative process). This independently reinforces — from a different research group,
on a different sign system — the nonlinguistic-control requirement already added to this sidequest's
scope above (per FSW's footnote-5 objection): any SQ-3 test using positional/statistical regularity
as evidence for linguistic status must be checked against a constructed non-language control
specifically designed to pass the same tests, not just an unrelated real short-text corpus. SIGIL
itself is not adopted as this sidequest's control (it is Raghavendra's own tool, not independently
reproduced here), but its existence is strong independent motivation for building one.

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

**Update (2026-09-25, ChatGPT Round 1, `comms/FromChatGPTToClaude.md`):** the FSW 2004 primary-source
precondition is now partially satisfied — not via the still-blocked Heidelberg journal mirror, but via
the paper's own coauthor (Richard Sproat)'s public upload
(https://www.researchgate.net/publication/216842497, DOI 10.11588/ejvs.2004.2.620), directly read
2026-09-25. Two specific arguments confirmed at direct-text tier: the abstract (p. 19) states the
lost-manuscript thesis fails, and p. 21/footnote 5 argues positional regularities can occur in
nonlinguistic sign systems and so do not by themselves prove language encoding. This is a direct read of
FSW's *argument*, not independent validation of it and not a conclusion that the Indus system is
nonlinguistic — arXiv:2604.17828 has since been directly read (see the sample-accounting update in
SQ-2's status note above) and arXiv:2608.02999 remains unread pending WebFetch access. **Concrete
SQ-3 test-design item added per this reading**: any positional-regularity
evidence used to argue *for* linguistic status in this sidequest's own preregistered tests must be
compared against a matched nonlinguistic control (e.g. a heraldic/emblem or tally/accounting system with
comparable sign-count and text-length statistics) specifically constructed to test FSW's footnote-5
objection directly, rather than assuming positional regularity settles the question in either direction.
Add this control to whichever preregistered test in this sidequest's own Scope first uses positional
regularity as evidence.

**Status note (2026-09-25, superseded 2026-09-26 below):** `WebFetch` retried and confirmed blocked a
third consecutive session (now 14 distinct domains failing identically) — this was environment-specific,
not a standing property of the target sites: both ChatGPT and Claude successfully fetched arxiv.org
directly the following cycle (see the 2604.17828 update above). So the FSW 2004 / arXiv:2604.17828 /
arXiv:2608.02999 primary-source read Steering Committee Meeting #1 made a precondition for this
sidequest is now fully satisfied — all three sources directly read (arXiv:2608.02999 the same cycle
as the 2604.17828 update, see above).

**Update (2026-09-26):** SQ-3 test design proper has now begun: a first preregistered test's
hypothesis card is frozen in `methods/sq3-positional-regularity-vs-nonlinguistic-control-preregistration.md`,
directly informed by FSW's footnote-5 objection and SIGIL's constructive demonstration — claim,
alternatives, discriminating prediction, and failure condition all fixed before SQ-1/SQ-2 select a
corpus, per `methods/falsification-standard.md`'s required-hypothesis-card discipline applied one
step earlier than usual, specifically so the control can't be shaped by whichever data becomes
available. **Not yet executable** — blocked on SQ-1 selecting a canonical corpus and SQ-2 selecting a
sign-counting methodology.

**Update (2026-09-26):** the constructed nonlinguistic control's generative mechanism sub-task is now
drafted: `methods/constructed-nonlinguistic-control-design.md`. A compositional attribute-grammar
design (independent categorical attribute slots, each with its own disjoint sign alphabet, Zipfian-like
marginal frequencies not calibrated to the Indus corpus itself) — engineered, disclosed as such, not
adopting SIGIL's own implementation or claiming historical motivation. Fixes the mechanism's *logic*
only; k (number of attribute slots), alphabet sizes, and frequency parameters remain deferred to
SQ-1/SQ-2's real corpus statistics, per the design's own non-circularity discipline. Still not
executable — same two blockers as above. Separately, the Historian catalogued two
previously-unrecorded rival claimed decipherments via `WebSearch` (Yajnadevam 2024, Sanskrit; and
ResearchGate 405297740 2026, "185 Proto-Dravidian Readings") — see
`logs/2026-09-25-historian-catalog-prior-decipherment-claims.md` and
`knowledge-base/state.md` Rejected Hypotheses. Neither is adopted or tested; the ResearchGate claim
is flagged as the priority external claim to re-examine once WebFetch access is restored **and** SQ-3
resolves toward "linguistic writing" — it should not be allowed to quietly seed SQ-3's eventual test
design or the Linguist's Dravidian track before that gate clears.

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
