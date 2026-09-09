# VSA Finite-Fourier Analysis: Status Report — 2026-04-30 Continuation

**Date:** 2026-04-30 local workspace time  
**Agent:** DeepSeek V4 shadow-math continuation  
**Predecessor:** docs/VSA_FINITE_FOURIER_EXPLORATION_REPORT_2026_05_11.md  
**Status:** Hinge A advanced (N=6 certified); Hinges B/C/D analyzed; NS regularity remains CONDITIONAL

---

## What Changed

### Hinge A: N=6 Witness Certified (r = 12.1867233028)

**CLAIM: PROVED.** The pointwise kinematic VSA constant `C_P <= 12.1` is false.

The previous N=6 candidate (r = 12.0821832397) failed at grid 128+ because a
competitor peak appeared at approximately (0.2209, 0.4909). A Nelder-Mead
grid-constrained repair optimization eliminated this competitor, producing a
new configuration with **r = 12.186723302792124**.

**Certificate structure (identical to N=5):**

1. **Multi-grid sweep**: No competitor at grids 64, 128, 256, 512, 1024, 2048.
   The origin is the unique global maximizer of F = a²+b² on each grid.
2. **Interval Hessian**: 32×32 subboxes of [-0.03, 0.03]² all negative-definite
   (0 failures). Radius reduced from 0.04 (used in N=5) because the weaker
   Hessian eigenvalue (-0.442) turns indefinite at ~0.045.
3. **Taylor-grid complement at grid 4096**: Margin = 0.000118432 (tight but
   positive). The outside upper bound is 1.181487486 vs F0 = 1.181605918.

**Key measurements:**
```
r = 12.186723302792124
S₁ = 7.589441185775115
|S₂| = 2.174033963139121
F0 = 1.1816059182032717
Hessian eigenvalues: [-18.839901, -0.441599]
```

**Artifacts:**
- `artifacts/vsa_campaign/finite_fourier_n6_counterexample.json` — full certificate
- `artifacts/vsa_campaign/n6_multigrid_candidate.json` — repair coefficients
- `experiments/vsa_finite_fourier_n6_counterexample.py` — replay script
- `experiments/n6_multigrid_certify.py` — verification infrastructure
- `tests/test_vsa_finite_fourier_n6_counterexample.py` — 17 regression tests

**Replay:**
```bash
PYTHONPATH=. python3 experiments/vsa_finite_fourier_n6_counterexample.py --cert-grid 4096
PYTHONPATH=. python3 -m pytest tests/test_vsa_finite_fourier_n6_counterexample.py -v
```

**Witness ladder (all certified):**
| N_max | Modes | r        | C_P bound falsified | Status    |
|-------|-------|----------|---------------------|-----------|
| 3     | 24    | 10.5297  | C_P <= 10           | Certified |
| 4     | 40    | 11.1808  | C_P <= 11           | Certified |
| 5     | 60    | 11.8055  | C_P <= 11.8         | Certified |
| 6     | 84    | 12.1867  | C_P <= 12.1         | Certified |

---

### Hinge B: Diophantine Boundedness Analysis

**STATUS: NUMERICAL EVIDENCE (no proof).** The VSA ratio r appears bounded
(~12) for the 2D streamfunction class, but no analytic proof has been
constructed.

**Parity constraint analysis (NEGATIVE RESULT):**

The three corner constraints at (π,0), (0,π), (π,π) give necessary conditions:

```
Re(E · Ō) ≥ 0    (k_x parity)
Re(F · Ḡ) ≥ 0    (k_y parity)
Re(H · Ī) ≥ 0    (k_x+k_y parity)
```

where E = Σ_{k_x even} v_k, O = Σ_{k_x odd} v_k, etc.

**These parity constraints are INSUFFICIENT to bound r.** A direct
optimization (minimize |S₂|² subject to S₁=1 and the three parity constraints)
finds weights with |S₂| ≈ 0 (r > 10²⁰) satisfying all three constraints for
every n_max tested (3 through 6). The parity conditions are nearly vacuous:
when both the even and odd components are near zero (achieved by balanced
weights), Re(E·Ō) ≈ 0 ≥ 0 trivially.

Consequently: **the bound on r, if it exists, must come from the full
continuous constraint** |Σ w_k u_k cos(k·x)| ≤ |Σ w_k u_k| for ALL x ∈ T²,
not just the four corner points.

**Structure of the full constraint:**

For each x ∈ T², the sign pattern s_k(x) = cos(k·x) is restricted to the
image of the 2D torus under the cosine map:
  S = {s(x) = (cos(k₁·x), ..., cos(k_N·x)) : x ∈ T²} ⊂ [-1,1]^N

dim(S) ≤ 2 (since x has 2 degrees of freedom), while the ambient cube has
dimension N. By Sard's theorem, almost every sign pattern is NOT achievable.

