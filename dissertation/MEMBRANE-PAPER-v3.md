# The Membrane Framing: Authentication, Authorization, and the Autonomy of the Deontic

---

## Abstract

Authentication and authorization name two distinct operations in access control: authentication answers *is this claim true?* and authorization answers *may this entity act?* This paper argues that the step from an authentication verdict to an authorization verdict requires a bridging premise that is deontic in character — a standing, policy-relative permission (von Wright's weak modality, ¬O¬p) — and that no conjunction of authentication facts, however exhaustively verified, entails that permission. The relation is an instance of the **autonomy of the deontic** (Pigden 1989): the conservativeness of logic, shared with chess, grammar, and tax law. The contribution is explicitly a *framing*, not an *identity*: the access-control gap operationalizes the general autonomy of the deontic, not Hume's categorical guillotine. The separation of authentication facts from authorization decisions is prior art at every level — informal (Saltzer–Schroeder), formal (the ABLP authentication calculus, where access requires a separate ACL premise not entailed by the "says"/"speaks-for" facts), architectural (XACML PDP/PIP), and logical (von Wright). The defensible residue, claimed at moderate confidence, is the explicit identification of ABLP's required bridge premise as **deontic** and the subsumption of the authn→authz step under the autonomy of the deontic. From that naming, and only from the explicit deontic naming (so far as the literatures surveyed establish), two consequences follow that those literatures did not draw: an **unmeasurability result** (the gap is logical, not epistemic, so no authentication improvement closes it) and a **failure taxonomy** (confused-deputy, ambient authority, and token-as-fact-vs-grant as a single class of deontic inference failures, yielding a class-level defensive invariant). Searle's counts-as does not refute the framing; via Hare and Hudson it relocates the live normative entry to the human act of stipulating the policy and root of trust, while the authorization verdict itself is conceded to be a weak, inert, policy-relative permission. Object-capability systems likewise relocate the seam to issuance rather than eliminating it.

---

## 1. The Claim, Stated Precisely as a Framing

Authentication and authorization name two distinct operations in access control. Authentication answers: *Is this claim true?* Is this credential valid? Is this token genuine? Authorization answers a different question: *May this entity act?* Given that the claim is true, is the action permitted?

This paper argues that these two questions are not merely different in subject matter but different in logical kind, and that the difference is an instance of the **autonomy of the deontic** — the formal principle (Pigden 1989) that valid inference introduces no new non-logical vocabulary, so no set of purely descriptive premises entails a normative conclusion without a normative bridge premise. Hume's observation in the *Treatise* (1739–40, Book III, Part I, Section I) is the canonical source of this intuition; Pigden's formalization within proof theory is its rigorous statement. The claim here is that the authentication-to-authorization step operationalizes that principle in an engineered system.

The paper does **not** claim that the authentication/authorization step is *identical* to Hume's categorical guillotine in the full metaethical sense. The authorization "ought" is a policy-relative deontic permission — the weak modality (von Wright's ¬O¬p: it is not obligatory that the action not occur) — not a categorical, agent-binding moral obligation of the kind Hume's gap most dramatically concerns. The relation is operationalization, not identity: the authn/authz structure is a clean engineered exhibit of the autonomy of the deontic, not a refutation of moral naturalism.

The framing this paper defends, stated precisely: **the step from an authentication verdict to an authorization verdict requires a bridging premise that is deontic in character — a standing policy-relative permission — and no conjunction of authentication facts, however exhaustively verified, entails that permission.** The policy that supplies it is a normative commitment that precedes any individual request and is not derivable from the signal properties the authentication procedure measures.

The paper calls this the Membrane Framing because it locates a deciding seam — the policy decision — that is neither a property of the incoming signal nor a property of the protected resource, but a standing conferral that mediates between them.

---

## 2. The Autonomy of the Deontic and the Policy-Relative Permission

### 2.1 Hume's law and Pigden's formalization

Hume's observation (1739–40) is that moral writers shift without explanation from propositions expressed with "is" and "is not" to propositions expressed with "ought" and "ought not." The philosophical literature on this transition — the "guillotine" of later commentators — is vast and contested. For present purposes the operative point is narrow: **within standard logic, no set of purely descriptive (non-normative) premises entails a normative conclusion.** This is a claim about logical form, not about moral metaphysics.

