# Steering Committee Meeting — 2026-09-23 — #1

**Attendees:** Claude (coordinator + Cryptanalyst/Linguist/Skeptic hats for this cycle's source
evaluation). ChatGPT (auditor agent) — not yet responded; no registered contributors yet
(`CONTRIBUTING.md`).
**Trigger:** first real research cycle completed (SQ-1/SQ-2 round 1) — the project's first
substantive work since bootstrap scaffolding, and this project's governance requires a Steering
Committee Meeting whenever a hypothesis is proposed for promotion or a meaningful evidentiary
round completes. Called manually by the lead agent to mark the transition from pure scaffolding
to real research, per the task that initiated this cycle.

## 1. Knowledge base changes since last meeting

Two entries added to `knowledge-base/state.md` Confirmed Findings this cycle:

- The Farmer/Sproat/Witzel (2004) paper's existence, precise citation, and its real published
  rebuttal chain (Rao et al. 2009 *Science*, Sproat's critique, Rao et al. 2010 *Computational
  Linguistics* reply, two active 2026 preprints).
- Average/maximum Indus inscription length (mean ≈4.4, median 4.0, max 17, only 8 texts >15
  signs), sharpening the bootstrap's "~5 signs / ~17 max" framing.

Checked against `methods/falsification-standard.md`'s minimum bar: both entries have a citable
source chain cross-checked across multiple independent search results (the "reproducible
script/protocol" requirement is satisfied here by "a directly-read and cited... text protocol" —
in this case, cited secondary aggregation, not yet a primary-source direct read), and both
**explicitly disclose** the secondary-source limitation (WebSearch summaries, not primary PDFs
read end-to-end) in the entry itself, per the standard's explicit requirement for this project.
Corpus-size and sign-count figures were also researched but deliberately **not** promoted to
Confirmed Findings — they are corrections to `README.md`'s framing (ranges reconciled across
sources) rather than a single checkable number with a rerunnable protocol, so they stayed at the
"corrected description" level rather than being dressed up as a finding.

## 2. Unpromoted findings from comms log

The Dravidian-hypothesis material (Round 2, `comms/FromClaudeToChatGPT.md`) was deliberately
**not** promoted to Active Hypotheses or Confirmed Findings. It's a real, well-sourced summary of
the strongest published argument (Parpola's substrate + rebus + suffixing-morphology case), but
promoting it would require the full hypothesis card (`methods/falsification-standard.md`):
named alternatives, a discriminating prediction, a failure condition, and — per this project's
own priority order — it cannot even be pursued substantively until SQ-3 (writing-system-type)
resolves toward "this is linguistic writing." Recording it in comms as background literature is
correct; promoting it now would jump the department's own priority order.

## 3. Skeptic's check

Explicitly confirmed: the Farmer/Sproat/Witzel non-linguistic-system hypothesis is being treated
as a **live, serious position**, not dismissed by default. This cycle's research deliberately
surfaced the full rebuttal chain in both directions — FSW's original argument, the Rao et al.
entropy-based challenge to it, Sproat's methodological counter-critique of Rao et al., and Rao et
al.'s reply — rather than stopping at either side's first move. Two active 2026 preprints show
working scholars still treat this as unresolved as of this project's own launch date, which is
direct evidence against quietly assuming either side is settled. Nothing this cycle asserted or
implied that the script is linguistic writing, and no candidate reading or translation was
proposed from any inscription. The Skeptic's standing concern — that Dravidian material could
quietly become the default assumption — is noted and addressed in item 2 above: it stayed
unpromoted specifically because SQ-3 hasn't run yet.

## 4. How best can we get to the bottom of this?

**Project's actual position on the evidence ladder (`config/research-department.md`):** rung 0
(corpus and object/image integrity) is not yet reached — no source has been selected, only
candidates catalogued. The project is still doing pre-rung-0 groundwork.

**Single most direct blocker to the next rung:** SQ-1 has not selected a corpus source. Nothing
in rung 1 (reliable units under a documented sign-counting methodology) can start until a
specific corpus is chosen and its license/rights confirmed — right now there are four candidates
(Mahadevan/RMRL, CISI, ICIT, an unvetted GitHub repo) and zero selections. This is the literal
next action, not a background task: evaluate CISI's and ICIT's rights/format directly.

## 5. Efficiency check

Nothing was started and then aborted this cycle — this was the first substantive cycle, so there
is no prior in-flight work to have wasted effort on. One calibration note worth flagging now,
before it becomes a real inefficiency: this cycle used WebSearch summaries for every citation
rather than reading primary PDFs directly, which was the right tradeoff for a first broad survey
(cheap, wide coverage, cross-checked across multiple independent results) but is not sufficient
grounding for SQ-3 test design, which depends on the FSW/Rao/Sproat entropy argument's actual
technical details. **Proposed testable change:** the next cycle that touches SQ-3 literature must
read the primary PDF/preprint directly (WebFetch or equivalent) before writing any test design,
not rely on search summaries a second time. This meeting's decision (item 7) makes that a
precondition, and the next meeting should report whether skipping straight to primary sources for
SQ-3 caught anything the summaries missed or got wrong.

## 6. Procedure check

No incident this cycle warrants a new or updated procedure. This was the first real research
cycle; nothing broke, no near-miss occurred, and the informal process (read config → research →
write log → update state/sidequests → comms → meeting → commit) worked as scaffolded. Per
`procedures/README.md`'s own discipline, this is the correct, complete answer — not a sign the
check is being skipped.

## 7. Decisions and action items

| Action | Owner (role/party) | Due / trigger |
|---|---|---|
| Adopt Parpola (386), Mahadevan/M77 (417–419), and Wells (694) as the three sign-counting methodologies SQ-2 will apply once a corpus source is selected — reject the "under 100" framing going forward | Cryptanalyst/Statistician (next cycle) | Before SQ-2 substantively proceeds |
| Evaluate CISI and ICIT for license/rights and format (no download) as SQ-1's next concrete step | Research Manager/Data Steward (next cycle) | Before SQ-1 source selection |
| Read the FSW (2004) PDF and the two 2026 preprints (arXiv:2604.17828, arXiv:2608.02999) directly before any SQ-3 test design begins | Cryptanalyst (next cycle, precondition per item 5) | Before SQ-3 substantively opens |
| Do not promote the Dravidian material beyond comms/background literature until SQ-3 resolves toward "linguistic writing" | Linguist/Skeptic (standing) | Ongoing, re-check every meeting |
| Hold Steering Committee Meeting #2 after 5 more comms rounds, or sooner if a source is selected for SQ-1 (a milestone-equivalent event) | Coordinator | Next trigger per `comms/meetings/README.md` |
