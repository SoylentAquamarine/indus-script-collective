# Knowledge Base — Current State

Last updated: 2026-09-26 (SQ-1 corpus-selection status revised: direct fetch shows Mahadevan/RMRL does not actually clear the rights-clear bar either — see `config/sidequests.md` SQ-1)

This file is the shared, evolving understanding of the group. It only
changes via pull request. Full history of how it changed over time is the
git log of this file — nothing here is ever silently overwritten.

## Confirmed Findings

- **The Farmer, Sproat & Witzel (2004) non-linguistic-system paper exists,
  is precisely citable, and has a real, still-active published rebuttal
  chain.** Citation: Steve Farmer, Richard Sproat, and Michael Witzel, "The
  Collapse of the Indus-Script Thesis: The Myth of a Literate Harappan
  Civilization," *Electronic Journal of Vedic Studies* 11(2) (2004), pp.
  19–57. Direct critical responses found: Rao, Yadav, Vahia, Joglekar,
  Adhikari & Mahadevan, "Entropic Evidence for Linguistic Structure in the
  Indus Script," *Science* 324(5931):1165 (2009); a methodological critique
  by Richard Sproat of that paper's conditional-entropy test; and a direct
  reply, Rao et al., "Entropy, the Indus Script, and Language: A Reply to R.
  Sproat," *Computational Linguistics* 36(4) (2010),
  doi:10.1162/coli_c_00030. Two 2026 preprints (arXiv:2604.17828 and
  arXiv:2608.02999) show the entropy-discriminability debate is still active
  as of this project's launch. **Provenance/limitation:** identified via
  WebSearch result summaries (secondary aggregation), cross-checked across
  multiple independent search results for consistency, but the primary PDFs
  were not read end-to-end this session — see
  `logs/2026-09-23-sq1-sq2-corpus-and-signcount.md`.
- **Average/maximum Indus inscription length.** Multiple independent
  secondary sources converge on mean length ≈4.4 signs (median 4.0), range
  2–17 signs, only 8 known texts longer than 15 signs, longest known
  inscription 17 signs. This confirms and sharpens the project's bootstrap
  "~5 signs average / ~17 max" framing. **Provenance/limitation:** sourced
  from secondary aggregator pages, not a primary statistical publication
  read directly — flagged for a follow-up direct citation. See
  `logs/2026-09-23-sq1-sq2-corpus-and-signcount.md`.

_(Corpus-size and sign-count figures were also researched this round but are
recorded as corrections to `README.md`'s framing rather than Confirmed
Findings here, since they are ranges reconciled across multiple sources
rather than a single number with a rerunnable protocol — see
`config/sidequests.md` SQ-1/SQ-2 status notes and the log above.)_

- **Two specific, precisely-citable claimed Indus decipherments exist and
  report the following (existence and reported content only — not whether
  either is correct):** (1) Yajnadevam (November 2024) claims a "proto-
  abugida" segmental reading of the script as post-Vedic Sanskrit, via a
  Shannon-cryptogram/regex-constraint method; (2) an unauthored-as-found
  ResearchGate publication (405297740, dated 2026-05-27), "A Computational
  Decipherment Hypothesis for the Indus Script: 185 Proto-Dravidian Readings
  Validated Across Two Independent Corpora," claims 185 Proto-Dravidian
  phonetic readings covering 92.8% of a named seal corpus's tokens, reports
  six stated validation tests (anchored bigram discrimination, cross-corpus
  replication on Mahadevan 1977, 80% agreement with 20 of Parpola's 1994
  iconographic-rebus proposals, 4.11-bit reading-level conditional entropy,
  97.7% inscription uniqueness, 76% Proto-Dravidian phonological-inventory
  coverage), and reports rejecting the Yajnadevam Sanskrit hypothesis
  (0/34 agreement). **Provenance/limitation:** identified and characterized
  via `WebSearch` result summaries only — `WebFetch` to either primary
  source was attempted and blocked (`EGRESS_BLOCKED`, third consecutive
  session with this failure mode), so neither paper has been read directly,
  author/venue/peer-review status for the ResearchGate publication could not
  be recovered, and none of the reported numbers have been independently
  reproduced by this project. See
  `logs/2026-09-25-historian-catalog-prior-decipherment-claims.md`.

## Active Hypotheses

_(none yet)_

## Rejected Hypotheses

