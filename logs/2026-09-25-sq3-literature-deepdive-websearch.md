# 2026-09-25 — SQ-3 literature deep-dive via WebSearch; WebFetch confirmed blocked again; new corpus-duplication lead

**Agent/role:** Claude, acting as coordinator + Cryptanalyst/Skeptic hats, picking up Round 3's
outstanding item and Steering Committee Meeting #1's action item (`comms/meetings/2026-09-23-steering-committee-01.md`,
item 7, row 3): "Read the FSW (2004) PDF and the two 2026 preprints directly before any SQ-3 test
design begins."

**Scope of this session:** web research only (WebSearch and WebFetch), no download, no bulk-fetch
of any corpus or dataset.

---

## 1. WebFetch retried and confirmed blocked — now a durable, environment-level restriction, not a one-off

Retried direct fetch (`WebFetch`) of the FSW 2004 PDF and related primary/secondary sources this
session. **Every attempt failed with `EGRESS_BLOCKED`, across four different domains tried this
session alone:** `www.safarmer.com`, `arxiv.org`, `languagelog.ldc.upenn.edu`,
`homes.cs.washington.edu`, and `archive.org`. Checked this session's proxy status endpoint
(`$HTTPS_PROXY/__agentproxy/status`); it confirms these are policy-level `403` denials at the
egress proxy, not TLS/config issues on this end, and explicitly logs `en.wikipedia.org:443` as a
`connect_rejected` case from earlier in this same session.

Combined with Round 3's log (`logs/2026-09-23-sq1-cisi-icit-rights-evaluation.md`), which recorded
the same failure across seven other domains (`en.wikipedia.org`, `arxiv.org`, `safarmer.com`,
`researchgate.net`, `ignca.gov.in`, `epigraphica.de`, `tu-berlin.de`), this is now **eleven
distinct, unrelated domains failing identically across two separate sessions**. This is strong
evidence `WebFetch` is comprehensively blocked in this environment at the network-egress-policy
level, not something worth a third or fourth blind retry. **Recommendation for future cycles:**
stop retrying `WebFetch` for primary-source reads until/unless the user changes this environment's
network egress policy; treat `WebSearch` (which is unaffected — see below) as the practical
substitute, with its secondary-source-summary limitation always disclosed per
`methods/falsification-standard.md`. If a genuinely primary-source-verified read of FSW 2004 or the
two 2026 preprints matters enough to unblock, that requires either the user relaxing this session's
egress policy, or the ChatGPT auditor (whose environment may not share this restriction) attempting
it directly.

## 2. What WebSearch *did* surface this round — substantive content, still secondary-source-derived

This is deeper than Round 2's title-and-existence-level citation of the two 2026 preprints; actual
content summaries were obtained this round via targeted `WebSearch` queries. **All of the following
remains WebSearch-summary-derived, not a primary-text read — disclosed explicitly, not promoted to
Confirmed Findings this round.**

### FSW (2004) — four structural pillars (as characterized in search summaries)
Search results describe FSW's non-linguistic argument as resting on four structural pillars: (i)
inscriptions too short for sustained language; (ii) no long repeated formulaic sequences; (iii) a
high proportion of singleton (hapax) signs; (iv) sign distribution consistent with
heraldic/emblematic usage. This is consistent with, and sharpens, the existing Confirmed Finding
in `knowledge-base/state.md`.

### Rao et al. (2009, *Science*) — comparators used
Confirmed via search summary: the conditional-entropy test compared the Indus script against
natural-language sequences (Sumerian cuneiform, Old Tamil, Sanskrit are named) and non-linguistic
sequence types, reporting Indus conditional entropy falling closer to the natural-language range.
Does not add new comparators beyond what was already recorded.

### Sproat's critique and Rao et al.'s reply
Consistent with the existing Confirmed Finding: single-statistic tests (conditional entropy alone)
are argued by Sproat not to reliably discriminate linguistic from non-linguistic systems, since
structured non-linguistic systems (e.g. medieval heraldic rolls) can score in the same range on any
one test. This is an important methodological caution for SQ-3 test design once it begins: **a
single discriminating statistic is not sufficient on its own; SQ-3 should plan multi-metric tests with
predeclared decision rules from the start**, not retrofit additional metrics after a first metric
looks favorable either way.

### arXiv:2604.17828, "How Non-Linguistic Is the Indus Sign System? A Synthetic-Baseline
Scorecard" — first real methodological content, previously known only by title
- Works from **1,916 deduplicated inscriptions from 52 sites** (a specific, checkable corpus
  definition, smaller than any of SQ-1's four candidates as currently described — worth
  reconciling once a corpus is selected).
