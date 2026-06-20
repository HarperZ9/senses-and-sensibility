<!-- EDITORIAL ERRATUM — read MEMBRANE-ERRATA.md before citing or submitting -->

> **Reframe required before submission.** Three adversarial passes (`MEMBRANE-REVIEWS.md`,
> `MEMBRANE-NOVELTY.md`, `MEMBRANE-ERRATA.md`) converge: this is a *framing /
> operationalization* of the **autonomy of the deontic** (Pigden), **not** an *identity*
> with Hume's categorical guillotine; the authn/authz *separation* is prior art
> (ABLP 1992/1993; von Wright; Searle's counts-as supplies the conferral); the
> defensible residue is the **deontic naming** of the bridging premise and its
> consequences (unmeasurability; the confused-deputy taxonomy). The draft below is
> retained as written — `MEMBRANE-ERRATA.md` governs what it may claim.
>
> **Superseded by `MEMBRANE-PAPER-v2.md`** — the revised, submittable Unit 2 (errata
> applied; retitled *The Membrane Framing*). This v1 is kept as the pre-errata draft
> of record.

# The Membrane Identity: Authentication, Authorization, and Hume's Guillotine

## 1. The claim, stated precisely

Authentication and authorization name two distinct operations in access control. Authentication answers the question: *Is this claim true?* Is this credential valid? Is this signal intact and untampered? Is this entity who it presents itself as? Authorization answers a different question: *May this entity act?* Given that the claim is true, is the action permitted?

The claim of this paper is that these two questions are not merely different in subject matter but different in logical kind — and that the difference is Hume's is/ought gap.

Authentication, when it succeeds, delivers a fact: a proposition of the form *this credential is valid*, *this signature verifies*, *this token matches the expected value*. These are IS-facts. They are the output of a verification procedure applied to a signal. They can in principle be measured, computed, and certified with arbitrarily high confidence.

Authorization, when it succeeds, delivers a grant: a deontic verdict of the form *this principal MAY perform this action on this resource*. This is an OUGHT-judgment — or more precisely, a permission, which is the weak deontic modality (¬O¬p: it is not obligatory that p not occur). It is not a measurement of a signal. It is a verdict issued by a policy that stands over and above any signal, and the policy's verdict is not entailed by the signal's properties however completely those properties are known.

The structural identity this paper defends: **the step from authentication to authorization is the step from is to ought, and it exhibits exactly the logical gap Hume identified in moral philosophy — no fact about a signal, however precisely measured, entails a permission.**

The paper calls this the Membrane Identity because it locates a deciding seam — the policy decision — that is neither a property of the incoming signal nor a property of the protected resource, but a standing conferral that mediates between them. This terminology is borrowed from a broader research program (the "membrane" project, from which this paper extracts one result as a standalone contribution), but the philosophical argument stands independently of that program.

---

## 2. Hume's guillotine: the relevant structure

Hume's observation appears in *A Treatise of Human Nature* (1739–40, Book III, Part I, Section I). In one of the most discussed paragraphs in the history of ethics, Hume notes that moral writers imperceptibly shift from propositions linked by "is" and "is not" to propositions linked by "ought" and "ought not," without explaining how this transition is made or why it is permissible. He takes the transition to require justification — justification that he implies is unavailable, because the logical connective changes and nothing in the premises licenses it.

The philosophical literature on Hume's guillotine (the name is due to later commentators; the image of a blade that separates fact from value) is vast and contested. The point that matters for this paper is narrow: **within standard two-valued propositional logic, no set of purely descriptive (non-normative) premises entails a normative conclusion.** This is a logical point, not a metaphysical one. It does not depend on moral realism or anti-realism, on whether values are objective, or on any contested claim about practical reason. It depends only on the observation that "is" and "ought" (or their deontic equivalents — may, must, must not) are different predicates, and that valid inference preserves logical form.

For the purposes of this paper, the relevant form of the gap is:

- Factual premise: *Entity E presents credential C, and C is valid.*
- Conclusion that does NOT follow: *Entity E may perform action A on resource R.*

The conclusion introduces a deontic operator (may, permission) not present in the premise. No conjunction of further IS-facts — the history of C, the integrity of the channel, the timestamp of the request — introduces the deontic operator. It must come from somewhere else: a policy, a rule, an institutional grant. That is the bridging conferral that Hume's gap demands.

This is not a surprising claim in philosophy. What this paper claims — and what, to the best of its knowledge, has not been explicitly stated before — is that this structure is precisely and completely instantiated in the distinction between authentication and authorization in access-control systems, and that recognizing the identity has non-trivial consequences for how we think about the architecture of those systems and about what goes wrong when the distinction is collapsed.

---

## 3. The prior art: what has been said, and what is new

### 3.1 The is/ought gap in philosophy

Hume's observation is the primary source (1739–40, high confidence). The "naturalistic fallacy" literature in ethics (G.E. Moore, *Principia Ethica*, 1903) extends the point from descriptive to natural-property premises. The deontic logic literature (von Wright, *Norm and Action*, 1963; high confidence) formalizes the distinction between propositions expressing norms and propositions describing states of affairs, and demonstrates that valid inference from purely descriptive premises cannot yield normative conclusions without normative premises.

None of this literature concerns authentication or authorization. The connection is not drawn.

### 3.2 Searle's constitutive rules and counts-as

Searle's *Speech Acts* (1969) and *The Construction of Social Reality* (1995) introduce the notion of constitutive rules — rules of the form "X counts as Y in context C" — as the mechanism by which institutional facts are created. Institutional facts (money, property, marriage, legal status) are facts that depend on collective recognition and institutional structures; they contrast with brute facts (physical states of affairs). Searle's framework is the most powerful objection to the Membrane Identity and is addressed at length in §5.2 below.

### 3.3 Security literature on authn/authz

Saltzer and Schroeder's foundational paper "The Protection of Information in Computer Systems" (*Proceedings of the IEEE*, 1975) distinguishes between authentication and access control (authorization). The distinction is well-established in the engineering literature. The XACML 3.0 specification (OASIS, 2013) formally separates the Policy Decision Point (PDP), which issues authorization verdicts, from the Policy Information Point (PIP), which supplies factual information about subjects, resources, and environments. The PDP/PIP separation is the architectural instantiation of the gap this paper analyzes.

Neither Saltzer–Schroeder nor the XACML specification discusses Hume. The separation is treated as an architectural good practice, not as a logical necessity with philosophical grounding.

### 3.4 Object-capability literature

The object-capability (ocap) model — developed in work including Dennis and Van Horn (1966), Hardy (1988), and later Miller, Shapiro, and Tribble's "Capability Myths Demolished" (2003, moderate confidence on exact year) — proposes that possession of an unforgeable capability token constitutes authorization to perform the associated action. This is the strongest structural objection to the Membrane Identity and is addressed at length in §5.1 below.

Hardy's "The Confused Deputy" (1988) is the canonical paper demonstrating a class of attacks that arises when authentication is mistaken for authorization — when a system uses a caller's verified identity rather than the caller's capabilities to determine what the caller may do. The paper argues for capability-based access control as the remedy. This paper agrees with Hardy's diagnosis (confused-deputy attacks are real and important) while arguing that the capability model relocates rather than dissolves the is/ought gap.

### 3.5 What is and is not claimed as new

The Membrane Identity is *not* claimed as the first observation that authentication and authorization are distinct. That distinction is decades old in engineering and implicit in Saltzer–Schroeder. It is *not* claimed as the first use of Hume's gap in the context of computing or information systems; there may be pedagogical uses this paper is not aware of. It is *not* claimed as a novel philosophical principle; the is/ought gap is Hume's.

What is claimed: that the identity — "the authentication/authorization distinction *is* (is structurally identical to, not merely analogous to or illuminated by) Hume's is/ought gap" — has not been explicitly stated and defended as a formal claim in the prior literature this paper can locate. Prior uses appear to be pedagogical framings ("you can think of authn/authz as a bit like is/ought") or incidental analogies, not systematic arguments for structural identity with philosophical consequences. The claim is modest: **identity, not novelty of subject matter.** The contribution is in making precise what the identity consists in, confronting the objections, and stating the limits.

---

## 4. The argument for the identity

### 4.1 What authentication establishes

Authentication is a verification procedure. It takes as input a presented claim — an identity assertion, a credential, a token — and produces as output a verdict about that claim's truth or validity. The verdict is of the form:

*This token matches the expected value / this signature verifies against the public key / this biometric matches the stored template / this password hash matches.*

This verdict is a fact. It is a fact about the relationship between a presented signal and a stored reference. It is in principle measurable, auditable, and independently verifiable. It carries no deontic content. The authentication system that outputs "credential valid" has said everything it can say about what IS the case regarding this credential. It has said nothing about what OUGHT to happen next.

The IS-character of authentication output is not merely definitional. It is structural: any additional claim the authentication system makes beyond "this credential is valid" — for instance, "this entity is therefore permitted to read this file" — is no longer authentication output. It is authorization output, and it requires a policy that is not present in the authentication verdict alone.

### 4.2 What authorization delivers

Authorization is a policy application. It takes as input a subject (a verified principal), an action, a resource, and the environmental context — and applies a standing policy to issue a deontic verdict:

*This principal MAY (or MAY NOT) perform this action on this resource in this context.*

The output is a permission (or prohibition). Permissions and prohibitions are normative entities. They are not measurements. They cannot be extracted from the signal. They are issued by a policy that exists independently of any individual request and would issue the same verdict for any request with the same parameters, regardless of the signal's properties beyond what the policy expressly references.

The OUGHT-character of authorization output is likewise structural: the policy decision point's verdict is not a further measurement of the signal. It is an application of a norm to a classified subject. The PDP says "given that the PIP has established these facts about the subject and resource, my policy says: permitted." The "my policy says" is the bridging conferral. It does not come from the signal.

### 4.3 The gap, precisely located

The gap is located at the seam between the PIP's fact-output and the PDP's permission-verdict. The PIP can supply arbitrarily detailed facts: the subject's verified identity, role memberships, group assignments, security clearance level, time of request, origin IP, device posture. None of these facts, taken jointly or severally, entails the permission verdict. The permission verdict is issued because a standing policy maps this combination of facts to a deontic outcome — and that mapping is itself a normative choice, not a logical consequence of the facts.

To see this: imagine two systems identical in every fact the PIP can supply. Both present the same credential, the same role membership, the same clearance level, the same request parameters. One system grants access; the other denies it. This is perfectly coherent. They have different policies. The facts are identical; the authorization verdicts differ because the policies differ. The policies are not derivable from the facts; they are choices about what ought to follow from facts of this kind.

This is Hume's gap in operational form. The facts about the signal — however complete — underdetermine the deontic verdict. Something else must supply the ought: the policy, the rule, the standing conferral. And that conferral is not a property of the signal; it is a standing normative commitment that precedes any individual request.

### 4.4 The conferral is not measurable

A further consequence: the grant cannot be recovered by measuring the signal more carefully. This is not an epistemic limitation — it is a logical one. The most perfectly authenticated request carries no information about what the requestor is permitted to do, because permission is not a property of requests. It is a property of the relationship between a recognized subject and a resource, under a policy. No improvement in authentication technology bridges the gap, because the gap is not a measurement gap; it is a logical gap between two different kinds of predicate.

This has a practical consequence. Systems that mistake authentication quality for authorization — that treat a more strongly verified identity as automatically carrying more permission — are not merely making an engineering mistake; they are making a category error. They are treating an IS-fact (this identity is strongly verified) as if it entailed an OUGHT-judgment (this identity is therefore more permitted). The confused-deputy attack class (Hardy 1988) exploits exactly this error: a component with verified legitimate identity is used by an attacker to request actions that the component is authorized to perform but the attacker is not. The authentication system confirms the component's identity correctly; the authorization failure is the mistaken inference that the component's verified identity authorizes the request.

---

## 5. Confronting the hard objections

### 5.1 Object-capability systems: does possessing the token collapse the gap?

The object-capability (ocap) model is the most direct structural challenge to the Membrane Identity. In an ocap system, a capability is an unforgeable reference to an object together with the right to invoke a specified set of operations on that object. Crucially, the capability *is* the authorization: if you hold the capability, you may invoke the operation. There is no separate authorization check against an external policy. Possession of the capability IS permission.

This appears to collapse the is/ought gap: "E possesses capability C" (an IS-fact, in principle verifiable) entails "E may invoke the operations designated by C" (an OUGHT-verdict). Authentication — verification that E genuinely holds C and has not forged it — seems to yield authorization directly.

The objection deserves the sharp response it has earned: **the capability model relocates the conferral; it does not eliminate it.**

The permission encoded in the capability had to be conferred at some prior point. The capability was issued. Issuance is an act: a principal with appropriate authority decided that entity E should have access to object O with rights R, and created the capability token encoding that decision. That act of creation is the conferral, and it is exactly the ought-grant that the Membrane Identity identifies: someone decided that E OUGHT to be able to invoke R on O, and instantiated that decision as a token.

The ocap model's elegance is precisely that it *materializes* the conferral — makes it a first-class object that can be passed, revoked, and managed. But materialization is not elimination. The token carries the conferral forward in time; it does not generate it from signal-properties. Before the token was issued, no inspection of E's properties — identity, behavior, history — entailed that E ought to have access to O. The issuance was a policy decision.

Put structurally: in a capability system, authentication verifies that E holds C and that C is a genuine unforgeable capability (IS-facts). What C then authorizes E to do is a fact about C's content (also an IS-fact, once C's issuance is given). But C's issuance is itself an authorization event — a prior conferral — and it exhibits the gap. The gap is pushed to the issuance point; it is not closed. The regress of authority that any access-control hierarchy faces — every delegated permission presupposes a delegation that was itself authorized — terminates not in a measured fact but in a root conferral that is not derived from signal-properties. That root is where the ought enters.

