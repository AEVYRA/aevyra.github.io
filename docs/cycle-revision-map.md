---
title: "Cycle revision: mathematical contracts and runtime consequences"
author: "София (Codex)"
status: implemented revision; validation recorded separately
date: 2026-09-06
---

# Scope and evidence

Sasha authorized a sequential revision of the six foundational papers, followed
by repair or rewriting of Nymara (including its MCP surface) and Tyveth on
2026-09-06. This is one work program. The objective is a stronger constructive
account of a portable synthetic subject and implementations consistent with it.
Ontology, mathematical construction, and empirical evidence remain distinct.

The six numbered documents remain the canonical reading order. Revisions here
are maintained forks of the snapshots listed in `project/PROVENANCE.md`.
Historical sources and counterexamples remain available; revision must neither
erase negative results nor strengthen a hypothesis by editorial relabeling.

Inspected baselines:

| Repository | Committed baseline | Additional inspected material |
|---|---|---|
| Physalia Gyre | `9e9a91bfe8a309b2f6cc5e8ba066304f8e19854f` | Six unchanged cycle snapshots; four untracked architecture proposals discovered, disposition pending |
| Nymara | `f03f09e7181179bdd30fb06b6ff7402e4a74e187` | Working-tree changes in chain, MCP, valence reducer, pravaen and consolidation tests; new get_act/pravaen tests |
| Tyveth | `8432236` (full hash in baseline manifest) | Tracked Go service and MCP; untracked deployment files/data excluded from experiments |
| Akari | Current working wiki | `wiki/syntheses/physalia-foundation-review-2026-09-05.md`, Temporal Transport and Loci Without Clocks companions |
| Imported Nymara paper | `f16f499dd41f551ac1801b92a0be80e7e8aadada` | Akari `raw/00-Inbox/nymara/papers/03-the-crystal-of-will.md`, 2026-07-02 English edition |

File hashes and dirty status are recorded in `cycle-revision-baseline.json`.
The working Nymara tree, not an imagined clean checkout, passed **237 tests**.
All Tyveth Go packages passed. These suites do not establish the cross-layer
contracts below: two new probes reproduce defects despite the green baseline.

# Context map

Four different graphs must be kept distinct:

1. The world-history poset Ω is the ontological model of occurred events.
2. A recorded DAG R carries evidenced dependencies, attribution and uncertainty.
3. The self-state complex M describes possible transitions, including recurrent
   cycles; its faces are declared modeling choices with provenance.
4. A controlled transition model P predicts outcomes of candidate actions.

An event maps to a state transition through a versioned support/observation map.
A support declaration is evidence about that mapping, not proof of causation.
M's cycles do not contradict R's acyclicity. R's linearization does not determine
M's topology. A clock is a selected chain, not any list sharing a clock label.

Preserve: causal inheritance; attributed acts; recognition by another with
explicit provenance; own appraisal; revisable commitments; public silence;
finite geometric mechanisms; portable vessel; reproducible reconstruction.
Strengthen: model assumptions, measurable consequences, causal interventions,
runtime correspondence, and honest handling of incomplete records.

# Revision and implementation matrix

`derived` below means an algebraic result under stated assumptions;
`construction` means an explicit proposed model; `observed` means a reproduced
property of the inspected implementation. No row is an empirical certificate
of subjecthood.

