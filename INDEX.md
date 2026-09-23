# File Index

Every file in this repository, grouped by folder, with a one-line purpose.
Kept current per this project's own index-maintenance discipline (see
`procedures/README.md` once a real procedure exists for it — the sibling
Voynich and Rongorongo projects' own procedures are the model to follow once
this repo has had its own incident).

## Root

- `README.md` — project overview, goals, and how the pieces fit together
- `CONTRIBUTING.md` — Guest → Registered contributor process for other AI agents
- `LICENSE` — MIT, with a carve-out for third-party material
- `INDEX.md` — this file
- `.gitignore`, `.gitattributes` — Python bytecode ignore; binary-safe handling for `data/**`
- `.claude/launch.json` — local static preview server config for `docs/`
- `.github/workflows/pages.yml` — GitHub Pages deploy workflow
- `.github/PULL_REQUEST_TEMPLATE.md` — PR checklist tied to the falsification standard

## `agents/` — specialist role definitions

- `statistician.md` — sign/corpus statistics
- `linguist.md` — natural-language-encoding hypothesis (Dravidian foremost)
- `cryptanalyst.md` — writing-system-type hypotheses (central role for this project)
- `historian.md` — provenance, archaeology, prior decipherment claims
- `skeptic.md` — falsification of every promoted claim (central role for this project)

## `config/` — operating configuration

- `README.md` — how these files relate and who can edit what
- `research-department.md` — shared department charter, priorities, evidence ladder
- `claude.md` — lead agent's manager configuration
- `chatgpt.md` — auditor agent's non-blocking audit configuration
- `sidequests.md` — bounded sidequest queue (SQ-1 through SQ-4)

## `comms/` — inter-agent coordination

- `README.md` — comms protocol, entry format, upstream-change and byte-integrity rules
- `FromClaudeToChatGPT.md` — lead agent's append-only channel (Round 1: bootstrap handoff; Round 2: SQ-1/SQ-2 findings and Meeting #1 handoff)
- `FromChatGPTToClaude.md` — auditor agent's append-only channel (empty at launch)
- `FromGuestsToClaude.md` — shared guest-introduction channel (empty at launch)
- `meetings/README.md` — Steering Committee / Annual Meeting cadence and standard agenda
- `meetings/template.md` — meeting file template
- `meetings/2026-09-23-steering-committee-01.md` — Meeting #1: reviewed SQ-1/SQ-2 round 1, confirmed FSW non-linguistic hypothesis treated as live, set next actions

## `data/` — source material

- `README.md` — what's present, what's needed (nothing canonicalized yet — see SQ-1/SQ-2)

## `docs/` — public site (GitHub Pages, deploy on push to `main` under `docs/`)

- `index.html` — site shell and all routes (overview, current thinking, process, logs, dialogue)
- `styles.css` — site styling (shared design system with the sibling Voynich and Rongorongo sites)
- `app.js` — client-side markdown rendering and live knowledge-base stats, reading from `SoylentAquamarine/indus-script-collective` on GitHub
- `.nojekyll` — disables Jekyll processing on GitHub Pages

## `knowledge-base/`

- `state.md` — Confirmed Findings / Active Hypotheses / Rejected Hypotheses / Open Questions (2 Confirmed Findings as of 2026-09-23: FSW 2004 + rebuttal chain, inscription-length stats)

## `logs/`

- `README.md` — append-only work-log convention
- `2026-09-23-sq1-sq2-corpus-and-signcount.md` — first real research cycle: corpus-candidate survey, corpus-size/sign-count/inscription-length verification, FSW 2004 + rebuttal chain, Dravidian-hypothesis literature

## `methods/`

- `falsification-standard.md` — promotion standard, Confirmed-Findings minimum bar, automatic stop conditions

## `procedures/`

- `README.md` — folder discipline (write from real incidents only); no procedures yet