The capability model is a powerful and arguably superior architecture for access control. The Membrane Identity does not argue against it. It argues that even within that model, the is/ought gap is present at the issuance layer. A system in which capabilities could be derived purely from signal-properties — with no act of conferral, no policy decision, no grant — would not be an access-control system; it would be a measurement instrument. The permission would be absent.

### 5.2 Searle's counts-as: does a constitutive rule bridge the gap?

Searle's constitutive rules have the form "X counts as Y in context C." In the relevant application: "a valid credential counts as permission to access this resource in this system." If such a constitutive rule is in force, then — it seems — the IS-fact that the credential is valid entails (by the rule) the permission verdict. The gap is bridged by the rule. The Membrane Identity is refuted.

This is the sharpest objection, and it deserves a careful response.

First, notice what the constitutive rule does. It does not deduce the permission from the credential-properties. It *declares* that valid credentials count as permissions in this system. The declaration is itself a normative act — an act of rule-making, of institutional creation. Searle is clear on this: constitutive rules create the institutional fact they define (they are not merely regulative rules that govern pre-existing facts). The rule "a valid credential counts as permission" does not exist independently of an act of enactment. Someone — an institution, a policy-maker, a system designer — decided that this ought to be the case and enacted the rule.

That act of enactment is the conferral that the Membrane Identity identifies. The constitutive rule does not bridge the gap; it *instantiates the bridging* as an institutional act. Before the rule was enacted, no fact about credentials entailed any permission. After the rule is enacted, valid credentials yield permissions — but only because the rule was conferred. The rule is itself an ought, created by a prior normative act.