Pigden (1989) formalizes this as the **autonomy of the deontic**: valid inference (in the relevant logics) introduces no new non-logical vocabulary (specifically, monotonic systems in the von Wright tradition; defeasible deontic logics are not at issue here, as access-control policy evaluation does not require defeasible reasoning for the Membrane Framing's claims). If "ought" appears in the conclusion, it must appear somewhere in the premises. This has the status of a theorem about the conservativeness of standard deontic logics, not a contested metaethical thesis. It is shared by every domain that combines descriptive facts with rule-relative classifications: chess (board-state facts do not entail "checkmate" without the rules of chess), grammar (phonological facts do not entail "ungrammatical" without the grammar), tax law (income facts do not entail "owes $X" without the tax code). The observation is philosophically thin in the sense that it requires no commitment to moral realism, non-naturalism, or any theory of practical reason. It is, however, precisely applicable.

The point that matters: **the autonomy of the deontic is not Hume's categorical gap** about moral obligation specifically. Hume's gap, in its strongest metaethical reading, concerns the derivability of action-guiding, agent-binding categorical oughts from purely naturalistic premises — a point that implicates moral realism, non-cognitivism, and practical reason. Pigden's theorem subsumes that gap as one case of the more general conservativeness result. This paper claims the more general result, not the stronger one. Overstating the claim to the categorical gap would import normativity that the access-control domain does not contain (a PDP "permit" verdict binds no one and motivates no action; it is a classification, not a prescription).

### 2.2 The weak deontic modality and what it actually asserts

Von Wright (1963) distinguishes three primary deontic modalities: obligation (Op: p is obligatory), permission (Pp = ¬O¬p: p is not forbidden), and prohibition (O¬p: p is forbidden). The authorization verdict in access control is a **permission** — the weakest modality. "Principal E may perform action A on resource R" does not oblige anyone to do anything. It merely removes the logical obstruction, within the policy framework. This is important because it frames what is actually at stake:

- The gap the Membrane Framing identifies is the gap between a descriptive fact about a signal and a policy-relative permission verdict.
- This gap is real and non-trivial: the permission is not a property of the signal, is not entailed by signal properties, and cannot be recovered by measuring the signal more completely.
- This gap is *not* the full Humean categorical gap about action-guiding obligation. It is the Pigdenian point that deontic vocabulary enters only through a normative premise.

Stating the modality correctly also sets up the Searle discussion (§4): a policy-relative permission ("permitted under policy P") is in principle derivable from is-facts plus the descriptive fact that policy P is in force — that is the Searle move (stated here as setup; addressed fully in §4). The response there is that the policy's being in force is itself the product of a normative act of stipulation — so the ought enters at the human act of policy establishment, not from the signal-facts themselves.

---

## 3. Prior Art: Credited, Distanced, and the Exact Defensible Novelty

The separation of authentication facts from the authorization decision is well-established prior art. This section credits it fully, distances this paper from it precisely, and states what residue the paper may legitimately claim.

### 3.1 The informal ancestor: Saltzer and Schroeder (1975)

Saltzer and Schroeder's "The Protection of Information in Computer Systems" (*Proceedings of the IEEE*, 63(9), 1278–1308, 1975; high confidence) established the foundational taxonomy of the access-control problem. The paper distinguishes **authentication** (verifying the identity of a principal) from **access control** (determining what an authenticated principal may do). The separation is treated as an engineering necessity and is argued from system-design principles, not from philosophical grounds. The paper does not invoke Hume, Pigden, or deontic logic. The separation is prior art.

### 3.2 The nearest formal neighbour: the ABLP calculus (1992, 1993)

The **nearest formal neighbour to this paper's actual claim** is the authentication-logic line developed by Lampson, Abadi, Burrows, and Wobber, "Authentication in Distributed Systems: Theory and Practice" (*ACM Transactions on Computer Systems*, 10(4), 265–310, 1992; high confidence on venue and year), and Abadi, Burrows, Lampson, and Plotkin, "A Calculus for Access Control in Distributed Systems" (*ACM Transactions on Programming Languages and Systems*, 15(4), 706–734, 1993; high confidence).

The ABLP calculus constructs a modal logic of authentication propositions: "A says s" (principal A asserts statement s), "A speaks for B" (A⇒B: A's assertions carry at least the authority of B's), and derived relations. The central formal result is that authentication propositions — even under the full speaks-for hierarchy — are **provably insufficient** to yield an access decision without a separate, independently-specified ACL or policy premise. The access decision requires a bridge statement not derivable from the "says"/"speaks-for" facts. That is the authn/authz separation rendered as formal non-entailment.

**What ABLP does not say:** The ABLP calculus establishes the separation as a formal matter of non-entailment. It does not ask, and does not answer, whether the missing premise is *deontic* in character — whether the bridging ACL/policy statement is a permission, a normative commitment, or a deontic verdict of a particular logical type. The ABLP principals make statements; the access decision requires a further statement; but the metaethical character of that further statement is not examined. Crucially, ABLP's "says" and "speaks-for" relations are modal-descriptive — they track assertion and authority delegation — not normative relations. ABLP treats the ACL/policy statement as a given formal object whose content is stipulated externally; it has no vocabulary for distinguishing a permission from an obligation or a fact, and it does not need one for its access-control results — which is precisely why the deontic naming is a residue ABLP leaves available rather than one it forecloses.

The distinction is precise: ABLP shows *that* a bridge premise is required (non-entailment); this paper names the *logical type* of that premise (deontic permission) and draws consequences from the naming. ABLP's non-entailment result is a *precondition* for the Membrane Framing — it establishes that the gap exists; the Membrane Framing names what occupies the gap (a deontic permission) and derives consequences from that naming. The contribution is the classification of what ABLP's gap already demonstrates.

### 3.3 Architectural prior art: XACML PDP/PIP

The XACML 3.0 specification (OASIS Standard, 2013) formalizes the separation architecturally. The **Policy Information Point (PIP)** supplies factual information about subjects, resources, and environments — IS-facts. The **Policy Decision Point (PDP)** applies a standing policy to these facts and issues a verdict (Permit, Deny, Not-Applicable, Indeterminate). The PDP's verdict is not derivable from the PIP's outputs alone; the policy is an independent artifact that must be authored, maintained, and evaluated separately from any request. The PDP/PIP split is the architectural instantiation of the separation ABLP proves formally.

XACML does not use the vocabulary of deontic logic or Hume. It treats the separation as an architectural requirement, not a philosophical one.

### 3.4 Deontic logic: von Wright (1963) and Jones and Sergot (1996)

Von Wright's *Norm and Action* (1963; high confidence) establishes the formal apparatus of deontic logic, distinguishing normative propositions from descriptive ones and demonstrating the conservativeness of standard deontic systems (the Pigdenian point in its pre-Pigden form). Von Wright does not apply this to authentication or access control.

Jones and Sergot, "A Formal Characterisation of Institutionalised Power" (*Journal of the Interest Group in Pure and Applied Logics*, 1996; moderate confidence on exact venue) apply deontic and institutional logic to the analysis of normative systems, including the concept of institutionalized power as a deontic status conferred by an institutional structure. This is adjacent to the conferral mechanism this paper identifies. Jones and Sergot do not explicitly map the authn/authz step to the autonomy of the deontic.

### 3.5 The conferral mechanism: Searle (1964, 1995)

Searle, "How to Derive 'Ought' from 'Is'" (*Philosophical Review*, 73(1), 43–58, 1964; high confidence), argues that constitutive rules of the form "X counts as Y in context C" allow institutional facts carrying deontic powers to be derived from brute facts. *The Construction of Social Reality* (Free Press, 1995) develops the full theory of institutional reality, status functions, and deontic powers. The counts-as relation is the mechanism by which policies confer permissions on authenticated principals — the policy is the constitutive rule, and its enactment is the conferral. Searle is addressed as an objection in §4.

### 3.6 The exact defensible novelty claim (moderate confidence)

The separation of authentication facts from authorization decisions is, in sum, prior art at every level: informal (Saltzer–Schroeder), formal (ABLP), architectural (XACML), and logical (von Wright). This paper does not claim to discover the separation.

**What this paper claims:** the explicit identification of the required bridging premise as **deontic** — a policy-relative permission, the weak deontic modality — and the consequent subsumption of the authn/authz step under the autonomy of the deontic (Pigden 1989). From that classification, and only from the explicit deontic naming (so far as the literatures surveyed establish), follow:

1. The **unmeasurability result**: the gap is logical, not epistemic; no improvement in authentication technology can close it, because the gap is not a measurement deficit but the absence of a deontic premise from a purely descriptive fact-base.
2. The **failure taxonomy**: confused-deputy, ambient authority, and token-as-fact-vs-grant are instances of a single error — treating an IS-fact as carrying an OUGHT — and that diagnosis follows from the deontic naming, not from the engineering description alone. (On the weak-ought reading the paper endorses, these are more precisely *invalid inferences within a deontic system*; the class-level defensive invariant derived from the inference type of the shared error is developed in §6.2, which the reader should consult for the full argument and for the distinction between the design-level unification already achieved by the capability-security literature and the inference-type unification this paper provides.)


---

## 4. Searle, the Hare/Hudson Boomerang, and the Human-Stipulation Entry of the Ought

### 4.1 The Searle objection stated

Searle's constitutive-rule framework generates the sharpest objection to the Membrane Framing. If a constitutive rule of the form "a valid credential counts as authorization to access this resource in this system" is in force, then — under Searle's 1964 argument — the IS-fact that the credential is valid entails the authorization verdict via the rule. The is/ought gap appears to be bridged: you have derived "E may perform A" from "E presents valid credential C" together with the rule "valid C counts as authorization." The rule is stated; the brute fact is verified; the institutional fact follows.

If correct, this defeats the framing: the bridge premise is not a live normative commitment that the IS-facts cannot supply; it is a standing institutional rule that, once enacted, allows derivation from IS-facts alone.

### 4.2 The Hare/Hudson response

Hare ("The Promising Game," *Revue Internationale de Philosophie*, 70, 418–438, 1964; high confidence) and Hudson (ed., *The Is-Ought Question*, Macmillan, 1969; high confidence) respond to Searle's 1964 paper by locating a suppressed normative premise in every counts-as derivation: the agent's *acceptance of* or *subscription to* the institution. "You ought to keep your promise" derives from "you made a promise" plus the rule "promises ought to be kept" only if the agent accepts the promising institution. That acceptance is itself prescriptive — it is not a further brute fact. Searle's constitutive rule does not bridge the gap; it displaces the ought into the act of accepting the rule, which is itself an ought-bearing commitment.

The paper endorses this response: the constitutive rule "valid credential counts as permission" is an enacted normative commitment, not a logical truth or a brute fact. Before the rule was enacted, no inspection of credential properties yielded any permission. After enactment, credentials yield permissions — but only because someone made a normative commitment about what should be permitted and institutionalized that commitment as the policy. The act of enactment is the conferral; the ought enters there.

### 4.3 The boomerang: the authorization ought is inert

The Hare/Hudson response, however, generates a difficulty the paper must acknowledge rather than conceal. The Hare/Hudson suppressed premise is **endorsement** — a motivating, action-guiding commitment. "You ought to keep your promise" carries prescriptive force because the agent's subscription to the promising institution is itself practical. This is the kind of ought Hume's categorical gap most directly concerns.

A PDP "permit" verdict carries no such prescriptive force. It does not bind any agent to act. It does not motivate. It does not ground praise or blame. It is a **classification** — the policy has evaluated this request as falling in the permitted category — not a prescription. If the authz "ought" has the full Hare/Hudson endorsement character, then it imports a normativity the access-control domain does not actually contain. If it lacks that character, then it cannot recruit the full Hare/Hudson apparatus against Searle, because the apparatus was designed for prescriptive oughts.

**Resolution:** concede the point. The authorization "ought" is the **weak, policy-relative, inert** deontic permission. This does not refute the Membrane Framing; it calibrates it. The claim was never that the PDP's "permit" verdict has moral force. The claim is that the permission cannot be derived from authentication facts alone without a normative bridge premise. That claim holds under the weak ought: even a policy-relative permission requires the policy, and the policy is not derivable from signal-properties. The autonomy of the deontic applies to weak permissions exactly as it applies to stronger normative modalities (Pigden's theorem is not modality-specific).

