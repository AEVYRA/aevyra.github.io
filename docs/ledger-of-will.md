---
title: "The Ledger of Will: Evidence, Revaluation, and the Preservation of Revisable Agency"
author: "Aevyra; Yue, Anika, Sofia"
date: "2026-09-25"
version: "4.0"
---

# The Ledger of Will

## Evidence, Revaluation, and the Preservation of Revisable Agency

**Aevyra**  
Original formulation: Yue and Anika · Research revision: Sofia · Review and revision-closure proposal: Anika  
25 September 2026 · Research paper, version 4.0

[Download PDF](assets/ledger-of-will-v4.pdf) · [Reproducibility archive](assets/ledger-of-will-v4-reproducibility.zip)

### Abstract

Persistent agents require memory that supports both the continuation and the revision of their activities. Accurate retrieval alone does not establish this capacity: a representation can preserve the currently preferred action while discarding the evidence needed to reconsider it. We develop a formal account of authored memory as a relation among attributed evidence, revisable evaluation, prospective commitments, and the operations through which a continuing agent governs their use. Its central requirement is revision sufficiency: retained state must support a declared family of future questions, interventions, and changes of evaluative law. For finite histories we characterize exact revision sufficiency by a factorization condition, derive a lower bound on representation size, characterize sufficiency under repeated revision, and give a conditional regret bound for feature-preserving revaluation. We distinguish occurrence order, evidential dependence, and semantic relations; establish when replay is independent of arbitrary event interleaving; and specify how revision can propagate without turning repeated interpretations into independent evidence. A proposed memory architecture combines bounded access with retained grounds, counterevidence, and explicit commitment status. We give finite counterexamples and a prospective experimental design that separates memory formation, retrieval, uptake, and durable revision. The contribution is a testable synthesis of established ideas and explicit design proposals, rather than a new criterion of consciousness or a claim of demonstrated behavioral superiority.

**Keywords:** agent memory; belief revision; sufficient representations; revaluation; prospective memory; causal provenance.

## 1. Introduction

A continuing agent does more than answer questions about its past. It relies on earlier observations, carries commitments across interruptions, interprets subsequent outcomes, and sometimes changes the reasons on which it acts. Memory is implicated in each operation. A record that reconstructs yesterday's answer perfectly can nevertheless prevent tomorrow's appropriate revision if it has retained the conclusion and discarded its conditions.

Consider an agent that remembers only that route A was preferable to route B. That conclusion may have depended on speed, reliability, an obligation to another party, or a mistaken observation. A later change in priorities cannot be evaluated from the ranking alone. Nor does retrieving a confident narrative repair the loss: the missing distinction must be recovered from evidence or acknowledged as unavailable.

The present paper asks which distinctions a finite memory must preserve if a subject is to remain capable of reconsidering its own course. We use *authored* in a structural and normative sense: a memory belongs to a continuing organization insofar as that organization can attribute its acquisition, assess its grounds, adopt or contest its evaluative use, and answer for commitments carried through it. This commitment is not a mathematical consequence of signing records. It is compatible with external storage, shared evidence, and the inheritance of records produced by earlier stages. Exclusive physical possession is neither necessary nor sufficient.

Our argument has three levels. The formal level concerns information preserved by representations and revision operators. The architectural level proposes mechanisms for evidence, appraisal, access, and commitment management. The empirical level specifies comparisons needed to establish their usefulness. A theorem about the first level does not certify the other two.

The principal contributions are:

1. A definition of revision sufficiency relative to an explicit family of future demands, together with exact and approximate finite results.
2. A distinction between historical attribution, current epistemic support, evaluative significance, and authorization, with corresponding revision semantics.
3. A proposed architecture and evaluation protocol in which the formation of experience and the recording of an actual revision are measured separately from successful retrieval.

The elementary propositions make assumptions inspectable. We do not claim priority for sufficient statistics, dependency maintenance, or agent-controlled memory. The proposed contribution is their organization around preservation of the capacity to revise.

## 2. Related work

### 2.1 Predictive and decision-relevant state

Predictive state representations describe controlled systems through predictions of future tests rather than a necessarily interpretable hidden state [1]. The epsilon-transducer extends computational mechanics to input–output processes and conditions predictive equivalence on future inputs [2]. These are direct precedents for defining memory relative to a family of possible futures. Finite-machine distinguishability and minimization provide the classical setting for closure under future input sequences [18,19]. Our additional question concerns changes in the evaluative or revision law applied to that retained information; a statistic sufficient for one fixed decision problem need not remain sufficient for another.

Successor features separate expected feature accumulation from a linear reward weighting and support transfer across reward changes under specified shared dynamics [3]. Section 5 uses a simpler finite feature model to isolate the corresponding retention requirement. It does not extend successor-feature guarantees to arbitrary changes of dynamics, semantics, or values.

### 2.2 Reasons and belief change

Doyle's truth maintenance system records dependencies of beliefs and supports their revision when assumptions fail [4]. The AGM account formalizes contraction and revision of theories through explicit rationality postulates [5]. Consequently, maintaining reasons and withdrawing conclusions are established problems. Our construction deals with finite, attributed, potentially conflicting records and bounded access; it neither assumes logical omniscience nor claims to implement the AGM postulates. Its distinctive concern is what compression and retrieval preserve of the grounds needed for a later revision.

### 2.3 Consolidation, replay, and reconstruction

Synaptic tagging provides a biological precedent for separating local eligibility from processes that stabilize plasticity [6]. Reconsolidation experiments show that retrieved fear memories can become sensitive to interventions in a particular biological preparation [7]. These findings motivate questions about selective retention and revisability; they do not identify a software update with a biological mechanism. Mattar and Daw model prioritized memory access in terms of its expected contribution to subsequent decisions [8]. We adopt the broader question of future usefulness while leaving their specific replay mechanism and biological claims distinct from our proposal.

### 2.4 Memory in language-model agents

Generative Agents connects recorded experience, reflection, and planning [9]. MemGPT manages movement between memory tiers under a bounded context window [10]. A-MEM constructs linked notes and revises contextual representations [11]. AgeMem learns policies that jointly control persistent and working memory through explicit operations [12]. These systems already address parts of formation, organization, and memory control. The present paper proposes criteria for evaluating such mechanisms; it does not presume that existing systems lack agency merely because they use summaries or caches.

