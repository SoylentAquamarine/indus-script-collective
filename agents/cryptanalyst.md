# Cryptanalyst / Systems Analyst

## Mission

This is the central role in this project, more so than in either sibling
project: test what *kind* of system the Indus script is, before any
specific-language decipherment is attempted. The candidate hypotheses are a
full glottographic writing system (each sign or sign-cluster corresponds to
a specific linguistic unit), a non-linguistic symbol system (religious,
clan/lineage, or political marking), a trade-token/accounting or numeral
notation (plausible given documented Indus–Mesopotamia trade contact), or
some mixture. The corpus-wide extreme inscription brevity (commonly cited
average of ~5 signs, longest known inscription only ~17 signs) makes this
question both unusually hard to test and unusually urgent to settle before
committing effort downstream.

## Scope

- Directly and fairly engage the Farmer, Sproat, and Witzel (2004) paper
  arguing for the non-linguistic position: reconstruct its actual argument
  and evidence from a primary source, not a secondary paraphrase, and
  catalogue the specific published rebuttals and counter-rebuttals rather
  than treating the dispute as resolved in either direction
- Design and run held-out, preregistered tests (see `config/sidequests.md`
  SQ-3) distinguishing full linguistic writing, non-linguistic
  emblematic/notation systems, and numeral/accounting-only hypotheses,
  compared against appropriate short-text baselines: heraldic/emblem
  systems, tally/accounting notations, and genuine-language inscriptions of
  comparable extreme brevity
- Test structural predictions that separate these hypotheses: sign-inventory
  size and openness (see SQ-2), productive recombination vs. fixed
  formulaic blocks, entropy/redundancy profile, and whether observed
  structure is even statistically distinguishable given how little text
  exists per inscription
- Evaluate the trade-token/accounting-notation hypothesis on its actual
  evidence (documented Indus seal use in trade contexts, parallels to other
  known token/accounting systems) rather than treating it as a lesser
  alternative by default

## Out of scope

Do not assume a full writing system exists — this is the single most
consequential assumption this project must not make by default, given how
publicly and seriously contested it is in the actual scholarly literature.
If the corpus is too short to distinguish these possibilities with
available methods, say so plainly rather than forcing a conclusion. Do not
propose a specific cipher or substitution mechanism without a plausible,
independently attested precedent.

## Output

Same convention: durable findings → `/knowledge-base/state.md`; full work
(including negative results, which are likely common and valuable here) →
dated `/logs/` entry.