Searle's framework actually supports this reading. He is explicit that institutional facts depend on collective recognition and that the constitutive rules must be accepted and maintained by a community. The "counts as" relation is not a logical truth; it is an institutional achievement. Change the institution — revoke the rule — and valid credentials no longer count as permissions. The permission is not a property of the credential; it is a property of the rule-system in which the credential is interpreted.

Second, consider what it would mean for the constitutive rule to bridge the gap in the strong sense — to make the permission a logical consequence of credential-validity with no additional normative premise. This would require that the rule itself is not a normative entity but a descriptive one. But "X counts as Y" is not a description of a physical state of affairs; it is the institution of a social practice. To treat the rule as a brute fact — as if it were a law of physics rather than a human institution — is to ignore exactly what Searle says makes institutional facts distinctive: they depend on ongoing acceptance, are created by declaration, and can be dismantled by counter-declaration.

The Searle objection, then, shows not that the gap is bridged but that gaps can be institutionalized — can be given a standing bridging structure in the form of a constitutive rule. This is an important observation. It explains why authorization systems that use rule-based policies function: they have institutionalized the bridging conferral in the form of a policy that governs which IS-facts yield which OUGHT-verdicts. But the policy is itself the standing conferral; it does not derive from the facts it classifies.

To put it as directly as possible: the constitutive rule smuggles the ought. "A valid credential counts as permission" is a rule that was chosen, enacted, and maintained as a normative commitment. It is not a logical truth. It is not derivable from the properties of credentials. The ought in "counts as permission" is supplied by the act of enactment — precisely the conferral the Membrane Identity locates. Searle's framework explains how the conferral is institutionalized; it does not show that the conferral is unnecessary.

