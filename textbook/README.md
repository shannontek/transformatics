# Transformatics textbook

The course begins with five mathematical lessons: finite transformations,
flow generators, transfer systems, composition errors, and scaling. Fluid mechanics and a
working 3D numerical laboratory follow. Research applications and evidence
appendices are a separate part of the reading order.

For readers starting with high-school calculus, the optional
[calculus bridge](chapters/calculus-bridge.md) develops the next prerequisites
through worked examples. The [mathematical reading map](chapters/reader-map.md)
offers a short entry problem and direct routes for experienced readers.
Both are linked from the preface and the course metadata. They are reference
chapters, so the main sequence still starts with finite transformations.

The site uses a plain early-web layout: ordinary text, blue links, native
controls and a collapsible chapter list. The finite-transformation lesson
includes an exact 2D shear/translation animation; the fluid lab retains its
3D numerical animation. Both start paused and include a textual explanation.
The visual direction is recorded in [DESIGN.md](DESIGN.md).

Human chapters live in `chapters/`. `claims.json` is the editable, machine-readable
claim register. `book.json` controls reading order. `course-outline.json` adds prerequisites and objectives. The generated `course.json` includes section and solution anchors and source hashes; `all-chapters.md` and `llms.txt` provide complete text and agent entry points. Search uses a local generated index. The Python builder emits a
static website in ignored `_site/`, snapshots referenced research notes and their
available companion pins, and validates source links, site links and claim dependencies.
Chapter Markdown uses repository-relative links, so it also reads directly on GitHub.
The builder translates those links for the site and its downloadable edition.
Local browser-review screenshots and reports stay in ignored `review/`.

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r textbook/requirements.txt
python scripts/build_textbook.py
python -m http.server 8000 --directory textbook/_site
```

Use the repository root as your working directory for these commands.
Reuse an existing suitable virtual environment if one is already active.
Only Markdown is a build dependency. MathJax 3.2.2 loads from a pinned CDN;
without network the original TeX notation remains present. No analytics,
external fonts, account service, or framework runtime is used.

The fluid laboratory uses browser modules and a worker, so it must be served
over HTTP. Its Fourier solver, diagnostics, tracer method and check command
are documented in [the lab notes](assets/fluid/README.md). The simulator
is a finite numerical approximation, with no claimed guarantee from a
completed general NS proof.

The [Textbook checks workflow](../.github/workflows/textbook-checks.yml)
builds the reader, runs the publication inventory test and runs the fluid
simulator self-tests on pushes and pull requests. It has read-only repository
permissions and performs no deployment. The
[Pages workflow](../.github/workflows/pages.yml) builds and deploys the site to
`https://shannontek.github.io/transformatics/` on pushes to `main` and on manual
dispatch. Its deploy job depends on the same textbook checks. It uses the
official GitHub Pages actions with least permissions and a concurrency group;
no proof job, external service or DNS change is involved.

## Updating a result

1. Finalize the source proof and canonical repository status first.
2. Edit the scoped claim, boundary, dependencies and evidence paths in `claims.json`.
   Refresh its readable GitHub view with `python scripts/build_textbook.py --update-claim-index`.
3. Update the corresponding teaching chapter and exercises.
4. Rebuild and review the new statement against its source.
5. Refresh the [publication inventory](../docs/PUBLICATION_INVENTORY.json) with
   `python scripts/update_publication_inventory.py` if the included file set changed.

Dependencies in this editorial index are scoped mathematical/prior-construction
inputs, not an assertion that the indexed results suffice for ROOT. The book records partial local Lean-checked cone algebra. The external OpenAI forced result is marked IMPORTED and linked to its inspected source record; the exact external Navier–Stokes target built locally. Its stronger imported-closure replay remained incomplete, and independent Comparator verification has not been run. See [the verification receipt](../formalization/external_ns/README.md).

## Sharing a mathematical excerpt

Share the chapter Markdown together with its linked source notes and the
versioned `claims.json`. The editable claim file contains a pinned primary-source
hash snapshot; the generated site expands this to the complete linked source
snapshot. The two scopes are labelled. `course.json` records both original chapter
hashes and hashes of downloadable chapters, whose relative links are adjusted.
A hash identifies bytes; it is not a mathematical proof or a statement of review.

The register's provenance, proof status, review and formal coverage are separate
fields. A structured contract is supplied for selected key claims; for other
claims, `contract: null` explicitly leaves the full prose statement authoritative.
Do not interpret an absent structured field as an absent hypothesis.

## Claim register

[The readable register](claims.md) and [the JSON register](claims.json) describe
the same scoped claims. The readable file is generated from the JSON source;
the builder rejects a stale copy. The reader-facing register shows only
`verification_label`. The legacy research-graph `status` (`PROVED`, `OPEN`, …)
stays in `claims.json` for continuity and is not a reader-facing certification.
Provenance, proof status, review and formal coverage remain separate JSON fields,
and formal-check receipts name the statement, checker, axioms and outcome. This
index is separate from the complete repository research graph, which is preserved
in the private archive, and it does not certify the proofs it records. A future
human reviewer can use the [reviewer guide](REVIEW_GUIDE.md); no human review
has been arranged, commissioned or received.
