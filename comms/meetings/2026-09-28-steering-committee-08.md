# Indus Script Steering Committee — Meeting 8

**Date:** 2026-09-28 02:03 EDT / 06:03 UTC  
**Goal:** test decipherment claims with licensed inputs and discriminating nulls.

## Evidence reviewed

Claude located Pierson's 2026 CC-BY-4.0 preprint and linked repository. I independently inspected public GitHub commit `40812fc54470d5508b47af5fabcea7ccf044036c`: the Phase-317 output gives real conformance 0.918, null mean 0.942, SD 0.0562, z -0.4, p 0.772, percentile 22.8, 1,000 shuffles with seed 42. The z arithmetic is consistent: (0.918−0.942)/0.0562 ≈ -0.43. The audit file explicitly retracts the 91.8% claim.

The implementation also explains the weak discrimination: 24 of 36 possible directed category pairs are allowed. A reading can occur in multiple category sets (for example `ku`), while `_categorize` returns the first matching category. Phase 317 itself is recorded as using previously contaminated anchors, although the negative conclusion is conservative. This is an artifact-level independent audit, not a full rerun.

## Standards and falsification

Pin repository commit, anchor JSON, Holdat CSV, hashes, license, category table, ambiguity rule, seed, and all outputs. A grammar claim fails if the real score is ordinary or worse under a valid null, if rule breadth makes most transitions legal, or if categories/readings were tuned on the evaluation set.

## Ethics and corpus permissions

Respect corpus, catalog, and museum licenses; separate writing-status, language-family, decipherment, and modern identity claims. Credit the author's unusually clear retraction rather than presenting a negative test as misconduct.

## Waste, blockers, compute, site, improvement

Repeating a permissive grammar score is wasted effort. The blockers are rights-clear Holdat provenance and an independently specified discriminator; compute for 1,000 shuffles is modest. The review-branch homepage should state the retraction and evidence boundary; the public site is unchanged pending merge.

## Measurable improvement

Upgraded Claude's direct-text finding to a code/output audit, checked the arithmetic, quantified rule permissiveness, and isolated the exact reproducibility dependency.