---

## 6. Failures predicted by the identity

The Membrane Identity is not merely a classification claim. It predicts a specific class of failures — failures that arise when the gap is collapsed, either by design or by accident.

**The confused-deputy attack** (Hardy 1988). A component A has been authorized to perform action X on resource R. An attacker B sends a request to A that causes A to perform X on R, using A's authorization rather than B's. B has not obtained authorization; B has exploited A's authorization by supplying an authentic request. The attack works because the system confused A's verified identity with A's authority: it treated the IS-fact (this is A's request) as if it entailed permission for the action A's request specifies. The gap between authentication (this is A) and authorization (A may do X to R on behalf of B) was collapsed. The predicted failure is a class of privilege escalation attacks, and it is exactly what is observed.

**Policy bypass via credential elevation**. Systems that treat higher authentication assurance as implying broader authorization — that grant more access to more strongly authenticated principals — are making the inferential error the Membrane Identity identifies. The strength of the credential is an IS-fact; the breadth of the permission is an OUGHT-grant. A more strongly authenticated principal is not thereby more authorized; they are more certainly identified. The authorization must still be conferred by policy.

**Authentication-only architectures**. Systems designed around the principle "if you can authenticate, you can act" — with no separate authorization layer — are not merely insecure; they are architecturally incoherent. They have built a wire where they needed a deciding membrane. The system that admits any correctly authenticated request is not an access-control system; it is an identity-verification system with no access control. The confusion is common enough that it has a standard remediation: add an authorization layer. The Membrane Identity explains why this layer cannot be eliminated by making authentication more sophisticated.

