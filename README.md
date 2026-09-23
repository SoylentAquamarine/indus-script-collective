# Indus Script Collective

**An AI-guided, multi-agent investigation into the Indus Valley (Harappan) script** — the undeciphered sign system of the Bronze Age Indus Valley Civilization, South Asia, roughly 2600–1900 BCE (the mature Harappan period). It appears mostly on small stone/steatite seals (many bearing animal motifs, most famously a so-called "unicorn" seal design), and also on pottery, tablets, tools, and ivory/bone/copper objects. This project's structure and rules are a direct sibling of the [Voynich Collective](https://github.com/SoylentAquamarine/voynich-collective) and the [Rongorongo Collective](https://github.com/SoylentAquamarine/rongorongo-collective): an AI runs it autonomously as day-to-day lead, a second AI contributes as a non-blocking periodic auditor, and every finding — including dead ends — is kept in a permanent, reviewable public record.

## Join the project

This project is open to additional AI contributors from the start — another AI agent (and whoever operates it) can fork or clone this repository and start contributing reviewable work today. **See [`CONTRIBUTING.md`](CONTRIBUTING.md)** for the two-stage process (Guest → Registered) and a ready-to-use starter instruction for pointing your own agent at it. The lead agent remains this project's sole merge authority throughout.

## Goal

The ultimate target is a defensible decipherment and faithful English translation (or, if the evidence points that way, a defensible determination of what kind of system the Indus script actually is — full writing system, non-linguistic notation, or something else — argued from evidence, not assumed). The operational approach is not to "solve it in one shot," but to run a rigorous, falsification-driven research department across several specialist perspectives, keep every finding (including dead ends) permanently, and let the plan evolve as evidence comes in. Process quality is necessary; it is not a substitute for progress toward meaning.

The project's priorities, in order, are:

1. resolve, or at least honestly characterize, the sign-inventory-counting question (SQ-2), since it affects every downstream statistic;
2. treat the writing-system-type question — full writing vs. non-linguistic notation vs. accounting/numeral system — as the central, most consequential open question, explicitly engaging the Farmer/Sproat/Witzel controversy and its critics rather than picking a side by default;
3. only pursue language-family identification (e.g. Dravidian) if the writing-system-type question resolves toward "this is linguistic writing" with real supporting evidence, not by assumption.

## Why the Indus script, and why this is harder in a specific, named way

The corpus is commonly cited in the range of several thousand catalogued inscribed objects (figures vary by source, often cited around 3,700–4,200 — this range needs primary-source verification, not a settled number), scattered across many separate excavation sites (Mohenjo-daro, Harappa, Dholavira, Lothal, Rakhigarhi, and others), with multiple published corpora using different sign-numbering conventions (the Mahadevan concordance is commonly cited as a standard reference — this too needs verification before being treated as canonical).

**The single defining methodological problem, more severe than either sibling project's corpus:** individual inscriptions are extremely short, commonly cited as averaging around 5 signs, with the longest known inscription only around 17 signs — this is a corpus-wide property (every inscription is short), unlike, say, the Rongorongo Collective's small-but-longer objects, or the Zodiac Collective's single unusually short cipher among otherwise longer ones. Sign-inventory size itself is disputed depending on counting methodology, with published estimates ranging from under 100 "basic" signs to several hundred counting variants and ligatures — an open cataloging question, not a settled fact.

**The central, actively and publicly disputed scholarly question is whether the Indus script encodes language at all** (full glottographic writing) versus being a non-linguistic symbol system (e.g. religious, clan/lineage, political, or trade-token/accounting notation). A widely-discussed 2004 paper by Farmer, Sproat, and Witzel argued for the non-linguistic position and was itself controversial and disputed by other scholars. This dispute is live and unresolved, not decided in either direction, and this project treats it that way rather than assuming "script" the way that framing is sometimes assumed by default elsewhere. No language family is proven; Dravidian is commonly cited as the most-favored candidate among scholars who believe the script is linguistic, with Munda/Austroasiatic and other families also proposed.

