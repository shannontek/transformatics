# Publication guide

*Prepared 9 September 2026 for the first public teaching edition.*

## What this repository is

This is the public teaching edition of Transformatics, published at
<https://shannontek.github.io/transformatics/>. It was prepared from a curated
snapshot of the research working tree. The user authorized publication of the
textbook on its educational merits. No complete-proof condition for the
unforced Navier–Stokes problem is claimed.

The full research history, including the complete research graph, the earlier
status snapshots and the pre-publication operational log, is preserved in the
private [research archive](https://github.com/Hmbown/transformatics-research-archive).
This repository retains the book, the sources cited by its claim register, the
attribution and license notices, and bounded reproduction tools.

## Included scope

The snapshot includes:

- the textbook sources, generated claim register, assets and course metadata;
- every source listed in `textbook/claims.json`, together with the files those
  sources link to;
- the scoped Lean formalizations and their verification receipts;
- the focused experiments and tests associated with the cited claims;
- the artifact receipts cited by the register;
- the license, citation metadata and provenance records.

Excluded from this snapshot (preserved in the archive):

- Git history, the former virtual environment, caches and build output;
- the pre-publication operational log and the earlier status snapshots;
- the full research graph and the route ledger;
- large numerical checkpoints and media rendering sources.

`docs/PUBLICATION_INVENTORY.json` records the included paths with their SHA-256
hashes and the source revision. `tests/test_publication_inventory.py` checks the
inventory against the checkout.

## Workflows

`.github/workflows/textbook-checks.yml` runs on pushes and pull requests. It
installs the pinned Markdown dependency, builds the textbook, runs the
publication inventory test and runs the fluid simulator self-tests. It has
read-only repository permissions.

`.github/workflows/pages.yml` runs on pushes to `main` and on manual dispatch.
Its first job runs the same textbook checks; the build job depends on that job
and the deploy job depends on the build. The site is built and deployed with
the official GitHub Pages actions. The build job receives `pages: read` to
read the configured site metadata; only the deploy job receives `pages: write`
and `id-token: write`, and a concurrency group prevents overlapping
deployments. The site is served under the project path `/transformatics/`;
the builder uses relative links.

No workflow runs a proof job, the archived research suite, Buildkite, an
external service or a DNS change.

## Recorded local validation

[Publication checks](docs/PUBLICATION_CHECKS.md) records the local commands and
their results. Those checks cover the build, the inventory, the simulator
self-tests, browser rendering at the project path and a secret scan. They do
not certify any mathematical result.

## Provenance

- Source repository: `Hmbown/transformatics-research-archive` (private
  archive preserving the full research history).
- Source revision: archival checkpoint `78d07dd4893ac07486d4b2b008af13fe2e25087c`
  on branch `codex/private-archive-checkpoint-20260909` (2026-09-09), whose
  parent is the original working revision
  `db0fffd7fa1f887707c7a868bde9c7b602e022ae`; recorded in
  `docs/PUBLICATION_INVENTORY.json`.
- Public repository: `shannontek/transformatics`.
- License: MIT, copyright ShannonTek; external sources retain their own terms.
- Imported result: OpenAI's forced Navier–Stokes construction is marked
  IMPORTED in the claim register and in `formalization/external_ns/`.
