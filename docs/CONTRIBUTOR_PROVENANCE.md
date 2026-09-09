# Contributor provenance and attribution

Bounded audit, 8 September 2026. This record supports [the textbook credits](../textbook/chapters/credits.md). It distinguishes participation attested by Hunter Bown, explicit repository labels, and assistance whose model identity is unspecified. It is an attribution record, not a mathematical certification or an ownership determination.

## Origin and user-attested participation

Hunter Bown describes this as his collaboration with frontier and open-source models, mostly DeepSeek and GLM. The project began with Navier–Stokes investigations and the intuition that calculus alone had not supplied the account he wanted of real-world transformations. It developed toward a proposed discipline that studies finite transformations, observables, flows, composition, and transfer between mathematical descriptions.

This is Hunter's account of the origin and principal model participation. The repository provides additional traces, but it cannot reconstruct every conversation, contribution, or model endpoint. “Mostly DeepSeek and GLM” is therefore recorded as user-attested, without an invented numerical share. The account does not establish scientific superiority over calculus or acceptance of Transformatics as a new mathematical field.

## Inspection boundary

- Inspected the 1,241 commits reachable from local HEAD `2bad5bd949524e43c4d299e7125d40aad8ec2545`. The checkout reports that it is not shallow. This is the reachable local history, not a claim to have inspected every remote branch or deleted history.
- Read author-name labels and searched commit messages for explicit model names and coauthor trailers. Email addresses were excluded from the evidence output and are not reproduced here.
- Searched selected tracked Markdown/configuration metadata for DeepSeek, GLM, authorship and acknowledgement labels, then read the relevant header lines at specific commits. No private home-directory material, credentials, private model conversations, or prompt contents were collected for this audit.
- Read the current `LICENSE`, `CONTRIBUTING.md`, textbook lineage sections, and selected model-labelled research notes. The `.deepseek/whalebro.toml` inspection was restricted to allowlisted name/model fields; configuration presence alone was not treated as evidence of model execution.
- The current September textbook work includes uncommitted changes. Historical commit metadata does not by itself cover those contributions.

The earliest reachable commit is `68abcb74`, dated 1 March 2026, and already concerns a two-dimensional Navier–Stokes investigation. That bounds this checkout's recorded history; it is not proof of the date Hunter first conceived the project. Document dates, filenames, and commit dates sometimes differ, so they are not silently merged into one chronology.

## Concrete evidence examples

| Commit or source | Observed record | What it supports; limitation |
|---|---|---|
| `298e757d` | `docs/VSA_FINITE_FOURIER_N6_CERTIFIED_2026_04_30.md`, line 4, identifies “DeepSeek V4 shadow-math continuation.” The label is present in the file at that commit. | Explicit DeepSeek-labelled assistance. A document header is not an independently authenticated runtime receipt. |
| `d7a2eddf` | `docs/REQUIRED_LEMMA_ATTACK_2026_06_17.md`, line 4, identifies “CodeWhale (deepseek-v4-pro).” | Explicit tool/model label attached to a written investigation. It does not identify authorship of every later edit. |
| `8dc27045` | `docs/CONJECTURE_ASSESSMENT_2026_05_08.md`, line 4, identifies “DeepSeek TUI (analytic PDE/Lean specialist).” | A further recorded DeepSeek association; the role description is the document's own label. |
| `b3c5b548` | `docs/VSA_FINITE_FOURIER_EXPLORATION_REPORT_2026_05_11.md`, line 5, identifies “DeepSeek V4 agent.” An earlier version at `a614eb2f` says “takeover agent.” | Shows why attribution must be pinned to a version: a later explicit label does not retroactively identify the earlier agent. |
| `8f19a126`, `a20e7637` | Coauthor trailers identify “Claude Fable 5.1.” | Explicit declared coauthorship labels. The strings are preserved as metadata, without asserting that a backend of that name was independently verified. |
| `6f7d4ea3` | A coauthor trailer identifies “Claude Fable 5.” | Another declared assistance label, with the same limitation. |
| `a7a93025` | Author-name field is `Cursor Agent`; its coauthor trailer names Hunter Bown. | Records a tool-labelled author and a named human collaborator. It does not identify the model used inside the tool. |
| `298e757d` | `docs/VSA_ANALYTICAL_ATTACK_ASSESSMENT_2026.md`, line 5, identifies an “AI agent.” | AI assistance with no specific model identity established by that label. |
| Current textbook revision | Codex-assisted drafting, mathematical calculations, review and implementation in the present collaboration. | Current-session assistance, distinguished from the historical commits above; this record does not infer an exact backend version. |

The reachable history contains author-name labels `Hunter B`, `Hunter Bown`, `Cursor Agent`, and `Claude`. Git author fields are editable metadata. They do not authenticate a person, identify a model endpoint, or establish who contributed every part of a commit. Commit counts are not contribution shares and were not used to estimate the relative roles of DeepSeek, GLM, or other models.

No explicit GLM label was found in the inspected commit messages and selected tracked documentation. This is a search limitation, not evidence that GLM did not participate. Hunter's direct account remains the stated basis for that acknowledgement. The same principle applies to other assistance that was not separately labelled in the surviving files.

The traces above describe provenance only. Several linked historical investigations have later corrections or supersession. Their titles and author labels must not be taken as evidence of present theorem status.

## Classical sources and the external OpenAI result

The current curriculum expressly draws on classical operator theory, finite differences, dynamical systems, differential geometry and numerical analysis. Its mathematical lineage is documented in [the discipline description](TRANSFORMATICS_DISCIPLINE.md), the [finite-transformations chapter](../textbook/chapters/transformations.md), and [flows and generators](../textbook/chapters/generators.md). Source notes separately cite the PDE and compact-Euler-profile results they use. Those authors' work is not relabelled as an original Transformatics theorem.

Credit OpenAI separately for the externally authored *Finite time blowup for Navier–Stokes* and its released formalization. The [external-result bridge](NSE_OPENAI_RESULT_BRIDGE_2026_09_08.md) pins the inspected primary sources and the limits of local verification. Shared standard identities or conceptual parallels do not show that this project caused, anticipated, or contributed to that proof. The external forced result also does not establish an unforced result for this project.

## License and recommended wording

The root [LICENSE](../LICENSE), present in the earliest reachable commit, is
the MIT license. At the time of the initial audit, its notice read
`Copyright (c) 2026` without a holder. During the subsequent reader-preparation
pass on 8 September 2026, Hunter explicitly selected **ShannonTek** as the
holder; the notice now reads `Copyright (c) 2026 ShannonTek`.
[CONTRIBUTING.md](../CONTRIBUTING.md) asks contributors to preserve third-party
attribution.

This correction records the user's attribution instruction. It does not
grant additional rights in external papers, copied passages, assets, or
dependencies. Those materials retain their own applicable terms;
acknowledging an author or linking a paper does not relicense it.

Recommended project-description wording, separate from any copyright notice:

> Transformatics is a textbook and research project initiated and directed by Hunter Bown, developed in collaboration with frontier and open-source AI models, especially DeepSeek and GLM according to Hunter's account. Repository records preserve additional model-labelled and unspecified AI assistance. Classical sources and external results are credited where they are used.

Future contribution records should identify the human contributor or maintainer, the actual task and affected artifact, any voluntarily supplied model/tool label, and the verification performed. Unknown model identity should remain unknown. Attribution, copyright ownership, and mathematical validation are separate questions.
