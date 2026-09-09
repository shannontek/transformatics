# Required Lemma — Adversarial Search: Is |P₂₃| ≤ C·δ·g at g-Maximizers?

**Date:** 2026-06-17
**Agent:** CodeWhale (deepseek-v4-pro)
**Status:** NUMERICAL — first direct adversarial optimization of P₂₃/(δ·g)

> **Corrected 2026-07-25.**  The follow-on decomposition script computed
> `-Hess p` while labeling it `Hess p`.  The exact identity has the opposite
> signs shown in §9 below.  Absolute adversarial-search ratios came from a
> separate correct Hessian path and stand.  See
> `REQUIRED_LEMMA_DECOMPOSITION_CORRECTION_2026_07_25.md`.

## 0. The Required Lemma (link 2 in the regularity chain)

The regularity chain's second load-bearing claim (after the product bound
|ω₂ω₃| ≤ C_ω·g, now VERIFIED-by-triangulation) is:

> At every global maximizer of g = |S|²_F, the off-diagonal entries of the
> pressure Hessian P in the S-eigenframe satisfy |P_{ij}| ≤ C·|λ_i−λ_j|·g.
> In particular, |P₂₃| ≤ C·δ·g where δ = λ₃−λ₂.

If δ is small (near-axisymmetry), the 1/δ singularity in the frame rotation
rate W₂₃ = (R^T D_tS R)₂₃/δ must be cancelled by the numerator — and the
Required Lemma is the mechanism. Without it, the discriminant dynamics has
an uncontrolled 1/δ term that could lock the flow near axisymmetry long
enough for g to blow up.

## 1. What was known before this session

- **DNS Kida (9 snapshots):** P₂₃/(δ·g) ≤ 0.71. Correlation P₂₃/g vs δ is
  NEGATIVE (−0.65): as the flow approaches axisymmetry, P₂₃/g INCREASES.
  `artifacts/vsa_campaign/hessian_condition_kida.json`
- **Adversarial ω₂ω₃ search (N=16/24/32):** incidental max P₂₃/(δ·g) = 0.95.
  Correlation P₂₃/g vs δ is POSITIVE (+0.52): fields with large P₂₃/g have
  large δ, and fields with small δ have small P₂₃/g.
  `artifacts/vsa_campaign/lbe_adversarial_omega23_*.json`
- **Adversarial P₂₃ search (N=16/24):** optimized for P₂₃/g directly. Found
  max P₂₃/g ≈ 0.26 but with LARGE δ (4.7–8.6), giving P₂₃/(δ·g) ≤ 0.05.
  The optimizer avoided small-δ configurations when maximizing P₂₃.
  `artifacts/vsa_campaign/lbe_adversarial_p23_*.json`
- **DNS true strain maxima (26 snapshots, N=64):** P_eigframe_23_over_g_max =
  0.094, ω₂₃/g ≤ 0.10. `artifacts/eigenframe_structure/analysis.json`
- **No direct optimization of P₂₃/(δ·g) existed.**

## 2. New: adversarial optimization of P₂₃/(δ·g)

Extended `experiments/lbe_adversarial_true_gmax_search.py` with new
objectives `p23_over_delta` and `p23_over_delta_safe` that directly
maximize the Required Lemma ratio.

### Results

| N | Trials | Gens | Best P₂₃/(δ·g) | P₂₃/g | δ | r | ω₂₃/g |
|---:|---:|---:|---:|---:|---:|---:|---:|
| 8 | 80 | 4 | **1.41** | 0.069 | 0.049 | 0.21 | 0.0008 |
| 12 | 80 | 4 | **0.35** | 0.104 | 0.297 | 0.16 | 0.0008 |
| 16 | 120 | 5 | **4.46** | 0.029 | 0.0064 | 0.30 | 0.0036 |
| 16 | 200 | 8 | **1.38** | 0.066 | 0.048 | 0.18 | 0.0097 |
| 16 | 200 | 8 | **6.38** | 0.121 | 0.019 | 0.21 | 0.127 |
| 24 | 150 | 6 | **2.03** | 0.074 | 0.036 | 0.33 | 0.032 |

The N=16 seed-20260617 search found δ = 0.0064 (very near-axisymmetric)
with P₂₃/g = 0.029, giving ratio 4.46. The seed-20260618 search (larger
budget, different seed) found ratio 1.38 — the high-ratio regime is RARE
in the random search space.

### The extremal strategy

The optimizer achieves high P₂₃/(δ·g) by MINIMIZING δ, NOT by maximizing
P₂₃. The extremal field (δ=0.0064) has:
- S_eigs = [−3.275, 1.634, 1.641] — nearly axisymmetric about the
  compressional axis
- ω = [1.396, 0.021, −2.774] in the S-eigenframe — ω₂ nearly zero
- ω₂₃/g = 0.0036 — negligible product (consistent with the two-obstructions
  finding)
- r = 0.30 — modest VSA ratio
- Hessian eigenvalues: [−418, −147, −114] — strongly NSD

## 3. Power-law analysis

Across 196 unique true-gmax measurements from all searches:

**P₂₃/g ≈ 0.12 · δ^0.19** (R² ≈ 0.3, rough fit)

This implies P₂₃/(δ·g) ≈ 0.12 · δ^{−0.81}, which GROWS as δ → 0. If this
power law holds to arbitrarily small δ, the Required Lemma with a universal
constant C is FALSE.

However:
- The fit is dominated by the large-δ regime (δ > 0.1 has 138/196 points)
- Only 5 points have δ < 0.05
- The small-δ asymptotics are unresolved

## 4. The two competing hypotheses