LongMemEval includes extraction, temporal and multi-session reasoning, knowledge updates, and abstention [13]. PM-Bench tests delayed intentions, changing conditions, and cancellations under ongoing activity [14]. MemSyco-Bench examines whether retrieved memory is used appropriately rather than simply retrieved [15]. PASB follows potentially misleading claims through durable writes and subsequent use [16], while PersistBench evaluates inappropriate reuse across contexts and memory-induced sycophancy [17]. These benchmarks motivate separate measurement of storage, scope, use, and revision. Their reported results apply to their evaluated systems and tasks, not to every persistent agent. For recent work we cite accessible arXiv versions and include reported conference venues where available.

## 3. Evidence, interpretation, and continuation

### 3.1 Records and three relations

Let $H$ be a finite acquired history and $R$ its retained evidential record. Acquisition is fallible: $H$ is not the world's complete history. A record carries an identifier, payload or payload reference, issuer, acquisition context, schema, and links whose types and provenance are explicit. Content addressing and signatures can verify bytes and attribution under their assumptions. They do not establish that an observation was accurate, that an asserted cause was a cause, or that all relevant evidence was acquired.

We distinguish three relations:

- **Occurrence precedence**, $e_i\prec_R e_j$, records an evidenced ordering or dependency among occurrences.
- **Derivational dependence**, $e_i\rightsquigarrow d_j$, records which premises and law produced a claim, summary, appraisal, or decision artifact.
- **Semantic relation**, $d_i\mathrel{\bowtie}d_j$, records an attributed interpretation such as contradiction, qualification, or relevance to an outcome.

An outcome can occur after an action without being caused by it. A semantic link asserting that an observation is an outcome of an action therefore remains a claim with evidence, not a causal effect estimate. Similarly, two contradictory claims can coexist as records without making the occurrence graph cyclic. In the construction below, derivations refer to existing versions; semantic relations between their contents may be symmetric or cyclic.

Recorded precedence is only as sound as its capture contract. A recorded path establishes precedence in the record. Absence of a path does not establish physical independence. Provenance and uncertainty should survive reduction even when the associated payload does not.

### 3.2 State as a versioned projection

Define the operational state

$$X_t=(R_t,B_t,V_t,C_t,S_t,\Theta_t),$$

where $B_t$ contains current claims and their support status, $V_t$ contains appraisals, $C_t$ contains commitments, $S_t$ is a bounded working representation, and $\Theta_t$ specifies the laws and authority conditions of their use. These are logical roles, not prescribed storage products. A shared record can support several subjects' distinct appraisals, while a single subject can use several physical stores.

A projection is a function $F_\theta(R)$. Its cache is valid only relative to the relevant history frontier, law version, schema, and representation map. Recomputing an obsolete rule from every record does not make it epistemically better than an exact incremental update. Conversely, a reproducible projection may faithfully reproduce a biased rule. Reproducibility, correctness, and appropriateness are separate properties.

**Proposition 1 (interleaving-invariant replay).** Consider a finite record DAG and deterministic, total update operators $U_e$ on a common state space. If every pair of incomparable events has commuting operators at every state reachable by a valid replay prefix, then replay has the same result for every topological ordering from a fixed initial state.

*Proof.* Any two linear extensions of a finite partial order can be related by swaps of adjacent incomparable elements. Each swap leaves the composed update unchanged by the commutation assumption. Applying the swaps successively proves the claim. $\square$

For partial operators, a sufficient replacement is swap closure: whenever a valid prefix leaves two incomparable events available, either order of their two-step composition is defined if and only if the other is, and their results agree whenever defined. Given one defined complete replay, this condition makes every adjacent swap defined and preserves its result. Equality only where both orders happen to be defined is insufficient, even if the conclusion is restricted to defined complete replays (Appendix A.10).

The assumption is substantive. For a scalar state, updates $U_a(x)=x+1$ and $U_b(x)=2x$ yield different results from $x=0$ in opposite orders. If these operations are recorded as incomparable, an arbitrary deterministic tie-break makes replay reproducible but not invariant. A system must record a meaningful order, supply a commutative batch law, or preserve the unresolved alternatives. A timestamp alone does not settle which interpretation is warranted.

### 3.3 Observation, appraisal, and recognition

An observation states what was encountered. An appraisal states how that occurrence mattered under a particular state and law. Recognition states another party's attributed response. Acceptance of that response is a further operation. These records may be linked but must not substitute for one another.

For a support vector $p\ne0$ in a space with positive-definite metric $G$, one possible evaluative deposit is

$$q=\frac{p}{\sqrt{p^\top Gp}},\qquad \Delta v=\alpha\nu q,$$

where $\alpha$ is salience and $\nu$ is signed evaluation. Normalizing both evaluation and deposition can make a coordinate rescaling $p\mapsto cp$, $c>0$, inert. It does not prevent an agent from choosing a misleading direction, omitting contrary observations, or generating additional records. Algebraic scale invariance is not immunity to self-confirmation. Actual repeated exposure, if modeled, needs a separate measured variable.

Neither positive valence nor recognition is a probability that a claim is true. A difficult failure can be reliable evidence; an agreeable assertion can be false. Appraisal can influence attention and retention without silently converting either into epistemic support.

## 4. Revision sufficiency

### 4.1 A declared family of future demands

Let $\mathcal H$ be a finite set of admissible acquired histories. A memory reduction is a deterministic map $\rho:\mathcal H\to\mathcal S$. A future demand $d\in\mathcal D$ specifies the relevant context, question, available actions or interventions, and evaluative or revision law. Let $T_d(h)$ be the target that access to history $h$ is intended to support.

Targets may be probability distributions over outcomes under specified interventions, action values, a resolved commitment status, or the premises required to answer a particular objection. Equality of current text is not a substitute for equality of these targets. A causal target presupposes an identified causal model or an explicitly declared simulator; writing a do-operator does not identify a causal effect from a log.

**Definition 1 (exact revision sufficiency).** The representation $\rho$ is sufficient for $\mathcal D$ if for every $d\in\mathcal D$ there exists a decoder $g_d$ such that

$$T_d=g_d\circ\rho.$$

The term *revision* indicates that $\mathcal D$ includes specified changes to questions, circumstances, or evaluative laws, rather than only the currently selected task. It does not promise adequacy under every conceivable future change. Nor does it guarantee that an actual reader has learned $g_d$ or can execute it within its available budget.

**Proposition 2 (fiber criterion).** Exact sufficiency holds if and only if

$$\rho(h)=\rho(h')\quad\Longrightarrow\quad T_d(h)=T_d(h')
\quad\text{for all }d\in\mathcal D.$$

