# Results

Profile `quick`: 305 runs, 0 failed (listed at the end if any). Seeds: [0]. Indus point: 2,906 texts, mean 4.6 signs (Mahadevan 1977, verified).

**Methods were frozen before this run** at git tag `frozen-v1` (commit e625f568d7). No method code changed afterwards.

**Intervals.** Pooled rates and means carry 95% *cluster-bootstrap* intervals: whole source languages or control families are resampled, then corpora within them. Corpora from one source are not independent, so these intervals are wider than Wilson intervals (Wilson bounds are kept in `aggregate.json`). Per-family rates use Wilson intervals. Task A and B decision rules are learned leave-one-source-out.

**How to read Task D.** Solvers are given the true script type (an oracle; Section 6 removes it). The `related` tier gives them a close synthetic relative, which is **not** the Indus situation: treat it as an upper bound. The Indus-relevant tiers are `candidates` and `none`. Default sister distance: sound change 0.3, lexical replacement 0.2. Section 5 varies it.

## 1. Leading result: the `holdout` regime

Under `holdout` only size, length and inventory are calibrated. The frequency and positional statistics that methods 1-3 measure are left free, so methods cannot be rewarded for statistics we injected. `full` tunes them too. `wrong_prior` calibrates to deliberately wrong targets. A conclusion that holds only under `full` is suspect.

| Task | Method | `holdout` | `full` | `wrong_prior` |
|---|---|---|---|---|
| A | Rao 2009 entropy | 0.63 [0.40, 0.85] | 0.77 [0.56, 0.93] | 0.23 [0.10, 0.38] |
| A | Yadav 2010 n-gram | 0.68 [0.46, 0.90] | 0.53 [0.29, 0.75] | 0.40 [0.25, 0.50] |
| A | Positional | 0.57 [0.36, 0.79] | 0.64 [0.46, 0.88] | 0.35 [0.22, 0.45] |
| A | Lee 2010 tree | 0.76 [0.53, 0.97] | 0.72 [0.48, 0.94] | 0.63 [0.38, 0.87] |
| A | Multi-feature LR | 0.59 [0.40, 0.82] | 0.72 [0.49, 0.95] | 0.81 [0.60, 1.00] |
| B | Inventory rule | 0.25 [0.05, 0.45] | 0.25 [0.10, 0.45] | 0.15 [0.00, 0.35] |
| B | Inventory/freq. LR | 0.35 [0.15, 0.60] | 0.55 [0.30, 0.80] | 0.70 [0.50, 0.90] |
| B | Segment length | 0.25 [0.05, 0.50] | 0.25 [0.00, 0.50] | 0.25 [0.05, 0.50] |
| D (related, upper bound) | Frequency-rank baseline | 0.037 [0.02, 0.07] | 0.051 [0.02, 0.09] | 0.072 [0.03, 0.12] |
| D (related, upper bound) | Knight-style EM (revised rule) | 0.237 [0.11, 0.40] | 0.228 [0.10, 0.38] | 0.377 [0.20, 0.56] |
| D (related, upper bound) | Knight-style EM (original rule) | 0.216 [0.09, 0.38] | 0.225 [0.09, 0.39] | 0.364 [0.19, 0.54] |
| D (related, upper bound) | EM cognate-matcher | 0.057 [0.02, 0.10] | 0.061 [0.02, 0.11] | 0.090 [0.04, 0.15] |

Kendall's tau between Task A method rankings under `full` and each other regime:

- `holdout`: tau = 0.11
- `wrong_prior`: tau = -0.11

## 2. Indus point, regime `full` (27 corpora)

### Task A: language vs non-language. **Status: UNRESOLVED**

We label language detection unresolved. Balanced accuracy averages over control families we built ourselves, and a method can score well on average while misclassifying a whole family. The false-positive rates per family below are the result to cite. The adversarial control is tuned to imitate language entropy (Sproat 2014).

| Method | Balanced acc. | Recall on languages | Specificity on controls |
|---|---|---|---|
| Rao 2009 entropy | 0.77 [0.56, 0.93] | 0.70 [0.50, 0.90] | 0.83 [0.50, 1.00] |
| Yadav 2010 n-gram | 0.53 [0.29, 0.75] | 0.55 [0.35, 0.75] | 0.50 [0.17, 0.83] |
| Positional | 0.64 [0.46, 0.88] | 0.95 [0.80, 1.00] | 0.33 [0.00, 0.67] |
| Lee 2010 tree | 0.72 [0.48, 0.94] | 0.95 [0.80, 1.00] | 0.50 [0.17, 0.83] |
| Multi-feature LR | 0.72 [0.49, 0.95] | 0.95 [0.80, 1.00] | 0.50 [0.17, 0.83] |

