# Origin and credits

Transformatics was initiated and directed by **Hunter Bown**, in collaboration
with AI models. It began as a sustained investigation of the Navier–Stokes
equations and developed into a textbook and research project about
transformations, models and the accuracy of predictions.

The initial motivation was to understand finite change beyond the usual presentation of calculus. The book lets that question develop through definitions, calculations and constructions.

## The collaboration

Hunter reports working with both frontier and open-source models, **mostly DeepSeek and GLM**. We credit that account explicitly. The repository also preserves model-labelled notes, commit trailers, and records of AI assistance. These are different forms of evidence: an author name or an editing tool does not identify the model behind every contribution.

| Contributor or assistance | Basis for the credit |
|---|---|
| **Hunter Bown** | Project origin, direction, questions, and sustained collaboration, described by Hunter and reflected in the repository history. |
| **DeepSeek and GLM models** | Hunter's account of their central participation. Several tracked notes additionally identify DeepSeek assistance. The inspected records do not establish contribution percentages or identify every model version. |
| **Other AI assistance** | The history includes Claude-labelled coauthor trailers, `Cursor Agent` author labels, and notes identifying an unspecified AI agent. Current textbook development also uses Codex for drafting, calculations, review, and implementation. |
| **Mathematical and software communities** | The classical sources, theorem-proving libraries, and computational tools cited alongside the material that uses them. |

A few concrete traces make the acknowledgement inspectable:

- At commit `298e757d`, a [finite-Fourier note](../../docs/VSA_FINITE_FOURIER_N6_CERTIFIED_2026_04_30.md) identifies its agent as “DeepSeek V4 shadow-math continuation.”
- At `d7a2eddf`, an [analytic attempt](../../docs/REQUIRED_LEMMA_ATTACK_2026_06_17.md) records “CodeWhale (deepseek-v4-pro).”
- Commit `8f19a126` has a coauthor trailer labelled “Claude Fable 5.1.” That is the recorded label; this credit does not authenticate a particular backend or model release.

These traces acknowledge work, including unsuccessful investigations and corrections. They do not validate every mathematical assertion in the historical documents. The commit identifiers refer to the private research archive's history; the cited note files are included here, so the labelled evidence remains inspectable in this repository. The [provenance record](../../docs/CONTRIBUTOR_PROVENANCE.md) gives the bounded inspection method and separates source labels from user-attested participation. It is not a complete census of the collaboration.

## Mathematical lineage and external results

The foundations taught here belong to established mathematics: finite differences and pullbacks, operator descriptions of dynamics, Lie derivatives and flows, stability estimates, Fourier analysis, and numerical approximation. The [finite-transformations chapter](transformations.md) identifies the Koopman lineage; [flows and generators](generators.md) identifies the classical Lie derivative and its sources. The fluid chapters cite their PDE results and the work on compact Euler profiles used in the research examples.

The externally authored *Finite time blowup for Navier–Stokes* is credited to **OpenAI**. Its reported forced C/D result and separate formalization are explained in [the published-proof chapter](published-proof.md), with primary-source links and explicit verification scope. Our use of some of the same standard mathematical tools does not establish that this project caused, anticipated, or supplied the external proof. The unforced Navier–Stokes question is distinct.

Lean, Mathlib, the other formal tools, and the numerical libraries used by particular examples receive attribution in the corresponding source and build documentation. A successful tool run has its stated verification scope; acknowledgements do not turn it into a check of an entire argument.

## Attribution and license

A concise description of this work is:

> Transformatics: a textbook and research project initiated and directed by Hunter Bown, developed in collaboration with frontier and open-source AI models, especially DeepSeek and GLM according to Hunter's account. Classical mathematics and external research are credited at their points of use.

The repository's [MIT license](../../LICENSE) names **ShannonTek** in the
2026 copyright notice, as directed by Hunter during preparation for sharing.
The [provenance record](../../docs/CONTRIBUTOR_PROVENANCE.md) preserves the
earlier audit and this correction. External papers and other third-party
material retain their own terms.