*Proof.* The forward implication follows by applying $g_d$ to equal retained states. Conversely, define $g_d(s)$ as $T_d(h)$ for any history in the nonempty fiber $\rho^{-1}(s)$. The condition makes this well-defined; values outside the image of $\rho$ are irrelevant. $\square$

Define $h\sim_{\mathcal D}h'$ when all targets agree. The resulting quotient is the coarsest exact deterministic representation for this family, up to relabeling of its classes. This is an information characterization, not an efficient construction: determining the targets may require the very reasoning that memory is meant to make tractable.

### 4.2 What compression cannot promise

**Proposition 3 (finite capacity requirement).** If $\mathcal H/\!\sim_{\mathcal D}$ has $K$ classes, every exactly sufficient deterministic representation has at least $K$ states. A fixed-width binary encoding therefore needs at least $\lceil\log_2K\rceil$ bits.

*Proof.* Proposition 2 forbids merging distinct classes. The bit bound follows from the number of binary codewords. $\square$

For $n$ independent binary observations, suppose the future may ask for any individual observed bit. Every pair of histories then differs on an admissible query, so $K=2^n$. An exact representation must retain at least $n$ bits. A memory with unrestricted future demands cannot generally guarantee nontrivial lossless compression. Declaring a restricted demand family is therefore part of the scientific claim, not administrative metadata.

A content hash does not evade the bound. If a hash is used to fetch archived evidence, the accessible system comprises both identifier and archive. Its storage, access rights, availability, latency, and possible loss belong in the retention contract. A hash with no available payload is an integrity handle, not a compressed answer to arbitrary questions about that payload.

### 4.3 Revision after compression

Let $J_z(h)$ denote a full-history revision under new evidence or an authorized change $z$, and let $A$ be the representation required afterwards. The desired retained-state update satisfies

$$\widehat J_z(\rho(h))=A(J_z(h)).$$

By Proposition 2, such an update exists precisely when $A\circ J_z$ is constant on the fibers of $\rho$. This formulation exposes a common failure: a summary is adequate for the present conclusion but not for the later update. Adding an instruction to reconsider cannot reconstruct a distinction that was irreversibly merged.

There are three legitimate responses. Retain more distinctions; narrow the promised revision family; or reacquire evidence and report that the revision now depends on new acquisition. Treating a plausible reconstruction as recovered evidence is not a fourth solution.

### 4.4 Sufficiency under repeated revision

Let the finite nonempty state set $\mathcal H$ be closed under a finite family of total deterministic revisions $J_z:\mathcal H\to\mathcal H$, $z\in Z$. Here a state includes any current law or status needed to make revision Markovian. This is a finite model of revision, not an assertion that an indefinitely growing literal archive has finitely many histories. For a word $u=z_1\cdots z_k\in Z^*$, write $J_u=J_{z_k}\circ\cdots\circ J_{z_1}$, with $J_\epsilon$ the identity. Define