**False-positive rate per control family** (share classified as linguistic; 0 is correct for every control. Kamon descriptions are Japanese text, so a high rate there is defensible):

| Method | heraldry | admin_tags | emblem_markov | adversarial | rao_type1 | rao_type2 | kamon | languages (recall) |
|---|---|---|---|---|---|---|---|---|
| Rao 2009 entropy | 0.00 [0.00, 0.79] | 0.00 [0.00, 0.79] | 0.00 [0.00, 0.79] | 0.00 [0.00, 0.79] | 1.00 [0.21, 1.00] | 0.00 [0.00, 0.79] | 1.00 [0.21, 1.00] | 0.70 |
| Yadav 2010 n-gram | 0.00 [0.00, 0.79] | 1.00 [0.21, 1.00] | 1.00 [0.21, 1.00] | 0.00 [0.00, 0.79] | 1.00 [0.21, 1.00] | 0.00 [0.00, 0.79] | 1.00 [0.21, 1.00] | 0.55 |
| Positional | 1.00 [0.21, 1.00] | 1.00 [0.21, 1.00] | 1.00 [0.21, 1.00] | 1.00 [0.21, 1.00] | 0.00 [0.00, 0.79] | 0.00 [0.00, 0.79] | 1.00 [0.21, 1.00] | 0.95 |
| Lee 2010 tree | 1.00 [0.21, 1.00] | 0.00 [0.00, 0.79] | 0.00 [0.00, 0.79] | 0.00 [0.00, 0.79] | 1.00 [0.21, 1.00] | 1.00 [0.21, 1.00] | 1.00 [0.21, 1.00] | 0.95 |
| Multi-feature LR | 0.00 [0.00, 0.79] | 0.00 [0.00, 0.79] | 1.00 [0.21, 1.00] | 1.00 [0.21, 1.00] | 1.00 [0.21, 1.00] | 0.00 [0.00, 0.79] | 1.00 [0.21, 1.00] | 0.95 |

### Task B: script type (chance 0.25)

| Method | Accuracy |
|---|---|
| Inventory rule | 0.25 [0.10, 0.45] (n=20, 5 languages) |
| Inventory/freq. LR | 0.55 [0.30, 0.80] (n=20, 5 languages) |
| Segment length | 0.25 [0.00, 0.50] (n=20, 5 languages) |

The inventory rule is defeated by construction: every corpus is calibrated to 400-700 signs.

### Tasks C and D: family and sign values (Indus-relevant tiers first)

Both EM selection rules are reported. The *revised* rule was adopted during development after the *original* rule picked Sumerian for almost every corpus. Readers should compare both.

| Tier | Method | Task C acc. (chance) | Task D mean token acc. | D: corpora ≥50% | D: sign-type acc. |
|---|---|---|---|---|---|
| candidates | Frequency-rank baseline | 0.40 [0.15, 0.65] (0.25) | 0.020 [0.00, 0.05] | 0.00 [0.00, 0.00] | 0.002 |
| candidates | Knight-style EM (revised rule) | 0.50 [0.15, 0.85] (0.25) | 0.151 [0.04, 0.31] | 0.05 [0.00, 0.20] | 0.073 |
| candidates | Knight-style EM (original rule) | 0.20 [0.00, 0.60] (0.25) | 0.023 [0.01, 0.04] | 0.00 [0.00, 0.00] | 0.015 |
| candidates | EM cognate-matcher | 0.25 [0.05, 0.45] (0.25) | 0.028 [0.01, 0.07] | 0.00 [0.00, 0.00] | 0.002 |
| none | Frequency-rank baseline | 0.20 [0.00, 0.50] (0.30) | 0.007 [0.00, 0.02] | 0.00 [0.00, 0.00] | 0.001 |
| none | Knight-style EM (revised rule) | 0.10 [0.00, 0.35] (0.30) | 0.042 [0.01, 0.08] | 0.00 [0.00, 0.00] | 0.021 |
| none | Knight-style EM (original rule) | 0.00 [0.00, 0.00] (0.30) | 0.021 [0.00, 0.04] | 0.00 [0.00, 0.00] | 0.014 |
| none | EM cognate-matcher | 0.05 [0.00, 0.20] (0.30) | 0.016 [0.00, 0.03] | 0.00 [0.00, 0.00] | 0.002 |
| related (upper bound) | Frequency-rank baseline | n/a | 0.051 [0.02, 0.09] | 0.00 [0.00, 0.00] | 0.004 |
| related (upper bound) | Knight-style EM (revised rule) | n/a | 0.228 [0.10, 0.38] | 0.15 [0.00, 0.35] | 0.112 |
| related (upper bound) | Knight-style EM (original rule) | n/a | 0.225 [0.09, 0.39] | 0.20 [0.00, 0.45] | 0.131 |
| related (upper bound) | EM cognate-matcher | n/a | 0.061 [0.02, 0.11] | 0.00 [0.00, 0.00] | 0.005 |

