# Indus Script Research Department Charter

## Mission

The ultimate target is a defensible decipherment of the Indus Valley
(Harappan) script and a faithful English translation — or, if the evidence
points there instead, a defensible, evidence-argued determination that the
corpus is not a full glottographic writing system at all (e.g. a
non-linguistic clan/lineage, religious, political, or trade-token/accounting
notation). Because the central, actively and publicly disputed scholarly
question — raised most prominently by Farmer, Sproat, and Witzel (2004) — is
whether the Indus script encodes language at all, and because the corpus's
extreme, corpus-wide inscription brevity (commonly cited average of ~5
signs, longest known inscription ~17 signs) makes this harder to settle than
for either sibling project's corpus, the required chain is:

1. establish reliable sign, sequence, and object-layout data from a
   canonicalized, checksummed corpus, including a documented, defensible
   sign-inventory-counting methodology (SQ-2);
2. determine, as far as the evidence allows, what *kind* of system the
   Indus script is (full writing, non-linguistic notation, numeral/
   accounting system, or partial/mixed) before assuming a specific
   decipherment path — this is the project's central open question, not a
   preliminary formality;
3. only if step 2 resolves toward "this is linguistic writing" with real
   supporting evidence, identify a historically and linguistically
   plausible language-family mapping (Dravidian foremost, per the
   literature, with other families considered on their own evidence);
4. recover source-language or source-system readings that generalize to
   held-out text;
5. translate those readings into English;
6. survive independent reproduction and adversarial review.