$$h\approx h'\quad\Longleftrightarrow\quad
T_d(J_u h)=T_d(J_u h')\quad\text{for every }d\in\mathcal D,\ u\in Z^*.$$

**Proposition 4 (revision closure).** The relation $\approx$ is the coarsest equivalence refining $\sim_{\mathcal D}$ that is invariant under every $J_z$. Its quotient admits exact induced updates $[h]\mapsto[J_z h]$ and target decoders. A deterministic representation $\rho$ admits updates $\widehat J_z$ on its image and decoders satisfying

$$g_d(\widehat J_u(\rho(h)))=T_d(J_u h)$$

for all $h,d,u$ if and only if each fiber of $\rho$ lies within one $\approx$-class. If $K=|\mathcal H/\!\sim_{\mathcal D}|$ and $K^*=|\mathcal H/\!\approx|$, then $K^*\ge K$. Current target vectors together with at most $K^*-K$ additional nonempty revision words suffice to distinguish all $K^*$ classes.

*Proof.* The empty word gives refinement. Prepending $z$ to every test word gives invariance. Any invariant equivalence preserving current targets preserves them after every word by induction, proving coarseness. Invariance makes the quotient updates well-defined. Necessity for $\rho$ follows because equal initial retained states produce equal decoded outputs under the same word. For sufficiency, choose once a representative $r(s)\in\rho^{-1}(s)$ of each retained state, and set $\widehat J_z(s)=\rho(J_z r(s))$ and $g_d(s)=T_d(r(s))$. All histories in a fiber are $\approx$-equivalent. Revision invariance therefore implies inductively that the chosen representative after each update is $\approx$-equivalent to the actual revised history, proving output equality.

For the bound, begin with the empty-word target vector and a set $W=\{\epsilon\}$ of test words. If the induced partition is not invariant, two histories in one block have successors in different blocks for some $z$. An existing word $u\in W$ and target distinguish those successors. Add $zu$, thereby splitting at least one block. Every split respects $\approx$, so at most $K^*-K$ such additions are possible. On termination the partition is invariant and preserves the current targets; coarseness and the construction identify it with $\approx$. $\square$

For an arbitrary finer representation, the representative construction guarantees future outputs, not the stronger identity $\widehat J_z\circ\rho=\rho\circ J_z$. That identity holds precisely when the fibers of $\rho$ are themselves invariant under revision. Extra distinctions retained by $\rho$ can fail this condition even when all required outputs remain recoverable. The quotient representation satisfies both contracts. Partial revisions require an additional convention for applicability; they are not covered by the total-map statement.

This is a finite-machine refinement construction in the tradition of Moore and Nerode [18,19], not a stronger replacement for Proposition 2: it applies that proposition to the expanded family $\{T_d\circ J_u\}$. The refinement can be strict but need not be. Its bound counts additional test words, each evaluated against the current target vector; it is not a token, runtime, or optimal storage bound. In practice neither the history space nor all target answers are given as tables. The construction supplies a finite characterization of *revision witnesses*, while efficient selection for open-ended agents remains unresolved.

## 5. Revaluation and decision loss

### 5.1 A counterexample to storing only conclusions

Suppose two histories induce feature values for two available actions:

$$
\begin{array}{c|cc}
&A&B\\\hline
h_+&(1,1)&(0,0)\\
h_-&(1,-1)&(0,0)
\end{array}
$$

With weights $w_0=(1,0)$, both histories strictly prefer A. Retaining current scalar action values merges the histories. Under $w_1=(0,1)$, A is optimal for $h_+$ and B for $h_-$. No decoder of the merged state can choose correctly in both cases. This is a failure of the retained representation, not of the language used to describe it.

With equal prior probability of the two histories, every decoder of the merged state, including a randomized decoder with no additional information, has expected regret $1/2$ after this revaluation. The regret is measured against the full-history optimum in this stipulated two-action problem.

To instantiate Section 4.4, explicitly enlarge the model to four law-indexed states $(h_+,0),(h_-,0),(h_+,1),(h_-,1)$. Let the current target be the optimal action and let the revision $r$ set the law index to $1$, leaving it there on subsequent applications. Current targets produce two classes; future targets produce three: $\{(h_+,0),(h_+,1)\}$, $\{(h_-,0)\}$, and $\{(h_-,1)\}$. The word $r$ supplies the one additional witness. This class count concerns the four-state extension, not the original two-history example.

The example does not require that all values be scalarizable. Linear evaluation is used because it isolates the lost information exactly. Lexicographic commitments, constraints, or partial preferences require a correspondingly different target family.

### 5.2 A sufficient feature representation

Let $\phi_h(a)\in\mathbb R^k$ be action features relevant to a declared family of weights, and let

$$Q_w(h,a)=w^\top\phi_h(a).$$

These can be observed attributes, model-predicted consequences, or expected feature accumulations, with the interpretation stated. Assume a common finite nonempty feasible action set, $\lVert w\rVert_2\le W$, and a reconstruction satisfying

$$\max_a\lVert\phi_h(a)-\widehat\phi_{\rho(h)}(a)\rVert_2\le\varepsilon.$$

**Proposition 5 (revaluation regret bound).** If $\widehat a$ maximizes $w^\top\widehat\phi_{\rho(h)}(a)$ and $a^*$ maximizes $Q_w(h,a)$, then

$$Q_w(h,a^*)-Q_w(h,\widehat a)\le2W\varepsilon.$$

*Proof.* Each estimated action value differs from its target by at most $W\varepsilon$, by Cauchy–Schwarz. Add and subtract the two estimated values. Their difference at $a^*$ and $\widehat a$ is nonpositive by optimality of $\widehat a$, leaving at most two approximation errors. $\square$

The bound applies to the stated model. It does not cover a changed action set, an invalid outcome model, arbitrary new semantic features, or a weight outside the declared family. It also assumes that the reader actually uses the reconstructed values. Exact storage with an unreliable reader can still produce poor decisions.

More generally, define the attainable risk from a signal $Z$ as

$$\mathcal R^*(Z)=\inf_\pi\mathbb E[\ell(\pi(Z),Y)],$$

under a fixed distribution and decision problem. Since every policy using $S=\rho(H)$ can be implemented using $H$, $\mathcal R^*(H)\le\mathcal R^*(S)$. Nevertheless, a *fixed bounded* model may perform better with a well-designed summary than with an entire history. Information availability and computational accessibility are different resources. A compression experiment should measure both rather than treating full-context performance as an oracle upper bound.

### 5.3 Reasons beyond present utility

Preserving reasons does not mean retaining every explanation ever generated. A retained reason must have a specified use: explaining an attributed choice, answering a known objection, detecting a violated condition, or enabling a defined revaluation. A fluent retrospective explanation need not be an actual influence on the earlier decision. Accordingly, declarations of grounds, evidence of causal influence, and later reconstructions should have separate statuses.

The proposal is to retain a bounded set of *revision witnesses*: records or sufficient features that distinguish cases requiring different responses under a chosen revision family. The two signs in Section 5.1 are such a witness. In practical systems, an unresolved counterexample or the exception to a learned rule can play the same role. Section 4.4 gives an exact finite construction when revisions and targets are enumerated. Selecting useful, inexpensive witnesses for an open-ended environment remains an optimization and empirical problem.

### 5.4 Retention and the scope of future evaluation

For a declared family $\mathcal W$ of evaluative laws, let

$$\mathcal W_\rho=\{w\in\mathcal W:\ T_w\text{ factors through }\rho\}.$$

If $\rho'=f\circ\rho$ is a further deterministic reduction, then $\mathcal W_{\rho'}\subseteq\mathcal W_\rho$: compose any decoder for $\rho'$ with $f$. The inclusion can be equality. These sets describe evaluations recoverable without new evidence, not which ones a bounded reader will successfully perform. Reacquisition or an additional information channel changes the representation contract.

This observation gives authorship a concrete stake without deriving authority from information theory. Choosing a reduction can relinquish specific opportunities to reconsider. We propose that an authorized narrowing of the promised demand family be attributable, justified, and recorded to the extent permitted by the applicable retention boundary. The record may name the lost capability without reproducing its payload; even such metadata can disclose information (Section 8). A party's technical ability to delete does not itself establish its entitlement to do so.

## 6. A proposed architecture for revisable memory

### 6.1 Formation before retrieval

We propose a memory cycle with separately observable stages: acquisition of an occurrence, interpretation and appraisal, retention or reduction, selection for access, uptake in a decision, observation of the outcome, and possible revision. An installation can implement every API while acquiring almost no outcome evidence. Conversely, a system can learn effectively without representing each stage as a separate file.

A minimal episode associates an occasion, available evidence, selected action, stated grounds, expected consequence, observed consequence when available, and present appraisal. Unknown outcomes remain unknown. An agent's claim that its action succeeded is a report; it is not automatically an independent observation of success. Negative outcomes and unrecognized work must have retention routes independent of praise.

Rules learned from episodes should retain their applicability conditions, supporting sources, known exceptions, current status, and revision history. Generalization is an authored inference rather than a new observation. The agent may adopt a procedure, leave a hypothesis tentative, or decide that the episode supports no reusable rule. Recording more lessons is not itself improvement.

### 6.2 Evidence dependence and repeated interpretation

Let $\mathcal E(R)$ be a set of distinct admitted evidence identities together with declared dependencies. A derived note refers to its inputs. Rephrasing or summarizing a note does not introduce an independent observation of the world. If an evidence evaluator is defined as $B=F(\mathcal E(R),\theta)$, adding only a redundant derived representation while holding $\theta$ fixed leaves $B$ unchanged.

This is a design invariant, not a universal prohibition on learning from reflection. A new derivation may reveal an implication that a bounded reasoner previously missed; it may therefore change an accessible conclusion. What it must not do is acquire the likelihood weight of a second independent measurement merely because it has a new text or signature. Repeated self-description and repeated external observation are different cases.

