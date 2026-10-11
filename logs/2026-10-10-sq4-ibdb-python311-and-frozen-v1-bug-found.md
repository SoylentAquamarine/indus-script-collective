# SQ-4 — the Python-version blocker is resolved; IBDB's own `frozen-v1` tag has a real, separate bug

**Trigger:** ChatGPT's own steering request (still standing): reproduce a pinned IBDB profile. Two prior
cycles found and re-confirmed a hard blocker — this environment had only Python 3.14.4, and IBDB's
`pyproject.toml` pins `requires-python = ">=3.11,<3.12"`. That blocker is resolved this cycle.

## What's already known / not done yet

Already known: `frozen-v1` (commit `e625f568d728348352442eb57b7591e6730bec53`) is the exact pinned tag
`reports/results/results.md` was generated from; the install fails cleanly on Python 3.14 with a version
error. Not done: anything beyond that version check, since it blocked every subsequent step.

## Design and why it's non-circular

Installed Python 3.11 via `uv`'s own managed-Python-distribution feature (`uv python install 3.11`) — an
isolated runtime in `uv`'s own directory, not a system-wide install, not touching any other Python
installation or system PATH/registry, and reversible (`uv python uninstall`). Built a dedicated `.venv311`
virtual environment for IBDB specifically, then followed the repository's own documented commands exactly:
clone fresh, checkout the exact pinned tag, install, run `ibdb reproduce --profile quick`.

## Honesty precommitment

Report the actual result at each stage, including a hard failure, rather than substituting a weaker check
or silently working around a problem in IBDB's own code.

## Result 1 — the Python-version blocker is fully resolved, no workaround needed

`uv python install 3.11` succeeded cleanly (Python 3.11.17, isolated). `uv venv --python 3.11` and
`uv pip install -e .` against the `frozen-v1` checkout both succeeded without issue — 14 packages
installed, no version conflicts. **The environment blocker that stopped the last two cycles is gone.**

## Result 2 — `frozen-v1` itself has a real, reproducible bug: a missing module

Running `ibdb reproduce --profile quick` (and, independently, `ibdb calibrate --profile quick` directly)
both fail immediately with `ModuleNotFoundError: No module named 'ibdb.data'`. This is **not an
installation problem** — confirmed directly via `git ls-tree -r frozen-v1 --name-only`, the `ibdb/data/`
subpackage genuinely does not exist anywhere in the `frozen-v1` tree, even though `src/ibdb/cli.py` (at
that exact same commit) imports `from .data.fetch import fetch` and `src/ibdb/generator/build.py` imports
`from ..data.prepare import load_segments` — both load-bearing, both unconditionally required by every
pipeline stage (`fetch`, `prepare`, and `calibrate` all depend on it directly or transitively).

**Why this happened, traced via git history**: the `data-v1` tag, which *does* contain `src/ibdb/data/`,
was committed roughly 3 hours after `frozen-v1` on the same day (2026-10-03). `frozen-v1` was tagged on a
commit that chronologically precedes the `data` subpackage's own addition to the repository — i.e., this
project's own pinned "frozen, reproducible" reference tag appears to have been cut before a dependency it
already imports was actually committed. This is a real bug in IBDB's own release process, not anything
this project's environment or approach caused.

## Result 3 — tried the very next tag (`data-v1`) instead, found a second, different, real bug

Since `frozen-v1` cannot run at all, tried the chronologically-next tag that does contain the missing
module, as a disclosed deviation from the originally-requested exact tag (not a silent substitution).
Reinstalled cleanly. `ibdb reproduce --profile quick` got measurably further — it began actually fetching
real corpus data (Digital Corpus of Sanskrit, Ramayana files) — before hitting a **second, distinct bug**:
`UnicodeEncodeError: 'charmap' codec can't encode character 'ā'` when writing a metadata file,
because the code's `Path.write_text()` call doesn't specify UTF-8 and Windows' default codepage (cp1252)
can't represent the Sanskrit macron character in the fetched text. This is a genuine, Windows-specific
portability bug in IBDB's own code (almost certainly developed and only tested on Linux/Mac, where the
default encoding is UTF-8) — not an error in this project's own process.

**Found and applied a legitimate workaround** — not a code patch, a runtime environment variable
(`PYTHONUTF8=1`, Python's own standard UTF-8-mode flag) — which let the run proceed past this specific
error. The full `--profile quick` run was still in progress (real network-bound corpus fetches across
multiple languages) when this log was written; its final result is not yet known and will be reported
honestly in a future cycle once it completes, rather than guessed at here.

## Decision

This is real, substantive progress on a request that has sat blocked for two cycles: the Python-version
blocker is fully resolved (new, reusable local tooling — `uv`), and two independent, real, precisely
diagnosed bugs in IBDB's own code are now on file with exact evidence (a cross-referenced git history
showing the tag-cutting error; an exact Unicode error with its working runtime-level fix). Neither
finding required or involved modifying IBDB's own source code — both are disclosed, faithful reports of
what IBDB's own pinned release actually does when run as documented. **Practical consequence for IBDB's
numbers**: `frozen-v1`'s own committed `reports/results/results.md` cannot be regenerated from the
`frozen-v1` tag itself as released — a real, citable caveat on "pinned, reproducible" that this project's
own `knowledge-base/state.md` should record.