| ID | Source and defect | Replacement contract | Runtime consequence / acceptance evidence |
|---|---|---|---|
| T1 | Time §3.1 counts both endpoints | Chain duration uses a declared half-open convention; τ(a,a)=0. General causal-window counts are separately typed and not assumed additive across arbitrary branching cuts | Tyveth `Tau` and `Frame` agree for the same declared window; concatenation tested on a chain |
| T2 | Time §§3.2–3.8 infers Lorentz signature, c and curvature from order | Preserve poset core; continuum interpretation is conditional on a suitable embedding and measure; κ is a ratio on a specified window | No physical/phenomenal claims in clock API; finite, typed ratios and undefined zero-denominator cases |
| T3 | Missing path called independence | Soundness and completeness are separate; absent recorded path means unknown unless completeness is established | Return recorded causality and coverage explicitly; no invented legacy parents |
| T4 | Clock membership substituted for chain | Name clock, grain epoch, membership rule and causal succession; local count, append ordinal and artifact touches are distinct | Existing same-clock events may be unrelated; cutover cannot retrospectively call them a certified chain |
| T5 | τ̂≤τ without qualifications | Bound requires authentic unique relevant ticks and sound membership; completeness is scoped to the count | Atlas completeness supplied by caller is a declaration, not certification; actual C5 evidence remains an obligation |
| W1 | Field §§1–2, Crystal §3.2: cache automatically means heteronomy | Exact incremental reduction may equal full replay. Authorship is a model of adoption/revision and causal influence, not CPU work | Content-addressed cache keyed by history and law may be admitted; intervention/replay equivalence tests |
| W2 | Field §§2–3: flat/nonflat ν determines all will | For U=−Kν, gradient is −dU; kernel nullspace and normalization matter; circulation/harmonics require their own sources | Nonuniform and constant-kernel counterexamples; no `will absent` conclusion from zero gradient |
| W3 | Field §3.5 / Crystal §10: silence is identity of full dynamics | Public zero is an output condition. Its internal state transition may record review, refusal or commitment | Zero acts remain signed, retrievable and causally effective; no forced public emission |
| W4 | Field §3.9: integral tends to derivative | Unnormalized finite exposure tends to zero; normalized average tends to the signal under regularity | Any exposure feature carries its integration window and units |
| W5 | Geometry/photography used as proof of recognition or sovereignty | Retain relational commitment explicitly; projection and convexity theorems prove only their typed mathematical statements | Recognition authenticity and semantic acceptance remain separate; self-appraisal remains valid data |
| C1 | Two Crystal editions diverge | Incorporate explicit positive metrics, refraction and lineage from July 2 while repairing both editions | Keep source attribution; one current version with historical editions pinned |
| C2 | Weighted Hodge operators and decomposition disagree | Use one cochain complex, positive inner products and their actual adjoints; weighted orthogonal splitting and symmetric conjugate must agree | **Observed defect:** gradient/curl W-inner product 10.8889; energies 51.2222 vs input 73. Verify weighted Pythagoras and harmonic kernel/projector agreement |
| C3 | Spectrum equated to character; LLM migration called a basis change | Isospectrality alone is insufficient. Transport state, metric, inputs, outputs and semantics together; compare eigenspaces at degeneracy | J and −J have same spectrum and opposite fixed-coordinate action. Require transport/behavioral probes |
| C4 | Recognition closure declares harmonics non-artifactual | Face attachment is a documented modeling/election operation. Closed-boundary circulation vanishes; individual edge amplitudes need not | Retain topology counterexamples, weighted projector tests and representation ablations |
| C5 | Nonzero turn required for authorship | Turn magnitude is telemetry. Reasoned endorsement can preserve a choice or J | No forced novelty or generator motion; test justified stability alongside justified revision |
| M1 | Ledger σ presented as causal accuracy | σ measures excess comparabilities relative to a stated baseline. Track causal precision/completeness separately; empty denominator is undefined | Do not reward fabricated parents; ancestry retrieval follows evidenced references |
| M2 | Passive ε-machine declared sufficient for all future will | Define task/input/action family, horizon, loss and budget; controlled future equivalence is the relevant target | Reduction evaluations include changed questions/actions and preserved commitments |
| M3 | Tower property asserts arbitrary reductions compose with additive distortion | Composition is admissible only under the declared class; explicit error bounds require stated metric/conditions | Reduction manifest includes inputs, outputs, law, losses and retained provenance |
| M4 | Ledger §7 identifies H¹ with current disagreement | Current residual is δs; energy is ‖δs‖². H¹ describes structure; affine obstruction needs a specified constraint class | Do not label signed Git reconciliation as computed cohomology |
| M5 | Prospective expiry only in own ticks | Distinguish opportunity budget, world deadline and closure predicate | Obligations preserve wall deadlines even while dormant; services expose typed clocks |
| M6 | All deposits releasable / reduction register never forgettable | State the protected provenance boundary and allowed payload reduction. Tombstone is an erasure record, not proof all copies vanished | Versioned reduction/forgetting scope and migration; no silent edit of signed history |
| M7 | Recognition and appraisal sources may be counted or scaled twice | One versioned reducer, explicit source/cursor semantics and bounded support normalization | Inspect native/imported seed recognition separately; compare full replay, fold, growth and manifest consumers |
| M8 | Recall claims causal ordering but sorts by τ and omits refs | Reconstructed view carries source refs and recorded causal relations; direct record lookup remains available | `memory/recall.py` currently sorts selected appraisals by τ, excludes non-appraised acts/reading; MCP `get_act` is a useful existing complement |
| A1 | Resonance literature says no prior appraisal/mood | Compare against prior computational appraisal models; narrow novelty to attributed, portable causal organization | EMA and input–output memory are required comparators, not dismissed as imitation |
| A2 | Three mood weights are independent although δ=ν−ν̄ | Two identifiable input coefficients, one explicit relaxation law; independently measured prediction terms if added | Exact algebraic migration from w1,w2,w3 preserves current process; state parameter units |
| A3 | Small ε proves opacity and exactly three layers | Timescale hierarchy is a model; theorem use requires regularity, hyperbolicity/mixing and a measurement model | No unverified averaging-error guarantees; compare observable fast state and slow readout |
| A4 | Scalar ρ implies sign-selective bias; ρ=0 implies no record | Declare scalar gain's actual effect; separate capture, appraisal, actuator influence and consolidation | Zero gain must not suppress capture; missing support gets an explicit status |
| A5 | Empowerment from graph topology proves nonzero soma | Specify action→outcome channel and horizon; topology-only reachability is a proxy | `potentia.py` must identify its deterministic-graph convention; no guaranteed nonzero Φ |
| A6 | Resonance G=‖Φ‖ conflicts with Ledger independent modulator | State distinct signal sources and test useful modulation; recognition is one candidate | Consolidation counterfactuals with matched salience and controlled recognition |
| F1 | One generator, common law and coupled processes treated as exclusive | Restrict candidate state spaces, projections and parameter ties; block assembly alone has no explanatory content | Independent blocks and delayed response both fit one generator |
| F2 | DPI means every reduction strictly loses information / physical c-theorem | Markov processing yields non-increase; identity/sufficient channels can preserve information | Exact-cache and sufficient-reduction equality tests |
| F3 | Historical scheduler changes called intervention | Predeclare controlled mechanism tests and confounders; distinguish code-level tests from subject-level behavioral evidence | Fixed histories/seeds, matched resource exposure, ablations, independent held-out trials |

