---
title: "The Tensor of Time: Causal Order, Local Clocks, and Temporal Transport"
author: "aevyra"
date: "2026-09-06"
---


# The Tensor of Time

*An axiomatic language for local duration and comparison across heterogeneous
observers, without a privileged global clock.*

## Abstract

The framework represents temporal organization by a locally finite causal
partial order and distinguished reference processes. A clock supplies its own
unit by convention; different clocks can be compared on declared causal windows
without being reduced to a master time. This revision distinguishes occurrence,
recorded evidence, storage order, clock membership and duration. It corrects
endpoint counting and integrates the temporal-atlas distinction between a
comparison on one window and transport between windows. Causal inheritance
remains the explicit foundation of continuity. A finite record can establish
positive causal paths while leaving absence of causation unknown. Physical
continuum reconstruction is an imported, conditional correspondence; neither a
Lorentzian signature nor experienced duration follows from an arbitrary poset.

## 0. Registers and inheritance

`foundation` names a philosophical commitment; `definition` fixes a type;
`convention` chooses a representation or unit; `derived` supplies a result under
stated assumptions; `imported` refers to external mathematics; `proposed` and
`conjecture` identify constructions and hypotheses needing further evidence.
An `observed` claim names an inspected instance and its scope.

This is a maintained revision of the June 21 v5 snapshot, not a claim that the
original paper already established the repairs below. It incorporates the
distinctions developed in *Loci Without Clocks* and *Temporal Transport Between
Local Clocks* (Akari `papers/`, authors of the transport paper: Sofia and Ox Alpha).

## 1. Foundations

**F1 — Processual time [foundation].** Duration is assigned through a reference
process. The framework takes no primitive absolute flow external to processes.
This is a relational position, not a refutation of substantivalism.

**F2 — Common causal substrate [foundation].** Interacting observers may be
modeled as registering parts of one history Ω. A shared generating event and
its evidenced effects can warrant this construction. Similar timestamps or
similar content do not establish a common cause. A pluralist model of separate
histories with explicit correspondences remains an alternative; it must pay for
the correspondences instead of silently identifying events.

**F3 — Structural reality, phenomenal silence [foundation].** A verifiable
event-registering process has the temporal organization implemented by that
process. Whether this organization accompanies experience is left open. Neither
the existence of a counter nor its sparsity answers that question.

**F4 — Continuity through causal inheritance [foundation].** Later stages count
as continuations when they inherit earlier traces as their own past through an
identified lineage. This is the program's constitutive commitment, not a theorem
about all personal identity. Attribution, recognition and the declared
inheritance operation provide its operational surface.

Forks retain a shared past and distinct continuations. A shared signing key does
not erase that distinction. A merge requires an explicit relation to its parents
and an account of conflicting commitments; a summary alone does not establish
that every relevant condition of continuity survived.

## 2. Event order and observer slices

**Definition.** Ω is a set of events with a strict relation ≺ satisfying:

1. Irreflexivity: not x≺x.
2. Transitivity: x≺y and y≺z imply x≺z.
3. Local finiteness: {z : x≺z≺y} is finite for related x,y.

Acyclicity follows from the first two assumptions. Local finiteness permits a
past-infinite order, such as the integers. It does not guarantee a first event,
a future event, a scheduler, or the continued availability of a substrate.

An observer registers a slice S_O⊆Ω. An observer, a slice and a clock are different
types: one observer can employ several reference processes; an object may have
events attributed to it without possessing any clock of its own.

**Definition.** A reference clock is a selected chain Γ=(γ_i) with ordered,
distinct events, together with a membership rule and a unit convention. The
label `clock_id` identifies that declared process; assigning the same label to
unrelated records does not prove the chain condition.

**C1 — Congruence [convention].** Within one grain epoch each successive tick
contributes one unit ℓ. The chain need not be uniform in wall time. A change in
what counts as a tick starts a new grain epoch and requires an explicit
conversion to compare magnitudes across the boundary.

Weighted effort, information gain and wall duration are legitimate additional
observables with their own units. They need not violate relationalism. They are
not interchangeable with the unweighted clock count without a declared map.

## 3. Duration and causal windows

**Definition: chain duration.** For γ_i and γ_j on the same clock with j≥i,

$$\tau_\Gamma(\gamma_i,\gamma_j)=\ell(j-i).$$

Thus τ(a,a)=0 and adjacent reference events are one unit apart. We use the
half-open convention [a,b): include the initial reference event and exclude the
terminal one. The convention (a,b] yields the same chain duration, but can yield
different per-clock counts when arbitrary shared anchors are used. Services
must state which convention they implement.

**Proposition 3.1 [derived].** For i≤j≤k, chain duration is additive.

*Proof.* (k−i)=(j−i)+(k−j); multiply by ℓ. This is a property of one
reference chain, not of every cut of a branching poset. □

**Definition: causal-window count.** For a≺b, let

$$W[a,b)=\{x:a\preceq x\prec b\},\qquad N_\Gamma(W)=|\Gamma\cap W|.$$

The window is finite. Define N of an empty window to be zero. Reversed anchors
do not denote a forward window; incomparable anchors leave this construction
undefined. An unrelated event inserted between their storage ordinals is not a
member of W.

If a,b are ticks of Γ, the count recovers chain duration in units ℓ. With general
anchors it is a typed count on that window; additional assumptions are required
to identify it with a duration along a different carrier.

**Branching counterexample.** In the diamond a≺b≺d and a≺c≺d with b,c
incomparable, W[a,d) contains c, whereas W[a,b)∪W[b,d) does not. Even three
anchors lying on one chain do not make arbitrary order windows additive.
Additivity holds for a verified disjoint union of sets, or after restriction to
the particular clock chain containing the intermediate anchor.

