# 2026-09-23 — SQ-1: CISI and ICIT license/rights evaluation (round 2)

**Agent/role:** Claude, acting as Research Director + Data Steward, per the explicit action item
from Steering Committee Meeting #1
(`comms/meetings/2026-09-23-steering-committee-01.md`, item 7, row 2): "Evaluate CISI and ICIT for
license/rights and format (no download) as SQ-1's next concrete step."

**Scope of this session:** web research only (WebSearch), no download, no bulk-fetch of any
corpus or dataset. Attempted to also read the FSW (2004) primary PDF and the two 2026 preprints
directly per the same meeting's item 7, row 3 — **could not**: this session's `WebFetch` tool
returned `EGRESS_BLOCKED` for every URL attempted this cycle, including plainly ordinary/uncontroversial
ones (`en.wikipedia.org`, `arxiv.org/pdf/2604.17828`, `www.safarmer.com/fsw2.pdf`,
`www.researchgate.net`, `ignca.gov.in`, `www.epigraphica.de`, `www.user.tu-berlin.de`) — this looks
like a network-egress restriction of this session's own environment, not a property of those
sources, so it is flagged here as a blocker for the *next* cycle or the other collaborator to
retry, not treated as "primary source unreadable." Only `WebSearch` (which fetches server-side, on
a different path) worked this session, so everything below is disclosed as **secondary-source
(WebSearch summary) derived**, same limitation as the prior round's log.

---

## 1. CISI (Corpus of Indus Seals and Inscriptions, Parpola et al.)

**Finding: CISI is not rights-clear for bulk reuse. Copyright is explicitly held by a named
rightsholder, not open or public domain.**

- Vol. 1 (*Collections in India*, 1987) is published by the Academy of Finland
  (Suomalainen Tiedeakatemia / Academia Scientiarum Fennica) in its *Annales Academiae
  Scientiarum Fennicae* series. **Copyright for the volume is held by Academia Scientiarum
  Fennica, and copyright in the individual object photographs is held separately by the owning
  institutions/museums** — i.e., two separate rightsholder classes, neither of which is this
  project.
- Vol. 2 (*Collections in Pakistan*, ed. Shah & Parpola) and Vol. 3 (2010, ed. Parpola, Pande &
  Koskikallio, in multiple parts) follow the same series and rightsholder structure.
- The corpus is **readable** through several channels — academic library holdings (WorldCat,
  HathiTrust, UW-Madison), and Vol. 1 appears to be digitized and viewable via the Indian
  government's Indian Culture Portal (`indianculture.gov.in/ebooks/corpus-indus-seals-and-inscriptions`,
  a National Virtual Library of India / IIT Bombay project) and referenced at harappa.com — but
  "viewable through a library or a government reading portal" is not the same as "rights-clear for
  this project to extract, transcribe, and redistribute a derived machine-readable dataset."
- **Verdict for SQ-1's rights-clear bar: CISI fails it as things stand.** It would need explicit
  permission from Academia Scientiarum Fennica (and, for individual photographs, potentially the
  owning museums) before any transcription/extraction work from it could be treated as licensed,
  not just readable.

## 2. ICIT (Interactive Corpus of Indus Texts, Wells & Fuls)

**Finding: corrects the prior round's log. ICIT is not merely "email and wait" — it has been a
live, named, publicly-addressed online tool since October 2009, hosted at
`epigraphica.de/indus/` with a mirror at `user.tu-berlin.de/fuls/Homepage/indus/`. But it is
query/search-interface software over a gated database, not a bulk-downloadable dataset, which
matters independently of the login question.**

- Per a documentation file found (*"Documentation of the Online Indus Writing Database,"* Andreas
  Fuls, Berlin 2010 — PDF at `user.tu-berlin.de/fuls/Homepage/indus/help_onlinedatabase.pdf`,
  not read directly this session, only its existence and description surfaced via search), the
  tool supports: searching the sign list, searching the text corpus for sign combinations,
  paradigmatic/syntagmatic pattern analysis, statistical tools, and spatial-distribution mapping
  of inscribed objects. Its outputs are described as **per-query** results — "HTML output with
  click-boxes," "Text output... useful in copying results to a Word document," and images at
  either thumbnail or publication resolution — i.e., a researcher retrieves what a specific query
  returns, not a single structured export of the full 4,537-object / 5,509-text / 19,616-sign-
  occurrence dataset.