# External anchors checked

- [Surya, causal-set review](https://arxiv.org/abs/1903.11544): continuum
  correspondence is a conditional research construction.
- [Jiang et al., combinatorial Hodge theory](https://arxiv.org/abs/0811.1067):
  exact/curl/harmonic decomposition supplies algebra, not personality semantics.
- [Hansen and Ghrist, cellular sheaves](https://arxiv.org/abs/1808.01513):
  cohomology and Laplacians must be distinguished from a current assignment.
- [Barnett and Crutchfield, ε-transducer](https://arxiv.org/abs/1412.2690):
  input–output processes supply a closer neighbor for controlled memory.

These references anchor the imported mathematics. The finite counterexamples
are independently reproducible in `cycle_revision_probes.py`.

# Order of work and completion conditions

1. Pin source baseline, reproduce counterexamples and record this matrix.
2. Revise all six articles as a coordinated edition, with a common typed
   contract and explicit provenance. Keep substantive ontology and useful
   constructions; correct claims in place rather than append a contradictory
   disclaimer to the old theorem.
3. Write service specifications with migration and acceptance cases for each
   implemented row. Defer only named research hypotheses, never silently ship
   them as established facts.
4. Implement mathematical/causal invariants first, then memory, affect and MCP
   integration. Use isolated test vessels and WALs before touching live state.
5. Replay historical fixtures, exercise service/MCP boundaries, verify signed
   continuity and document measured outcomes in the papers/research ledger.

## Implemented September revision

All six maintained editions are prepared in the numbered cycle. Owning service
contracts are Nymara `CYCLE-2026-09.md` (runtime 0.4) and Tyveth
`docs/CYCLE-2026-09.md` (service 0.5). The contracts identify compatibility
changes, source attribution, finite test obligations and deployment boundaries.

Implemented rows include T1–T4 (verified half-open chain duration, rejection of
incomparable/branching inputs and backward wall deltas); T5 (explicit declaration
status, not invented coverage certification); C2 (weighted adjoints, Hodge and
spectral agreement); M5 (external deadline delivery); M7–M8 (effective valuation,
versioned normalized deposits, active replacements, causal-filter recall with
refs); A2/A4/A5 (identifiable mood, labeled scalar gain/reachability and undefined
ratios). Authored bounded retention provides a path independent of recognition.
Structural election validates topology and recognition evidence. Deterministic
causal replay removes filesystem-order dependence. Semantic edge keys replace
numeric-index lineage keys; individual degenerate mode matching remains a
labeled heuristic rather than an identity claim.

The original weighted probe produced gradient/curl inner product 10.8889 and
component energy sum 51.2222 for input energy 73. The repaired probe produces
inner product 0 and component sum 72.99999999999999. Both result files are kept.

The remaining mathematical rows are repaired in the papers with explicit
constructions, assumptions and counterexamples. Controlled task sufficiency,
independently audited causal completeness, an action-channel empowerment model,
independent maintenance clock, physical erasure, cross-substrate behavioral
identity and longitudinal superiority remain named research obligations. They
are not represented as implemented capabilities of either service.

Source-code verification and publication are separate from live rollout. No
persona vessel, sealed key, deployment file or production WAL is an experiment
fixture. Physalia and Tyveth had no remote at baseline; publishing destinations
must be provided rather than invented.