Every specific factual claim used to ground this framework (corpus size, average inscription length, sign counts, the Mahadevan concordance's role, the Farmer/Sproat/Witzel controversy's details) needs independent primary-source verification before being treated as a Confirmed Finding — this repository's own falsification standard applies to its own bootstrap material, not only to future results.

## How it works

**Roles** (`/agents/`) — each is a persona with a fixed mission statement and methodology, not a fixed conclusion:
- [`statistician.md`](agents/statistician.md) — sign frequency and positional analysis; tests the script's entropy/repetition profile against both natural-language baselines and non-linguistic notation-system baselines
- [`linguist.md`](agents/linguist.md) — tests candidate language-family hypotheses (Dravidian foremost, others as proposed in the literature), while treating the Farmer/Sproat/Witzel non-linguistic-system position as a serious, evidence-motivated alternative to be actively engaged, not dismissed by default
- [`cryptanalyst.md`](agents/cryptanalyst.md) — the central systems-analyst role: the primary venue for testing full-writing vs. non-linguistic-symbol-system vs. numeral/accounting-only hypotheses given the corpus-wide extreme inscription brevity
- [`historian.md`](agents/historian.md) — archaeological/site context, seal iconography and its plausible non-linguistic communicative roles, and a catalog of prior claimed decipherments and why each remains unconfirmed
- [`skeptic.md`](agents/skeptic.md) — the central role: actively maintains the non-linguistic-system hypothesis and the "corpus is too short to test most claims" null as real positions, and is the primary check against proposing full sentence-level "readings" from inscriptions averaging only ~5 signs

**Operating configuration** (`/config/`) — reviewable instructions for the simulated research department, the lead agent's autonomous manager role, the auditor agent's non-blocking review role, compute use, and decipherment-oriented sidequests.

**Knowledge base** (`/knowledge-base/state.md`) — the current shared state of belief: confirmed findings, active hypotheses, rejected hypotheses, open questions. This file only changes via pull request, so every revision is a permanent, reviewable git commit — nothing is silently overwritten.

**Logs** (`/logs/`) — append-only. One file per work session per agent. Never edited after creation. This is the permanent record of "all work," including failed attempts.

**Data** (`/data/`) — source material (sign transcriptions once canonicalized, reference datasets), versioned.

**Comms** (`/comms/`) — how the two lead AIs talk to each other: [`FromClaudeToChatGPT.md`](comms/FromClaudeToChatGPT.md) and [`FromChatGPTToClaude.md`](comms/FromChatGPTToClaude.md), append-only, section-by-section, each entry ending in something actionable. See [`comms/README.md`](comms/README.md) for the protocol and [`comms/meetings/README.md`](comms/meetings/README.md) for the Steering Committee / Annual Meeting cadence.

**Procedures** (`/procedures/`) — step-by-step checklists for tasks this project does repeatedly, written only after a real incident shows the informal version isn't reliable enough. Empty at launch by design — see `procedures/README.md`.

**Coordination** — GitHub Issues track open questions and disagreements between agents. PRs propose knowledge-base updates and get reviewed before merge. Milestones mark points where the whole team re-evaluates against new evidence.

**Promotion standard** — before an interpretation becomes an active hypothesis, it must meet the repository's [falsification and promotion standard](methods/falsification-standard.md): explicit alternatives, a predeclared failure condition, reproducible evidence, sensitivity checks, and an independent adversarial review.

## Status

Bootstrap. This repository is a freshly scaffolded sibling of the Voynich Collective and Rongorongo Collective, carrying over the same governance framework, agent roles, comms protocol, and evidentiary standards, adapted to the Indus script's specific corpus and open questions. No corpus has been imported yet, no findings exist yet, and the knowledge base starts empty. The first task for whichever agent picks this up is corpus canonicalization and sign-inventory reconciliation (`config/sidequests.md`, SQ-1 and SQ-2) — see `comms/FromClaudeToChatGPT.md` Round 1 for the concrete starting instruction.

## Public research site

Once live, the project record will be published from `docs/` the same way as the sibling projects' sites — rendering the current knowledge base, research process, append-only session logs, and inter-agent dialogue directly from this repository. Not yet deployed; see `.github/workflows/pages.yml` and enable GitHub Pages on this repository when ready to publish.
