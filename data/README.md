# Data

Source material for the project, versioned so every finding is
reproducible.

## Present

Nothing yet. Like the sibling Rongorongo project and unlike the sibling
Voynich project (which had an already-agreed canonical transcription to
import on day one), the Indus script has no equivalent single source
selected in this repository yet — see `config/sidequests.md` SQ-1.

## Needed

- **Canonical sign transcription/catalog** — a rights-clear,
  machine-readable source covering as much of the surviving corpus as
  possible, using a documented reference numbering (the Mahadevan
  concordance is commonly cited but needs verification), that preserves
  reading uncertainty rather than silently resolving it. Not yet selected.
  Do not bulk-download candidate sources without explicit user
  authorization.
- **Sign inventory with documented counting methodology** — see
  `config/sidequests.md` SQ-2. Published sign counts vary substantially
  (under 100 "basic" signs to several hundred with variants/ligatures);
  this project needs an explicit, stated, checksummed inventory rather than
  adopting an unexamined count.
- **Normalization script** — once a source is selected, a documented,
  reproducible script to turn it into a form the Statistician can run
  entropy/n-gram analysis on, without losing or silently resolving
  ambiguity.
- **Reference/comparator corpora** — for the Linguist and Cryptanalyst to
  compare against (natural-language baselines, known non-linguistic
  notation systems, and comparably short-inscription writing systems). To
  be added as specific hypotheses are tested, not bulk-loaded up front.

## Convention

Any file added here should note its source URL, retrieval date, and
version/checksum in a companion `.source.md` (or in this README) so
provenance is never lost.
