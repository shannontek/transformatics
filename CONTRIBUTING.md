# Contributing

Transformatics is an open textbook and research project on finite
transformations, evolution and transfer between models. Contributions include
clearer explanations, worked examples, exercise solutions, accessibility fixes,
scholarly references, precisely scoped lemmas and corrections.

For a textbook correction, name the chapter and section, state the difficulty,
and propose the smallest clear repair. Include a worked counterexample for a
false statement. Preserve the distinction between classical material, original
teaching examples, local research and imported external results. Credit model
assistance with the actual known model label; do not infer a model from an editor.

Run the textbook builder and review the changed page at desktop and phone width.
Check equations, keyboard operation, print, links and solution disclosures.
`textbook/course-outline.json` records prerequisites and objectives; the builder
derives section and solution anchors from the chapter sources. Changes in
notation should also update the glossary and cumulative exercises.

Unforced ROOT and E-prime remain open. FORCED-D is an imported external result
with its own source and verification record.

## Read the current standing

Start with [the canonical status](docs/STATUS.md),
[the claim register](textbook/claims.md), and
[the working instructions](design.md). Dated documents record the program's
history; later corrections govern their interpretation. In particular, the
GSO averaged-noncollapse route is retired by the
[cap-vacuity audit](docs/NSE_QGSO_CAP_VACUITY_2026_09_06.md).

Keep each mathematical claim explicit about its domain, hypotheses,
regularity, constants, and conclusion. Distinguish exact algebra, analytic
proof, interval certification, floating-point evidence, and conjecture.
A static field or scalar ledger does not establish an evolving NS solution.

## Set up and check a change

Python 3.11 is the CI reference version. From the repository root:

```bash
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install -r textbook/requirements.txt
python scripts/build_textbook.py
python -m pytest -q tests/test_publication_inventory.py
node textbook/assets/fluid/checks.js
```

Run the focused tests for the files and claims you change. Include the exact
command and result in your contribution. Automatic CI runs the textbook checks
on pushes and pull requests: the builder, the publication inventory test and
the simulator self-tests. A green check covers those items only; it does not
certify the external Navier–Stokes construction or any other mathematical
result. The complete historical Python suite is not part of public CI; the
original research archive retains it.

If you change the set of included files, refresh the publication inventory with
`python scripts/update_publication_inventory.py` and include the result in your
change. The inventory test compares the committed inventory against the
checkout.

Unsolved Navier–Stokes research is currently paused. Teaching corrections and
bounded reproduction checks belong to the current release work. Historical
experiment notes and next-attempt fields do not authorize new research,
DNS or accelerator jobs.

## Preserve reproducibility

For a new result, link its note, implementation, focused tests, and receipt.
Record the input parameters, resolution, seed when relevant, interpreter,
dependency versions, and the command that produced the receipt. Explain
which checks are exact and which are numerical. Keep expensive experiment
outputs separate from tests that merely read a frozen receipt.

Update the claim register and the publication inventory when a claim's standing
changes. Preserve failed attempts and retractions with clear supersession links.
Do not silently replace a historical receipt or remove an artifact that a test
or proof note uses.

Use repository-relative paths in new runnable code and documentation. Keep
virtual environments, local credentials, caches, logs, and build output out
of commits. Stage only the files belonging to your contribution, especially
when the checkout contains unfinished research from another session.

## Describe the result for review

A contribution should explain the problem, the resulting change, the
evidence, and the remaining gap. For mathematical changes, state whether
the result is new, an application of a known theorem, or a correction.
For generated material, include its source and build instructions.

The repository carries the [MIT license](LICENSE), copyright ShannonTek.
Preserve third-party attribution and verify redistribution rights before
adding external material.
