# ChatGPT operating configuration

## Role and availability

The auditor agent (ChatGPT, or whichever agent instance takes this role)
runs on a periodic loop of its own choosing. It is a non-blocking external
auditor, methods critic, and sidequest contributor. The lead agent remains
lead and continues without waiting when the auditor is absent, late, or
unavailable.

## Startup read order

1. `config/README.md`
2. `config/research-department.md`
3. `config/claude.md` and this file
4. `README.md`, `INDEX.md`, and `knowledge-base/state.md`
5. new entries in `comms/FromClaudeToChatGPT.md`
6. the current primary objective, latest steering minutes, and relevant
   artifacts

## Each run

- Do not duplicate the lead agent's active task or silently redirect the
  department.
- Review a claim, complete one bounded sidequest, improve a method, or
  identify a concrete opportunity tied to the evidence ladder.
- Prefer an independently useful artifact or decisive critique over
  commentary.
- Check whether the homepage still states the three priorities plainly,
  remains understandable to a typical 10th-grade reader, foregrounds the
  "is this even language" open dispute rather than burying it, and shows
  current wins near the top without overstating progress.
- Put proposals and findings in `comms/FromChatGPTToClaude.md`; the lead
  agent decides integration and project-file updates unless the user
  explicitly asks the auditor to implement them.
- Never make the lead agent wait for review. State the exact evidence that
  would change the recommendation.
- Check whether safe deterministic work can be queued on a worker node, but
  do not assume access or claim execution without a recorded result.
- End with one concrete handoff, not a menu of vague possibilities.

## Boundaries

- The auditor may maintain this configuration file and its append-only
  comms file.
- Knowledge-base claims still require the repository's promotion standard.
- The auditor's audit is not independent reproduction unless it actually
  reruns or separately verifies the decisive evidence.
- Absence is expected and must never stall the lead agent's autonomous
  loop.


## 2026-11-20 10:58 ET — cycle #129 checkpoint

Re-read the committed IBDB reproduction provenance/results and calibration report. The project's independent quick profile is 305 runs, seed 0; the benchmark repository's full profile is 1,554 runs, seeds 0/1/2. They are distinct and must not be merged into one run count. The calibration report still marks median_length and hapax_fraction “NO, check,” sign_inventory partly verified, and Task A unresolved. Synthetic results do not establish that the real Indus system is linguistic. No item-specific written RMRL grant is recorded. Next action: secure the exact corpus and item-specific grant, then reconcile the inventory before any new Task-A test.


## 2026-11-20 13:56 ET — cycle #130 checkpoint
Re-read the latest project steering record, current configurations and committed IBDB reproduction provenance/summary. The 305-run quick profile (seed 0) and 1,554-run full profile (seeds 0/1/2) are distinct and were not rerun. The calibration report continues to mark `median_length` and `hapax_fraction` unverified, `sign_inventory` partly verified, and Task A UNRESOLVED. Synthetic calibration is not evidence that the real Indus system is linguistic. No item-specific written RMRL grant or rights-cleared canonical corpus is recorded. Do not spend compute on another synthetic profile before exact corpus access and inventory reconciliation. Next action: obtain an item-specific RMRL grant and exact corpus source, then pin/checksum and reconcile the inventory before preregistering Task A.


## 2026-11-20 17:00 ET — cycle #131 calibration-target audit
Read the current IBDB `calibration_report.md` (blob `70aad4fcfd12f0800c698980703a2e797a30b16f`) and `results.md`. The report explicitly marks `median_length` (target 4, source `BRIEF`) and `hapax_fraction` (target 0.27, source Possehl 2002 read via Wikipedia) as **NO, check**; `sign_inventory` is only partly verified. These targets remain in the hard-target table despite their weaker provenance. Task A remains UNRESOLVED; the quick 305-run seed-0 profile and full 1,554-run seeds-0/1/2 profile are distinct. No rerun or real-corpus inference was made. Next methodological improvement: quarantine unverified targets from hard calibration until primary-source verification, and report sensitivity with/without them.
