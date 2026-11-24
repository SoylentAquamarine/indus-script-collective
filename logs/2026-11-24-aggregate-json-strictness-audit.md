# Upstream aggregate JSON strictness audit — 2026-11-24

## Pinned input
- Repository: [ArnavGoel98/indus-blind-benchmark](https://github.com/ArnavGoel98/indus-blind-benchmark)
- Commit: `bbd0e49151853f4a42a7df394a6cbdb3b7b05c85`
- Aggregate: [`reports/results/aggregate.json`](https://github.com/ArnavGoel98/indus-blind-benchmark/blob/bbd0e49151853f4a42a7df394a6cbdb3b7b05c85/reports/results/aggregate.json)
- Target definitions: [`config/indus_targets.yaml`](https://github.com/ArnavGoel98/indus-blind-benchmark/blob/bbd0e49151853f4a42a7df394a6cbdb3b7b05c85/config/indus_targets.yaml)
- Method/report description: [`README.md`](https://github.com/ArnavGoel98/indus-blind-benchmark/blob/bbd0e49151853f4a42a7df394a6cbdb3b7b05c85/README.md)

## Independent parser check
A strict JavaScript `JSON.parse` rejects the committed aggregate because it contains **35 bare `NaN` tokens**, which are not valid JSON values. Replacing only those tokens with `null` allowed inspection; this normalization was for reading only and does not repair or rewrite the upstream artifact.

After that normalization, the root metadata reports `profile="full"`, `n_records=1554`, and `n_errors=0`. At the full-profile point with 2,906 texts and mean length 4.6, the aggregate reports 7 of 81 total corpora passing all hard targets, including 7 of 60 language corpora. The benchmark's results report identifies these as synthetic calibration results, not an Indus decipherment.

## Calibration caveat
The pinned target file marks both `median_length` and `hapax_fraction` as `verified: false`, yet both remain hard targets in the `full` regime. The README likewise says the median is unverified; the hapax value is attributed to Possehl via Wikipedia rather than a direct check of the cited book pages. The `holdout` regime avoids calibrating the frequency and positional targets and should remain prominent when interpreting the results.

## Limits and decision
No raw benchmark rerun was performed and no real Indus corpus was accessed. A permissive parse does not make the artifact strict JSON. Recommend an explicit null/NaN serialization policy and continued sensitivity reporting for the unverified hard targets before making any inference about the script.