Segmentation boundary F1 (branching entropy vs true word starts): 0.46

## 3. Robustness: only corpora that meet every calibration target

At the Indus point, 4 of 27 corpora meet every hard target (4 of them languages). Rules are re-learned inside this subset.

| Task | Method | All corpora | Passing only |
|---|---|---|---|
| A | Rao 2009 entropy | - | - |
| A | Yadav 2010 n-gram | - | - |
| A | Positional | - | - |
| A | Lee 2010 tree | - | - |
| A | Multi-feature LR | - | - |
| B | Inventory rule | 0.25 [0.10, 0.45] | 0.00 [0.00, 0.00] |
| B | Inventory/freq. LR | 0.55 [0.30, 0.80] | 0.00 [0.00, 0.00] |
| B | Segment length | 0.25 [0.00, 0.50] | 0.50 [0.00, 1.00] |
| D (candidates) | Frequency-rank baseline | 0.020 | 0.015 |
| D (candidates) | Knight-style EM (revised rule) | 0.151 | 0.148 |
| D (candidates) | Knight-style EM (original rule) | 0.023 | 0.027 |
| D (candidates) | EM cognate-matcher | 0.028 | 0.022 |
| D (none) | Frequency-rank baseline | 0.007 | 0.007 |
| D (none) | Knight-style EM (revised rule) | 0.042 | 0.024 |
| D (none) | Knight-style EM (original rule) | 0.021 | 0.034 |
| D (none) | EM cognate-matcher | 0.016 | 0.022 |
| D (related) | Frequency-rank baseline | 0.051 | 0.035 |
| D (related) | Knight-style EM (revised rule) | 0.228 | 0.163 |
| D (related) | Knight-style EM (original rule) | 0.225 | 0.205 |
| D (related) | EM cognate-matcher | 0.061 | 0.085 |

## 4. Task D vs sister-language distance (Indus point)