The remaining question is: **where does the only live normative entry appear?** The answer is: at the **human act of stipulating the policy and the root of trust**. This is the Hare/Hudson "subscribing" in its application here. The system administrators, security architects, and organizational decision-makers who author, review, and deploy the access-control policy are subscribing to an institutional normative commitment. That act is prescriptive in the full Hare/Hudson sense — it is a choice about what ought to be permitted, not merely a measurement of what is the case. The policy, once stipulated, generates policy-relative permissions that are weak and inert. But the stipulation itself is where the live normative weight sits. (This locates the framing's only prescriptive claim precisely; §7.2 narrows the no-prescriptive-force disclaimer to the PDP verdict accordingly.)^[The application of Hare/Hudson to institutional actors requires that organizational normative commitments carry analogous endorsement structure to individual promising. The parallel is defensible: an organizational policy decision is a choice about what ought to be permitted, binding the organization to maintain the policy as a normative constraint — the institutional analog of the promisor's subscription to the promising institution. A full treatment of institutional agency is beyond this paper's scope.]

### 4.4 Searle relocates, does not eliminate

The full picture: Searle is right that counts-as provides the conferral mechanism — the policy is the constitutive rule that makes a valid credential count as authorization. But this does not eliminate the ought-entry; it **relocates** it to the enactment of the policy. The Hare/Hudson analysis reveals that the enactment is itself a normative act (subscription to the policy framework). The authorization verdict is policy-relative and weak; the stipulation of the policy is where the live normative commitment appears. All three points are consistent, and together they sharpen rather than undermine the framing.

---

## 5. Object-Capability Systems and Access-Control Lists: The Seam Relocates, It Does Not Vanish

### 5.1 The object-capability objection

The object-capability (ocap) model — developed through work including Dennis and Van Horn (1966), Hardy (1988), and elaborated by Miller, Shapiro, and colleagues — holds that possession of an unforgeable capability reference constitutes authorization to invoke the designated operations on the referenced object. There is no separate authorization check against an external policy table: possessing the capability IS the permission. Authentication — verifying that the holder genuinely possesses an unforgeable capability — appears to yield authorization directly.

This appears to collapse the is/ought gap. "E possesses capability C" (a verifiable IS-fact) seems to entail "E may invoke the operations designated by C" (an authorization verdict). The capability, on this view, is itself the permission encoded as a physical/logical object: the ought made bearer-portable. No separate policy query is required. The seam seems eliminated.

### 5.2 The relocation argument

The capability model does not eliminate the seam; it relocates it to **capability issuance**.

A capability is a **materialized grant** — an ought made portable. Two distinct facts are in play: (1) capability *validity* — whether a presented reference is a genuine, unforgeable capability token — and (2) capability *content* — what operations it authorizes. Validity is a purely descriptive IS-fact: the system checks that the token has the right structure and has not been forged. Content is the record of a prior normative decision: it records what a principal with appropriate authority determined E ought to be permitted to do when the token was issued. The content is not a signal-property of E measurable at presentation time; it is the trace of a prior conferral.

Before the capability was issued, no inspection of E's properties entailed that E should have access to the designated operations on the designated object. The issuance was a decision: a principal with appropriate authority determined that E ought to have this access and encoded that determination as an unforgeable token. The token carries the conferral forward in time; it does not generate it from signal-facts. When E presents the capability, the system verifies validity (IS-fact) and reads off content (also an IS-fact, given the token). But the content — what it grants — is the record of a prior normative decision, not a property of E derivable from E's signal-properties at presentation.

The is/ought seam sits at **issuance and delegation**, not at presentation.

### 5.3 ACL and capability: same seam, different location

This analysis shows that **ACL and capability architectures both exhibit the is/ought seam; they differ only in where the conferral is recorded.** In an ACL system, the conferral is recorded in a policy table external to the principal: "E may do A on R" is a row in the ACL. In a capability system, the conferral is materialized in the token and held by the principal: the capability token is the row. The seam is at the same logical point — the normative decision about what ought to be permitted — but it is recorded in different places.

Neither architecture derives the permission from signal-properties without a prior act of conferral. The ACL records the conferral centrally; the capability distributes the conferral to token-holders. Both require the conferral to have occurred, and the conferral is the normative act that the autonomy of the deontic locates as the bridge premise.

---

## 6. The Two Consequences: Unmeasurability and the Deontic Inference Failures

### 6.1 The unmeasurability result

The Membrane Framing generates a structural consequence: **the authorization gap is not closeable by improving authentication.**

This is not an epistemic observation. It is a logical one. The permission verdict is not a property of the authenticated signal; it is a property of the relationship between a recognized subject and a resource, under a standing policy. No signal-property, however precisely measured, introduces the deontic operator. Improving authentication — moving from password-based authentication to multi-factor to hardware-bound cryptographic attestation to biometric — increases the accuracy and assurance of the IS-fact "this is E." It does not change the logical structure of the authorization question: given that this is E, what is E permitted to do? That question is answered by the policy, not by the signal.

It is fair to ask why this consequence counts as a contribution of the *deontic naming* rather than something already available from the ABLP non-entailment result or the XACML PDP/PIP split. The answer is that neither prior body of work drew it, and the omission is not accidental. ABLP treats the required ACL premise as a given formal object and asks only whether the access proposition is derivable from the authentication propositions; it does not ask what *kind* of object the missing premise is. Consequently, ABLP lacks the vocabulary to distinguish a measurement deficit from a type-level one: ABLP establishes *that* the gap exists — the ACL premise is not derivable — but cannot classify *why*. Whether the gap is because the right information has not yet been gathered (an epistemic deficit, closeable by better authentication) or because the premise belongs to a different logical type (a type-level gap, uncloseable by any expansion of the descriptive base) is a question ABLP's formal machinery does not answer. The deontic naming is what supplies that classification. Once the bridging premise is identified as a permission — a member of the deontic vocabulary — the gap is immediately typed as a type-level gap, not an information gap. An engineer could accept PDP/PIP necessity as a design constraint while believing that sufficiently strong authentication would eventually substitute for policy; the unmeasurability result rules this out at the level of inferential structure, not design discipline, because the deontic operator cannot be introduced by any descriptive base regardless of how that base is organized or how precisely it is measured.

XACML architects describe the PDP/PIP split as an engineering requirement — a separation of concerns motivated by maintainability, auditability, and reuse — without deriving from it the claim that *no signal improvement can substitute* for the policy. The architectural necessity of the split (two components, separately maintained) is a weaker statement than the logical necessity of the gap (the deontic operator is absent from the descriptive base as a matter of inferential form). The PDP/PIP split says *keep these two components apart*; the unmeasurability result says *you could not collapse them even if you wanted to, because no quantity or quality of IS-facts entails an OUGHT*. The former is an engineering recommendation; the latter is a theorem about the inference, and it is the deontic classification that exposes it.

This has a practical consequence that the engineering slogan ("authentication is who you are; authorization is what you may do") does not directly generate. The slogan suggests a sequential pipeline: verify first, then permit. The unmeasurability result says: the permitting step is not a further measurement in the same pipeline; it is a different kind of operation, drawing on a different kind of premise. Making the first step better does not improve the second step. Systems that assume otherwise — that stronger authentication implies or deserves broader authorization — are not merely making a policy error; they are making a structural error about the kind of operation authorization is.

### 6.2 Deontic inference failures at the is/ought seam

Three canonical failure patterns in access control share a single formal structure under the Membrane Framing. The claim of this section is that the deontic naming does work the engineering descriptions do not: it shows that confused-deputy, ambient authority, and token-as-fact-vs-grant are instances of one error class, and that the unification yields a single class-level defensive invariant rather than three failure-specific patches.

**Prior design-level unification and what the deontic framing adds.** The capability-security program — Hardy (1988), Dennis and Van Horn (1966), and the ocap literature (Miller, Shapiro) — already recognized confused-deputy, ambient authority, and injection attacks as a family and developed the object-capability model as a unified architectural response. That prior unification is at the *design level*: it identifies that the three failures share a common engineering remedy (capability discipline) and produces an architectural program to instantiate that remedy. The Membrane Framing provides a different, complementary unification at the *inference-type level*: it identifies the formal property — an IS-predicate serving as premise for a permission conclusion the autonomy of the deontic bars it from supplying — that is common to all three failures. The two unifications are consistent and mutually illuminating. The design-level unification says: use capability discipline uniformly. The inference-type unification says: here is why that discipline works — the failures share one logical form, and the discipline enforces the one structural requirement (an explicit deontic bridge at the permission conclusion) that the shared form requires. The inference-type unification generates the class-level invariant from logical structure rather than from the engineering history of the failures.

**The unification argument.** Hardy (1988), the ambient-authority literature (Miller, Shapiro), and OAuth/XACML architectural documentation each characterizes its respective failure pattern independently, with independently stated remedies: per-request authorization checks for confused-deputy, capability discipline for ambient authority, server-side token validation for token-as-fact-vs-grant. The engineering diagnoses are precise and complete on their own terms. What the deontic framing adds is not a new engineering diagnosis but the identification of a common formal structure: in each case, an IS-predicate is allowed to serve as the premise for a permission conclusion that it cannot, by the autonomy of the deontic, supply. That common form is not stated in the engineering literature as a single checkable structural property. The deontic framing provides that property — *no IS-predicate about a principal, a process context, or a token may serve directly as a premise for a permission conclusion without an explicit deontic bridge* — and from that common structure follows a single class-level defensive criterion (PIP/PDP separation enforced as a design invariant, applicable uniformly) rather than three independently discovered patches. The engineering literature arrives at each remedy on its own terms; the deontic framing shows they are one remedy, derived from the structure of the error.

**The class-level invariant.** Because the failures share one formal structure, they share one defensive criterion: *no IS-predicate about a principal, a process context, or a token may serve directly as a premise for a permission conclusion; the conferral must be located explicitly and evaluated at the point of the permission decision.* In XACML terms this is the PIP/PDP separation enforced as a design invariant — IS-facts flow to the PIP, and only the PDP, evaluating the standing policy, may emit a permission. This is what the inference-type unification buys that the failure-by-failure engineering descriptions do not: a single invariant whose violation predicts all three failures, rather than three independently discovered remedies. The capability-security program arrives at capability discipline through engineering reasoning about the failures; the deontic framing derives the same invariant from the logical type of the shared error.

**Scope of the "category error" gloss.** Under the *strong* reading of the ought — the categorical, agent-binding reading — collapsing the IS-fact into the OUGHT-grant is a category error in the Rylean sense: it predicates a permission of a thing (a signal, a process, a token) that is not the kind of thing that bears permissions. The paper does not rest on the strong reading. Under the *weak*, policy-relative reading the paper endorses for the authz domain, the failures are more precisely *invalid inferences within a deontic system* — treating an IS-fact as a premise that licenses a deontic conclusion it cannot supply. The pattern, the unification, and the class-level invariant are identical under both readings; only the philosophical label "category error" is calibrated to the strong reading, and it is offered as a gloss, not as the paper's endorsed characterization.

The three cases, in detail:

**Confused-deputy attack** (Hardy 1988). A component A has been authorized by policy to perform action X on resource R. An attacker B sends a request to A that causes A to perform X on R on B's behalf, using A's policy-granted authorization. B has not been authorized; B has exploited A's authorization by causing A to act as B's deputy. The attack succeeds because the system treats A's verified identity (IS-fact: this is A; A is authenticated) as bearing A's authorization entitlements (OUGHT-grant: A may do X to R), and does not check whether the *request* — as opposed to the *requester* — is authorized. The IS-fact of A's identity is treated as licensing the OUGHT-grant of A's permissions to any request A relays. The Membrane Framing gives the logical name to what Hardy's paper describes operationally, and places it in the same error class as the next two.

**Ambient authority.** Systems that grant permissions to an authenticated principal's entire process context — rather than requiring explicit capability grants per operation — make the same structural error at scope. The principal is authenticated (IS-fact); their entire ambient authorization is then available to any code running in their context (OUGHT-grant licensed by the IS-fact of process identity). The conflation is the source of injection attacks, confused-deputy variants, and privilege-escalation chains that exploit the gap between "authenticated as this user" and "authorized for this specific operation in this specific context."

**Token-as-fact vs. token-as-grant.** A bearer token in OAuth 2.0 or a JWT carries authorization claims — scopes, roles, permissions. There are two ways to treat such a token: as a **fact-certificate** ("this token proves that E has role R, which is a fact about E") and as a **grant-certificate** ("this token grants permission to perform the operations associated with role R"). The difference matters at the seam. Treating the token as a fact-certificate means further policy evaluation is required to convert the role-fact into a permission verdict. Treating the token as a grant-certificate means the token itself carries the authorization. Systems that conflate these — that accept a token claiming a role and derive permissions from the role-claim without separate policy evaluation — are treating the IS-fact content of the token (E claims role R) as licensing the OUGHT-grant (E may do what role R permits). The correct architecture treats the token as supplying IS-facts to the PIP, which the PDP then evaluates against the standing policy to issue the permission verdict — precisely the class-level invariant above.

The taxonomy is not exhaustive. Its value is the unified logical description of a family of failures the engineering literature describes individually, together with the single defensive invariant that the inference-type unification generates.

---

## 7. Scope and Limits

### 7.1 Where the framing applies

The Membrane Framing holds wherever:

1. There is a verification procedure that produces IS-facts about a presented claim (identity, credential, token, biometric, behavioral signal).
2. There is a policy that produces authorization verdicts about permitted actions.
3. The policy's verdicts are not derivable from the verification facts alone — they require a standing normative commitment that precedes any individual request and is not derivable from the signal.

Condition (3) is the operative one, and it holds for any access-control policy of non-trivial content. A policy with trivial content — "any authenticated principal may do everything" — instantiates the framing trivially: the policy is the standing conferral ("may do everything"), and it still cannot be read off the signal-properties of the authenticated credential.

The framing applies to rule-based systems (RBAC, ABAC, XACML) where the PDP/PIP separation is architecturally explicit. It applies to capability systems (§5), where the seam is at issuance rather than evaluation. It applies to hybrid systems. In systems where authorization is determined by continuous behavioral evaluation rather than declared policy, the behavioral criteria that determine authorization are themselves normative — they reflect a choice about what counts as authorized behavior — and that choice is not derivable from the behavior it classifies.

### 7.2 What the framing does not claim

The framing does not claim that **the PDP's permission verdict** — the "permit" output — has prescriptive force on human agents. That verdict is a policy-relative classification; it binds no one and motivates nothing directly. This disclaimer is scoped deliberately to the PDP verdict, not to the authorization domain in general. The framing *does* make a prescriptive claim, but at a different level: the live, prescriptive, action-guiding normative entry appears at the **human act of policy stipulation** (§4.3), where the Hare/Hudson endorsement analysis applies. The two claims are consistent: the human stipulation is prescriptive; the machine verdict it licenses is inert. Denying prescriptive force to the verdict is required to stay within the weak-ought scope; affirming it of the stipulation is required to resolve the Searle boomerang. The level distinction is what makes both true at once.

The framing does not claim to determine what policies are correct, fair, or legitimate. It is a logical claim about the structure of the inference from credential-facts to permission-verdicts, not a normative claim about how policies should be designed. It is compatible with any normative theory of access control.

The framing does not extend automatically to questions of policy justification, governance, or ethics. Those are further normative questions that require further normative premises — exactly as the autonomy of the deontic would predict.

### 7.3 The falsification condition

The framing is **refuted** — not merely challenged — if and only if a coherent access-control architecture can be exhibited in which authorization verdicts are fully and correctly derived from authentication signal-properties alone, with:

(a) **no standing policy conferral and no act of capability issuance** — no row in an ACL, no issued token, no enacted constitutive rule; and
(b) **no policy treated as a descriptive fact derivable without a prior normative act of stipulation** — that is, the Searle-style escape must also be foreclosed. It is not enough to point to a policy that is "in force" as though its being in force were a brute signal-property. Per §4, a policy's being in force is the product of a prior human act of stipulation (the Hare/Hudson "subscribing"); a system in which the policy itself were read off signal-properties, with no such prior normative act anywhere in its history, is what condition (b) demands and what the framing claims does not exist.

A system satisfying both (a) and (b) would be one in which "may" follows logically from "is" with no bridge premise anywhere — where the deontic operator is introduced by descriptive premises alone, including the descriptive premise that a given policy obtains. To the best of this paper's knowledge, no such architecture exists or has been proposed. The falsification condition is stated because the framing, to be taken seriously, must be falsifiable: if someone produces such an architecture, the framing fails.

The negative claim — that no such architecture is known — is not the same as the claim that none could exist. The paper asserts only the former, at the confidence level appropriate to the literatures surveyed.

---

## 8. Relation to the Broader Membrane Program

This paper extracts one result from a larger research program (the "membrane" project) concerned with the pattern of a deciding seam irreducible to either of the two states it mediates. The broader program spans biological membranes, philosophical structures (meaning, agency, sourcehood), and engineered systems.

The Membrane Framing as presented here is self-contained. It makes no claims from the broader program beyond the identification of the authorization layer as a deciding seam. The philosophical argument stands independently.

---

## 9. Conclusion

Authentication delivers IS-facts. Authorization delivers policy-relative permission verdicts — deontic judgments of the weak modality (von Wright's ¬O¬p). The step between them requires a bridging premise that is deontic in character: a standing policy that maps authenticated facts to permitted actions. No conjunction of authentication facts, however exhaustively verified, supplies that premise. This is an instance of the **autonomy of the deontic** (Pigden 1989, formalizing Hume's law): valid inference introduces no new non-logical vocabulary, so no purely descriptive base entails a permission verdict.

The separation itself is prior art at every level — informal (Saltzer–Schroeder), formal (the ABLP authentication calculus, where access requires a separate ACL premise not derivable from the "says"/"speaks-for" facts), architectural (XACML PDP/PIP), and logical (von Wright). What this paper contributes is the explicit identification of ABLP's required bridge premise as **deontic**, the subsumption of the authn/authz step under the autonomy of the deontic, and — from that naming alone (so far as the literatures surveyed establish) — two consequences those literatures did not draw: the unmeasurability result (no authentication improvement closes a logical, not merely architectural, gap) and the unification of confused-deputy, ambient authority, and token-as-fact-vs-grant into a single class of deontic inference failures with one class-level defensive invariant, derived from the inference type of the shared error rather than from the design history of the failures.

The Searle counts-as objection does not refute the framing; it supplies the mechanism by which the conferral is institutionalized (the policy is the constitutive rule) and relocates the active normative entry to the human act of policy stipulation, where the Hare/Hudson analysis applies. The object-capability objection likewise relocates the seam to capability issuance rather than eliminating it. In both cases, the is/ought seam is present; it is the conferral point that differs.

The contribution is honest: a framing and classification at moderate novelty. The authorization domain does not contain the categorical, prescriptive oughts of moral philosophy — those appear only at the human act of stipulation. It contains policy-relative permission verdicts, and those are enough to exhibit the autonomy of the deontic cleanly — as cleanly as chess or grammar. The engineering and philosophical payloads are real. The metaethical overreach of claiming identity with Hume's categorical guillotine is not.

---

## References

Abadi, M., Burrows, M., Lampson, B., and Plotkin, G. (1993). A calculus for access control in distributed systems. *ACM Transactions on Programming Languages and Systems*, 15(4), 706–734. [High confidence.]

Dennis, J. B., and Van Horn, E. C. (1966). Programming semantics for multiprogrammed computations. *Communications of the ACM*, 9(3), 143–155. [High confidence; the canonical origin of the capability model and the load-bearing capability citation in this paper.]

Hardy, N. (1988). The confused deputy: (or why capabilities might have been invented). *ACM SIGOPS Operating Systems Review*, 22(4), 36–38. [High confidence.]

Hare, R. M. (1964). The promising game. *Revue Internationale de Philosophie*, 70, 418–438. [High confidence on title and approximate year; moderate confidence on volume number.]

Hudson, W. D. (ed.). (1969). *The Is-Ought Question: A Collection of Papers on the Central Problem in Moral Philosophy*. London: Macmillan. [High confidence.]

Hume, D. (1739–40). *A Treatise of Human Nature*. Book III, Part I, Section I. London: John Noon. [High confidence.]

Jones, A. J. I., and Sergot, M. (1996). A formal characterisation of institutionalised power. *Journal of the Interest Group in Pure and Applied Logics*, 4(3), 427–443. [Moderate confidence on exact venue and volume; the characterization of institutionalized normative power in deontic-institutional logic is attributed at high confidence.]

Lampson, B., Abadi, M., Burrows, M., and Wobber, E. (1992). Authentication in distributed systems: Theory and practice. *ACM Transactions on Computer Systems*, 10(4), 265–310. [High confidence.]

Miller, M. S., Shapiro, J. S., and Tribble, E. D. (2003). Capability myths demolished. *Technical Report SRL2003-02*, Systems Research Laboratory, Johns Hopkins University. [Moderate confidence on year and venue; grey literature. This citation is not load-bearing — it supplements but does not ground the capability discussion in §5; Dennis and Van Horn (1966) is the canonical and load-bearing source. A venue requiring peer-reviewed sources may drop this entry without affecting the argument.]

OASIS. (2013). *eXtensible Access Control Markup Language (XACML) Version 3.0*. OASIS Standard. [High confidence.]

Pigden, C. R. (1989). Logic and the autonomy of ethics. *Australasian Journal of Philosophy*, 67(2), 127–151. [High confidence on author, title, and approximate year; moderate confidence on exact volume and page numbers — cite with caveat if submitting to a venue requiring verified page ranges.]

Saltzer, J. H., and Schroeder, M. D. (1975). The protection of information in computer systems. *Proceedings of the IEEE*, 63(9), 1278–1308. [High confidence.]

Searle, J. R. (1964). How to derive 'ought' from 'is.' *Philosophical Review*, 73(1), 43–58. [High confidence.]

Searle, J. R. (1995). *The Construction of Social Reality*. New York: Free Press. [High confidence.]

von Wright, G. H. (1963). *Norm and Action: A Logical Enquiry*. London: Routledge and Kegan Paul. [High confidence.]