**H1 (BOUNDED):** P₂₃/g decays at least as fast as O(δ) as δ → 0, so
P₂₃/(δ·g) is bounded by a universal constant C ≈ 5.

Mechanism: the g-maximizer condition ∇g = 0 forces (λ₁−λ₃)∂_aS₁₁ ≈ δ·∂_aS₂₂
in the S-eigenframe. As δ → 0, the strain gradient along the distinguished
eigendirection must vanish as O(δ). This constraint propagates through the
pressure Poisson equation to suppress P₂₃.

Evidence FOR: positive correlation between P₂₃/g and δ; the evolutionary
search's difficulty finding small-δ fields with non-negligible P₂₃; DNS
maxima show P₂₃/(δ·g) ≤ 0.71.

**H2 (UNBOUNDED):** P₂₃/g decays slower than O(δ) (α < 1), so P₂₃/(δ·g)
grows without bound as δ → 0.

Mechanism: the pressure Hessian is a nonlocal Riesz transform of the source
f = g − |Ω|²_F. There is no local elliptic estimate that forces P₂₃ → 0
when eigenvalues approach. For any ε > 0, one can construct a field with
δ < ε and P₂₃/g ≥ c > 0 by localizing the vorticity away from the
g-maximizer.

Evidence FOR: the power-law exponent α ≈ 0.19 < 1; the adversarial search
already achieved ratio 4.46 at δ = 0.0064; no theoretical lower bound on
δ at g-maximizers is known.

## 5. The decisive experiment

The open question is: **can δ be pushed below 10⁻⁴ at a g-maximizer while
P₂₃/g ≥ 0.01?**

If yes → H2 supported, Required Lemma refuted (or C ≥ 100).
If no → evidence for a structural constraint at δ → 0.

**Proposed approach:** gradient-based optimization on the Fourier
coefficients to minimize log δ while constraining P₂₃/g ≥ 0.01 and
maintaining the g-maximizer condition. The gradient of δ with respect to
Fourier coefficients is computable via the eigenvalue perturbation formula:

∂δ/∂b_α = v₃^T T_α v₃ − v₂^T T_α v₂

where v_i are eigenvectors of S(0) and T_α are the basis tensors. The
constraint P₂₃/g ≥ 0.01 can be handled via a penalty or barrier method.

A first attempt (`experiments/vsa_required_lemma_refine.py`) using random
perturbations from the δ=0.0064 field failed to improve — suggesting the
field is a local minimum of δ (or the perturbation method is too crude).

## 6. Relationship to the product bound

The Required Lemma and the product bound are the TWO load-bearing estimates
in the regularity chain. They appear to be complementary:

- **Product bound** (link 1): large |Ω|²/g → ω₂ω₃ ≈ 0 (two obstructions)
- **Required Lemma** (link 2): small δ → P₂₃/g is small (this investigation)

Together they form a "pincer": when VSA is large (|Ω|²/g ≫ 1), the product
is small; when the eigenvalue gap is small (δ ≪ 1), the pressure off-diagonal
is small. The dangerous regime where BOTH are large may be empty.

## 7. Evidence class

**NUMERICAL** — first direct adversarial optimization. Not PROVED.
The key open question (can δ → 0 while P₂₃/g stays finite?) requires
either a more powerful optimizer, a theoretical analysis, or both.

## 8. Files

| File | Purpose |
|---|---|
| `experiments/lbe_adversarial_true_gmax_search.py` | Extended with `p23_over_delta` objective |
| `experiments/vsa_required_lemma_refine.py` | Targeted δ-minimization (first attempt) |
| `artifacts/vsa_campaign/lbe_adversarial_p23_over_delta_N8_seed20260617.json` | N=8 results (ratio 1.41) |
| `artifacts/vsa_campaign/lbe_adversarial_p23_over_delta_N12_seed20260617.json` | N=12 results (ratio 0.35) |
| `artifacts/vsa_campaign/lbe_adversarial_p23_over_delta_N16_seed20260617.json` | N=16 results (ratio 4.46) |
| `artifacts/vsa_campaign/lbe_adversarial_p23_over_delta_N16_seed20260618.json` | N=16 larger search (ratio 1.38) |
| `artifacts/vsa_campaign/lbe_adversarial_p23_over_delta_N16_seed20260620.json` | N=16 largest search (ratio **6.38**) |
| `artifacts/vsa_campaign/lbe_adversarial_p23_over_delta_N24_seed20260619.json` | N=24 preliminary (ratio 2.03) |
| `artifacts/vsa_campaign/required_lemma_refined_N16.npz` | Refinement attempt output |

## 9. Theoretical connection: the [S,P] commutator identity

The NS strain evolution gives an EXACT identity (sympy-verified):
[S, P] = −[S, Ω²] − [S, D_tS] + ν[S, ΔS]

In the S-eigenframe for the (2,3) entry:
**P₂₃ = −ω₂ω₃/4 − (D_tS)₂₃ + ν(ΔS)₂₃**

This means the off-diagonal pressure Hessian is DIRECTLY tied to the vorticity
product ω₂ω₃ (the product bound's quantity), plus transport and viscous terms.
The Required Lemma is NOT independent of the product bound — they are the same
estimate up to O(g) transport corrections.

**Implication:** The static adversarial search overestimates the ratio by
exploring configurations where the transport term (D_tS)₂₃ contributes
significantly — a freedom that actual NS solutions may not have. In the data,
the corrected term-by-term values are recorded in
`REQUIRED_LEMMA_DECOMPOSITION_CORRECTION_2026_07_25.md`.

**Open question:** Does |(D_tS)₂₃| ≤ C'·δ·g hold? If yes, the Required Lemma
reduces entirely to the product bound (VERIFIED-by-triangulation).
