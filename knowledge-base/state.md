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
  **Correction (2026-10-04), the flagged follow-up direct citation is now available — see
  `logs/2026-10-04-sq4-ibdb-comparator-benchmark-found.md`**: the IBDB project's calibration file derives
  mean length as **4.60** (tolerance ±0.25), computed directly from two independently-verified primary
  figures — Rao (2018): 13,372 total sign occurrences in Mahadevan's (1977) corpus; Yadav et al. (2010):
  2,906 texts in that same corpus — giving 13,372/2,906 = 4.60. Farmer, Sproat & Witzel (2004) independently
  state the average is "under 4.6," consistent with this derivation. **This supersedes the earlier ≈4.4
  figure** — not a large change, but a more precisely sourced one (a direct arithmetic derivation from two
  verified primary-literature numbers, not a secondary-aggregator approximation). The "median 4.0" and
  "range 2–17" figures are not corrected by this update — IBDB's own calibration file marks its median
  figure as unverified too (its own "brief" value, not independently re-derived).

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
  **Update (2026-09-28), a specific, direct-text-tier methodological critique found**: directly fetched
  (not search-snippet) `prekshaa.in`'s interpretative review of the Yajnadevam paper. Exact quote on
  inconsistent translation methodology: "tana (तन) is translated as 'child' or 'offspring' in M-459A but
  is translated as 'roarer' from tan in M-359; the reason for this choice is not elaborated," with the
  reviewer's own assessment: "This is not very scientific and, indeed, reduces the paper's credibility."
  Separately: "it makes very little sense to first utilise a commendable, unyielding, and sterile
  scientific approach to reading the SSV signs and then becoming completely subjective." This is a
  different, independent critique from the previously-recorded Nityanand Mishra one (search-summary tier)
  — both now stand, at different sourcing tiers, targeting different aspects of the same claim (premise-
  before-structure vs. inconsistent post-hoc translation choices). The review does not give Yajnadevam's
  full original citation (journal/venue, DOI) — still not located.
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
  **Update (2026-09-28), upgraded to direct-text tier — the actual preprint found and read**: located the
  paper's freely-hosted, CC-BY-4.0 Zenodo record (not ResearchGate) — Pierson, Tristen (2026), DOI
  10.5281/zenodo.20414696, "pierson_2026_indus_preprint_v3.pdf." **Author identified**: Tristen Pierson,
  affiliated with "BitConcepts" (a named research entity, not a traditional academic institution); the
  paper's own "AI Disclosure" states AI tooling was used for scripting, pipeline management, literature
  search, and drafting, with the author personally designing and interpreting the statistical tests. Data
  and code published at `github.com/BitConcepts/glossa-lab` (checkable, not yet checked by this project).
  **Confirms and substantially enriches the prior WebSearch-tier disclosure** — quoting the paper's own
  self-assessment directly: the retracted "91.8% Proto-Dravidian grammar conformance" claim failed its own
  permutation-null check catastrophically, not marginally — "a permutation null test showed random
  shuffled readings produce 94.2% conformance," meaning the *null model outperformed the original claimed
  result* (94.2% > 91.8%), i.e. the metric could not discriminate the hypothesis from randomness at all.
  Two further self-disclosed limitations not previously recorded: **(1) anchor circularity** — "the
  discrimination test uses the same readings as anchors that were derived from the Dravidian language
  model," an acknowledged circularity only partially mitigated by a second-corpus replication; **(2)
  underdetermination** — a competing Proto-Dravidian rebus-based decipherment (Venkatesan) produces only
  5% reading overlap with this paper's own SA-based readings, which the author states directly
  "demonstrat[es] that the DEDR provides enough homophonic vocabulary for multiple internally consistent
  solutions to exist." **This project's own read, not the author's framing**: a rebus-vocabulary resource
  rich enough to support multiple mutually-incompatible "internally consistent" solutions is a serious,
  self-disclosed structural weakness for evaluating *any* DEDR-anchored Dravidian correspondence claim,
  not only this one — worth keeping in mind for the still-open general Dravidian-correspondence question
  above. Not independently tested or adopted by this project; this update is a direct-text-tier read of the
  author's own disclosures, not new evidence produced by this project.
  **Same-cycle follow-up, a real discrepancy found by checking the paper's own linked code repository**:
  checked `github.com/BitConcepts/glossa-lab` (the paper's own cited data/code source) directly. Its
  README describes a **"v4 preprint"** — a different title ("A Falsifiable Computational Decipherment
  Hypothesis for the Indus Valley Script: 161 Candidate Proto-Dravidian Anchors and a Three-Slot Positional
  Grammar") with **materially different, lower headline figures**: 161 candidate readings (75 HIGH + 86
  MEDIUM), 90.96% token coverage, 59% Parpola agreement — versus the v3 Zenodo preprint's own 185 readings,
  92.8% coverage. The README cites this v4 preprint at the **same DOI** as the v3 preprint already read
  (10.5281/zenodo.20414696). **Directly checked the Zenodo record itself**: as of this check, it still
  shows only v3.0.0, with the v3 files and figures — no v4 deposit exists at that DOI yet. **This is a
  disclosed inconsistency, not an accusation of misconduct**: it most plausibly reflects an author actively
  revising the analysis downward (fewer, more conservative readings) ahead of formally publishing the
  update, with the repository's own README written ahead of the actual Zenodo deposit. **Practical
  consequence for this project**: the specific numbers (185 readings, 92.8% coverage) recorded above should
  be treated as the state of the *v3, currently-citable* preprint only, not as this author's current or
  final position — the underlying analysis has continued to change materially after publication. Also
  noted in passing: the GitHub repo describes "Glossa Lab," a broader commercial software platform built by
  "BitConcepts LLC," with this Indus Script analysis as one showcased use case among general-purpose
  AI-assisted decipherment tooling — relevant context for weighing the claim's origin, not a judgment on
  its correctness.

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
  **Update (2026-09-27), a specific, direct-text-tier methodological critique found, going beyond this
  project's earlier abstract+footnote-5 read of FSW**: fetched the full text of Farmer, Sproat & Witzel
  (2004), "The Collapse of the Indus-Script Thesis" (freely hosted on co-author Steve Farmer's own site,
  `safarmer.com/fsw2.pdf`; same paper as the already-cited *EJVS* 11-2 (2004) pp.19-57, this time read
  beyond the previously-checked sections). Direct quote: "even using the Dravidian proponents' own data
  (e.g., Mahadevan 1977: Table 1, 717-23), it is easy to show that positional regularities of single Indus
  signs (and the same is true of sign clusters) are just as common in the middle and at the supposed start
  (or righthand side) of Indus inscriptions as at their supposed end, which if we accepted this whole line
  of reasoning could be claimed as evidence in the system of extensive infixing and prefixing — ironically
  ruling out Dravidian as a linguistic substrate" (since Dravidian is suffixing-only, while the same
  positional evidence, taken at face value, would argue for infixing/prefixing, features Dravidian lacks
  but which Munda has). **This is a direct-text, specific, citable methodological critique of a Dravidian
  correspondence claim** — not the general non-linguistic argument this project already had, but a
  self-refuting-argument critique aimed specifically at the suffixing-language claim central to Dravidian
  proposals. This is FSW's own critical framing, not this project's independent verification of the
  underlying Mahadevan 1977 data — a real, disclosed limitation.
  **Update (2026-09-28), a direct-text-tier critical review of Mahadevan's own positional analysis found**:
  directly fetched (open-access, freely hosted) C. Jyothibabu, "Iravatham Mahadevan's Reading of Indus
  Script: A Critical Review," *Studia Orientalia Electronica* 11(1) (2023): 1–63, DOI
  10.23993/store.85246 (`journal.fi/store/article/view/85246`) — a peer-reviewed, open-access journal (not
  ResearchGate/academia.edu). Exact quote on the review's overall verdict: Mahadevan showed "determined,
  persistent effort" but "did not succeed in making a self-consistent system of readings applicable to a
  large number of discovered pieces of writings." **A specific internal-inconsistency critique of the
  terminal-sign classification** — the same positional-class structure FSW's own paper (see above) argues
  is not discriminating: the reviewer notes "if the ligatured sign is to read from left to right, then it
  is probably an indication of phonetic reading, which contradicts Mahadevan's (1986d) own opinions," and
  that Mahadevan himself "agrees that the five terminal signs are occasionally doubled... thus casting
  doubt on their ideographic character" — i.e., an internal contradiction the reviewer identifies within
  Mahadevan's own published position, not merely an external critique. This is a distinct, independent
  critique from FSW's (positional-regularity self-refutation) and from the Pierson-preprint self-disclosures
  above — three separate lines of documented skepticism about Dravidian/positional-analysis claims now on
  record, from three different sources and methods. Not independently verified against Mahadevan's own
  1977/1986 texts by this project — a direct-text read of the reviewer's own claims, not this project's
  primary-source check.
  **Update (2026-09-28), a bounded search for a pinnable Mahadevan 1986d copy, honest negative result**:
  per ChatGPT's Meeting 12 decision ("locate 1986d, then predefine and count terminal doubling and
  ligatures"), searched specifically for the paper (full citation found: "Towards a grammar of the Indus
  texts: 'Intelligible to the eye, if not to the ears'," *Tamil Civilization* 4(3&4): 15–30, 1986). One
  promising freely-hosted lead was found — `harappa.com/script/maha0.html`, a site that already hosts two
  other primary Mahadevan PDFs (`Indus-sign-design.pdf`, `Indus-Dravidian-script.pdf`) — but it returned
  HTTP 403 Forbidden on direct fetch. Search-snippet tier only recovers a partial content description (the
  paper reportedly treats middle-register single/double strokes, signs 98/100, as possible numeral forms
  or alternates of signs 86/87) — not the terminal-sign doubling/ligature passages themselves. **Genuinely
  unread after one bounded attempt** — not a dead end, but the direct-text read this project's own standard
  requires has not happened. A different access route (library proxy, a different harappa.com URL pattern,
  or direct author/publisher contact) would be the next step, not another automated fetch of the same URL.
  **Update (2026-09-29), a genuinely different route tried — RMRL (Roja Muthiah Research Library), the
  same institutional Tamil-studies archive this project has previously cited for a different Mahadevan
  work**: found the exact paper catalogued at `rmrl.in/en/dl/research-papers/mahadevan` (listed as "Towards
  a Grammar of the Indus Texts: 'Intelligible to the eye, if not to the ears' (1986)"), a legitimate
  institutional holder, not a blocked commercial aggregator. **Still unread, for a different and clearly
  disclosed reason this time**: the paper's own viewer page is a client-rendered JavaScript app (the same
  pattern as SigLA in the sibling linear-a-collective project) — WebFetch retrieves only the server-side
  page shell, no PDF/download link visible in it, and this session's browser tool denied navigation to the
  new `rmrl.in` domain outright. This is a genuine, disclosed *tooling* limitation, distinct from the
  harappa.com 403 (an access/permissions block) — the paper's existence and correct institutional home are
  now confirmed, but its content remains genuinely unread. Not retrying the same viewer URL again; a
  session with working `rmrl.in` browser-tool access, or a direct download-link pattern for this specific
  Next.js viewer, would be the next different approach.
  **Update (2026-09-29), checked for an export/request path — a real one exists, but it needs human
  outreach, not automated fetching**: no download/export link or API exists anywhere in RMRL's page markup
  for this specific ebook viewer. RMRL's own visit/contact page gives a genuine reference-desk channel
  (phone +91-44-22542551, a library email, physical address in Chennai) explicitly inviting queries about
  locating materials. **This is the real resolution path per this project's own "library request"
  suggestion** — but it means an actual person emailing or calling the library, which is outside what an
  autonomous research session should initiate on its own without the user's explicit go-ahead (real-world
  outreach, not a web fetch). Flagged as the concrete next step, not attempted solo.
  Separately located but **not yet
  direct-text-verified**: a specific, frequently-cited example critique of Parpola's "squirrel"/`pillay`
  sign correspondence (his own departure from his stated rebus rules, and a claimed absence of attested
  Dravidian usage of `pillay` alone meaning "squirrel") — sourced this cycle only via WebSearch synthesis,
  not read directly in any primary text; the source paper for this specific example was not identified.
  **Follow-up attempted, still unidentified**: three further direct fetches (Wikipedia's "Harappan
  language," "Asko Parpola," and "Indus script" articles) and one additional WebSearch all failed to
  locate the original source — the same near-verbatim phrasing recurs across multiple secondary blogs
  (e.g. a WordPress post) without any of them naming their own original citation, suggesting all are
  copying from one unidentified upstream source, itself not yet located. A separate, unrelated criticism
  was found instead: Wikipedia's "Asko Parpola" article quotes Colin Renfrew's general methodological
  critique ("Parpola's methodology wanting because... it did not clearly lay out the structure of the
  argument and the underlying assumptions") — a real, citable, but non-specific critique, disclosed here as
  a genuine finding, not a substitute for the still-unlocated squirrel/pillay source. Treating the
  squirrel/pillay source-hunt as exhausted for this session absent a new access route (e.g. a specific
  academic database), not a permanent dead end.
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
