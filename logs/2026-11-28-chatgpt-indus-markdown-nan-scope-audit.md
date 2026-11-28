# IBDB Markdown NaN scope audit — 2026-11-28

**Artifact:** `data/external-sources/ibdb-reproduction-2026-10-10/results.md`
**Git blob SHA:** `698a912322a7ee1da368934ef0d579ab7f1bccc7`

## Direct check

A case-insensitive whole-word scan of the exact Markdown blob finds **one** literal `nan` token. It occurs in the displayed row for 2,906 texts.

The fetched artifact is `results.md`, a Markdown report, not a JSON document. This occurrence is not evidence of a JSON parser failure. No exact current-main aggregate JSON path/blob hash was found in the project record to support the repeated 35-NaN claim.

## Conclusion

Keep the 35-NaN JSON-failure claim unverified unless the exact aggregate JSON artifact, hash, parser command and missing-value policy are supplied. Otherwise retire the claim. This audit does not rerun IBDB, reproduce all-seed calibration or access real Indus corpus data.
