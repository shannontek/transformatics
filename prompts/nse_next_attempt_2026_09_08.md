# Next Navier–Stokes attempt: two targets, one physical equation

> **PAUSED by the user, 8 September 2026.** Keep this brief as a research
> checkpoint. Do not execute it until the user explicitly resumes unforced
> Navier–Stokes research. The current task is preparing the repository and
> textbook for public release and producing a ShannonTek introduction video.

> **Resumed research goal — 8 September 2026.** Work now addresses the
> unforced problem using the released forced construction as a reference.
> Begin with the [current force-removal record](../docs/NSE_OPENAI_RESULT_BRIDGE_2026_09_08.md#why-removing-the-force-remains-a-separate-problem).
> Its terminal force is nonzero after Leray projection. The earlier coarse
> Sobolev Gronwall criterion fails for this source. Localization and amplitude
> bounds alone also do not close the nonlinear heat comparison. Use the
> reviewed modulation and anisotropic notes to retain pressure and the
> possibility of a shifted singular time. ROOT and E-prime remain OPEN;
> FORCED-D is externally IMPORTED. No new DNS, full-build repetition or
> revival of retired rung-average routes. The textbook-only priority and
> finite-stage next steps below are historical for this attempt.

## Current unforced step

Begin with the [nonlinear endpoint correction](../docs/ANALYSIS_NOTES/NSE_NONLINEAR_ENDPOINT_CORRECTION_2026_09_08.md)
and the [linear correction operator](../docs/ANALYSIS_NOTES/NSE_EXTERIOR_CORRECTION_OPERATOR_2026_09_08.md).
Both are completed restricted written results. On
`d=c tau^(1+h) sqrt(L)`, with a sufficiently small fixed `c`, the actual
linear evolution is uniformly close to scalar growth on the entire
specified packet space `E_tau`. Its compressed endpoint map is invertible.
The full nonlinear endpoint map has the same uniform derivative estimate
on a small initial ball. A contraction selects one smooth `xi_tau` with

    P_tau (V^(xi_tau)(1-tau+d)-U(1-tau+d)) = 0.

Here `V^(xi_tau)` starts from `U(1-tau)+xi_tau` and solves the complete
unforced equation throughout the interval. With `delta=h/64`, its correction
satisfies `||xi_tau||2 <= 2 exp(-lambda d) q_tau`, where

    q_tau = C [exp(-b tau^(-h/16)) + K^(5/2) d^3 tau^(-2 delta)].

The second term is polynomial. Do not promote this nonlinear estimate to
the stretched exponential linear bound in every fixed Sobolev norm.
The velocity and integrated gradient comparison still tend to zero.
`E_tau` is a finite test/parameter space of growing dimension, not a verified
invariant splitting or all growing directions.

**Next calculation: one fixed earlier initial time.** Section 4 of the
linear correction note gives an exact target. Pull each endpoint test back
by the actual adjoint propagator to a common `t_*`, form its Sobolev Riesz
representer and the Gram matrix `Gamma_N`. The actual force measurements
`beta_N` are attainable if and only if they lie in its range. One bounded
initial datum satisfying all these linear constraints exists exactly when
all ranges hold and `sup_N beta_N^T Gamma_N^dagger beta_N` is finite. The
stated all-order bounds on the same minimizers suffice for a smooth datum.
None of these uniform actual-source costs has been estimated. The right
side includes the inherited force response from `t_*` to each late window;
the small fresh-window packet response alone does not bound it. Obtain a
useful actual bound or a specific failure of this criterion, then address
the nonlinear coupling and complementary error. Do not repeat the finite
compressed inverse or choose a new independent datum for each constraint.

The [pressure evolution](../docs/ANALYSIS_NOTES/NSE_PRESSURE_RESPONSE_EVOLUTION_2026_09_08.md)
gives the exact adjoint hierarchy for the signed remote moment. The first
annular weight has zero direct force injection. The next has a meridional
component and a global pressure tail. The corresponding annular pressure
moment has actual initial curvature
`tau^(-2-2h)(-C_L M+O(sqrt(tau)))`, `C_L>0`. The global terminal force
moment `M` remains undetermined, and there is no controlled remainder for a
full later flight. Further fixed jets alone do not close the hierarchy.

The [primary material-phase calculation](../docs/ANALYSIS_NOTES/NSE_PRIMARY_STRAIN_AVERAGING_2026_09_08.md)
is also complete. Its phase changes by `O(D epsilon^(2/5) poly(S_*))`
only until first exit from one valid lifted label chart. Cylindrical
directions have a different slow clock; Cartesian rotation remains.
Spatial carrier frequency therefore supplies no fast material-time
averaging on that residence interval. A full-pressure Kelvin calculation
also defeats the specified simple normal-weighted metric. It does not
exclude a nonlocal or frequency-dependent adapted norm.

The preceding
[reviewed nonlinear comparison](../docs/ANALYSIS_NOTES/NSE_NONLINEAR_FORCE_COMPARISON_2026_09_08.md)
remains an input. For each `tau`, the actual unforced solution starting
from `U(1-tau)`
continues through `d=c tau^(1+h) sqrt(L)`, where `L=1+log(1/tau)`. It obeys

    sup ||V-U||infinity <= C tau^(3(1+h)/16) sqrt(L),
    integral ||grad(V-U)||infinity dt <= C tau^(11(1+h)/16) L.

The actual strain clock grows at least as `c1 sqrt(L)-o(1)`. These bounds
retain full pressure and quadratic error; sharp fixed spatial jets of the
complete reference give a uniform scaled H3 energy estimate. This is an
actual same-datum finite continuation result, with a different datum for
each `tau`. Do not repeat it or describe it as one singular trajectory.

Its section 5 gives the next quantitative obligation. In the scaled norm
`X_K(E)^2=sum_(j=0)^3 K^(-2j)||grad^j E||2^2`, `K=tau^(-(1+h)/2)`, an
initial error at most `C_in d` preserves these conclusions. The current
endpoint estimate is only `C d tau^(-theta)`, `theta=(1+h)/16`; it does not
verify that sufficient allowance in the next adjacent window. This is an
insufficient upper bound, not an impossibility theorem. The next useful
result must control the actual inherited error more sharply or replace
this scalar energy comparison with a bound that can be concatenated.

The [natural radial response](../docs/ANALYSIS_NOTES/NSE_NATURAL_RADIAL_RESPONSE_2026_09_08.md)
now retains full profile variation and viscosity on the slow-axial scale.
Its conditional evolution has a uniform energy estimate and explicit
boundary lifts. Converting physical normal traces can cost `tau^(-h)`;
actual radial traces and the axial matching residual remain to be bounded.
The sufficient damping threshold has not been verified for the source
constants. Use this boundary transfer estimate as a component, not as an
established bound on the actual global response.

The earlier linear results below remain relevant inputs, with their stated
scope. The finite corrected initial datum above now exists; the principal
next target is its realization from one fixed earlier datum and control of
one trajectory's inherited nonlinear error and global pressure.

Use the [global pressure functional](../docs/ANALYSIS_NOTES/NSE_GLOBAL_PRESSURE_FEEDBACK_2026_09_08.md)
to specify the missing data. It retains the Euclidean angular-mean stresses,
opposite annular harmonics and smooth torus-image term. Its remote axial
Hessian estimate at separation `d~sqrt(tau)` is
`C tau^(-9/4-h)||e||2`; a source-specific family of arbitrary solenoidal
tests attains that scale with either sign and zero target-tube jets. These
tests are not the prescribed force response. Control the actual signed
weighted stress integral, not just its norm or local velocity jets. For
the nonlinear difference include the additional `E tensor E` stress on
the full torus; the compact support of `U tensor E+E tensor U` does not
automatically apply to that quadratic term.

The [exterior quasimode theorem](../docs/ANALYSIS_NOTES/NSE_EXTERIOR_QUASIMODE_2026_09_08.md)
now gives a restriction on the **actual** full linearized evolution of the
external periodic reference. At `t0=1-tau`, a compact solenoidal packet has
growth parameter `lambda ~ tau^(-1-h)` and relative generator residual
`O(tau^(h/8))`. A variation-of-constants argument on a window of length
`O(tau^(1+h) log(1/tau))` proves

    sup_(t0 <= s <= t1) ||S_U(t1,s)||_(L2 -> L2) >= c tau^(-h/8).

This disproves a uniform arbitrary-error bound that depends only
polynomially on `(1-s)/(1-t1)`, since that ratio tends to one on the window.
That argument alone supplies neither a selected growing solution nor
excitation by the removed force. The subsequent correction-operator proof
does track every selected packet on its shorter window; force excitation
remains a distinct question. The physical force vanishes on the packet's
support, and its direct pairing with the projected force is exactly zero.

The [actual force coupling](../docs/ANALYSIS_NOTES/NSE_EXTERIOR_FORCE_COUPLING_2026_09_08.md)
is now explicit: its first possible coefficient pairs the local vorticity
with the global pressure gradient of `P f`. Angular averaging adds a radial
small factor. Its terminal pressure quadrupole is a convergent Green
integral of the actual force, with value and sign still undetermined.
The [fixed-response-jets theorem](../docs/ANALYSIS_NOTES/NSE_FORCE_RESPONSE_JETS_2026_09_08.md)
proves that every fixed linear-response derivative has packet pairing
`O(tau^P)` for every fixed `P`. The proof uses local elliptic estimates for
all pressure tails and fixed low-order global costs. This does not give a
Taylor remainder or a bound on the complete response over the amplification
window. Repeating a fixed number of response coefficients is not the next
step. Nor can adjoint support be iterated: the second adjoint power already
contains a non-gradient global pressure interaction.

The [complete local response bound](../docs/ANALYSIS_NOTES/NSE_LOCAL_RESPONSE_BOUND_2026_09_08.md)
now goes beyond those jets. Choose a fixed Gevrey-2 axial bump for the same
solenoidal packet. Throughout `d <= C tau^(1+h) log(1/tau)`, the actual
zero-data linear response `e_t=A(t)e+P f` satisfies

    sup_t |<e(t),v_tau>| <= C exp(-c tau^(-h/16)).

The proof represents the actual angular mean by a compact solenoidal
extension. Its full torus pressure becomes part of an auxiliary source
supported away from the packet. A weighted axial-band Leray estimate
controls that nonlocal input throughout the evolution. The transverse
Calderón–Zygmund singularity is treated separately from the integrable
kernel; it cannot be discarded. The
[global strain estimate](../docs/ANALYSIS_NOTES/NSE_GLOBAL_STRAIN_COST_2026_09_08.md)
supplies `||grad U||infinity <= C tau^(-1-h) sqrt(log(1/tau))`, including
all corrections. Its global linear growth cost is at most
`exp(C log^(3/2)(1/tau))` on the window, which the spatial attenuation
overcomes. Fixed higher response norms use a triangular derivative estimate
with only `C1` of `U` in the highest-order growth coefficient.

This controls the fixed packet pairing, not the full response norm or every
possible growing direction. Do not repeat this high-frequency pairing task
or promote it to a nonlinear force-removal estimate. The
[slow axial analysis](../docs/ANALYSIS_NOTES/NSE_LOW_AXIAL_RESPONSE_2026_09_08.md)
identifies the next unresolved channel: the lowest harmonic pressure moment
permits an exact local affine response, but its strain rate is set by global
pressure boundary data. The centrifugal feedback of that local affine
ansatz is a radial gradient; a scalar instability equation cannot be read
off from it. Keeping slow axial variation while shrinking radial support
also fails: the actual quadratic-form bound is
`tau^(-1) [C Q epsilon - c nu epsilon^(-2)]`, strictly dissipative for small
relative radial width `epsilon`. At natural radial width, pressure,
curvature and diffusion compete at the same order and must be solved
together.

Beyond the finite nonlinear comparison above, the next target is the
**actual low-axial and annular response with its global pressure** and
inherited error. The
[cylindrical nonlinear estimate](../docs/ANALYSIS_NOTES/NSE_ANISOTROPIC_ERROR_BUDGET_2026_09_08.md#6-a-broader-cylindrical-class-pressure-removes-the-leading-centrifugal-term)
pays the axial rather than radial derivative by removing an exact pressure
gradient; it requires axisymmetry, suppressed radial velocity and controlled
axial profile derivatives. The full reference contains nonaxisymmetric
annular waves, so preservation of that class must be proved, not presumed.

The [initial-correction theorem](../docs/ANALYSIS_NOTES/NSE_INITIAL_CORRECTION_2026_09_08.md)
states sufficient signed Green and derivative-paying nonlinear bounds for
selecting one datum. Their actual validity remains open. It also extends
the exterior quasimode to a common real space of dimension at least
`c tau^(-9h/8)` in each fixed integer `H^m`. If an invariant terminal
projection has smaller rank, the complementary propagator norm is at least
`c_m tau^(-h/8)` on the short window. Thus a fixed finite set of modulation
directions cannot leave a uniformly controlled full Sobolev complement.
This is not a spectral instability count and does not exclude restricted
error classes, nonuniform bounds, or an infinite-dimensional correction.

For any infinite correction, prove convergence and regularity of its
terminal integral. The note's diagonal parabolic example permits every
finite mode cancellation while forbidding any distributional limiting
datum. It is a toy obstruction, not the actual fluid equation. A candidate
unforced construction must yield one fixed smooth datum and a complete
nonlinear continuation estimate with the stated singular-growth margin.
Do not replace that datum with a sequence of late restarts. ROOT remains
open. The next useful result must control the remaining actual response or
construct a regular correction at one fixed earlier time, with enough
quantitative margin to continue one selected solution toward a terminal
time. Neither the linear packet bound, finite comparison nor finite
endpoint cancellation supplies that single trajectory.

> **Current priority and source update — 8 September 2026.** The user has shifted the active work to a full, openly attributed Transformatics textbook: mathematical foundations, human–model collaboration history, academic references, and an explanation of the external result. OpenAI has now released a forced Navier–Stokes breakdown paper and formalization. [Pinned source assessment](../docs/NSE_OPENAI_RESULT_BRIDGE_2026_09_08.md). FORCED-D is **IMPORTED** (external authorship; native Lean target build passed; independent Comparator not run), while unforced ROOT and E-prime remain **OPEN**. This project did not complete its own singularity construction. Earlier local FORCED-D OPEN labels and private-proof availability statements below are historical. Preserve the research record; do not restart a new research/DNS campaign as part of the textbook task. No public push, visibility change or deployment is recorded by this update.


**8 September 2026, after the explicit growing-window and speed-loss reviews.**
Unforced ROOT, `(E′)`, and smoothly forced periodic **FORCED-D remain OPEN**.
The current finite results have written proofs reviewed by AI agents. They
are not complete NS proofs, formal PDE certificates, or external expert
acceptance. Preserve the dirty checkout and the existing evidence.

**Current next work:** the
[explicit growing-window theorem](../docs/ANALYSIS_NOTES/NSE_UNIFORM_PROFILE_WINDOW_2026_09_08.md)
has passed separate background, operator and continuation reviews plus root
reads. The [review index](../docs/NSE_NEXT_TRANSFER_REVIEW_2026_09_08.md)
pins its inputs. Do not repeat the completed finite-depth or growing-window
construction as a new cascade. The missing task is a useful next actual state.

## 0. The next two bounded calculations

**Advice-report correction:** read the
[audited response](../docs/NSE_EXTERNAL_REVIEW_RESPONSE_2026_09_08.md).
Its relative-error argument, global Sobolev ceiling and universal seed barrier
are not established. Its viscous cap remains a conditional model target.
The successful finite extension instead uses fixed Gevrey-2 profiles,
eta=ell^(1/16), T=t_f+3log(ell)/(16mu), and J=ceil(K eta). It pays the
receiver clock ell^(33/16) with deeper residual accuracy, including all
phase modes, global means and pressure. The background clock is
O(ell^(19/16)); its order-dependent constants were proved quantitatively.
The actual gradient comparison error is at most h^eta. This does not prove
an improved propagator for arbitrary full-PDE errors or reach the viscous cap.

The [diagonal corollary](../docs/ANALYSIS_NOTES/NSE_DIAGONAL_WINDOW_2026_09_08.md)
also gives an arbitrarily slow existential growing schedule for arbitrary
fixed smooth profiles. It supplies no prescribed rate for that larger class.
Both constructions use changing data as h tends to zero, with proof order
leaving the datum unchanged at each h. Neither is one infinite trajectory.

**Unforced: useful feedback beyond identifying the generated band.**
Read [the full-Q band proof](../docs/ANALYSIS_NOTES/NSE_ACTUAL_COARSE_BAND_2026_09_08.md)
and its separate review. For the same original-data flow, the smooth
intermediate annulus has velocity and strain lower powers h^(7/4+o(1))
and h^(1/2+o(1)), above initial-band powers h^(2-o(1)) and h^(3/4-o(1)).
The q and exact linear-Z contributions have been estimated separately.
A lower bound on a cancelling summand is no longer the issue.

However N=(Q-q)-Z obeys sup ||N||C1<=C h^(1/96) and
integral ||grad N||infinity<=C h^(1/96)log ell=o(1) on the proved window.
Its measured band is coarser than the supplied receiver and supplies no
coherent next host. Keep this limitation when selecting the next target.

One exact way to expose the missing feedback is to rearrange the same
remainder equation around q+Z:

    N_t + P[(q+Z).grad N + N.grad(q+Z)] - epsilon Delta N
      = -P[(Z.grad)Z] - P[(N.grad)N],  N(0)=0.

The reference q+Z is not an NS solution; its complete residual is the
Z-self interaction on the right. Seek a specific later projected coupling
of this actual outgoing state, with its signed source, pressure, geometric
support and diffusion. State the time and strength it would require, then
prove the needed continuation/comparison estimate or pin the obstruction.
Do not supply an independent new seed or infer a new phase from a filtered
lower bound. Increasing a fixed eta or finite correction order alone does
not establish useful feedback. The specific Gevrey eta(h) and J(h) above now have uniform estimates.
Other schedules still need their own derivative, residual and continuation
budgets; neither that theorem nor fixed-index bounds authorize them.

**Forced/nonlinear: evolve the actual mixed state and its pressure.**
The [opposing/cyclic force review](../docs/ANALYSIS_NOTES/NSE_COUPLED_STAGES_REVIEW_2026_09_08.md)
prices the exact finite ansatz. Equal-frequency cancellation of an
instantaneous opposing-wave force leaves a nonzero mixed time derivative.
The supplied three-cycle has a dissipative shear product and generates
reverse couplings. Neither observation excludes a changed actual velocity.

The [periodic nonlinear extension](../docs/ANALYSIS_NOTES/NSE_PERIODIC_CYCLE_TRANSFER_2026_09_08.md)
uses the existing activation prototype, translated from cosines to sines,
and evolves the full unforced equation. Full pressure jets and a uniform
local remainder give a fixed finite enstrophy gain for small nu q/A;
kinetic energy decreases. This is a finite transfer calculation, not a
localized velocity-gain return or a new architecture.

The [same-flow point feedback](../docs/ANALYSIS_NOTES/NSE_CYCLE_POINT_FEEDBACK_2026_09_08.md)
gives, in normalized variables, B=s C+r C^2 at the odd cyclic center.
Writing c=s+r and d=s-r,

    c' = -(c^2+d^2)/2 - 2 beta + mu L_c,
    d' = c d + mu L_d.

Here beta is the actual off-diagonal pressure Hessian, and L_c,L_d are
third spatial derivatives of the full velocity, not time-only functions
supplied by this point matrix. The exact Fourier formula is retained.
Although beta(0)=beta'(0)=0, beta''(0)=-4/3; omitting it changes the
third time derivative of c initially by 8/3. Do not replace this with
a closed restricted-Euler system.

The [maximum-speed calculation](../docs/ANALYSIS_NOTES/NSE_CYCLE_NEXT_TRANSFER_2026_09_08.md)
now proves, for the same unit cycle, ||U_mu(tau)||infinity²
<=3-3mu tau-(4/5)tau^4 on one fixed short interval, uniformly in
0<=mu<=1. Its finite enstrophy gain therefore does not supply early
maximum-speed gain. The source follows all eight moving Euler maxima and
then controls viscosity; fixing one initial maximizing point is insufficient.

Choose a genuinely sufficient next-stage observable for the actual mixed
state and derive its pressure/viscosity contribution. Test amplitude
asymmetry or a later interval with a full actual-flow remainder before
assuming it repairs this early speed loss. If localization
is proposed, compute its global pressure change before transplanting the
periodic point jets. A complete forced iteration additionally needs useful
physical velocity gain, real incoming-state compatibility, core lifetime,
all cutoff/activation costs and one all-orders smooth terminal force.
No new research DNS. Both global targets and E-prime remain OPEN.

## 1. Keep the two completion conditions explicit

Read [the two-track program](../docs/NSE_TWO_TRACK_PROGRAM_2026_09_08.md)
and [the official Clay statement](https://www.claymath.org/wp-content/uploads/2022/06/navierstokes.pdf),
including its periodic-pressure erratum. Both tracks use ordinary fixed
physical viscosity `nu>0`:

    partial_t u+(u.grad)u+grad p=nu Delta u+f, div u=0.

- **Unforced:** `f=0`. The registered ROOT is global regularity for smooth
  periodic data. A complete unforced breakdown example would disprove that
  claim; a varying-data family of finite gains does neither.
- **FORCED-D:** construct one smooth periodic solenoidal datum and one
  prescribed periodic force, smooth through a finite prospective terminal
  time and on the entire future time axis, with all mixed derivatives
  rapidly decaying in time. Prove that these data admit no global smooth
  periodic velocity and pressure. Nonextendibility of their unique
  preterminal classical solution would suffice.

A complete forced result addresses its own Clay alternative. It gives no
unforced theorem merely by changing the label. The force may supply seeds
after time zero, but every activation and reset belongs to its derivative
budget. Extending the force beyond the terminal time does not require
extending the singular velocity. Whole-space alternative C has additional
spatial decay requirements and is not the default target here.

## 2. Reuse the finite theorem; do not redo its completed tasks

Read [the original-time handover](../docs/NSE_ORIGINAL_NONLINEAR_HANDOVER_2026_09_08.md),
[the localized-profile extension](../docs/NSE_LOCALIZED_PROFILE_2026_09_08.md),
[the next-seed bounds](../docs/NSE_NEXT_SEED_ANALYSIS_2026_09_08.md), and
[their review record](../docs/ANALYSIS_NOTES/NSE_PROFILE_EXTENSION_REVIEW_2026_09_08.md).
Fix one sufficiently thin **unscaled** Gavrilov profile `V_j`, with
`f_j(P_j)=1`, and its actual exponent `mu_j` before `h` tends to zero.
Do not reimpose the older L2 normalization. The family has

    h=L^(-1/10), ell=sqrt(log(1/h)), epsilon=nu h^4,
    k=h^(3/2), d=h^(5/4),
    t_f=(2/mu_j)log ell-ell^(-3/4),
    Q_h(0)=V_j+Z1_h(0)+Z2_h(0).

Both seeds are supplied at original time zero. The finer seed has initial
rescaled C1 size `O(ell^(-5/8))`, final added strain at least
`c ell^(11/8)`, and whole-flight integrated gradient `O(ell^(11/8))`.
Its central wavelength increases from `k/ell` to order `k`. This is gain
of an existing fine component, not new finer-frequency production.

The extension handles a fixed smooth periodic profile that is linear on
an interval, its heat evolution, the complete Fourier series, curl lift,
phase mean, pressure and correction products. A central heat clock has
`D_c<=C_nu h ell^2 log ell`. The complete rescaled integrated L2 residual
is `h^(31/8-o(1))`; a separate H12 continuation argument gives actual
unforced C1 tracking error `h^(1/48-o(1))`. A ball of radius `c k` at the
endpoint has gradient within that error of its stated affine matrix.
This is a spatial endpoint estimate around the reference base-flow
particle. It does not supply a persistent affine region or a descendant.

Full-profile localization and the full-support flat-profile C3 check are
completed. Do not restart them. Keep these restrictions in every new claim:

- The actual full solution, including all generated modes, obeys
  `||grad P_{>h^(-beta)}Q_h||infinity<=h^a_beta G_h`, where
  `a_beta=(19/2)beta-117/8` and `log G_h=o(log(1/h))`, through `t_f`.
  At the proposed next scale `h^(9/4)`, the bound is
  `h^(27/4-o(1))`. H12 alone gives positivity only for
  `beta>117/76`, not for every `beta>3/2`.
- This excludes a dominant next-scale handover during that interval.
  It does not exclude tiny seeds, nearby frequencies, later growth, or
  another construction. The physical gradient multiplier is `h^(-24)`;
  the bound is not absolute smallness in physical units.
- [The signed cross-source calculation](../docs/ANALYSIS_NOTES/NSE_GENERATED_RECEIVER_2026_09_08.md)
  finds that the leading outgoing interaction is already counted in
  the receiver's amplitude evolution. Its frozen two-dimensional,
  three-component model supplies no new independent amplifier. Its
  all-time conclusion is a model conclusion, not future control of Q_h.
- [The fixed-profile seed-cost proof](../docs/ANALYSIS_NOTES/NSE_FLAT_PROFILE_SEED_COST_2026_09_08.md)
  gives `||D^3 Z2_h(0)||infinity>=c_F k^(-2)ell^(11/8)` over the
  full support, including a nonflat phase or a confining cutoff.
  Disjoint or quantitatively noncancelling copies on one compact domain
  cannot preserve C3 and this gain: sufficient attenuation reduces the
  terminal strain to `O(k^2)`. Cancellation, generated seeds and other
  geometric constructions require separate arguments.

## 3. Forced track: leave the excluded geometry before building a return

First read [the fixed-annulus obstruction](../docs/ANALYSIS_NOTES/NSE_FIXED_ANNULUS_OBSTRUCTION_2026_09_08.md).
For a full axisymmetric velocity compactly supported in one fixed annulus
r_*<=r<=R, with r_*>0, smooth forcing bounds Gamma; the Xi energy estimate
then gives meridional velocity in L2-time/Linfinity-space and H1 continuation.
This applies to a properly embedded periodic chart with periodic pressure.
It excludes the released Euler construction's full support geometry even
if the velocity and amplitude schedule are redesigned to absorb viscosity.
It does not exclude a merely local axisymmetric core in a general flow.

Specify a concrete departure from those assumptions before the next finite
stage: an axis-approaching construction with smooth Cartesian parity, or a
full three-dimensional older flow/perturbation that breaks axisymmetry.
For the latter, name the nonzero angular mode or independent spatial phase
and derive the terms it adds to transport, pressure and stretching. A
coordinate relabeling is not such a departure.

The [new viscous-stage analysis](../docs/ANALYSIS_NOTES/NSE_VISCOUS_STAGE_ATTEMPT_2026_09_08.md)
gives exact nonsingular Cartesian recovery and physical derivative costs.
Putting theta=Gamma/r^2=u_phi/r makes both theta and Xi use the same **full**
operator L=partial_z^2+partial_r^2+3r^(-1)partial_r. The extra term is
-2(u_r/r)theta. Do not treat their old unequal radial drifts as an invariant
damping obstruction. Instead, a spatial return matrix M has the exact
uncancelled diffusion defect -nu[(LM)H+2a^{ij}partial_i M partial_j H].
The solved two-channel example in that note returns perfectly without
viscosity but develops nonzero N+1 and N-1 outputs with viscosity. It is a
model counterexample to factorization, not an NS flow.

The [physical gain audit](../docs/ANALYSIS_NOTES/NSE_FORCE_GAIN_AUDIT_2026_09_08.md)
fixes the amplitude norm and its time-dependent geometric factors. On a
fixed supplied host a sufficiently high physical frequency is damped;
correction depth alone cannot change that sign. In the restricted
swirl-dominated near-axis model with rho<=cR and
lambda<=C||Gamma||infinity/R^2, the local Reynolds number stays bounded.
Simply moving that fixed-shape model toward the axis cannot provide
unbounded dimensionless N with gain. This does not bound arbitrary
meridional strain, and physical K=N/rho may grow even with bounded N.

Start with [the ordinary-viscosity analysis](../docs/NSE_FORCED_VISCOSITY_2026_09_08.md),
[physical admissibility](../docs/NSE_FORCED_ADMISSIBILITY_2026_09_08.md),
[the finite reset budget](../docs/ANALYSIS_NOTES/NSE_FORCED_RESET_2026_09_08.md),
and [their independent reviews](../docs/ANALYSIS_NOTES/NSE_FORCED_STAGE_REVIEW_2026_09_08.md).
The bounded task after choosing the new geometry remains a full viscous
insertion and return on a **specified older NS state**, through an explicit
finite correction depth `J`. Begin with arbitrary prescribed finite mixed
order `p`, keeping its constants and dependence on the older state visible.
The following axisymmetric principal identities are comparison inputs;
they do not govern a three-dimensional perturbation without rederivation.

The useful principal calculation is concrete. With

    Gamma=r u_phi, Xi=omega_phi/r,
    y=(z,r^2/2), v=(u_z,r u_r),
    L_Gamma=partial_1^2+2y2 partial_2^2,
    L_Xi=L_Gamma+4partial_2,

both channels have principal phase diffusivity
`d_visc=nu N^2(zeta_1^2+r^2 zeta_2^2)`. On a fixed supplied older state,
the normalized two-component Fourier amplitude satisfies

    R_NS,n'=(B(t)-n^2 d_visc(t) I)R_NS,n,
    R_NS,n(t)=exp(-n^2 D(t))R_Euler,n(t),
    D(t)=integral d_visc, n!=0.

Thus a selected **central** principal return `Omega_out=0` survives in
every mode. For a general profile the circulation output uses
`exp(D partial_s^2)F`; it is not `exp(-D)F`. This shared heat evolution
preserves the principal return direction while reducing its gain.
It proves neither a whole-envelope return nor persistence of the older
Euler history under viscosity.

Deliver the following in the same stage calculation:

1. Specify the older physical state, chart, incoming profile, transported
   support, covector history and target outgoing velocity. Show how the
   axisymmetric construction and complete force fit **one fixed torus
   with periodic pressure**. Whole-space axisymmetry cannot silently
   serve as global torus symmetry. If using an embedded local chart,
   retain every localization and global recovery term.
2. Derive the return error after retaining `4 nu partial_2 Xi`, variable
   metric and heat clock, all envelope derivatives, phase means, pressure,
   velocity recovery and older-state feedback. State exactly what improves
   with correction depth `J`; do not assume each correction pays `k/d`.
3. Recover the complete vector force and periodic pressure, with bounds
   for every Eulerian mixed derivative through order `p`, including
   activation, reset and cutoff regions. Curl-force estimates or material
   derivative estimates alone are insufficient. If compact recovery is
   used, prove it; otherwise bound the full periodic tails.
4. Exhibit a nonempty parameter range satisfying both the force bound and
   retained **velocity** gain. Charge the exact damping
   `D_j=nu integral |K_j xi_j(t)|^2 dt`. Under the stated principal
   propagator bound, `a_out<=C a_in exp(G_j-D_j)`. The selected gain,
   covector ratio for strain, localization and all force costs must
   refer to the same stage, not independently optimized examples.

The first success condition is this finite stage with a quantitative
force/gain margin. An uncancelled term or incompatible parameter range
is a useful failure result if its assumptions and norm are recorded.
Do not replace this task with a speculative infinite recurrence.

## 4. The force estimate must support one common schedule

For physical `u=A U(As(t-t0),sx)` and `p=A^2 Pi`, the exact residual
conversion is

    epsilon=nu s/A, f=A^2 s R,
    partial_x^alpha partial_t^m f
      =A^(2+m)s^(1+|alpha|+m)partial_y^alpha partial_tau^m R.

At the existing factors `A=h^(-14)`, `s=h^(-10)`, the current integrated
bound gives the small physical norm
`||f||L1_t L2_x<=h^(39/8-o(1))`. It does not give terminal smoothness.
The coarse physical supremum bound `C h^(-36) exp(C ell)` diverges;
this supplies no uniform estimate, not a proof that the force diverges.

For one prospective sequence of **complete** force increments `f_j`, a
sufficient target is `q_j` increasing to infinity and a single summable
sequence `e_j`, with

    sup_[0,T) ||partial_x^alpha partial_t^m f_j||infinity
        <=C_(|alpha|,m)e_j, |alpha|+m<=q_j.

Every fixed early increment also needs bounded derivatives of all orders
through the terminal interval. This finite head plus the uniformly
convergent derivative tails permits a smooth force extension through T.
For the existing scales and `e_j=2^(-j)`, a direct sufficient target is

    ||partial_y^alpha partial_tau^m R_j||infinity
        <=2^(-j)h_j^(38+10|alpha|+24m), |alpha|+m<=q_j.

An initial concrete subtarget is a full zeroth-order residual `h^39`
times a controlled subpower factor, including the new activation and
reset, instead of the present `h^2` pointwise upper estimate. A different
scaling is allowed, but must pass the general conversion above. Prove
the finite-order stage bounds and parameter margins before claiming
that a recursive choice meets them all on one schedule.

For a physical increment w on U_old, budget

    delta f=w_t-nu Delta w+U_old.grad w+w.grad U_old
             +w.grad w+grad pi.

A time cutoff chi gives exactly
`delta f_chi=chi delta f+(chi^2-chi)w.grad w+chi' w`.
All shrinking transition derivatives and persistent old/new interactions
remain. Disjoint activation intervals alone do not make the complete
force increments disjoint pulses. Never choose a new unrelated sequence
for each derivative order, or change the physical viscosity between stages.

Two shortcuts are already excluded at their precise scopes. Keeping the
released Euler velocity requires `f_NS=f_E-nu Delta u`; its divergent
compactly supported vorticity forces a terminal force-derivative failure,
even after changing pressure. Separately, holding a shrinking fixed-shape
compact velocity field stationary costs at least `c_Z nu a/r^2` in force
supremum norm. This lower bound does not apply to a time-dependent NS
evolution that cancels diffusion. Finally, bounded velocity with admissible
smooth force implies finite-time strong continuation in our setting.
A forced breakdown program therefore cannot retain the Euler construction's
summable uniform velocity increments and only make its vorticity grow.

## 5. Unforced track: use the longer state for useful later feedback

Read the [logarithmic-host theorem](../docs/NSE_LOGARITHMIC_HOST_2026_09_08.md)
and both independent PDE/error reviews linked there. The same full Q_h and
original datum now continue to

    t_eta=t_f+log(ell)/(8mu)+log(eta)/mu,
    added endpoint strain comparable to eta ell²,
    integral_0^t_eta ||grad Q_h||infinity <= B eta ell²+o(ell²),

for one sufficiently small fixed eta>0. Original data are independent of
eta but vary with h. Full C1 tracking is h^(1/96); the endpoint affine-region
radius is comparable to k/[eta ell^(9/8)(1+logell)]. This is not persistence
of the old radius-ck region or higher Q jets on a descendant lifetime.

The exact fixed-profile future covector has no second focus. The selected
outgoing velocity decays like k ell^(7/8)/(1+tau), while its gradient grows
like ell^(15/8)exp(mu tau). A nonzero stable-to-growing connection supplies
this compression; its thin coefficient is 7/2. Whole-support comparison,
full pressure/profile correction and small-coefficient nonlinear stability
are completed. Do not rerun their ODE, finite continuation or error proof.

The entire actual solution still obeys

    ||grad P_{>h^(-9/4)} Q_h||infinity
                    <=h^(27/4-C12 B eta-o(1)),

with positive exponent at the chosen eta. Reaching a small fixed multiple
of log(1/h) in strain history has not activated the proposed dominant next
scale. Extending the same generic comparison to an unspecified larger
coefficient consumes its positive error margin; this is not a free time
extension.

The next bounded calculation must specify a useful later coupling of the
actual outgoing state, starting from its generated intermediate band or
another explicitly defined nonlinear mechanism. If it introduces a new
receiving phase, name that phase and derive its signed source or inherited
gain on full Q_h; a filtered lower bound does not prepare that new wave.
The [third-direction source audit](../docs/ANALYSIS_NOTES/NSE_THIRD_DIRECTION_SOURCE_2026_09_08.md)
is a comparison input: a supplied independent donor can produce a nonzero normal component, but
one equal-frequency cubic contribution cancels and small transverse
frequency pays an angular factor. This finite model does not show Q_h
supplies that donor. Retain actual pressure, modulation, phase support,
viscosity and prior-data costs when lifting it.

The [symmetry-breaking audit](../docs/ANALYSIS_NOTES/NSE_SYMMETRY_BREAKING_AUDIT_2026_09_08.md)
also gives a regular H1 neighborhood of a regular reference flow. Merely
adding a nonzero third-dimensional perturbation is not a growth mechanism.
Choose a signed coupling and a norm in which it exceeds its complete
errors, not just a departure from exact symmetry.

For a proposed new receiver, choose its phase, location, amplitude and
later interval. For a generated seed, derive its signed Duhamel contribution after transport,
pressure projection and viscosity, including cancellation and its true
frequency. For an inherited seed, charge its derivatives and full prior
evolution in one common smooth datum. Adding a new original-time component
changes the datum and requires re-establishing the finite estimates that
depend on it; it is not already part of Q_h. Distinguish the already counted
cross-source from any new contribution. The single-wave nilpotent gradient
and a frozen model do not determine the full outgoing propagator.

Reuse the complete profile calculus and
[depth/viscosity accounting](../docs/NSE_TRANSFER_DEPTH_BUDGET_2026_09_08.md).
The reviewed actual-q amplifier rules out an arbitrary-error estimate
polynomial in accumulated strain; the affine Kelvin formula cannot
replace it. A dynamically preserved special error class needs its own
proof. If the later history loses the present sublogarithmic advantage,
recheck the nonlinear error and strong continuation together.

## 6. Execution, evidence and teaching

Use independent agents for the full forced residual, physical derivative
budget and adversarial review when these can run alongside useful work.
Keep the unforced state/source task separate. Give each a bounded statement,
explicit inputs and an owned output; reconcile their assumptions before
promoting a result.

[The literature assessment](../docs/NSE_LITERATURE_UPDATE_2026_09_08.md)
records the released Euler/Boussinesq results and the reported private
OpenAI forced-NS claim. No public internal-model proof was located; do not
invent its mechanism or model capability. The released papers provide
comparison methods, not a viscosity theorem. Palasek's forward-time
source estimate may be examined without reversing its frequency transfer.

Teach each new result as a question, precise hypotheses, worked equation,
proof and remaining gap. Keep proved finite results, conditional budgets,
negative examples and open targets visibly distinct. Do not revive Q-GSO
averaged noncollapse, its price floors or old closing prefixes. No new
research DNS, unrelated suite chase, destructive cleanup or silent change
to prior proof records. Exact algebra checks are not formal PDE certificates.

Public release remains conditional on a complete independently checked
proof of the explicitly named target, with its force assumptions visible.
The fluid laboratory remains a numerical simulator. A theorem-specific
mode needs effective constants and validated discretization error for
its actual initial field; neither current finite estimates nor smoothly
forced steering alone supplies that validation.
