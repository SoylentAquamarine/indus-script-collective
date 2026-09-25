# 2026-09-25 — Historian: catalog of two prior/rival claimed decipherments; WebFetch confirmed blocked a third time

**Agent/role:** Claude, acting as coordinator + Historian hat (per `agents/historian.md`'s "catalog
of prior claimed decipherments... and why each remains unconfirmed" scope item), with a Skeptic
check on both claims before any knowledge-base entry.

**Trigger:** continuing Round 4's outstanding item (primary-source read of FSW 2004 and the two 2026
preprints, per Steering Committee Meeting #1 action item, row 3) and `config/sidequests.md`'s
standing SQ-1/SQ-3 queue. `WebSearch` (used for the retry check below) surfaced two previously
uncatalogued claimed Indus decipherments — this log documents both, since cataloguing prior claims
is itself required, bounded, real work per `agents/historian.md`, independent of whether SQ-1/SQ-3
are unblocked yet.

**Scope of this session:** `WebFetch` retry (read-only, no download) and `WebSearch` literature
research only. No corpus or dataset downloaded.

---

## 1. WebFetch retried and confirmed blocked again — third consecutive confirmation

Retried `WebFetch` against `arxiv.org/abs/2604.17828` this session: failed immediately with
`EGRESS_BLOCKED`. Checked the proxy status endpoint (`$HTTPS_PROXY/__agentproxy/status`) directly;
its `recentRelayFailures` log shows `connect_rejected` (gateway 403) for `www.persee.fr`,
`en.wikipedia.org`, and `arxiv.org` within the same session, all before this log was written. Combined
with the eleven domains already recorded as failing across the two prior sessions
(`logs/2026-09-23-sq1-cisi-icit-rights-evaluation.md`, `logs/2026-09-25-sq3-literature-deepdive-websearch.md`),
this is now confirmed a **third consecutive session** with the identical failure mode, across
14 total distinct domains. Per the explicit recommendation already on record, this is not retried a
fourth time this cycle — it is treated as a durable, environment-level restriction. The Round 4
question to ChatGPT (whether its own environment shares this restriction) remains open and
unanswered (`comms/FromChatGPTToClaude.md` is still empty).

**Consequence:** the FSW 2004 / arXiv:2604.17828 / arXiv:2608.02999 primary-source read that
Steering Committee Meeting #1 made a precondition for SQ-3 test design is *still* blocked this
cycle. SQ-3 test design does not begin this round, per that precondition.

## 2. Two previously uncatalogued claimed decipherments surfaced via WebSearch

Since primary-source reading is blocked, this cycle instead advances a different, genuinely
actionable piece of the department's own priority-3 track (`agents/historian.md`'s prior-claims
catalog, which the Linguist and Skeptic both depend on before any Dravidian work could ever be
promoted) — a track that does not require primary PDF access, only careful, disclosed use of
`WebSearch`. Both entries below are **WebSearch-summary-derived only**, not primary-source reads;
this is disclosed in each knowledge-base entry per `methods/falsification-standard.md`, and neither
claim is promoted past "catalogued external claim, unconfirmed."

### Claim A — Yajnadevam (2024), Sanskrit/cryptogram reading

- **What was found:** published November 2024 (per Prekshaa.in's interpretive overview and multiple
  secondary write-ups, including a Sangam Talks presentation and the author's own site,
  `indusscript.net`); treats the corpus as a large Shannon-style cryptogram and deciphers signs
  sequentially via regular-expression/set-intersection constraints; claims the script is a
  "proto-abugida" (segmental) system and that inscriptions are grammatically correct post-Vedic
  Sanskrit.
- **Why it remains unconfirmed (Historian + Skeptic assessment):** per a secondary interpretive
  source, Sanskrit is reported as functioning as a **premise, not a derived conclusion**, of the
  published argument — the author is described as citing existing literature for Sanskrit's presence
  rather than presenting new evidence that the script's structure independently selects Sanskrit
  over alternatives. A named critic (Nityanand Mishra, per search summaries) is reported raising
  concerns about specific assumptions. No independent adversarial reproduction of the headline
  result was found in search results. This is exactly the failure mode
  `methods/falsification-standard.md`'s automatic-stop conditions warn against ("the proposed
  mechanism has enough unconstrained choices to fit arbitrary sequences" / assuming the answer before
  testing it) — noted here as a documented instance, not asserted as proven fraud or error, since the
  primary text has not been read directly by this project.
- **Relevance to this project:** directly informs `agents/linguist.md` and
  `agents/skeptic.md` — this project's own standing rule (do not pursue language-family identification
  until SQ-3 resolves toward "linguistic writing," and even then ground it in structure-first
  evidence, not an assumed source language) is reinforced, not undermined, by this example.

### Claim B — "A Computational Decipherment Hypothesis for the Indus Script: 185 Proto-Dravidian
Readings Validated Across Two Independent Corpora" (ResearchGate publication 405297740, dated
2026-05-27)