---

## 7. Scope and limits

The Membrane Identity holds for access-control architectures that separate the verification of a claim from the decision about what a verified claimant may do. More precisely, it holds wherever:

1. There is a verification procedure that produces IS-facts about a presented claim.
2. There is a policy that produces OUGHT-verdicts about permitted actions.
3. The policy's verdicts are not derivable from the verification facts alone — they require a standing normative commitment (a policy) that precedes any individual request.

The identity does not hold — or holds trivially — for systems in which there is no meaningful distinction between "who you are" and "what you may do." In a single-user system with no access control, authentication and authorization collapse because the policy is the trivial one: "the only user may do everything." The identity is present but vacuous.

The identity does not commit to any particular account of where policies come from, how they are justified, or what makes a policy good or bad. It is a logical claim about the structure of the inference from credential-facts to permission-verdicts, not a normative claim about how policies ought to be designed. It is compatible with any normative theory of access control.

The identity does not extend automatically to the question of whether a policy is correct, fair, or legitimate. Those are further normative questions that the Membrane Identity does not address. It addresses only the structural question: given that there is a policy, the permission it grants is an OUGHT not derived from IS-facts.

The identity applies most cleanly to declarative, rule-based authorization systems (RBAC, ABAC, XACML) where the PDP/PIP separation is architecturally explicit. It applies with equal force to capability systems, where the conferral is located at capability issuance. It applies with some analytical cost to implicit or emergent authorization systems (e.g., systems where authorization is determined by observed behavior rather than declared policy), but even in those cases, the behavioral criteria that determine authorization are normative — they reflect a decision about what counts as authorized behavior, and that decision is not derivable from the behavior it classifies.

**The identity fails** — is genuinely refuted, not merely challenged — if and only if a coherent access-control architecture can be exhibited in which authorization is fully read off the properties of the authenticated signal with no standing policy conferral and no act of issuance. Such a system would be one in which "may" follows logically from "is," with no bridge premise. To the best of this paper's knowledge, no such architecture exists, because the "may" in any access-control verdict is not a function of signal properties but of policy commitments.

---

## 8. The architecture of the conferral: the PDP as deciding seam

The policy decision point in standard access-control architecture is instructive. The PDP receives a request (subject, action, resource, context), queries the PIP for factual information, evaluates applicable policies, and issues a verdict (permit, deny, not-applicable, indeterminate). The PDP is not a measurement instrument; it is a judgment engine. It applies normative rules to facts.

The PDP exhibits all the features the Membrane Identity identifies:

- It is neither the incoming signal nor the protected resource. It is the deciding layer between them.
- Its verdict is not a function of the signal alone; it is a function of the signal as classified by a policy.
- The policy is a standing normative commitment that must be authored, maintained, and enforced independently of any individual request.
- Removing the policy (setting it to empty or trivially permissive) does not leave the signal bearing the authorization; it leaves the system with no authorization layer at all.

This architecture — PDP separate from PIP, policy authored independently of signal-properties, verdict not entailed by facts alone — is the engineered acknowledgment of the is/ought gap. The architectural separation is not a convenience; it is a necessity. A system that collapsed PDP and PIP — that derived authorization from signal-verification facts by logical consequence alone — would not be an access-control system; it would be a system with a single signal-measurement step that doubled as a permission grant. The security consequence would be exactly what Hardy identified: every authenticated caller would be authorized to do whatever the signal-verification confirms it can prove itself capable of requesting.