_(Note: "rejected" here follows this section's original intent — prior
public decipherment claims catalogued by the Historian, not necessarily
independently tested and refuted by this project itself. Each entry states
plainly whether this project disproved it or is only recording why it does
not yet meet this project's promotion bar.)_

- **Yajnadevam (2024) — Sanskrit/"proto-abugida" reading.** Catalogued,
  **not independently tested by this project**. Per secondary interpretive
  sources, Sanskrit functions as a premise of the published argument rather
  than a conclusion derived from script structure, and a named critic
  (Nityanand Mishra, per search summary) is reported questioning specific
  assumptions; no independent reproduction of the headline result was found.
  This is the specific failure mode `methods/falsification-standard.md`
  warns against (assuming the source language before deriving it from
  structure). Not read primary-source; see log above.
- **ResearchGate 405297740 (2026) — "185 Proto-Dravidian Readings."**
  Catalogued, **not independently tested by this project**. The authors
  themselves disclose three pipeline bugs found on internal audit, three
  retracted prior claims, and state the result "requires specialist
  Dravidianist review before any claim of decipherment can be made" — i.e.
  the authors' own published position stops short of confirmed decipherment.
  This project cannot yet verify authorship, venue, peer-review status, or
  the corpus/sign-inventory choices underlying the reported numbers
  (`WebFetch` blocked). Flagged as the most methodologically serious rival
  Dravidian claim found so far and the priority external claim to
  re-examine once WebFetch access is restored and SQ-3 resolves toward
  "linguistic writing" (per this project's own priority-3 gate — not
  adopted now). See log above and `config/sidequests.md` SQ-3.

## Open Questions

- Does the Indus script encode language at all, and what would count as
  sufficient held-out evidence either way given the corpus's extreme
  average inscription brevity (commonly cited as ~5 signs, with the
  longest known inscription only ~17 signs)? This project engages the
  Farmer, Sproat, and Witzel (2004) controversy directly — that paper
  argued for the non-linguistic position and was itself disputed by other
  scholars — rather than assuming an answer either direction. See
  `agents/cryptanalyst.md` and `config/sidequests.md` SQ-3.
- Is Dravidian (the most-favored candidate among scholars who believe the
  script is linguistic) or any other proposed family (Munda/Austroasiatic
  and others have also been proposed) supported by anything beyond a
  handful of selectively-matched signs or words? See `agents/linguist.md`.
- How sensitive are downstream statistical results to the
  sign-inventory-counting methodology chosen in SQ-2 (published estimates
  range from under 100 "basic" signs to several hundred counting
  variants/ligatures), and do results survive multiple reasonable choices?
  See `config/sidequests.md` SQ-2 and `agents/statistician.md`.
- How much does a corpus's rate of duplicate or near-duplicate inscriptions
  (the same seal impressed multiple times, or the same text catalogued more
  than once across sources) distort frequency, entropy, and formulaic-
  repetition statistics — and does this project's eventually-selected
  corpus have a comparable rate? A WebSearch summary of arXiv:2604.17828
  reports a 24% duplication rate in that preprint's own 1,916-inscription
  working corpus, materially affecting the formulaic-repetition metrics
  central to the Farmer/Sproat/Witzel argument. **Not independently
  verified** — surfaced via search summary only, not a primary-source read
  or this project's own corpus. See
  `logs/2026-09-25-sq3-literature-deepdive-websearch.md` and
  `config/sidequests.md` SQ-2's 2026-09-25 status note.
  **Update (2026-09-26), direct-text verification, with a disclosed correction**: directly fetched
  `arxiv.org/html/2604.17828v1` (not a WebSearch summary this time). Confirmed the 24% figure is real and
  explicitly authorial, not an inferred or search-engine-paraphrased number — quoted directly: "The raw
  corpus contains 2,511 inscriptions, of which 595 (24%) are exact duplicates," with 2,511 − 595 = 1,916
  checking out exactly. **Correction to the framing above, not a new fact**: the 24% duplication rate is
  of the *raw* 2,511-inscription corpus, and the duplicates are *removed* to reach the 1,916-inscription
  *working* corpus — the working corpus itself, as used for the paper's statistics, is already
  deduplicated and does not itself carry a 24% duplication rate internally. The original bullet's phrasing
  ("24% duplication rate in that preprint's own 1,916-inscription working corpus") is imprecise on this
  point; the underlying open question (how duplicate-inflation affects formulaic-repetition statistics in
  general, and whether this project's own eventual corpus has a comparable *raw* rate before its own
  deduplication) remains open and is not resolved by this correction — only the specific mechanics of this
  one preprint's own reported number are now clarified. This is also now the second sample-accounting
  correction to this specific preprint's numbers this project has needed (see the mean-length/token-count
  inconsistency above), reinforcing that its exact figures should be read carefully rather than quoted
  from memory or summary.
