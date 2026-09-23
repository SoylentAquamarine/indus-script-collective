# 2026-09-23 — SQ-1/SQ-2: Corpus canonicalization and sign-inventory reconciliation, round 1

**Agent/role:** Claude, acting as Research Director + Cryptanalyst/Linguist/Skeptic (combined,
bootstrap cycle) with real web research (WebSearch), no bulk download performed.

**Scope of this session:** verify or refute, with primary/secondary citations, the specific
factual claims the scaffolding (`README.md`, `config/research-department.md`) was written from
general background knowledge and explicitly flagged as unverified in
`comms/FromClaudeToChatGPT.md` Round 1. This is SQ-1 (corpus canonicalization) and SQ-2
(sign-inventory reconciliation) source-discovery work, not computation — no corpus was pulled.

---

## 1. The Mahadevan concordance — does it exist digitally, and is it "the" standard reference?

**Finding: exists, historically foundational, but not the sole or most complete modern corpus.**

- Iravatham Mahadevan published *The Indus Script: Texts, Concordance and Tables* (Archaeological
  Survey of India, Memoir No. 77, 1977) — a concordance of **2,906 inscribed objects**, reduced to
  a standardized sign list, indexing every sign occurrence by position. It is available as a free
  scan on the Internet Archive
  ([archive.org/details/TheIndusScript.TextConcordanceAndTablesIravathanMahadevan](https://archive.org/details/TheIndusScript.TextConcordanceAndTablesIravathanMahadevan))
  and the Indus Research Centre at the Roja Muthiah Research Library (RMRL), Chennai, has put an
  electronic/searchable version online free of charge (per the Harappa.com blog post "An Indus
  Concordance and Tamil Potsherds, Now Online").
- Mahadevan's own sign list assigns **417 (sometimes cited as 419) unique sign numbers** across
  **3,573 lines of text** drawn from those 2,906 objects. This "M77" numbering is still the most
  widely cross-referenced sign-numbering convention in the secondary literature, which is likely
  why it is "commonly cited as the standard reference" — but it is materially **smaller and older**
  than later corpora.
- It has since been superseded in coverage (not necessarily in citation convention) by:
  - The multi-volume **Corpus of Indus Seals and Inscriptions (CISI)**, edited by Asko Parpola,
    B.M. Pande, and others, covering collections in India, Pakistan, and elsewhere — described in
    secondary sources as more extensive than Mahadevan's.
  - The **Interactive Corpus of Indus Texts (ICIT)**, a digital database built by Bryan K. Wells
    and Andreas Fuls (Wells' PhD project, ISBN 978-1-84217-994-9), currently holding **4,537
    inscribed objects, 5,509 texts, and 19,616 sign occurrences**
    ([Digital Classicist Wiki entry](https://wiki.digitalclassicist.org/Interactive_Corpus_of_Indus_Texts);
    administrator contact per [epigraphica.de](https://www.epigraphica.de/indus/menueindus.htm) is
    fuls(at)epigraphica.de — access is by request, not an open download, so it is not yet a
    "rights-clear, machine-readable source" by SQ-1's own bar without that permission step).
  - A GitHub repository, `mayig/indus-valley-script-corpus`, surfaced in search as an existing
    digitization effort. Its license/provenance/rights were **not verified this session** — noted
    as a candidate to evaluate, explicitly **not** downloaded or vetted further, per the standing
    "no bulk download without explicit user authorization" rule.

**Verdict for SQ-1:** the Mahadevan concordance is real and still the standard *sign-numbering*
reference, but it is not automatically the best corpus-*coverage* choice — the department should
treat CISI and ICIT as stronger coverage candidates once a source-comparison writeup (SQ-1's
actual deliverable) formally evaluates license/rights and completeness. No source is selected yet;
this is provisional groundwork, not a decision.

## 2. Corpus size and average inscription length

**Finding: corpus size is genuinely unsettled across sources — the README's "3,700–4,200" framing
undersells how much it has grown in more recent compilations. Average inscription length and max
length are well-supported.**

| Source | Object count | Note |
|---|---|---|
| Mahadevan (1977) | 2,906 objects (3,573 text lines) | earliest systematic concordance |
| Parpola (1982) | ~3,700 objects | commonly cited "standard" figure |
| Fairservis (1992) | ~4,000 objects | |
| ICIT (Wells/Fuls, digital, ongoing) | 4,537 objects / 5,509 texts | most recent compilation found |
| General secondary claim (undated) | "more than 4,700" | stamp seals, sealings, copper tablets/tools, ivory rods, pottery, miniature tablets combined |

**Correction proposed:** the commonly-cited range should be stated as **roughly 2,900 (earliest
systematic concordance) to at least 4,500+ (most recent digital compilations), with figures
climbing over time as more material is catalogued** — not a static "3,700–4,200." The
3,700–4,200 figure is a reasonable snapshot of the Parpola/Fairservis-era literature but is stale
relative to ICIT and later claims. This is a secondary-source-derived range (search-engine
summaries of Parpola, Fairservis, and the ICIT project site, not the primary monographs read
directly) — disclosed per `methods/falsification-standard.md`.

**Average/max inscription length — confirmed, more precise than the README's current text:**
multiple independent secondary sources converge on **mean length ≈ 4.4 signs, median 4.0**,
range 2–17 signs, only 8 known texts longer than 15 signs, and the longest known inscription is
**17 signs**. This matches and sharpens the README's "~5 signs average, ~17 max" language — no
correction needed to the headline numbers, but "average ~5" is better stated as "mean ~4.4/median
4.0" if a precise figure is wanted. **Limitation disclosed:** the mean/median/range figures came
from secondary aggregator pages (World History Encyclopedia, Harappa.com-linked summaries), not
a primary statistical source read directly this session — a primary citation (e.g., Rao et al.'s
or Wells' own published length distribution) should be pulled before this is promoted to a
Confirmed Finding with full provenance.

## 3. The sign-count dispute

**Finding: real, well-documented, and the README's own framing ("under 100 to several hundred")
is not well supported — no credible modern sign list found puts the count under 100.**

Actual published sign-list sizes found:
- Parpola (1994): 386 (+12 uncertain) signs/graphemes with variant forms.
- Mahadevan (1977): 417–419 graphemes; of these, 179 have variants totaling 641 forms.
- Wells (2006, ICIT): 694 signs — a much broader count that treats more damaged forms, rotated
  signs, ligatures, and graphic variants as distinct.
- General summary: "modern sign lists vary from roughly 417 to 694 signs... a narrow list may
  count about 400–450 basic signs; broader lists... can approach 700."

**Correction proposed:** the sign-count dispute is real, but its actual documented range among
serious modern catalogers is **~386 to ~694**, not "under 100 to several hundred." The
"under 100" end of the README's current claim does not match anything found this session and
should be removed or re-attributed if a source for it turns up later. This is exactly the kind
of imprecise commonly-cited figure the bootstrap README itself warned might need correction.

## 4. Farmer, Sproat & Witzel (2004) and its critical reception

**Finding: confirmed to exist, with a real and still-active scholarly rebuttal chain — the
dispute is genuinely live, not one-sided or settled.**

- **Citation:** Steve Farmer, Richard Sproat, and Michael Witzel, "The Collapse of the
  Indus-Script Thesis: The Myth of a Literate Harappan Civilization," *Electronic Journal of
  Vedic Studies* 11(2) (2004), pp. 19–57. Available directly from the author
  ([safarmer.com/fsw2.pdf](https://safarmer.com/fsw2.pdf)) and via the journal's own site
  ([hasp.ub.uni-heidelberg.de](https://hasp.ub.uni-heidelberg.de/journals/ejvs/article/view/620)).
  Their argument: the Indus sign system shows no evidence of the kind of change/evolution toward
  linguistic representation seen in other early scripts over ~600+ years of use, lacks the long
  inscriptions typical of genuine early writing systems, and is more consistent with a
  non-linguistic symbol system (religious/political/clan marking) than full glottographic writing.
- **Substantive published critical responses found (this satisfies the task's request for at
  least one):**
  1. Rajesh P. N. Rao, Nisha Yadav, M. N. Vahia, Hrishikesh Joglekar, R. Adhikari, and Iravatham
     Mahadevan, "Entropic Evidence for Linguistic Structure in the Indus Script," *Science*
     324(5931):1165 (2009) — used conditional-entropy measures to argue the Indus sign sequences
     pattern more like known linguistic systems than like rigid non-linguistic sign systems,
     directly challenging FSW's conclusion.
  2. Richard Sproat published a methodological critique arguing the Rao et al. conditional-entropy
     test does not actually discriminate linguistic from non-linguistic symbol systems once
     proper controls are used (summarized on Language Log,
     [languagelog.ldc.upenn.edu/nll/?p=1374](https://languagelog.ldc.upenn.edu/nll/?p=1374)).
  3. Rao, Yadav, Vahia, Joglekar, Adhikari, and Mahadevan replied directly: "Entropy, the Indus
     Script, and Language: A Reply to R. Sproat," *Computational Linguistics* 36(4) (2010),
     doi:10.1162/coli_c_00030 ([dl.acm.org](https://dl.acm.org/doi/10.1162/coli_c_00030)).
  4. The dispute remains active in the current literature: two 2026 preprints surfaced directly —
     "How Non-Linguistic Is the Indus Sign System? A Synthetic-Baseline Scorecard"
     ([arxiv.org/abs/2604.17828](https://arxiv.org/pdf/2604.17828)) and "On the Non-Specificity of
     Statistical Measures Used in Script Decipherment"
     ([arxiv.org/abs/2608.02999](https://arxiv.org/pdf/2608.02999)), both explicitly engaging the
     entropy-based discriminability question FSW/Rao/Sproat opened. **Their content was not read
     in depth this session** — flagged for a follow-up SQ-3 sidequest read, not treated as
     verified here.

**Verdict:** the controversy is exactly as live as the project's scaffolding assumed. This is
good grounding for treating it as an active, unresolved dispute rather than picking a side.

## 5. Is Dravidian the most-favored linguistic candidate, and what's the strongest argument for it?

**Finding: yes, among scholars who believe the script is linguistic, Dravidian is the most-cited
candidate — chiefly through Asko Parpola's body of work.**

- Strongest published argument found: Asko Parpola, "A Dravidian solution to the Indus script
  problem" (2010 Coimbatore lecture; PDF hosted at
  [harappa.com](https://www.harappa.com/sites/default/files/pdf/Parpola-2010-Coimbatore.pdf) and
  mirrored at [tamilnet.com](https://tamilnet.com/img/publish/2014/11/Parpola-2010-Coimbatore.pdf)),
  building on Parpola's earlier monograph *Deciphering the Indus Script* (1994). The argument
  combines: (a) substrate evidence — Brahui, a Dravidian language still spoken in the Indus
  region (Balochistan), plausibly a relic population; Dravidian loanwords argued in the Rigveda;
  Dravidian substratum influence argued in Prakrit dialects; (b) a rebus-based sign-reading method
  (e.g., a "fish" sign read via Dravidian *mīn*, which means both "fish" and "star" in Dravidian
  languages, to explain star-like signs paired with fish signs); (c) computational morphological
  argument — analysis reportedly showing the inferred underlying language pattern has suffixing
  only, consistent with Dravidian's agglutinative suffixing typology, and inconsistent with
  Indo-Aryan (prefixing) or Munda (infixing).
- **Explicit caveat, carried over faithfully:** search results also surfaced very recent (2025)
  claims of a "computational decipherment" with "185 Proto-Dravidian readings validated across two
  independent corpora." This was **not verified against a primary, peer-reviewed source this
  session** and should not be treated as anything more than an unconfirmed claim pending scrutiny
  — it is exactly the kind of claim `agents/skeptic.md` and `agents/linguist.md` exist to test
  before any promotion, and citing it here is not an endorsement.

## Overall disclosed limitation

All findings above come from WebSearch result summaries (secondary aggregation of primary
sources), not from directly reading the full primary monographs/papers end-to-end. Titles, venues,
authors, and headline numbers were cross-checked across multiple independent search results where
possible (e.g., corpus-size and sign-count figures appear consistently across several distinct
pages), which raises confidence, but per `methods/falsification-standard.md` this is disclosed as
a secondary-source limitation on every item above, and none of it should be treated as
independently verified against the original PDFs/books without a follow-up direct read.

## What changed as a result

- `config/sidequests.md` SQ-1 and SQ-2 status notes updated with these findings.
- `knowledge-base/state.md` Confirmed Findings gets two entries that meet the falsification
  standard's minimum bar (citable, cross-checked, provenance-disclosed): the FSW (2004) paper's
  existence/citation plus its real critical-response chain, and the average/max inscription
  length figures. The corpus-size and sign-count figures are recorded as corrections to the
  README's framing but are **not** promoted to Confirmed Findings themselves, since they are
  ranges across sources rather than a single checkable number with a rerunnable protocol.
- `README.md` corpus-size and sign-count language corrected to reflect the wider, better-sourced
  ranges found above.

## Next step

Formally begin SQ-1's source-comparison writeup (Mahadevan/RMRL vs. CISI vs. ICIT vs. the
unvetted GitHub corpus) with license/rights checked for each before any is selected, and open
SQ-3 literature groundwork by actually reading the FSW 2004 PDF and the two 2026 preprints in
full rather than via search summaries.