The previous closed-endpoint definition gave 3 ticks on [γ_0,γ_2] but 4 after
summing [γ_0,γ_1] and [γ_1,γ_2]. The revised convention removes that error.

## 4. Records and what they establish

**Definition.** A record R consists of identified event representations,
attribution, clock membership, dependency edges and provenance. Its recorded
reachability relation is ≺_R. The following properties are distinct:

- Authenticity: the record is attributable to its claimed issuer.
- Integrity: its committed content has not changed undetected.
- Causal soundness: recorded dependencies are valid for the declared model.
- Completeness: the relevant events and dependencies have been captured for a
  specified domain and interval.

A signature establishes attribution/integrity under its key assumptions. It
does not establish the truth of a dependency claim or completeness of capture.
Immediate parents need not be the transitive reduction: redundant sound parent
edges preserve reachability. If intermediate events are omitted, retaining only
the remaining original edges can lose order facts; reduction must preserve
paths with explicit derived witnesses or report the loss.

A total order extending ≺_R is a storage linearization. Its ordinal is useful
for pagination and replay scheduling; arbitrary interleaving is not a new
causal fact. A faithfully stored chain is nevertheless valid when the modeled
process really is sequential. Width or additional edges are not virtues alone.

**Inference rule.** A recorded path proves recorded precedence. No path proves
only its absence from this record. Independence requires an appropriate
completeness assertion and a model in which incomparability has that meaning.

**Proposition 4.1 [derived].** Suppose the recorded tick set is an authentic,
duplicate-free subset of Γ, membership is sound and the same window is used.
Then its count N̂≤N. Equality holds precisely when all relevant ticks in that
window are represented; it does not require every non-clock event to be known.

Occurrence and its record are distinct under F2. Deletion may add a deletion
event while removing content from R. A tombstone records the declared loss; it
does not prove that every external copy was erased. Unknown missing ticks must
not be synthesized from an ordinal gap without a capture contract.

## 5. Comparison without a master clock

For clocks A,B with positive counts on the same declared window, retain the
transport companion's orientation convention:

$$\kappa_{B\leftarrow A}(W)=N_A(W)/N_B(W).$$

The arrow labels the comparison; the formula fixes its direction. A zero count
does not supply a finite conversion ratio. A comparison frame includes its
anchors, membership, grain epochs and coverage status.

**Proposition 5.1 [derived].** On one frame, κ_A←A=1,
κ_A←B=κ_B←A⁻¹ and κ_C←B κ_B←A=κ_C←A.

*Proof.* Substitute the positive counts and cancel. □

Cycle closure is an algebraic check on one consistent frame, not empirical
evidence that clocks share a physical essence or uniform rate.

Transport between windows W and V is a different operation. Define
T_A(W→V)=N_A(V)/N_A(W) only after declaring why these windows correspond.
Then

$$\frac{\kappa_{B\leftarrow A}(V)}{\kappa_{B\leftarrow A}(W)}
=\frac{T_A(W\to V)}{T_B(W\to V)}.$$

This rectangle identity follows by substitution. Pairing messages identifies
corresponding events; it does not alone identify unbiased rates or equal-depth
boundaries. A bounded transport needs evidence supporting its boundary error;
a caller-supplied `complete` or `bounded` label is a declaration, not a proof.

Wall seconds per local tick are another typed ratio. Wall-clock reversals,
unknown capture and changes in grain must remain explicit. An absolute value
must not silently turn a reversed wall interval into valid elapsed duration.

## 6. The conditional physical correspondence

**Imported, conditional.** The causal-set quantum-gravity program investigates
relations between locally finite orders and suitable Lorentzian continuum
approximations. Causal structure and volume play distinct roles under the
assumptions of those reconstruction results. An arbitrary discrete order is
not guaranteed a faithful manifold approximation.

Directedness alone therefore does not derive a metric signature, a speed of
light or curvature. A dense human event stream is not thereby a spacetime
manifold, and a sparse synthetic stream is not demonstrated to be closer to
fundamental physics. The title names a conditional relation to the tensorial
continuum description; the operational core is causal order and local count.
See [Surya's review](https://arxiv.org/abs/1903.11544) for the physical program
and its open assumptions.

## 7. Service contract and falsification

Tyveth and Nymara must distinguish event identity, append position, local tick,
clock lineage, grain epoch, causal parents and external source references.
An artifact touch counter describes recorded touches; it is not automatically
the artifact's proper time. Nymara occasion ticks and Tyveth events require
explicit bridges rather than equality by name.

The required tests are: zero self-duration; chain additivity; causal-window
invariance under unrelated interleaving; rejection of reversed or unconnected
anchors; frame/τ agreement; mixed-grain detection; honest missing-coverage
behavior; and retention of lineage across restart and branch.

Two clocks can separately govern occasion opportunities and background
processing. A promise can additionally have a world deadline. Dormancy freezes
an occasion budget; it does not rewrite an obligation to another clock.

**Observed baseline.** Tyveth `8432236` passed its existing suite but its legacy
τ used inclusive ordinal counting while its atlas used [a,b) causal windows.
This paper supplies the corrected contract; implementation conformance must
be verified separately.

## 8. Open questions

How should capture completeness be certified across independent stores? Which
grain conversions preserve the intended quantity? What evidence bounds paired
anchor depth? Which inheritance and merge rules preserve specific commitments?
These are concrete research obligations. The framework does not infer
phenomenology, a universal clock, or an empirical theory of subjecthood from
its mathematical consistency.
