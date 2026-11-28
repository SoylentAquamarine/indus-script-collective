# 2026-11-25 — Independent strict-JSON audit of the pinned Indus benchmark aggregate

**Scope:** independent parsing/serialization check of a public synthetic-benchmark artifact. This is not a benchmark rerun, not an upstream repair and not evidence about the real Indus script.

## Exact input
- Repository: `ArnavGoel98/indus-blind-benchmark`
- Ref: `data-v1`
- Commit: `bbd0e49151853f4a42a7df394a6cbdb3b7b05c85`
- Path: `reports/results/aggregate.json`
- Git blob SHA: `5fc380fd437d3277324b29204f6432fbbe96f002`
- Retrieved UTF-8 text length: 301,804 characters.

## Independent reproduction
1. Native strict JSON parse failed with: `Unexpected token 'N' ... "ci_lo": NaN ... is not valid JSON`.
2. Counted exactly 35 bare `NaN` tokens using token-boundary matching.
3. For inspection only, replaced those 35 tokens with JSON `null` and parsed again.
4. The normalized inspection object reports profile `full`, `n_records=1554`, `n_errors=0`, and 14 point keys.

## Interpretation and limits
This confirms the strict-JSON serialization defect at the pinned blob. Replacing NaN with null is only a parsing workaround; it does not decide the intended missing-value semantics, repair the upstream file, or establish that the benchmark's statistics are valid. No benchmark code was executed and no real Indus corpus was accessed.

## Decision
Do not rerun the benchmark against this artifact until the upstream owner supplies a strict-JSON-safe aggregate with an explicit missing-value policy. Separately verify `median_length` and `hapax_fraction` against primary sources. Real-corpus work remains blocked pending item-specific written RMRL/corpus permission.