| Sound change / lexical repl. | Tier | Method | Mean token acc. | Task C acc. |
|---|---|---|---|---|
| 0.10 / 0.05 | related | Frequency-rank baseline | 0.050 [0.02, 0.09] | n/a |
| 0.10 / 0.05 | related | Knight-style EM (revised rule) | 0.275 [0.14, 0.43] | n/a |
| 0.10 / 0.05 | related | Knight-style EM (original rule) | 0.249 [0.12, 0.41] | n/a |
| 0.10 / 0.05 | related | EM cognate-matcher | 0.058 [0.02, 0.10] | n/a |
| 0.10 / 0.05 | candidates | Frequency-rank baseline | 0.023 [0.00, 0.06] | 0.45 [0.15, 0.75] |
| 0.10 / 0.05 | candidates | Knight-style EM (revised rule) | 0.165 [0.05, 0.31] | 0.50 [0.15, 0.85] |
| 0.10 / 0.05 | candidates | Knight-style EM (original rule) | 0.032 [0.01, 0.07] | 0.20 [0.00, 0.60] |
| 0.10 / 0.05 | candidates | EM cognate-matcher | 0.028 [0.01, 0.07] | 0.25 [0.10, 0.45] |
| 0.30 / 0.20 | related | Frequency-rank baseline | 0.051 [0.02, 0.08] | n/a |
| 0.30 / 0.20 | related | Knight-style EM (revised rule) | 0.228 [0.10, 0.38] | n/a |
| 0.30 / 0.20 | related | Knight-style EM (original rule) | 0.225 [0.10, 0.38] | n/a |
| 0.30 / 0.20 | related | EM cognate-matcher | 0.061 [0.02, 0.10] | n/a |
| 0.30 / 0.20 | candidates | Frequency-rank baseline | 0.020 [0.00, 0.05] | 0.40 [0.15, 0.65] |
| 0.30 / 0.20 | candidates | Knight-style EM (revised rule) | 0.151 [0.04, 0.30] | 0.50 [0.15, 0.85] |
| 0.30 / 0.20 | candidates | Knight-style EM (original rule) | 0.023 [0.00, 0.04] | 0.20 [0.00, 0.60] |
| 0.30 / 0.20 | candidates | EM cognate-matcher | 0.028 [0.01, 0.07] | 0.25 [0.10, 0.45] |
| 0.50 / 0.35 | related | Frequency-rank baseline | 0.055 [0.02, 0.09] | n/a |
| 0.50 / 0.35 | related | Knight-style EM (revised rule) | 0.247 [0.12, 0.38] | n/a |
| 0.50 / 0.35 | related | Knight-style EM (original rule) | 0.229 [0.10, 0.37] | n/a |
| 0.50 / 0.35 | related | EM cognate-matcher | 0.066 [0.02, 0.12] | n/a |
| 0.50 / 0.35 | candidates | Frequency-rank baseline | 0.020 [0.00, 0.05] | 0.40 [0.15, 0.65] |
| 0.50 / 0.35 | candidates | Knight-style EM (revised rule) | 0.151 [0.04, 0.30] | 0.45 [0.10, 0.80] |
| 0.50 / 0.35 | candidates | Knight-style EM (original rule) | 0.026 [0.01, 0.05] | 0.20 [0.00, 0.60] |
| 0.50 / 0.35 | candidates | EM cognate-matcher | 0.025 [0.01, 0.06] | 0.20 [0.05, 0.40] |
| 0.70 / 0.50 | related | Frequency-rank baseline | 0.060 [0.02, 0.10] | n/a |
| 0.70 / 0.50 | related | Knight-style EM (revised rule) | 0.246 [0.12, 0.39] | n/a |
| 0.70 / 0.50 | related | Knight-style EM (original rule) | 0.224 [0.10, 0.37] | n/a |
| 0.70 / 0.50 | related | EM cognate-matcher | 0.066 [0.03, 0.11] | n/a |
| 0.70 / 0.50 | candidates | Frequency-rank baseline | 0.020 [0.00, 0.04] | 0.40 [0.15, 0.65] |
| 0.70 / 0.50 | candidates | Knight-style EM (revised rule) | 0.147 [0.04, 0.29] | 0.45 [0.10, 0.80] |
| 0.70 / 0.50 | candidates | Knight-style EM (original rule) | 0.028 [0.00, 0.06] | 0.20 [0.00, 0.60] |
| 0.70 / 0.50 | candidates | EM cognate-matcher | 0.025 [0.01, 0.06] | 0.20 [0.05, 0.40] |

## 5. Removing the script-type oracle (Indus point)

The solver's unit level comes from the leave-one-source-out prediction of `script_type_lr`, which is correct for 55% of these corpora.

| Tier | Method | Mean token acc. (oracle script type) | Mean token acc. (predicted) | Task C (oracle → predicted) |
|---|---|---|---|---|
| candidates | Frequency-rank baseline | 0.020 [0.00, 0.05] | 0.018 [0.00, 0.05] | 0.40 → 0.30 |
| candidates | Knight-style EM (revised rule) | 0.151 [0.04, 0.30] | 0.097 [0.01, 0.23] | 0.50 → 0.45 |
| candidates | Knight-style EM (original rule) | 0.023 [0.00, 0.04] | 0.017 [0.00, 0.03] | 0.20 → 0.20 |
| candidates | EM cognate-matcher | 0.028 [0.01, 0.07] | 0.013 [0.00, 0.02] | 0.25 → 0.15 |
| none | Frequency-rank baseline | 0.007 [0.00, 0.01] | 0.007 [0.00, 0.02] | 0.20 → 0.15 |
| none | Knight-style EM (revised rule) | 0.042 [0.02, 0.08] | 0.036 [0.01, 0.08] | 0.10 → 0.15 |
| none | Knight-style EM (original rule) | 0.021 [0.00, 0.04] | 0.015 [0.00, 0.03] | 0.00 → 0.00 |
| none | EM cognate-matcher | 0.016 [0.00, 0.03] | 0.011 [0.00, 0.02] | 0.05 → 0.05 |
| related | Frequency-rank baseline | 0.051 [0.02, 0.09] | 0.035 [0.01, 0.06] | n/a |
| related | Knight-style EM (revised rule) | 0.228 [0.10, 0.38] | 0.188 [0.06, 0.32] | n/a |
| related | Knight-style EM (original rule) | 0.225 [0.09, 0.38] | 0.183 [0.06, 0.32] | n/a |
| related | EM cognate-matcher | 0.061 [0.02, 0.10] | 0.038 [0.01, 0.07] | n/a |

