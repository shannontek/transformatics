# Project status

## Current standing — one screen

The first public teaching edition is live at
[shannontek.github.io/transformatics](https://shannontek.github.io/transformatics/).
It was published from a curated snapshot of the research working tree on the
textbook's educational merits. Publication does not claim that a complete-proof
condition for the unforced Navier–Stokes problem has been met.

**Unsolved Navier–Stokes research remains paused at the user's request.**
Proof verification, simulations, research automations, virtual machines and
media rendering are not running.

| Subject | Current standing |
| --- | --- |
| Transformatics textbook | First public teaching edition: foundations, worked examples, exercises, assessments, fluid case studies and an information/control application. |
| Unforced ROOT | **OPEN.** No unconditional global regularity or finite-time blow-up theorem is established here. |
| E-prime | **OPEN.** The project's separate sufficient estimate has not been proved. |
| Smoothly forced FORCED-D | **IMPORTED.** A separately authored external result, with the verification limits below. |
| Local research | Reviewed finite and conditional results, diagnostics, failed routes and corrections are included. They do not supply one singular unforced trajectory. |
| Human review | No human expert or learner review has been recorded for this edition. |

Start with [the textbook preface](../textbook/chapters/index.md),
[the readable claim register](../textbook/claims.md) or
[the contribution guide](../CONTRIBUTING.md). The first public edition is
version `1.0.0`; [CITATION.cff](../CITATION.cff) identifies it.
The [publication guide](../PUBLICATION.md) records the release setup, and the
[publication inventory](PUBLICATION_INVENTORY.json) lists the included paths
and the source revision.

## What has been verified

The external forced Navier–Stokes targets built from the pinned OpenAI source
with official Lean 4.34.0-rc2. All 580 project-local modules in their import
closure compiled, using matching cached Mathlib artifacts. Both exported
targets printed `propext`, `Classical.choice` and `Quot.sound` as axiom dependencies.
The [external verification receipt](../formalization/external_ns/README.md)
records those exact results.

A separate full-import replay with Lean's bundled checker remains
**incomplete**. An earlier attempt hit a 600-second limit; a later attempt was
stopped after 1485.74 seconds under severe host memory and swap pressure, with
exit 143 and an empty buffered log. Neither outcome is a proof rejection or a
passing verification. Independent Comparator/Nanoda verification has **not been
run** on the Navier-Stokes theorems; a sandbox probe confirmed only that the
tool environment starts. The successful target build does not certify every detail
of the paper or the companion Euler library. The
[source and statement assessment](NSE_OPENAI_RESULT_BRIDGE_2026_09_08.md)
keeps those distinctions explicit; the construction belongs to its external authors.

Local formal coverage includes the restricted
[oblique-cone algebra](../formalization/oblique_cone/README.md) and
[phase-covariance corollary](../formalization/phase_covariance/README.md), each
with its own compilation, axiom and replay receipt. These are bounded algebraic
results. Other local analytic arguments have written proofs and recorded AI
reviews rather than formal PDE certificates or external expert acceptance.
No human expert or learner review of the textbook has been recorded.

## Reading the included research

The [claim register](../textbook/claims.md) and its
[machine-readable source](../textbook/claims.json) record individual
statements, evidence and corrections for the claims cited by the book. Every
source listed in the register is included in this snapshot. A metadata audit
passing means these records are consistent with its checks; it does not prove
their mathematical contents. The
[archive reading guide](ARCHIVE_READING_GUIDE.md) explains how to read the
dated research notes included here. The full research graph, the earlier
status snapshots and the pre-publication operational log are preserved in the
private [research archive](https://github.com/Hmbown/transformatics-research-archive).

For the reviewed finite work, use the
[next-transfer review index](NSE_NEXT_TRANSFER_REVIEW_2026_09_08.md).
For the later force-removal studies, use the
[reviewed source record](NSE_OPENAI_RESULT_BRIDGE_2026_09_08.md#why-removing-the-force-remains-a-separate-problem).
The latest completed endpoint correction concerns a chosen packet space on a
finite interval and a datum depending on its late restart. It does not establish
compatible corrections from one fixed earlier datum, control the full complement,
or remove forcing through a singular time.

Earlier positive labels must be read with subsequent corrections. In particular,
the [cap-vacuity audit](NSE_QGSO_CAP_VACUITY_2026_09_06.md) retires the proposed
averaged-noncollapse strategy; old instructions to pursue it are not current.
The [textbook evidence guide](../textbook/chapters/evidence.md) explains how to
read proof, certification, numerical and imported-result labels.

## History and preservation

The public snapshot includes the notes cited by the book. The complete dated
research history, including the earlier status snapshots, the full research
graph and the pre-publication operational log, is preserved in the private
[research archive](https://github.com/Hmbown/transformatics-research-archive).
That archive retains the original Git history and the earlier pull requests.
Sources listed in the claim register were not edited for publication except
where this status page and the other release guides were updated; the
corresponding source hashes were refreshed after review.