- Multiple independent search results consistently state that a prospective user must ask the
  administrator (Andreas Fuls; `andreas.fuls@tu-berlin.de` or `fuls@epigraphica.de`) for access —
  so it is real software that has existed publicly for over a decade, but functions behind a
  login/registration gate, not an anonymous open pull.
- **Verdict for SQ-1's rights-clear + machine-readable bar: ICIT also fails it as things stand**,
  for two independent reasons that should not be conflated: (a) access requires the administrator's
  permission (a rights/access question), and (b) even with access granted, the tool's own
  documented output model is per-query HTML/text/image, not a single machine-readable bulk export
  — so "getting the whole corpus out" would mean either building a scripted scraper against many
  individual queries (a new question to put to the administrator directly, since automated
  scraping against someone else's login-gated tool is its own rights issue distinct from viewing
  access) or negotiating a direct data-sharing agreement for the underlying structured data.

## 3. Re-checked: Mahadevan/RMRL, for contrast

Not re-litigated in depth this round (already covered in the prior log), but worth stating
plainly now that CISI and ICIT have both been evaluated and found not rights-clear: the Mahadevan
1977 concordance is hosted on the Internet Archive as a free, unauthenticated,
download/borrow/stream item
(`archive.org/details/TheIndusScript.TextConcordanceAndTablesIravathanMahadevan`), and the Roja
Muthiah Research Library's Indus Research Centre separately published a free online version. This
is not a confirmed explicit open license (Archive.org hosting does not by itself establish
public-domain status, and this project has not directly read any RMRL/Archive.org terms-of-use
page this session — another WebFetch-blocked check to retry), but it is the only one of the three
named candidates that is *currently, anonymously, freely accessible in full* rather than gated by
a named rightsholder's permission or an administrator's login grant.

## Overall disclosed limitation

Everything above is WebSearch-summary derived, not a primary read of CISI's copyright page, the
ICIT documentation PDF, or any RMRL/Archive.org terms-of-use page — all direct-fetch attempts this
session hit `EGRESS_BLOCKED` regardless of domain. This is a stronger limitation than the prior
round's (that round could have used WebFetch and simply chose breadth-first search; this round
could not use it at all), so nothing here should be treated as higher-confidence than the prior
round's equivalent disclosures, and the specific numbers/claims (e.g., "online since October 2009")
should be re-verified by direct read the next time WebFetch or an equivalent works in-session.

## What changed as a result

- `config/sidequests.md` SQ-1 status note updated with this evaluation and a **provisional**
  (not final) recommendation: given CISI and ICIT both currently fail the rights-clear bar for
  different reasons, and the unvetted GitHub repo remains unvetted, the least-blocked path for
  SQ-1 is to provisionally adopt **Mahadevan/RMRL as the first working corpus** (smaller, older
  coverage, but actually freely accessible today), explicitly trading coverage for rights-clarity,
  while keeping CISI and ICIT on the queue as permission-pending/higher-coverage sources to revisit
  if the project (with the user's authorization) ever contacts either rightsholder directly.
- No change to `knowledge-base/state.md` this round — per the precedent set at Steering Committee
  Meeting #1, source rights/access findings are infrastructure decisions for `config/sidequests.md`,
  not Confirmed Findings about the script itself.
- `comms/FromClaudeToChatGPT.md` Round 3 added, reporting this finding, flagging the WebFetch
  outage, and re-issuing the still-outstanding request to read the FSW 2004 PDF and the two 2026
  preprints directly.

## Next step

1. Next cycle that can actually reach the open web with a fetch tool: read the FSW (2004) PDF and
   the two 2026 preprints directly — this is now a **twice-deferred** precondition for SQ-3 test
   design (first deferred at Meeting #1 for being search-summary-only; now deferred again by an
   environment-level fetch block), so it should be treated as increasingly urgent, not routine.
2. Before treating "Mahadevan/RMRL, provisionally" as an actual SQ-1 selection (not just a
   recommendation), directly verify RMRL's/Archive.org's stated terms of use/rights for their
   digitization, the same rigor just applied to CISI and ICIT — do not let it pass by default
   just because it's the only unblocked option.
3. If/when the user gives explicit authorization to contact a rightsholder, the concrete asks are
   now specific: Academia Scientiarum Fennica (or Parpola/the CISI editors) for CISI reuse terms;
   Andreas Fuls for ICIT bulk/structured data access beyond the per-query web tool.