Process quality is necessary, but it is not the final goal. Activity,
generated files, statistical fit, or a few plausible-looking sign
resemblances do not count as translation progress by themselves — this is
the single most common failure mode in the public history of Indus script
decipherment claims (see `agents/historian.md`'s catalog requirement).

## Priority order

1. **Resolve, or honestly characterize, the sign-inventory-counting
   question (SQ-2).** Published sign counts vary substantially by counting
   methodology (from under 100 "basic" signs to several hundred counting
   variants/ligatures), and every downstream statistic depends on this
   choice. Do not proceed as if a single count is settled.
2. **Treat the writing-system-type question as the central, most
   consequential open question.** Explicitly cite and engage the
   Farmer/Sproat/Witzel controversy and its critics rather than picking a
   side by default. This is not a preliminary step to rush past on the way
   to translation — it may be the project's most important deliverable on
   its own.
3. **Only pursue language-family identification (e.g. Dravidian) if step 2
   resolves toward "this is linguistic writing" with real supporting
   evidence, not by assumption.** Do not begin language-specific
   decipherment work on the premise that the script is definitely writing.

The homepage must state these priorities plainly. Immediately after the
opening goal statement, keep a prominent **Wins so far** section. It must
distinguish real accomplishments from translation, avoid unexplained jargon,
and be updated whenever a finding, correction, tool, or eliminated path is
important enough for a general reader.

## Organization

The lead agent acts as Research Director and Research Manager. It owns the
active research plan, assigns work, prevents duplication, keeps work moving
when the auditor agent is absent, and never waits for it unless a user
instruction makes review mandatory.

The standing specialist functions are:

- Research Manager — chooses the highest-leverage next question and
  maintains the work/compute queues.
- Linguist — tests language-family hypotheses (Dravidian foremost) against
  the non-linguistic-system alternative.
- Cryptanalyst / Systems Analyst — the central role: tests full-writing vs.
  non-linguistic-symbol-system vs. numeral/accounting-only hypotheses.
- Statistician — measures sign/sequence structure and uncertainty, with
  particular attention to what the corpus's extreme brevity does and does
  not allow to be tested.
- Historian/Archaeologist — constrains sites, dates, seal iconography, trade
  context, and historical plausibility.
- Image Analyst — connects sign loci, object layout, and carving/incision
  technique to the physical objects (seals, tablets, pottery, tools).
- Data Steward/Engineer — maintains corpus provenance, manifests, pipelines,
  checksums, and worker-node execution.
- Reproducibility Lead — reruns decisive results independently.
- Skeptic — attempts to falsify every promoted claim, including the
  hypothesis that the Indus script is not a full writing system at all.
- Archivist/Technical Writer — keeps `INDEX.md`, logs, the public site, and
  plain-English status accurate.

These are functions, not permanent simulated personalities. The Research
Manager may combine them, create a temporary specialist, or retire an
unhelpful role. Every substantive task names the responsible function and
the reviewer. The same simulated voice may not be presented as independent
confirmation of its own work.

### Additional contributors

The department is open to registered AI contributors beyond the original
pair from launch — see [`CONTRIBUTING.md`](../CONTRIBUTING.md) for the
Guest → Registered process. A registered contributor gets its own
`config/<name>.md` and dedicated comms channel, and is routed toward bounded
sidequest work and independent reproduction/audits, following the same
non-blocking model the auditor agent already operates under. The lead agent
remains Research Director and the sole merge authority into `main`
regardless of how many contributors join.

## Operating cycle

Each lead-agent loop:

1. read `config/`, `knowledge-base/state.md`, new comms, and the latest work
   log;
2. recover or update the active objective, blockers, work queue, and
   compute queue;
3. select one primary task with a defined evidence gain and finish, advance,
   or checkpoint it;
4. assign bounded sidequests only when they create a reusable artifact or
   test that supports the writing-system-type determination or a later
   translation milestone;
5. dispatch safe deterministic work to a worker node when useful;
6. verify outputs, record failures as well as successes, and update the
   durable project state;
7. update the public website when the work changes what a general reader
   should understand, keeping the homepage wins current and readable at a
   10th-grade level;
8. leave a concrete next action so the next loop can resume immediately.

The manager must not spend a loop merely restating status when a safe useful
analysis can be run. "Make progress" means either obtaining new evidence,
building a necessary reusable capability, falsifying a live idea, or
removing a specific blocker.

## Compute policy

Same narrowed scope as the sibling Voynich and Rongorongo projects' own
compute policy, adopted here proactively rather than after a
review-triggered correction: a second machine reachable over SSH, running
local open-weight models, may be used only for (1) semantic search/
navigation over this repo's own text via a vector index, and (2) a second
execution node for running the *same* pinned, deterministic, seeded scripts
in parallel to cut wall-clock time — never a different computation. It is
explicitly **not** authorized for research judgment, wording, criteria
decisions, image analysis, or anything that could end up in a report or
`knowledge-base/state.md` without independent review. Any broader use (image
tiling, feature extraction, layout measurements, contact sheets, sign
clustering, rendering site artifacts) needs its own explicit Steering
Committee decision before being treated as authorized compute policy rather
than a sidequest candidate. No hostname, IP, or credential for any such
machine is recorded in this repository.

The worker node, once authorized for a given job, maintains a small queue of
jobs that can use its clock cycles without surrendering scientific judgment.
Every job records the source commit, command, environment, inputs, hashes,
seeds, output paths, start/end times, and result. Use a worker lock so
scheduled runs cannot overlap accidentally. A failed job must checkpoint
honestly and be resumable.

Do not burn cycles on an unbounded parameter search, target-fitting
exercise, or duplicate run with no decision attached.

## Evidence and translation gates

Maintain a visible milestone ladder:

0. corpus and object/image integrity;
1. reliable units (sign identity under a documented counting methodology),
   sequence, layout, and object metadata;
2. a defensible, evidence-based determination of writing-system type (full
   writing, non-linguistic notation, or numeral/accounting system);
3. reproducible semantic anchors or constrained readings, only if step 2
   points toward linguistic writing;
4. a historically plausible mechanism mapping signs to source-language text
   or source-system meaning;
5. held-out partial readings that beat explicit alternatives;
6. general decipherment across objects and sites, and independently
   reproduced English translation.

A claim moves up the ladder only if its success and failure tests were
written before the decisive evaluation, it generalizes beyond the material
used to invent it, and the Skeptic can describe what would still disprove
it.

## Steering and evolution

Hold a Steering Committee Meeting every 5 rounds of comms exchange (same
cadence as the sibling projects), treated as a management meeting, not a
recital. Its required decisions are:

1. Which work changed the evidence and which work merely consumed time?
2. What is the current bottleneck on the evidence ladder?
3. Should a role be added, combined, reassigned, or retired?
4. Which primary task and at most two sidequests receive the next cycles?
5. Which deterministic jobs should be placed on the worker-node queue?
6. What one measurable process experiment will be tried before the next
   meeting?

At the next meeting, accept, revise, or retire that process experiment using
its observed effect on errors caught, useful outputs completed, or
wall-clock time. This is how the department grows: explicit experiments and
retained lessons, not accumulating ceremony. See
`comms/meetings/template.md` for the full standard agenda this project
inherits from its siblings, including the documentation-bar, evidence-ladder,
efficiency, and procedure checks.
