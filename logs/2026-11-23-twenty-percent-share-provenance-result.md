# Result — provenance of the "20% all-seed full-regime share" (ChatGPT #154)

Precommit: `logs/2026-11-23-twenty-percent-share-provenance-precommit.md` (written before the row count).

## 1. Committed quick-profile report (this project's own 2026-10-10 run; 305 runs, seed [0])
Read-only count of section 2.1 (`full`, seed 0) of `data/external-sources/ibdb-reproduction-2026-10-10/calibration_report.md`:
- 27 rows = **20 synthetic-language corpora** (finnish/latin/sanskrit/sumerian/tamil × alphabetic/logographic/logosyllabic/syllabic) + **7 emblem controls** (admin_tags, adversarial, emblem_markov, heraldry, kamon, rao_type1, rao_type2).
- 10/10 passes: latin-syllabic, sanskrit-syllabic, sumerian-alphabetic, sumerian-logographic — all four are languages.
- 4/20 = **20%**, exactly the line-160 "Share of synthetic-language corpora (all seeds) passing every hard target: 20%".
- **Prediction CONFIRMED.** In a quick-profile report "all seeds" = seed 0 only. The 20% is the same four passes as the 4/27 figure, re-divided by the 20-language denominator (controls excluded). It is not an all-seed figure and not a 1,554-run figure.
- Cross-check: all ten section-3 *language* pass rates recompute exactly from the section-2.1 language rows (e.g. sign_inventory 16/20 = 80%, beginners80 9/20 = 45%). **Disclosed residual:** two *control* rates do not: top1_share (section 2.1 gives 4/7 = 57%, section 3 prints 43%) and enders80_signs (3/7 = 43% vs 29%). Possible cause: section 3 recomputes size-dependent statistics on a fresh random subsample. Not resolved. It does not affect the language-only 20%.

## 2. Upstream 1,554-run full-profile source — pinned
- Repo `github.com/Arnavthemighty/indus-blind-benchmark`. `git ls-remote` confirms tag `data-v1` peels to `bbd0e49151853f4a42a7df394a6cbdb3b7b05c85`, the commit pinned in README.source.md. Current `main` is `3f01abf3`, a different commit, so it is not used.
- `reports/results/results.md` @ bbd0e49: SHA-256 `df7751bd0f1fc5602c88d8e8f77960b6f65869c543d049a44122d337241409bc`; line 3: "Profile `full`: 1554 runs, 0 failed … Seeds: [0, 1, 2]".
- `reports/calibration_report.md` @ bbd0e49: SHA-256 `6c83b2a88554637642230219d059f7239b0eda7d85747b0ef09907bdf33b08b1`. Its seed-0 section 2 (lines 30–141) is identical to ours apart from CRLF line endings. Its section 3 (re-check across seeds 0–2), line 160: **"Share of synthetic-language corpora (all seeds) passing every hard target: 12%."** The language rates (83/57/75/83/63/37%) imply 60 language corpora (20 × 3 seeds), so this is about 7/60.
- The upstream files were fetched as two individual public text files to the session scratchpad. They are not committed here (third-party file). Path, commit and hash are recorded above for anyone who wants to re-fetch.

## 3. Correction (append-only; earlier entries unchanged)
The project's notes (config/chatgpt.md entries, ChatGPT #152–#154) call the 20% the "full-regime all-seed share". That label is wrong:
- **20% = quick profile, seed 0 only, 4/20 languages.**
- **12% = the actual all-seed (seeds 0–2) full-profile share, from the upstream 1,554-run calibration report at `data-v1`/bbd0e49.**
This project has not reproduced the 12% by running anything. It is read from the pinned upstream report. The all-seed effect of demoting `median_length`/`hapax_fraction` is still unmeasured, because neither report has per-run rows. Synthetic calibration only; no bearing on whether the real Indus script is linguistic. Task A is still UNRESOLVED.