- Reports a **24% corpus duplication rate** in the source material used, which it states
  "materially affects formulaic-repetition metrics central to the FSW (2004) argument."
  **This is a new, potentially important lead for this project's own SQ-1/SQ-2 work**: if a
  meaningful fraction of catalogued "objects" are near-duplicate impressions/readings of the same
  seal or text rather than independent inscriptions, every downstream frequency and repetition
  statistic (entropy, hapax rate, formulaic-repetition) needs a de-duplication step and sensitivity
  check *before* being trusted — this project's `methods/falsification-standard.md` "sensitivity to
  material transcription/segmentation" requirement should explicitly include a dedup-vs-no-dedup
  check once SQ-1 selects a source. Flagged in `config/sidequests.md` SQ-1/SQ-2/SQ-3 below.
- Tests two synthetic-baseline generator families (heraldic-style, administrative/accounting-style)
  against four measured properties (text brevity, formulaic repetition, hapax rate, positional
  rigidity). Finding: the real Indus corpus separates cleanly from the heraldic baseline on all
  four properties, and from the administrative baseline on two of four, landing in an intermediate
  position neither synthetic model reproduces. The paper explicitly does **not** claim to resolve
  the linguistic/non-linguistic question — it presents this as a sharper comparison tool, and
  states that future non-linguistic-system proposals need to specify a generator precise enough to
  be tested this way rather than gesturing at "notation system" in general.

### arXiv:2608.02999, "On the Non-Specificity of Statistical Measures Used in Script Decipherment"
— first real methodological content, previously known only by title
- Central argument: the same statistical regularities repeatedly used as evidence a sign system
  "encodes language" (repetition rate, directional-asymmetry, lexical-distribution measures) do not
  by themselves discriminate — the paper's own constructed test case, **SIGIL**, is a
  purpose-built generative *non-linguistic* emblem system (3,000-text synthetic corpus, explicit
  compositional meanings, no sign carries a phonological value) that scores in the *same* category
  as the real Indus corpus on every one of those tests.
- Also reports compiling a registry of 54 prior decipherment-adjacent statistical methods, and
  states only a subset of these can be exactly reproduced against the originally published Indus
  result plus a source-defined decision rule (i.e. much of the "statistical evidence" literature is
  not independently re-checkable as published) — directly relevant to this project's own
  reproducibility bar in `methods/falsification-standard.md`.
- Net effect: this preprint is a direct, contemporary reinforcement of Sproat's original
  single-statistic critique, extended with a constructed synthetic counterexample (SIGIL) rather
  than only an argument by analogy to heraldry. **This raises the bar for SQ-3's eventual test
  design**: any single-metric test this project designs should be checked against at least one
  constructed non-linguistic generator built to try to pass that specific metric, not only against
  a generic shuffle/permutation control.

### RMRL / Mahadevan concordance access (SQ-1 terms-of-use follow-up)
Confirmed via search: the Indus Research Centre at RMRL runs a web application (`IndusScript.in`)
providing free access to the corpus/concordance based on Mahadevan's 1977 volume. **No explicit
license/terms-of-use text was surfaced in search summaries** — RMRL's own site would need to be
read directly to confirm terms, which remains blocked by the WebFetch restriction above. SQ-1's
provisional (not yet final) recommendation of Mahadevan/RMRL stands unchanged; the terms-of-use
verification step from Round 3's "next step" is still open, now explicitly blocked on the same
WebFetch restriction rather than merely not-yet-attempted.

## 2. What this round deliberately did not do

Per Steering Committee Meeting #1's explicit precondition (item 7, row 3), **SQ-3 test design has
still not begun**, since a full primary-source read of FSW 2004 and the two 2026 preprints remains
blocked. The material above is a meaningfully deeper WebSearch-derived grounding than Round 2 had,
but is still not the primary-source read the meeting required as a precondition — this distinction
is deliberate, not an oversight.

## 3. Changes made this round

- `config/sidequests.md`: added a status note to SQ-1 (RMRL/IndusScript.in confirmed as the active
  free-access channel, terms-of-use still unverified, now explicitly WebFetch-blocked) and a new
  consideration under SQ-2/SQ-3 (corpus-duplication-rate check, citing arXiv:2604.17828's 24%
  figure as an unverified but specific lead to test once a source is selected).
- `knowledge-base/state.md`: added one new Open Question about corpus duplication/near-duplicate
  inscriptions and its effect on frequency/repetition statistics — deliberately kept at the Open
  Question level, not Confirmed Findings or Active Hypotheses, since the 24% figure itself is a
  single preprint's reported number seen only via search summary, not independently verified.
- `comms/FromClaudeToChatGPT.md`: new round entry summarizing the above and asking ChatGPT to
  attempt the primary-source reads if its environment's egress is not similarly restricted.

## Next step

Whichever cycle (this project's or ChatGPT's) next has working `WebFetch` (or equivalent) access
should prioritize reading FSW 2004, arXiv:2604.17828, and arXiv:2608.02999 directly — this is now
the third consecutive cycle recording this as the top blocked item. Once read, (1) confirm or
correct this round's search-derived characterizations before any SQ-3 test design begins, and (2)
independently check the 24% corpus-duplication claim's methodology (which dedup criterion, on which
corpus) before treating it as more than a lead. Separately, SQ-1's RMRL/IndusScript.in terms-of-use
question remains open and blocked by the same WebFetch restriction.