The condition |Σ v_k s_k| ≤ |Σ v_k| for all s ∈ S is equivalent to:
  |Σ v_k - Σ v_k (1 - s_k)| ≤ |Σ v_k| for all s ∈ S
  → |A(x)|² ≤ 2 Re(S₂ · A(x)̄)  where A(x) = Σ v_k (1 - cos(k·x))

This must hold for all x ∈ T². The "worst-case" x is where cos(k·x)
simultaneously deviates far from 1 for modes contributing constructively
to S₂ and stays near 1 for modes contributing destructively.

**Conjecture (2D Streamfunction VSA Boundedness):** There exists a universal
constant C < ∞ such that for any finite Λ ⊂ Z² and any c_k > 0, if the origin
is a global maximizer of F(x) = |Σ c_k k² cos(k·x)|², then
  r = (Σ c_k |k|²)² / |Σ c_k k²|² ≤ C.

**Numerical estimate:** C ≈ 12.2 based on certified witnesses up to |k|_∞ = 6
and N=7 candidate regression to r ≈ 11.5 (suboptimal search).

**What a proof would require:** Show that the condition
  Re(Σ w_k cos(2θ'_k) · (1 - cos(k·x))) ≥ 0  ∀x ∈ T²
combined with the Hessian negative-definite condition at the origin, forces
|Σ w_k u_k| ≥ γ · Σ w_k for some universal γ > 0. The Hessian condition
couples the weights to the wavevector geometry: Σ w_k cos(2θ'_k) k_a k_b < 0.

---

### Hinge C: 2D vs 3D Extremality

**STATUS: CONJECTURED (numerical evidence favors 2D extremality).**

The 2D streamfunction ansatz achieves r ≈ 12.2 (certified), while the best
3D adversarial optimization at g-maximizers found r ≈ 1-3 (DNS Kida r ≈ 2.8,
random search r ≈ 1.26 after refinement). The large gap suggests 2D is either
extremal or nearly so.

**Key 3D constraint:** In full 3D, the additional strain components (S₁₃, S₂₃,
S₃₃) contribute positively to g without increasing |Ω|²_F, reducing r. The
∇g=0 condition at the g-maximizer creates 3 coupling equations (vs 2 in 2D),
making the cancellation structure harder to achieve.

**PROVED:** The 2D streamfunction ansatz is a valid subspace of divergence-free
3D fields, so sup_{3D} r ≥ sup_{2D} r. The lower bound r > 12.1867 holds for
the full 3D VSA problem.

**CONJECTURED:** The 2D streamfunction saturates VSA: sup_{3D} r = sup_{2D} r.
No proof; the extra 3D DOFs could theoretically enable a configuration where
S₁₃=S₂₃=S₃₃=0 at the g-maximizer while ω has x,y components not derivable
from a streamfunction. No such configuration has been found numerically.

---

### Hinge D: Dynamical Exclusion Routes

**STATUS: ANALYSIS COMPLETE — no closed lemma.**

All previously attempted NS dynamical bypasses are BLOCKED or KILLED:
- Pointwise Riccati: BLOCKED (c₁·α < 1)
- Riesz l=0 decoupling: BLOCKED (third-derivative gap)
- S:P r-trapping damping: BLOCKED (false for r > 1)
- Moving g-maximizer stationarity: KILLED as standalone bypass

**New routes explored:**

1. **Viscous mode dispersion (PROMISING):** The high-r VSA witnesses achieve
   large r via delicate cancellation of complex Fourier coefficients. NS
   viscosity acts as −ν|k|² on each Fourier mode, preferentially damping
   high-|k| modes. The dominant modes in the VSA witnesses (|k| ≤ 5) share
   similar |k| values, so viscosity damps them uniformly — it would NOT break
   the high-r configuration quickly. However, viscous dispersion of the PHASES
   (through the NS nonlinearity) could break the delicate cancellation.
   **Blocker:** Requires a quantitative estimate of phase dispersion rate
   for the specific mode set. No lemma formulated.

2. **Pressure Hessian evolution via discriminant Δ(S) (SPECULATIVE):** 
   The discriminant Δ(S) = |S|⁶/2 − 27·det(S)² measures departure from
   axisymmetry. For the 2D streamfunction, S is planar (S₁₃=S₂₃=S₃₃=0),
   which is a degenerate case of the discriminant. The NS evolution of Δ
   under planar strain is not analyzed.
   **Blocker:** The 2D streamfunction subspace is NS-invariant (2D flow with
   no z-dependence stays 2D), so the discriminant analysis for 3D fields
   doesn't directly apply to the witnesses.

3. **g-maximizer migration (PROMISING):** The VSA witnesses place the
   g-maximizer at the origin by construction (all cos(k·x) = 1). Under NS
   evolution, the maximizer migrates. The phase-velocity identity
   x* = −K⁻¹·φ gives the migration velocity. If the maximizer quickly moves
   to a point where r is lower, the high-r configuration is dynamically
   harmless.
   **Blocker:** Requires computing the NS evolution of the Fourier phases
   φₖ(t) for the specific witness mode set. The phase velocity depends
   on the nonlinear convolution, which for 2D streamfunctions couples only
   modes within the same k_z=0 plane. A quantitative estimate needs the
   specific initial velocity field, not just the g-maximizer structure.

**Verdict:** None of the explored dynamical routes closes the gap. The
dynamical exclusion problem remains OPEN. Any solution would need a
quantitative PDE estimate specific to the VSA witness Fourier structure.

---

## Tests Run (All Passing)

```
Full VSA regression suite: 30 tests passed
  tests/test_vsa_finite_fourier_counterexample.py — 5 passed
  tests/test_vsa_finite_fourier_n4_counterexample.py — 8 passed
  tests/test_vsa_finite_fourier_n5_counterexample.py — (preexisting)
  tests/test_vsa_finite_fourier_n6_counterexample.py — 17 passed

N=5 certificate replay: PASSED (status=PROVED, margin=0.000486)
N=6 certificate replay: PASSED (status=PROVED, margin=0.000118)
```

---

## Current NS Status

**NS regularity: CONDITIONAL/OPEN.**

What is proved:
- Theorem A: At a strain maximizer with source_kz_frac ≥ 1/2, c₁ > 0
  (directional share positivity). CERTIFIED for single-shell and multi-shell
  (via g(x) ≥ 0 obstruction).
- Lemma 9-B (refined): All abstract counterexamples violate g(x) ≥ 0, which
  is necessary for NS-realizability. CERTIFIED.
- Envelope migration identities (M1-M5): CERTIFIED.

What is NOT proved:
- That the VSA ratio is bounded by a universal finite constant
- That c₁·α > 1 (or any quantitative damping sufficient for regularity)
- That high-r kinematic witnesses are dynamically excluded

The VSA constant falsification ladder now extends to C_P > 12.1 (N=6 certified),
further constraining any potential proof that relies on a small universal VSA
bound.

---

## Files Changed

| File | Action | Description |
|------|--------|-------------|
| `experiments/vsa_finite_fourier_n6_counterexample.py` | **NEW** | N=6 full certification (interval Hessian + Taylor-grid) |
| `experiments/n6_multigrid_certify.py` | **NEW** | Multi-grid verification and Nelder-Mead repair |
| `tests/test_vsa_finite_fourier_n6_counterexample.py` | **NEW** | 17 regression tests for N=6 witness |
| `artifacts/vsa_campaign/finite_fourier_n6_counterexample.json` | **NEW** | Full N=6 certificate artifact |
| `artifacts/vsa_campaign/n6_multigrid_candidate.json` | **NEW** | Repair coefficients and grid sweep |
| `docs/VSA_FINITE_FOURIER_N6_CERTIFIED_2026_04_30.md` | **NEW** | This report |

No existing proof files or previously certified artifacts were modified.

---

## Next Exact Moves (Priority Order)

1. **Push N=7 or higher.** The N=7 candidate regression (r ≈ 11.5, lower than
   N=6) suggests the search is suboptimal, not that the bound is saturated.
   A systematic multi-start Nelder-Mead at N=7 with grid constraint may find
   r > 12.2. The certification framework is now in place.

2. **Prove the 2D boundedness conjecture.** The parity constraints being
   insufficient means the proof must engage the full cosine manifold geometry.
   The key inequality |A(x)|² ≤ 2 Re(S₂ · A(x)̄) for all x ∈ T², combined
   with the Hessian negative-definite condition, is a well-posed problem in
   Diophantine approximation. A covering-radius argument on the lattice Z²
   may yield a bound.

3. **Construct a 3D field exceeding r = 12.2, or prove 2D extremality.**
   The 2D streamfunction subspace is a natural candidate for the worst case,
   but this is not proved. Either direction (construction or proof) would
   advance the state.

4. **Rigorously connect the kinematic VSA bound to NS dynamics.** Even if
   r ≤ C for all initial fields, NS regularity still needs the dynamical
   inequality d⟨Δ⟩/dt ≤ C₁⟨Δ⟩^(5/6) + C₂⟨g⟩ with explicit constants.
   This is a PDE problem; the discriminant route (Path B in _proof.py)
   remains FORMAL-CONDITIONAL.

---

## Claim Labels Enforced

- **PROVED:** N=6 finite-Fourier high-r witness (r = 12.1867 > 12.1)
- **PROVED:** C_P ≤ 12.1 is FALSE for the pointwise kinematic VSA bound
- **NUMERICAL EVIDENCE:** r is bounded (~12) for 2D streamfunctions
- **CONJECTURED:** 2D streamfunctions extremal for full 3D VSA
- **CONDITIONAL:** NS regularity — all routes require further work
- **BLOCKED:** Pointwise Riccati, Riesz decoupling, r-trapping bypass
- **KILLED:** Moving g-maximizer stationarity as standalone bypass
- **FORMAL SCAFFOLD:** Spatial discriminant path (Lemma 6 κ-bound, sublinear exponent)

No NS regularity closure is claimed. The VSA constant floor has moved from
C_P > 11.8 to C_P > 12.1.