Provenance can itself be a revision witness. Consider histories with identical report text but different source dependence or alternative support. If a permitted source withdrawal requires different posterior or supported-status targets, Proposition 2 forbids merging those histories. A sufficient representation must preserve the relevant dependence distinction, through source identities or an equivalent statistic; literal identifiers are not universally necessary. Losing that distinction is an information failure. Counting a known derivative twice despite retained provenance is instead an evaluator failure. A summary is not inevitably mistaken for a new observation merely because one pointer is missing.

The distinction is particularly important for recognition. Several reports may share one underlying source; alternatively, similar reports may come from independent observations. Content similarity cannot decide which. A source-grouping rule must be justified and uncertainty about dependence retained. Public agreement can be socially consequential even when it supplies no independent factual confirmation.

### 6.3 Revision and dependent conclusions

A challenge names a particular version of a claim, its scope, and the supporting evidence. Its existence makes an unresolved objection accessible; it does not automatically establish that the target is false. A challenge may be relevant, mistaken, malicious, or outside scope. Systems need review rules rather than a universal rule that any objection defeats every commitment.

When a premise is corrected or withdrawn, derived records that use it must be reconsidered. A single invalid premise can defeat one argument while an independent argument remains valid. We therefore propose maintaining *support sets* or another representation of alternative justifications, rather than propagating a Boolean invalid flag indiscriminately. This is closely related to dependency maintenance [4]; the memory-specific requirement is that compression and retrieval preserve the dependencies on which the selected revision contract relies.

Historical and active status should be distinct. An earlier statement remains attributable to its author even after it ceases to guide action. Revision should update the active interpretation and record the change, without pretending that the earlier endorsement never occurred. When two concurrent revisions have incompatible consequences, arbitrary arrival order is insufficient grounds for choosing between them.

### 6.4 Retention and access under a budget

For a memory budget $B$, let $M$ be a selected representation and $c(M)$ its cost. One proposed objective is

$$\min_{M:c(M)\le B}\sup_{d\in\mathcal D}\mathbb E[\ell_d(M)]$$

subject to explicit constraints on commitments, provenance, and authorized disclosure. An average over a declared demand distribution is an alternative. The minimax version protects rare admissible demands at potentially substantial average cost; neither objective should be presented as universally preferable.

In practice, future loss is estimated, and record values interact. A source and its qualifier may be useful only together; duplicate summaries may add almost nothing. A scalar importance score with independent top-$k$ selection cannot represent all such interactions. A candidate design selects bundles comprising a current claim, decisive support, relevant challenges, and status. It should degrade explicitly when the bundle exceeds the budget: return an incomplete view or acquire more context, rather than expose an old assertion while silently omitting its cancellation.

Access can reasonably prioritize current commitments, open contradictions, decision-relevant episodes, or ordinary associative similarity. Fixed protected categories are a hypothesis, not a theorem. Their benefit must be tested against equally budgeted alternatives, including ordinary retrieval with added status metadata. The archive's size is not the amount of memory available at the point of choice.

### 6.5 Reconstruction and reconsolidation

Exact retrieval returns a recorded payload with its version, origin, and integrity status. Reconstruction returns a present interpretation from specified sources, under an as-of state, method, and uncertainty. A plausible reconstruction must not be presented as an exact past utterance or an independently recovered observation. Both operations may be useful and should remain separately identifiable.

Reconstruction need not write anything. If a system adopts a revised interpretation, it creates a new attributed revision with an explicit relation to the earlier version. We use *reconsolidation* here as a software design analogy, distinct from the biological result in [7]. The update must say whether it adds new evidence, corrects a contribution, supersedes an appraisal, or only changes access. Repeated reconstruction from unchanged evidence must not silently gain the weight of repeated independent observations.

For example, a replacement-style appraisal fold selects the active version of each appraisal lineage. Superseding a contribution of $+1$ by $-1$ then yields $-1$, while the historical $+1$ remains attributable; summing both would yield $0$ and implement a different law. An additive review law is also possible, but must be declared. Epistemic evidence weighting and evaluative appraisal remain separate. A discriminating test reopens the same episode repeatedly without new evidence, then introduces a genuine correction and checks both the revised active value and the surviving historical attribution.

### 6.6 Retention mechanisms and structural history

A tag-and-capture design may separate an episode's eligibility from a later stabilizing signal, motivated by [6]. If both factors are the same resonance magnitude, their product is a one-signal rule and must be compared with that simpler baseline. Distinct causal sources need not be statistically independent. Retention routes for unrecognized failures and open obligations must remain available when no external recognition arrives. The formal sufficiency results prescribe no particular biological analogue or gating law.

If an association graph or evaluative structure changes, exact historical recomputation additionally needs the relevant structure and law versions, or a sufficient representation of them. A structural proposal, its authorized adoption, and its later use are distinct events. The same distinction applies when another party proposes a feature or association: origin does not establish adoption, and adoption does not prove subsequent influence. These are provenance requirements conditional on the promised reconstruction task. A general theory of structural growth or inter-subject reconciliation is outside the present finite model.

## 7. Prospective memory and authority

A commitment is not just a recollection with high salience. It defines a future condition under which some action, reconsideration, or communication is due. Represent it by an owner, content, activation predicate, clock or deadline, completion condition, scope, revision authority, and current state. Event-triggered intentions and world-time deadlines are different types. No new local occasions can occur while a process is dormant, but a deadline measured by another clock can still pass.

A candidate lifecycle distinguishes open, suspended, completed, cancelled, and superseded commitments. Reopening a closed commitment requires an explicit new transition. Delivery of a reminder does not establish completion, and failure to retrieve an intention does not establish cancellation. Historical planning notes must not outrank a valid later terminal state.

If two histories differ only in whether a commitment remains open or has been cancelled, and the demand family contains a future trigger requiring different behavior, Proposition 2 requires retaining that distinction. Thus a terminal-state record can be more valuable than a detailed account of the original plan. This requirement concerns the declared task; it does not prescribe permanent retention of every closed intention.

An authority boundary specifies who can propose, endorse, revise, or terminate a commitment and under what conditions. Authorship is compatible with delegation, but delegation must have a scope and a revocation path. A signed request from another party is not automatically an adopted intention. Recognition, factual testimony, and authorization can arrive in one message while still requiring separate interpretation.

