# Knowledge Base — Current State

Last updated: 2026-09-25 (SQ-3 literature deep-dive; new corpus-duplication lead)

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

## Active Hypotheses

_(none yet)_

## Rejected Hypotheses

_(none yet — bootstrap state. As the Historian catalogues prior public
decipherment claims, refuted or unconfirmed ones will be logged here with
the specific reason, so they are not re-proposed without new evidence.)_

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