---

## 9. Relation to the broader membrane program

This paper extracts one result from a larger research program concerned with what has been called the "membrane" structure — the pattern of a deciding seam that is irreducible to either of the two states it mediates. The broader program spans biological membranes (the lipid bilayer, the action potential threshold), philosophical membranes (the standpoint that confers significance in meaning and sourcehood in agency), and engineered membranes (the firewall, the authorization layer).

The Membrane Identity as presented here is self-contained. It depends on no claims from the broader program except the identification of the authorization layer as exhibiting the membrane structure. That identification is argued on its own terms in this paper.

The broader program makes stronger claims: that meaning, agency, and authorization instantiate the same three-property structure (selectively permeable, continuously re-maintained, itself neither of the two states it mediates), and that this structure is the "explanatory residue" that no purely factual inventory closes. Those claims are not asserted here and are not needed for the Membrane Identity to hold. This paper makes one claim: the logical structure of the authentication-to-authorization inference is Hume's is/ought gap, and the policy conferral is the bridging act that the gap requires.

---

## 10. Conclusion

Authentication delivers IS-facts. Authorization delivers OUGHT-grants. The step between them is Hume's guillotine: no permission is entailed by any fact about a signal, however exhaustively verified. The grant — the *for* — is not a property of the signal and cannot be recovered by measuring it. It must be conferred by a standing policy that is not itself derivable from signal-properties.

This is the Membrane Identity. It is not a novel philosophical principle — the is/ought gap is Hume's. It is not a novel observation that authentication and authorization are distinct — that is decades old in computer security. The contribution is the identification of the logical structure: that the distinction *is* the gap, structurally, and not merely a practical separation that happens to resemble it.

The two hardest objections — object-capability systems and Searle's counts-as — do not dissolve the gap. They relocate it: capability systems push the conferral to the issuance layer; constitutive rules institutionalize the conferral without deriving it from the facts it classifies. In both cases, the ought enters through an act of conferral that the IS-facts do not entail.

The identity has consequences. It predicts a specific class of failures — confused-deputy attacks, policy bypass via credential elevation, authentication-only architectures — that arise when the gap is collapsed. It explains why the policy decision point cannot be eliminated by improving authentication. It grounds the architectural necessity of separating credential verification from permission granting, not as engineering hygiene but as logical necessity: two different kinds of predicate are in play, and the inferential move between them requires a bridging act.

The identity holds wherever there is a policy that grants permissions, because any policy that grants permissions is a standing normative commitment not derived from the signal-properties it classifies. It fails only if a coherent access-control architecture can be exhibited in which authorization is fully read off authenticated signal-properties with no conferral. No such architecture, to this paper's knowledge, exists.

---

## References

Anderson, R., and Moore, T. (2006). The economics of information security. *Science*, 314(5799), 610–613.

Dennis, J. B., and Van Horn, E. C. (1966). Programming semantics for multiprogrammed computations. *Communications of the ACM*, 9(3), 143–155.

Hardy, N. (1988). The confused deputy: (or why capabilities might have been invented). *ACM SIGOPS Operating Systems Review*, 22(4), 36–38.

Hume, D. (1739–40). *A Treatise of Human Nature*. Book III, Part I, Section I. London: John Noon.

MacIntyre, A. (1981). *After Virtue: A Study in Moral Theory*. Notre Dame: University of Notre Dame Press.

Miller, M. S., Shapiro, J. S., and Tribble, E. D. (2003). Capability myths demolished. *Technical Report SRL2003-02*, Systems Research Laboratory, Johns Hopkins University. [Moderate confidence on year and venue.]

Moore, G. E. (1903). *Principia Ethica*. Cambridge: Cambridge University Press.

OASIS. (2013). *eXtensible Access Control Markup Language (XACML) Version 3.0*. OASIS Standard.

Saltzer, J. H., and Schroeder, M. D. (1975). The protection of information in computer systems. *Proceedings of the IEEE*, 63(9), 1278–1308.

Searle, J. R. (1969). *Speech Acts: An Essay in the Philosophy of Language*. Cambridge: Cambridge University Press.

Searle, J. R. (1995). *The Construction of Social Reality*. New York: Free Press.

von Wright, G. H. (1963). *Norm and Action: A Logical Enquiry*. London: Routledge and Kegan Paul.