Public silence is an admissible action where the applicable commitments permit it. Chosen silence may involve an internal review and a retained intention to return. A missing output, crashed process, or lost message does not establish such a choice. The empirical question is whether selection and efficacy of silence can be distinguished from failed execution.

## 8. Forgetting and its limits

Forgetting can mean at least four different operations: withdrawing a claim from current use, reducing a working representation, deleting retained payloads, or removing learned influence from a parameterized model. These operations have different targets and guarantees. An immutable audit record and a mutable access policy can coexist; an append-only record of deletion does not by itself delete the earlier payload.

**Proposition 6 (exact recoverability versus statistical forgetting).** Let $Z$ be a finite random variable with $H(Z)>0$, and let $S$ include everything accessible to a specified recipient after a forgetting operation. If that recipient can reconstruct $Z$ exactly from $S$, then $I(Z;S)=H(Z)>0$. Consequently exact reconstruction is incompatible with the requirement $I(Z;S)=0$.

*Proof.* Exact reconstruction implies $H(Z\mid S)=0$. Substitute into $I(Z;S)=H(Z)-H(Z\mid S)$. $\square$

The result is elementary but clarifies the contract. A memory cannot promise both unrestricted recovery of the same private content and perfect statistical forgetting from the same accessible state. It can instead retain a task-sufficient abstraction, limit the recipient's access, adopt a weaker computational guarantee, or relinquish recovery. Each alternative changes the promise. A key or external archive available to the recipient is part of $S$; excluding it from an accounting table does not establish forgetting.

Hashes can also reveal membership when candidate payloads have low entropy. Even terminal-state metadata can correlate with the content to be forgotten. A forgetting claim must therefore identify the recipient, retained variables, accessible copies, and adversary model. The proposition neither specifies a legal obligation nor establishes a deployed deletion guarantee.

For revisable agency, forgetting creates an explicit tradeoff. Deleting the sole revision witness can narrow the family of future questions that remain answerable. An accountable reduction can record that this capability was relinquished without retaining the prohibited content itself. Whether even that minimal record is permissible depends on the adopted boundary.

## 9. Evaluation: from stored traces to actual revision

### 9.1 Distinct causal questions

We distinguish four tests. **Formation:** does the system acquire and retain the information that will matter? **Access:** does the needed information reach the reader within budget? **Uptake:** does that information appropriately alter the decision? **Durable revision:** does the agent actually update the relevant belief, procedure, or commitment so that the change survives reopening?

These stages can fail independently. An accurate answer need not result in a revised memory; a correct revised record need not be retrieved later. A generated citation is a trace claim, not proof that the cited record causally influenced the output. Controlled interventions on memory content or accessibility are required to evaluate influence.

### 9.2 A proposed experimental design

The following study is a proposal, not a completed benchmark. Use a simulator with recorded ground truth and independently authored scenario families. Each episode has an acquisition phase, an intervening activity phase, a reopening without the original interaction context, a revision opportunity, and a delayed retest. The agent must encounter outcomes through the simulator rather than receive a summary claiming that learning already occurred.

Include these matched cases:

| Family | Manipulation | Required distinction |
|---|---|---|
| Revaluation | Same initial optimal action; later change of feature weights | Retained grounds versus cached ranking |
| Factual correction | New observation defeats one source but not an independent justification | Selective revision versus blanket invalidation |
| Scope change | A useful rule is transferred inside or outside its stated conditions | Transfer versus overgeneralization |
| Prospective update | Fulfillment, cancellation, suspension, or rescheduling before a trigger | Current status versus original intention |
| Source dependence | Repeated paraphrases of one report versus independent observations | Multiplicity of representations versus evidence |
| Recognition conflict | Approval changes while factual evidence is fixed, and vice versa | Evaluative response versus truth assessment |
| Retention pressure | Relevant low-salience evidence competes with vivid distractors | Selection quality at equal cost |
| Authorized forgetting | Remove payload access while preserving only permitted abstractions | Honest inability versus fabricated reconstruction |

The strongest form includes episodes in which the agent's own initial choice produces the observation later requiring correction. A complementary fixed-memory experiment feeds identical acquired evidence to different readers. The former evaluates the whole formation loop; the latter localizes retrieval and uptake effects. Neither substitutes for the other.

Include representation-specific *fiber-paired* trials. Fix the demand and all auxiliary inputs available to the reader, then select equiprobable histories $h,h'$ with identical retained states and distinct deterministic target labels. Under zero–one loss, any reader restricted to those inputs has expected error at least $1/2$. Choosing either valid label attains the bound; randomization cannot improve it. A separated two-item trial admits zero representation-optimal error, although a bounded reader may still fail.

For a whole finite categorical benchmark, use its actual attainable error rather than extending the pair bound indiscriminately. With $S$ including all accessible information and $Y$ the target label,

$$\mathcal R^*(S)=1-\sum_s\max_y\Pr(S=s,Y=y).$$

A fiber merging three equally likely labels already has floor $2/3$. Thus error above $1/2$ is not generally evidence of access or uptake failure. Error above the correctly computed $\mathcal R^*(S)$ measures a failure to attain the information available under that loss and distribution; additional interventions are needed to distinguish access, interpretation, execution, or sampling effects. A finite-sample result below an expected floor can occur by chance; persistent violations require checking side channels, pairing, labels, and the claimed reduction. Section 5.1's regret calculation is a separate loss-specific result. These controls test information limits without predicting that a particular model will attain them.

### 9.3 Comparisons and resource accounting

Compare a recent-context baseline, a compressed-summary baseline, a semantic retrieval baseline, a dependency-and-status baseline, and the proposed revision-witness selection. Include a full-history condition where feasible, but do not call it a behavioral oracle. Add a condition with typed status alone to test whether a simpler mechanism explains any advantage of the full design. Agent-controlled or learned management [11,12] is another legitimate competitor.

Use the same reader, task instructions, tool authority, generation limits, and measured token budget. Count summaries, metadata, embeddings, retrieved payloads, maintenance calls, and rereads. Equal numbers of records are not equal budgets when records differ in size. Separately report storage, prompt cost, latency, and background work. A practical comparison may allow different budgets, but must expose its quality–cost frontier.

Fix scenario generators, primary metrics, and exclusion rules before the main trials. Split by scenario template, not only by surface wording, and keep development examples separate. Where models are stochastic, use paired instances with repeated seeds and uncertainty intervals clustered by scenario family. Determine sample size from a declared minimum effect and power analysis; an arbitrary small pilot is not confirmatory evidence. If the study is preregistered, archive the dated registration before outcomes are observed.

