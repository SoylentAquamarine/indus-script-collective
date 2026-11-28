# Indus calibration NaN artifact-scope audit — 2026-11-27

**Scope:** inspect committed text reports and current main tree only; no real Indus corpus bytes accessed.

## Exact artifact
- data/external-sources/ibdb-reproduction-2026-10-10/results.md
- Git blob: 698a912322a7ee1da368934ef0d579ab7f1bccc7

A case-insensitive scan of this Markdown file finds exactly one literal occurrence of nan, in the row for 2,906 texts and the A-best balanced-accuracy cell. This is a Markdown report value, not a JSON parse error.

The current main Git tree contains no aggregate JSON path/hash supporting the repeated claim of 35 bare NaN tokens. Without the exact file, commit/blob hash, parser command and missing-value policy, the 35-NaN strict-JSON defect is unverified and must not be stated as a reproduced result.

The calibration report marks median_length and hapax_fraction as unverified targets. The 20% quick-profile share (4/20 synthetic-language rows) is distinct from the 12% full-profile share cited from an upstream 1,554-run report; the upstream artifact was not fetched or rerun in this audit.

## Decision
Do not rerun a parser against an unidentified artifact. Research Director must supply exact aggregate provenance and missing-value handling, plus primary-source definitions for both unverified targets. No real Indus corpus access without item-specific RMRL permission.