## 6. Size sweep (mean length 4.6)

| texts | A best bal. acc. | B best acc. | C best acc. (candidates) | D best (candidates) | D best (none) | D best (related, upper bound) |
|---|---|---|---|---|---|---|
| 500 | 0.82 (Rao 2009 entropy) | 0.45 (Inventory/freq. LR) | 0.40 (Frequency-rank baseline) | 0.078 (Knight-style EM (revised rule)) | 0.026 (Knight-style EM (revised rule)) | 0.180 (Knight-style EM (revised rule)) |
| 2906 | 0.77 (Rao 2009 entropy) | 0.55 (Inventory/freq. LR) | 0.50 (Knight-style EM (revised rule)) | 0.151 (Knight-style EM (revised rule)) | 0.042 (Knight-style EM (revised rule)) | 0.228 (Knight-style EM (revised rule)) |
| 20000 | 0.78 (Lee 2010 tree) | 0.35 (Inventory/freq. LR) | 0.50 (Knight-style EM (revised rule)) | 0.169 (Knight-style EM (revised rule)) | 0.035 (Knight-style EM (revised rule)) | 0.230 (Knight-style EM (revised rule)) |

Same sweep, only corpora meeting every target:

| texts | A best bal. acc. | B best acc. | C best acc. (candidates) | D best (candidates) | D best (none) | D best (related, upper bound) |
|---|---|---|---|---|---|---|
| 2906 | nan (-) | 0.50 (Segment length) | 0.75 (Frequency-rank baseline) | 0.148 (Knight-style EM (revised rule)) | 0.034 (Knight-style EM (original rule)) | 0.205 (Knight-style EM (original rule)) |

## 7. Length sweep (2,906 texts)

| mean signs/text | A best bal. acc. | B best acc. | C best acc. (candidates) | D best (candidates) | D best (none) | D best (related, upper bound) |
|---|---|---|---|---|---|---|
| 3.0 | 0.84 (Rao 2009 entropy) | 0.40 (Inventory/freq. LR) | 0.25 (Frequency-rank baseline) | 0.074 (Knight-style EM (revised rule)) | 0.026 (Knight-style EM (revised rule)) | 0.149 (Knight-style EM (revised rule)) |
| 4.6 | 0.77 (Rao 2009 entropy) | 0.55 (Inventory/freq. LR) | 0.50 (Knight-style EM (revised rule)) | 0.151 (Knight-style EM (revised rule)) | 0.042 (Knight-style EM (revised rule)) | 0.228 (Knight-style EM (revised rule)) |
| 10.0 | 0.73 (Lee 2010 tree) | 0.40 (Inventory/freq. LR) | 0.65 (Knight-style EM (original rule)) | 0.361 (Knight-style EM (original rule)) | 0.054 (Knight-style EM (revised rule)) | 0.431 (Knight-style EM (revised rule)) |

## 8. Smallest corpus where a method beats chance (lower 95% cluster bound above chance)

Size sweep at mean length 4.6. `never` = not reached by 50,000 texts.

