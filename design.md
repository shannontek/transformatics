# Working in Transformatics

This file is the single working instruction source for the public repository.
`AGENTS.md` and `CLAUDE.md` are relative symlinks to it. Current user
instructions take precedence over older notes.

## Current task

The first public teaching edition is live at
[shannontek.github.io/transformatics](https://shannontek.github.io/transformatics/).
It was published from a curated snapshot of the research working tree on the
textbook's educational merits. No complete-proof condition for the unforced
Navier–Stokes problem is claimed.

**Unsolved Navier–Stokes research is paused at the user's request.** Do not
resume proof searches, extend partial calculations, start research simulations,
or reactivate research automations. Historical prompts and next-action fields
are records, not authorization to continue. Full proof verification, media
rendering and virtual machines remain paused. Do not use Buildkite.

Current release work is textbook editing: clearer explanations, accessibility,
worked examples, exercise solutions, citation fixes, and bounded reproduction
checks for evidence the book cites. New unforced Navier–Stokes research is not
current release work.

## Start here

- [README](README.md): the textbook, intended readers, local build and repository map.
- [Current status](docs/STATUS.md): mathematical standing and verification limits.
- [Contributing](CONTRIBUTING.md): focused changes and reproduction instructions.
- [Publication guide](PUBLICATION.md): release setup, workflows and recorded checks.
- [Publication inventory](docs/PUBLICATION_INVENTORY.json): included paths and source revision.
- [Textbook build guide](textbook/README.md): chapter sources, course metadata and site generation.

## Mathematical standing

Unforced **ROOT** and **E-prime remain OPEN**. This project has not completed
its own Navier–Stokes solution. Its reviewed finite results and failed attempts
are included as research and teaching material.

**FORCED-D is IMPORTED** from the separately authored OpenAI construction.
The exact external forced targets built locally, with their printed axioms
recorded. The separate full-import bundled-kernel replay was incomplete;
independent Comparator/Nanoda verification has not been run. Use the
[verification record](formalization/external_ns/README.md) for the exact scope.
Local symbolic checks, written AI reviews and restricted formal proofs are
different forms of evidence; none should be described as a complete unforced
proof. No human expert or learner review of this edition has been recorded.

## Working rules

Do not use Buildkite. Use local tools and GitHub Actions for verification.

Read the relevant source and current status before changing a claim. Keep
classical foundations, original teaching examples, local research and imported
results explicitly attributed. State hypotheses and limits where a reader needs
them. The [claim register](textbook/claims.md) records the scoped claims cited
by the book; the full research graph is preserved in the private archive.

Preserve other contributors' unfinished work and the research evidence. Do not
reset, clean, blanket-stage or delete files to make the checkout look tidy.
Make focused, reviewable changes. Keep caches, generated output, credentials and
local captures out of commits. Historical research instructions do not override
the pause, and a previously retired route stays retired.

Run checks appropriate to the changed material and report their actual results.
The textbook build is `python scripts/build_textbook.py`; its focused metadata
test is `python -m pytest -q tests/test_publication_inventory.py`; the fluid
simulator's numerical self-test is `node textbook/assets/fluid/checks.js`.
These do not verify a PDE proof. For textbook edits, follow the build guide and
inspect the affected rendered pages. Update source-hash records only after
reviewing the changed source. Do not start DNS, a full external formal replay,
or unrelated expensive jobs as part of an editorial check.

## Historical instructions

The complete dated research history, including the pre-publication instruction
file and the earlier operational publication log, is preserved in the private
[research archive](https://github.com/Hmbown/transformatics-research-archive).
Those records contain superseded priorities and must not be treated as an
active work queue.