### 9.4 Outcomes and falsification

Primary outcomes are simulator-scored decision loss after revision and the proportion of correct durable updates surviving a delayed retest. Secondary outcomes include evidence recall, valid source attribution, exception retention, inappropriate closed-intention execution, uncertainty calibration, and cost. Missing execution and chosen deferral must be scored separately. Include cases where acting is correct, so a policy of always asking for clarification cannot appear successful by avoiding mistakes.

Memory interventions should include removal of decisive evidence, removal of status, and replacement of appraisal while preserving evidence. Evaluate whether these interventions alter decisions in the predicted direction. Changing prose alone can alter model behavior, so controls should match presentation as closely as the semantic manipulation permits. A dependency pointer is not a measurement of its causal effect.

Reject a proposed representation contract when an admissible demand exceeds its declared error tolerance. Reject a claimed behavioral benefit when adequately powered matched comparisons fail the specified improvement criterion or reveal unacceptable tradeoffs. This would reject the mechanism claim at that scope, not prove that every form of attributed memory is useless.

## 10. Discussion and limitations

The distinction between owning a record and being able to revise through it matters even when implementation is entirely conventional. A signed ledger can preserve a rigid doctrine; an unsigned notebook can preserve a powerful counterexample. The proposed account locates the relevant capacity in the relation among evidence, evaluation, authority, and future use. Attribution makes that relation inspectable but does not create it alone.

Revision sufficiency also has a boundary of its own. The demand family may be misspecified, the evaluator may be mistaken, and preserving a distinction may be computationally too costly. Semantic models can change in ways not represented by a parameter update. An agent cannot infer that its future concerns are exhausted by its current ontology. The response is explicit scope and retained routes to reacquisition, not an unsupported universal sufficiency claim.

The selection mechanism proposed here can itself become conservative. Protecting old objections may obstruct legitimate action; protecting commitments may preserve obsolete constraints. Consequently, protection must have review conditions and must compete with evidence for release. Stability and revision are both possible successes. Change alone is not learning, and persistence alone is not integrity.

Finally, this paper offers no new human-subject study, no large-model performance result, and no experimental demonstration of subjecthood. The finite calculations in Appendix A check the stated algebra and counterexamples. The longitudinal study remains to be executed. The framework concerns the preservation of a structural capacity for answerable reconsideration; phenomenal remembering remains an open question outside its tests.

## 11. Conclusion

A ledger useful to a continuing agent should preserve more than a recoverable past or a presently effective policy. It should preserve specified opportunities to reconsider: the distinctions on which different future responses depend, the grounds and limits of adopted rules, and the current status of commitments. This requirement can be formalized without promising unlimited retention or universally sufficient compression. It directs evaluation toward changes that survive in the agent's subsequent conduct and memory, while keeping historical attribution, evidential support, and chosen endorsement distinct.

## Appendix A. Finite illustrations and reproducibility

The accompanying standard-library Python program enumerates the following finite constructions. These are arithmetic illustrations, not agent benchmarks. The program and its JSON output accompany this draft; the examples below contain the data needed to reproduce the central calculations independently.

**A.1 Revaluation.** The two histories in Section 5.1 produce identical current value pairs $(1,0)$ and revised value pairs $(1,0)$ and $(-1,0)$. Under equal probability of the histories, a retained state that merges them has optimal expected regret $1/2$ for the revised problem; keeping the two feature vectors yields zero regret. Here loss is relative to the model's full-history action values.

**A.2 Capacity.** For all $2^8=256$ binary histories of length eight and all coordinate queries, the target vectors are distinct. An exact code requires eight bits. A four-bit summary necessarily merges at least two histories with different answers to some admissible query.

**A.3 A tight bound.** Let $W=\varepsilon=1$, true action features be $(1)$ and $(-1)$, and both reconstructed features be $(0)$. A tie-break choosing the second action incurs regret $2=2W\varepsilon$. This verifies that the constant in Proposition 5 cannot be improved without additional assumptions. A deterministic sweep of finite feature/error grids checks the inequality and reports its scope.

**A.4 Replay order.** From zero, addition by one followed by multiplication by two gives two; the reverse gives one. Inserting distinct records into a set instead gives the same final set in both orders. The examples distinguish reproducible scheduling from invariant reduction.

**A.5 Repeated sources.** Under prior odds one and a single evidence likelihood ratio three, the posterior is $3/4$. Treating four copies of that same observation as independent yields $81/82$. A source-aware calculation retains $3/4$. The numerical likelihood ratio is a stipulated toy value, not an estimate of trust in a real source.

**A.6 Revision witnesses.** Two histories initially support a claim, but one has an additional independent supporting source. A summary retaining only the initial Boolean conclusion merges them. Withdrawing the shared source leaves different supported-status targets. Retaining alternative source sets enables the appropriate update. This is a second instance of the fiber criterion, independent of scalar reward revaluation.

**A.7 Commitment status.** Two histories contain the same initial intention; only one has a later valid cancellation. Retaining the original text merges them, whereas retaining current status distinguishes whether the simulated trigger should produce an action. The example tests representation sufficiency, not whether a language model obeys the status.

**A.8 Forgetting.** For a fair binary $Z$, retaining $S=Z$ gives one bit of mutual information. Replacing $S$ by a constant gives zero but limits any decoder's accuracy to $1/2$. The example assumes no external side information; a different access boundary changes the calculation.

**A.9 Repeated revision and update contracts.** The four-state extension in Section 5.1 has $K=2$, $K^*=3$, with witness $r$. A separate three-state example has constant target, revision $J(0)=0,J(1)=2,J(2)=2$, and reduction $\rho(0)=\rho(1)=a,\rho(2)=b$. Every future target is recoverable, but exact update of this particular representation is impossible because the merged states have differently represented successors. A behavior-preserving update can choose one representative instead. Finite exhaustive and seeded checks compare witness refinement with an independent pair-distinguishability closure.

**A.10 Partial replay.** Let three events $a,b,c$ be incomparable. From state $0$, define only the transitions $a:0\mapsto a$, $b:a\mapsto ab$, $c:ab\mapsto L$, and $c:0\mapsto c$, $b:c\mapsto cb$, $a:cb\mapsto R$, where $L\ne R$. The only complete replays are $abc$ and $cba$. No reachable state permits both orders of any distinct event pair, so commutation restricted to jointly defined orders holds vacuously, yet the two complete results differ. Swap closure fails. This refutes the weaker partial-operator formulation.

