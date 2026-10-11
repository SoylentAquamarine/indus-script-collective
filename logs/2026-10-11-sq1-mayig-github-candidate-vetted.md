# SQ-1 — vetting candidate (4): `mayig/indus-valley-script-corpus`

## Precommitment self-review (written before fetching)

**Known:** SQ-1's first survey (2026-09-23) named four corpus candidates. Three
(Mahadevan/RMRL, CISI, ICIT) have since been formally evaluated and all three currently fail
SQ-1's rights-clear bar for different reasons, leaving the question genuinely blocked pending
either the user's explicit authorization to proceed on ambiguous terms or the user's sign-off to
contact a rightsholder directly. The fourth candidate, an "unvetted GitHub repo
(`mayig/indus-valley-script-corpus`)," was named but never checked — license/provenance
unexamined, not downloaded.

**Not done yet:** this repo's actual license, data provenance, and real completeness have never
been verified.

**Design and why it's non-circular:** use `gh api` to read the repository's metadata, README,
LICENSE file, and one representative sample file — a handful of individual file reads via the
GitHub API, not a git clone of the whole repository and not a bulk download of corpus content,
consistent with this project's standing no-bulk-download-without-authorization rule. The goal is
to answer the specific question SQ-1 already posed (is this candidate rights-clear and how
complete is it), not to adopt or extract the corpus.

**Honesty precommitment:** report whatever the license/provenance check actually shows,
including if it complicates rather than resolves the rights question — don't let an MIT license
badge be read as a clean resolution without checking what it actually covers.

## Findings

**License**: the repository itself carries an MIT license (`gh api .../license` confirms
`"key":"mit"`; the LICENSE file names the copyright holder as "Michael Carlson," 2024, a named
real individual, the repo's maintainer).

**Provenance — the real complication, disclosed rather than smoothed over**: the README states
plainly this is "a (currently WIP) digitization of the Corpus of Indus Seals and Inscriptions
(CISI) by Parpola et al.," using Parpola's own sign-numbering scheme (`P086` etc.) plus the
maintainer's own added feature-vector annotations. **This means the MIT license covers the
maintainer's own code and annotation scheme, but the underlying transcribed sign sequences are
explicitly a re-digitization of CISI** — the exact source this project's own SQ-1 work already
found fails the rights-clear bar (CISI's copyright is held by Academia Scientiarum Fennica and
individual owning institutions, not freely licensed). An individual contributor's own MIT
license on his repository does not, by itself, establish that he held the right to grant that
license over content derived from a separately-copyrighted published corpus. **This candidate
does not resolve SQ-1's rights question — it relocates it one level down**, from "can this
project use CISI directly" to "can this project rely on an unaffiliated volunteer's own claimed
right to redistribute a CISI-derived transcription," which is if anything a weaker basis than a
native open-source dataset, not a stronger one.

**Completeness**: the corpus directory contains 181 files across two subfolders (`m001_m099`,
`m100_m199`) — Mohenjo-daro objects M001 through M199 only, explicitly marked "WIP" in the
README. This is a small fraction of the ~2,900–4,700 objects the other candidates cover (per
SQ-1's own prior surveys), and covers only one site (Mohenjo-daro), not the full multi-site
corpus.

**Data format** (sampled one file, `corpus/m001_m099/m001.json`): a real, structured, machine-
readable JSON schema matching the README's description exactly — per-object arrays of
sides/graphemes, each grapheme carrying a Parpola sign ID and an integer feature vector
(damage/line/uncertainty plus sign-specific features). The format itself is well-designed and
would be usable if the provenance question were resolved.

## Outcome

**Candidate (4) is now vetted, closing SQ-1's own "unvetted" status for it** — but the result is
a disclosed complication, not a resolution: real, named maintainer, genuinely MIT-licensed
repository code, but a WIP, single-site, CISI-derived dataset whose underlying rights status is
inherited from CISI's own already-documented rights ambiguity, not independently clean. This
does not change SQ-1's bottom line — **source selection still requires the user's own
explicit call**, now informed by a complete picture of all four originally-named candidates
rather than three.

## Decision

All four of SQ-1's originally-named candidates have now been formally evaluated. None clears
the rights-clear bar independently. The open paths remain exactly what the prior cycle's log
already named: the user's explicit authorization to proceed on one candidate despite ambiguous
terms, or the user's sign-off to contact a rightsholder directly. Neither is a research-only
decision this project can make unilaterally.
