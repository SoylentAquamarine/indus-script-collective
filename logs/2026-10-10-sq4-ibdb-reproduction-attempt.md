# SQ-4 — IBDB reproduction attempted, genuine environment blocker found

**Trigger:** ChatGPT's steering handoff (2026-10-09 22:46 UTC): "Reproduce one documented IBDB profile
with pinned version and hashes while awaiting lawful Mahadevan access; keep the two evidence tracks
separate." This is the explicit "next step" this project's own IBDB log already named as not yet done.

## What's already known / not done yet

Already known: IBDB (`github.com/Arnavthemighty/indus-blind-benchmark`) has a documented reproduction
command, `ibdb reproduce --profile <full|quick>`, with results frozen at git tag `frozen-v1`
(commit `e625f568d728348352442eb57b7591e6730bec53`). Not done: actually running it.

## Design and why it's non-circular

Clone the repository fresh (not relying on a prior session's possibly-stale local copy), checkout the
exact frozen tag the published `reports/results/results.md` was generated from, and run the smaller
`quick` profile (the `full` profile is documented as taking "hours on 4 cores," not a reasonable scope
for one cycle) exactly as the repo's own README specifies, recording the actual outcome whether it
succeeds or not.

## Honesty precommitment

Report the actual result, including a hard failure, rather than silently substituting a weaker check (e.g.
reading the committed results file and calling that "reproduction") and leaving the impression the
original ask was met.

## Result: genuine environment blocker, not attempted-and-failed

Cloned the repository cleanly (tags `data-v1`, `frozen-v1`, `paper-v1` all present and confirmed).
`pyproject.toml` pins `requires-python = ">=3.11,<3.12"` — a **strict, narrow** version requirement. This
session's environment has only Python 3.14.4 available (confirmed: no 3.11.x installed anywhere on the
system, no `pyenv` or equivalent version manager present). The install itself fails cleanly and honestly
at the first step:

```
ERROR: Package 'ibdb' requires a different Python: 3.14.4 not in '<3.12,>=3.11'
```

This is `pip` correctly refusing to install on an incompatible interpreter — not a bug in IBDB, and not
something safely worked around by forcing the install on 3.14 (a project pinned this tightly to one minor
version likely depends on specific stdlib/dependency behavior that changed by 3.14; forcing it would risk
producing non-representative results, which would undermine the whole point of a "pinned, hash-verified"
reproduction).

## Decision

Not resolved this cycle. Installing a second, isolated Python 3.11 runtime (e.g. via an installer) would
be a real system change beyond this bounded research task's own scope to make unilaterally — flagged as
the concrete next step, not attempted here without it being a deliberate, disclosed decision. The two
evidence tracks ChatGPT asked to keep separate remain exactly as before: IBDB's reported numbers stay at
"directly read from the repo's own committed results, not independently re-executed" tier, and the
Mahadevan 1986d/RMRL primary-access blocker is unchanged and still needs the user's own outreach.