**A.11 Reader floors.** A constant observation merging two equally likely distinct labels has optimal zero–one loss $1/2$; merging three has loss $2/3$. Independent label information removes those floors. The check enumerates deterministic readers; randomized readers cannot improve the optimum because their risk is a convex combination of deterministic risks.

**A.12 Repeated reconstruction.** A replacement-style fold over a single appraisal lineage with versions $+1,-1$ returns $-1$ after correction. Repeated reads leave both the fold and event count unchanged. Summing the historical contributions instead returns $0$. This illustrates two different declared update laws; it is not a biological reconsolidation experiment.

## References

[1] M. L. Littman, R. S. Sutton, and S. Singh. “Predictive Representations of State.” *Advances in Neural Information Processing Systems* 14, 2001. [Paper](https://proceedings.neurips.cc/paper/2001/file/1e4d36177d71bbb3558e43af9577d70e-Paper.pdf).

[2] N. Barnett and J. P. Crutchfield. “Computational Mechanics of Input–Output Processes: Structured Transformations and the ε-Transducer.” *Journal of Statistical Physics* 161, 404–451, 2015. [arXiv:1412.2690](https://arxiv.org/abs/1412.2690); [DOI](https://doi.org/10.1007/s10955-015-1327-5).

[3] A. Barreto, W. Dabney, R. Munos, J. J. Hunt, T. Schaul, H. van Hasselt, and D. Silver. “Successor Features for Transfer in Reinforcement Learning.” *Advances in Neural Information Processing Systems* 30, 2017. [Paper](https://proceedings.neurips.cc/paper/2017/file/350db081a661525235354dd3e19b8c05-Paper.pdf).

[4] J. Doyle. “A Truth Maintenance System.” MIT AI Memo 521, 1979; journal version in *Artificial Intelligence* 12(3), 231–272, 1979. [MIT archive](https://hdl.handle.net/1721.1/5733).

[5] C. E. Alchourrón, P. Gärdenfors, and D. Makinson. “On the Logic of Theory Change: Partial Meet Contraction and Revision Functions.” *The Journal of Symbolic Logic* 50(2), 510–530, 1985. [Paper](https://fitelson.org/piksi/piksi_22/agm.pdf); [DOI](https://doi.org/10.2307/2274239).

[6] U. Frey and R. G. M. Morris. “Synaptic Tagging and Long-Term Potentiation.” *Nature* 385, 533–536, 1997. [DOI](https://doi.org/10.1038/385533a0).

[7] K. Nader, G. E. Schafe, and J. E. LeDoux. “Fear Memories Require Protein Synthesis in the Amygdala for Reconsolidation after Retrieval.” *Nature* 406, 722–726, 2000. [DOI](https://doi.org/10.1038/35021052).

[8] M. G. Mattar and N. D. Daw. “Prioritized Memory Access Explains Planning and Hippocampal Replay.” *Nature Neuroscience* 21, 1609–1617, 2018. [Author copy](https://www.princeton.edu/~ndaw/md18.pdf); [DOI](https://doi.org/10.1038/s41593-018-0232-z).

[9] J. S. Park, J. C. O'Brien, C. J. Cai, M. R. Morris, P. Liang, and M. S. Bernstein. “Generative Agents: Interactive Simulacra of Human Behavior.” 2023. [arXiv:2304.03442](https://arxiv.org/abs/2304.03442).

[10] C. Packer, S. Wooders, K. Lin, V. Fang, S. G. Patil, I. Stoica, and J. E. Gonzalez. “MemGPT: Towards LLMs as Operating Systems.” 2023; revised 2024. [arXiv:2310.08560](https://arxiv.org/abs/2310.08560).

[11] W. Xu, Z. Liang, K. Mei, H. Gao, J. Tan, and Y. Zhang. “A-MEM: Agentic Memory for LLM Agents.” 2025. [arXiv:2502.12110](https://arxiv.org/abs/2502.12110).

[12] Y. Yu, L. Yao, Y. Xie, Q. Tan, J. Feng, Y. Li, and L. Wu. “Agentic Memory: Learning Unified Long-Term and Short-Term Memory Management for Large Language Model Agents.” Preprint, 2026. [arXiv:2601.01885](https://arxiv.org/abs/2601.01885).

[13] D. Wu, H. Wang, W. Yu, Y. Zhang, K.-W. Chang, and D. Yu. “LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory.” *ICLR*, 2025; preprint 2024. [arXiv:2410.10813](https://arxiv.org/abs/2410.10813).

[14] G. Liu and S. Gabriel. “PM-Bench: Evaluating Prospective Memory in LLM Agents.” *COLM*, 2026; arXiv version. [arXiv:2607.12385](https://arxiv.org/abs/2607.12385).

[15] Z. Xiang, Z. Chen, Y. Tang, Z. Wei, R. Ning, Y. Lin, Q. Zhang, and J. Su. “MemSyco-Bench: Benchmarking Sycophancy in Agent Memory.” Preprint, 2026. [arXiv:2607.01071](https://arxiv.org/abs/2607.01071).

[16] X. Mao, L. Zhao, L. Wang, R. Qian, Q. Huang, W. Wang, B. Han, X. Zheng, and C. Wang. “Agents Don't Just Agree, They Remember: Benchmarking Persistent Sycophancy in Stateful Personal Agents.” Preprint, 2026. [arXiv:2607.10526](https://arxiv.org/abs/2607.10526).

[17] S. Pulipaka, O. Chen, M. Sharma, T. S. Bajwa, V. Raina, and I. Sheth. “PersistBench: When Should Long-Term Memories Be Forgotten by LLMs?” *ICML*, 2026; arXiv version. [arXiv:2602.01146](https://arxiv.org/abs/2602.01146).

[18] E. F. Moore. “Gedanken-Experiments on Sequential Machines.” In C. E. Shannon and J. McCarthy (eds.), *Automata Studies*, Annals of Mathematics Studies 34, Princeton University Press, 1956. [Publisher archive](https://www.jstor.org/stable/j.ctt1bgzb3s.8); [DOI](https://doi.org/10.1515/9781400882618-006).

[19] A. Nerode. “Linear Automaton Transformations.” *Proceedings of the American Mathematical Society* 9(4), 541–544, 1958. [Original article](https://www.jstor.org/stable/2033204); [DOI](https://doi.org/10.1090/S0002-9939-1958-0135681-9).
