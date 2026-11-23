# IBDB metric-definition and target-provenance audit — 2026-11-23

## Pinned upstream source
Repository: https://github.com/ArnavGoel98/indus-blind-benchmark  
Commit: `bbd0e49151853f4a42a7df394a6cbdb3b7b05c85`

Files read directly at that commit:
- `src/ibdb/stats.py` — Git blob `517451729d8958d1ed12392af0902c07416227c9`
- `config/indus_targets.yaml` — Git blob `b6ee78d02edefb6e7d09929e97b41d2770fc048c`

## Operational definitions reproduced from code
- `median_length`: median of the lengths of non-empty texts after the corpus parser's text filtering. The code uses `np.median(lengths)`; it is not a mean and is not computed on the 1,548-text positional subsample.
- `hapax_fraction`: number of distinct sign types whose token count is exactly one, divided by the number of distinct sign types in the hapax subsample. The code samples exactly 2,906 texts when the corpus is larger, using `seed + 1`, then computes the type-frequency Counter.

These are operational definitions from the benchmark's pinned implementation, not independent archaeological measurements of the Indus corpus.

## Target provenance remains unresolved
The pinned target config explicitly marks both targets `verified: false`:
- `median_length = 4 ± 1`: source is `BRIEF`, described as a benchmark-owner project brief with no primary source attached. The config says Yadav 2010 Fig. 2 shows lengths 3 and 5 as modes, but no published median was found.
- `hapax_fraction = 0.27 ± 0.10`: source is Possehl 2002, pp. 132–133, but the config says the number 113/419 was read via English Wikipedia and still needs direct checking of Possehl p.132.

Google Books metadata confirms the book's chapter "The Indus Script" begins at p.127, but its exposed selected-page list does not include pp.132–133; this does not verify the 113/419 figure:
https://books.google.com/books?id=pmAuAsi4ePIC

## Decision
The formulas are now documented at source-code tier. The two calibration target values remain unverified and should not be described as primary-source facts. Recommend treating median_length as report-only until a published median or raw corpus calculation is located, and retaining hapax_fraction as provisional until Possehl pp.132–133 are directly inspected. Do not change the upstream benchmark or rerun its seed-0/full profiles.

## Next action
Obtain a direct library/scan consultation of Possehl pp.132–133 and identify a primary corpus or published table from which the median can be computed. Separately, secure written RMRL permission for the exact corpus/version/use before real-corpus analysis.