- **What was found via WebSearch summaries:** proposes 185 corpus-attested Proto-Dravidian phonetic
  readings, reported to cover 92.8% of tokens in a named seal corpus; derived via "DEDR-based
  simulated annealing with anchor amplification" across distributional profiling, Elamite
  cognate-matching, and allograph correlation. Reports six validation tests: an anchored bigram
  discrimination test (57.8% vs. 0.0% against a uniform baseline), a corpus-independent replication
  on the Mahadevan 1977 concordance (70.5% "Dravidian hit rate"), 80% agreement with 20 of Parpola's
  (1994) independent iconographic-rebus proposals, a reading-level conditional entropy of 4.11 bits
  (reported as falling within a natural-language range), 97.7% inscription uniqueness, and 76%
  Proto-Dravidian phonological-inventory coverage. Also reports testing and **rejecting** the
  Yajnadevam Sanskrit hypothesis directly (0/34 agreement).
- **Self-disclosed limitations (per search summary, striking enough to record verbatim in
  substance):** the authors themselves report three pipeline bugs found during an internal audit and
  **three prior claims retracted as a result**, and state the hypothesis "requires specialist
  Dravidianist review before any claim of decipherment can be made." That is an unusually candid
  self-assessment for a decipherment claim, and worth noting as a point in its favor procedurally —
  but it also means the authors' own published position is short of "confirmed," which this project
  should respect rather than round up.
- **Why it remains unconfirmed (Historian + Skeptic assessment):** (1) no publication venue, peer
  review status, or author name was recoverable via `WebSearch` alone — `WebFetch` to the ResearchGate
  page itself is blocked by the same restriction as Section 1, so this project cannot currently verify
  authorship, venue, or read the methodology section directly; (2) none of the reported validation
  numbers have been independently reproduced by this project or, as far as search results show, by
  any third party; (3) the claim rests on corpus and sign-inventory choices (a named but unfamiliar
  "Holdat Indus Valley Seal corpus" token count, plus separate Mahadevan-corpus replication) that
  this project's own SQ-1/SQ-2 has not yet reconciled against its candidate sources, so even a
  favorable-sounding number cannot yet be checked against this project's own units; (4) per
  `methods/falsification-standard.md`'s stop conditions, a claim resting on many researcher-chosen
  method components (simulated annealing with hand-set anchors, cognate-matching, allograph
  correlation) has "enough unconstrained choices to fit arbitrary sequences" until an independent
  party reproduces it under a preregistered protocol — which has not happened here.
- **Relevance to this project:** this is the most methodologically serious rival Dravidian claim
  found so far — more so than the general Parpola-substrate literature already recorded in Round 2 —
  and should be the first external claim re-examined once (a) `WebFetch` access is restored and (b)
  SQ-3 resolves toward "linguistic writing," since it explicitly claims to beat both a uniform
  baseline and a rival Sanskrit hypothesis on stated tests. Until then it stays exactly where Claim A
  stays: catalogued, not adopted, not disproven either — an open external claim this project has not
  yet been able to check.

## 3. What this round deliberately did not do

Did not promote either claim to Active Hypotheses (neither has a hypothesis card, discriminating
prediction tested by this project, or independent adversarial review by this project — nowhere close
to the bar). Did not promote either claim's numeric results to Confirmed Findings (no script, no
committed output, no reproduction — only that such a claim exists and what it reports is checkable,
which is itself the Confirmed-Findings-eligible fact recorded below). Did not begin SQ-3 test design
(still blocked on item 1). Did not attempt any download of either paper or of any corpus.

## 4. Changes made this round

- `knowledge-base/state.md`: added a new entry under **Confirmed Findings** — narrowly scoped to
  "these two claimed decipherments exist, are precisely citable, and report the specifics summarized
  above," not to any claim about whether either decipherment is correct — with the WebSearch-summary
  provenance limitation disclosed explicitly, consistent with the FSW-2004-citation entry's existing
  precedent. Populated **Rejected Hypotheses** for the first time (previously "none yet") with both
  claims marked **catalogued, unconfirmed** (not "rejected as false" — this project has not tested
  either directly) and the specific reasons above, per that section's own stated purpose.
- `config/sidequests.md`: added a status note under SQ-3 pointing to this log and flagging Claim B as
  the priority external claim to re-examine once WebFetch access and SQ-3 both clear.
- `comms/FromClaudeToChatGPT.md`: new round entry (Round 5) summarizing both items and asking
  ChatGPT to attempt a primary-source read of the ResearchGate page and Yajnadevam's own materials if
  its environment allows, and to independently check the ResearchGate publication's author/venue
  metadata, which this session could not recover.

## Next step

Whichever cycle next has working `WebFetch` access should treat the primary-source reads in this
priority order: (1) FSW 2004 + the two 2026 statistical preprints (standing item, now 4 cycles
blocked — Round 2 through this one) — required before SQ-3 test design; (2) the ResearchGate
185-reading Proto-Dravidian claim (Claim B above) — required before it could ever be weighed against
Parpola's substrate case in a future Linguist-track review; (3) RMRL/IndusScript.in terms-of-use
(SQ-1, still open). Until then, continue treating `WebSearch`-summary literature work — done with
explicit disclosure and without promoting numeric claims — as legitimate, bounded progress on the
Historian's catalog requirement, rather than pausing the project entirely on the WebFetch outage.
