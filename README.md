# Transformatics

**Finite change, continuous evolution, and the passage between mathematical models.**

An open textbook about a practical mathematical question: **when we simplify a
description of something that changes, what can we still predict?**

[Read the book](https://shannontek.github.io/transformatics/) or start with
[the preface](textbook/chapters/index.md).

Start with a number whose square is 4. If the number increases by one,
its square might become 9 or 1. Knowing the old square has lost information
needed to predict the new one. More accurate arithmetic will not recover it.
That small example leads to questions about measurements, differential
equations, numerical error, fluid motion, and control.

*Transformatics* is the name of this book's organizing viewpoint. Its foundations
are established mathematics: finite differences, pullbacks and Koopman operators,
dynamical systems, and stability estimates. The contribution offered here is a
connected course of explanations, examples and carefully scoped research case
studies. The [literature guide](textbook/chapters/references.md) identifies the
subjects in their conventional terms.

The project was initiated and directed by Hunter Bown and developed with AI
assistance, especially DeepSeek and GLM according to Hunter's account. The
[credits](textbook/chapters/credits.md) describe that collaboration and its
limits. Mathematical claims are linked to their arguments and source records.

## Read the textbook

Start with [the preface](textbook/chapters/index.md) or choose a route below.
High-school calculus is enough to begin. An optional
[calculus bridge](textbook/chapters/calculus-bridge.md) develops the vectors,
partial derivatives, norms and Fourier notation used next. The research
chapters identify the additional analysis their complete source proofs require.

Readers already comfortable with dynamics or PDEs can use the
[mathematical reading map](textbook/chapters/reader-map.md) to find the central
statements, test their hypotheses, and follow their sources. The course includes
proofs, worked examples, exercises with solutions, two cumulative assessments,
a glossary, and academic reading guides.

- **Foundations:** finite transformations, generators, exact transfer,
  composition of errors, and scaling.
- **Fluid mechanics:** the equation, a 3D numerical laboratory, frequency
  creation, pressure, concentration and finite amplification.
- **Construction and limits:** residuals, smooth forcing, repeated stages,
  and a carefully attributed reading of the published Navier–Stokes result.
- **Information and control:** observation, reliable action, finite communication
  requirements, and a worked transition-feasibility calculation.
- **Study tools:** local search, direct links to solutions, downloadable
  Markdown, and a course index containing prerequisites and learning objectives.

The teaching takes inspiration from Leonard Bernstein: encounter an example,
make a prediction, calculate, then return to the example with a deeper question.
An exact 2D map animation and a 3D fluid laboratory support that approach.

Choose a starting point:

| Your interest | Start here |
| --- | --- |
| I know single-variable calculus | [Finite changes](textbook/chapters/transformations.md), with the [calculus bridge](textbook/chapters/calculus-bridge.md) as needed |
| I want one satisfying short argument | [What a measurement cannot predict](textbook/chapters/reader-map.md#a-small-problem-with-two-ways-forward) |
| I know analysis and want the mathematical substance | [The reading map and standard terminology](textbook/chapters/reader-map.md#the-mathematics-in-familiar-terms) |
| I want to understand the fluid result | [The equation and an exact shear](textbook/chapters/equation.md), then [the external construction](textbook/chapters/published-proof.md) |
| I want an application without PDE prerequisites | [Information and reliable action](textbook/chapters/information-action.md) after the foundation chapters |
| I want to check a claim or its source | [Readable claim register](textbook/claims.md), [claim data](textbook/claims.json), [current status](docs/STATUS.md) |

Chapter links work directly on GitHub. The [built edition](https://shannontek.github.io/transformatics/)
adds typeset equations, search, animations and a complete reading index.
AI review is not external expert acceptance. The claim register's review entries
are process records, separate from its proof statements and formal checks.

## Build and read locally

From the repository root, using Python 3.11 or later in a virtual environment:

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r textbook/requirements.txt
python scripts/build_textbook.py
python -m http.server 8000 --directory textbook/_site
```

The generated site is in `textbook/_site/`. Its `course.json` indexes chapter
sources, prerequisites, objectives, section anchors and solutions; `claims.json`
records research claims and source hashes. `all-chapters.md` provides one complete
text source, and `llms.txt` points automated readers to these same materials.
The book is readable without JavaScript; search and animations require it.
See [the build guide](textbook/README.md) for the remaining details.

## The Navier–Stokes case study

This project did not complete its own Navier–Stokes solution. It developed
restricted finite theorems, computational diagnostics and corrected failed
routes. These form useful teaching examples with explicit boundaries.

OpenAI's 8 September 2026 [forced breakdown paper](https://openai.com/index/navier-stokes-solution/)
and accompanying formalization are separately authored sources. The
[bridge chapter](textbook/chapters/published-proof.md) explains their relation
to our calculations. FORCED-D is recorded as **IMPORTED**; unforced ROOT and
E-prime remain **OPEN**. Our [source assessment](docs/NSE_OPENAI_RESULT_BRIDGE_2026_09_08.md)
states what was read and checked. The exact forced Navier–Stokes target
has [built successfully here](formalization/external_ns/README.md), with its
axiom output recorded; independent Comparator verification remains separate.
The browser simulator remains a finite numerical approximation.

Further unforced-proof research is currently **paused**. This edition focuses
on teaching the reviewed material clearly and preserving its open questions.
The full research history, including the complete research graph and the
pre-publication operational log, is preserved in the private
[research archive](https://github.com/Hmbown/transformatics-research-archive).
Every source listed in the claim register is included in this snapshot.

## Repository map

| Directory | Contents |
| --- | --- |
| [textbook/](textbook/) | Chapter sources, exercises, visual lessons and the static reader. |
| [docs/](docs/) | Current status, references and research arguments cited by the book. Start with [current status](docs/STATUS.md) and the [archive reading guide](docs/ARCHIVE_READING_GUIDE.md). |
| [formalization/](formalization/) | Scoped Lean checks and their verification receipts. |
| [experiments/](experiments/), [tests/](tests/) | Reproduction programs and focused validation for the cited evidence. |
| [artifacts/](artifacts/) | Evidence retained for the claims cited by the book. |
| [scripts/](scripts/) | The textbook builder and the publication inventory check. |
| [.github/workflows/](.github/workflows/) | Textbook checks and GitHub Pages deployment. |

## Contribute or inspect the research

For teaching corrections, begin with [CONTRIBUTING.md](CONTRIBUTING.md).
For a mathematical claim, read [current status](docs/STATUS.md) and the linked
source argument in [the claim register](textbook/claims.md).
Historical failures and corrections are retained because they explain the
limits of the surviving results. Build output, caches and local review captures
are ignored.

```sh
python scripts/build_textbook.py
python -m pytest -q tests/test_publication_inventory.py
node textbook/assets/fluid/checks.js
```

These check the book build, its published file inventory and the simulator's
numerical self-tests. They do not verify a PDE proof. Each mathematical result
has its own verification scope and reproduction instructions.

## Publication status

This is the first public teaching edition, built from a curated snapshot of the
research working tree. The snapshot was prepared for textbook use. Publication
does not claim that the complete-proof condition for the unforced Navier–Stokes
problem has been met. Unforced research remains paused.

- [Publication guide](PUBLICATION.md): repository setup, workflows and scope.
- [Publication inventory](docs/PUBLICATION_INVENTORY.json): included paths and source revision.
- [Publication checks](docs/PUBLICATION_CHECKS.md): recorded local validation results.

The private [research archive](https://github.com/Hmbown/transformatics-research-archive)
retains the full Git history and the earlier pull requests. The old operational
publication log is archived there rather than presented here as current.

Copyright 2026 ShannonTek. License: [MIT](LICENSE), with external sources
retaining their own terms. Citation metadata: [CITATION.cff](CITATION.cff).