| Task | Method | Smallest size | Smallest size for a strong result |
|---|---|---|---|
| A | Rao 2009 entropy | 500 | never (bal. acc. ≥ 0.9) |
| A | Yadav 2010 n-gram | never | never (bal. acc. ≥ 0.9) |
| A | Positional | never | never (bal. acc. ≥ 0.9) |
| A | Lee 2010 tree | 20000 | never (bal. acc. ≥ 0.9) |
| A | Multi-feature LR | never | never (bal. acc. ≥ 0.9) |
| B | Inventory rule | never | never (acc. ≥ 0.5) |
| B | Inventory/freq. LR | 2906 | 2906 (acc. ≥ 0.5) |
| B | Segment length | never | never (acc. ≥ 0.5) |
| C (candidates) | Frequency-rank baseline | never | never (acc. ≥ 0.5) |
| C (candidates) | Knight-style EM (revised rule) | never | 2906 (acc. ≥ 0.5) |
| C (candidates) | Knight-style EM (original rule) | never | never (acc. ≥ 0.5) |
| C (candidates) | EM cognate-matcher | never | never (acc. ≥ 0.5) |
| C (none) | Frequency-rank baseline | never | never (acc. ≥ 0.5) |
| C (none) | Knight-style EM (revised rule) | never | never (acc. ≥ 0.5) |
| C (none) | Knight-style EM (original rule) | never | never (acc. ≥ 0.5) |
| C (none) | EM cognate-matcher | never | never (acc. ≥ 0.5) |
| D (candidates) | Knight-style EM (revised rule) | never (vs baseline) | never (half of corpora ≥50% tokens) |
| D (candidates) | Knight-style EM (original rule) | never (vs baseline) | never (half of corpora ≥50% tokens) |
| D (candidates) | EM cognate-matcher | never (vs baseline) | never (half of corpora ≥50% tokens) |
| D (none) | Knight-style EM (revised rule) | never (vs baseline) | never (half of corpora ≥50% tokens) |
| D (none) | Knight-style EM (original rule) | never (vs baseline) | never (half of corpora ≥50% tokens) |
| D (none) | EM cognate-matcher | never (vs baseline) | never (half of corpora ≥50% tokens) |
| D (related, upper bound) | Knight-style EM (revised rule) | 2906 (vs baseline) | never (half of corpora ≥50% tokens) |
| D (related, upper bound) | Knight-style EM (original rule) | 2906 (vs baseline) | never (half of corpora ≥50% tokens) |
| D (related, upper bound) | EM cognate-matcher | never (vs baseline) | never (half of corpora ≥50% tokens) |

## 9. Feasibility region at the Indus point (16 random writing-system scenarios)

Each scenario draws allograph, homophony and polyvalence rates, determinatives, word dividers and direction at random around a calibrated script. Language and script type are also random. Scenarios are perturbations, not re-calibrated: mean share of targets still met = 74%.

| Task | Method | Share of scenarios where the method succeeds |
|---|---|---|
| A (languages called languages) | Rao 2009 entropy | 0.94 [0.73, 1.00] |
| A (languages called languages) | Yadav 2010 n-gram | 0.75 [0.46, 1.00] |
| A (languages called languages) | Positional | 1.00 [1.00, 1.00] |
| A (languages called languages) | Lee 2010 tree | 0.81 [0.50, 1.00] |
| A (languages called languages) | Multi-feature LR | 0.88 [0.64, 1.00] |
| B | Inventory rule | 0.31 [0.06, 0.58] |
| B | Inventory/freq. LR | 0.44 [0.17, 0.76] |
| B | Segment length | 0.19 [0.00, 0.56] |
| C (candidates) | Frequency-rank baseline | 0.25 [0.05, 0.62] |
| C (candidates) | Knight-style EM (revised rule) | 0.31 [0.06, 0.65] |
| C (candidates) | Knight-style EM (original rule) | 0.19 [0.00, 0.64] |
| C (candidates) | EM cognate-matcher | 0.12 [0.00, 0.36] |
| C (none) | Frequency-rank baseline | 0.06 [0.00, 0.30] |
| C (none) | Knight-style EM (revised rule) | 0.06 [0.00, 0.27] |
| C (none) | Knight-style EM (original rule) | 0.00 [0.00, 0.00] |
| C (none) | EM cognate-matcher | 0.06 [0.00, 0.27] |
| D ≥50% tokens (candidates) | Frequency-rank baseline | 0.00 [0.00, 0.00] |
| D ≥50% tokens (candidates) | Knight-style EM (revised rule) | 0.00 [0.00, 0.00] |
| D ≥50% tokens (candidates) | Knight-style EM (original rule) | 0.00 [0.00, 0.00] |
| D ≥50% tokens (candidates) | EM cognate-matcher | 0.00 [0.00, 0.00] |
| D ≥50% tokens (none) | Frequency-rank baseline | 0.00 [0.00, 0.00] |
| D ≥50% tokens (none) | Knight-style EM (revised rule) | 0.00 [0.00, 0.00] |
| D ≥50% tokens (none) | Knight-style EM (original rule) | 0.00 [0.00, 0.00] |
| D ≥50% tokens (none) | EM cognate-matcher | 0.00 [0.00, 0.00] |
| D ≥50% tokens (related, upper bound) | Frequency-rank baseline | 0.00 [0.00, 0.00] |
| D ≥50% tokens (related, upper bound) | Knight-style EM (revised rule) | 0.06 [0.00, 0.27] |
| D ≥50% tokens (related, upper bound) | Knight-style EM (original rule) | 0.06 [0.00, 0.27] |
| D ≥50% tokens (related, upper bound) | EM cognate-matcher | 0.00 [0.00, 0.00] |
