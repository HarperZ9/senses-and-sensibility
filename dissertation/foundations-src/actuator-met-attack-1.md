<!-- lens: PRIORITY / NOVELTY — adversarial prior-art assessment of the Actuator-Met Condition (egress dual of the Membrane Framing); verdict=needs-bounding -->

## Adversarial Priority Analysis: The Actuator-Met Condition

### Verdict: needs-bounding (not overclaim, not relabel, not sound as-is)

The actuator-met condition is a real structural contribution. The egress-dual argument — that a conferred OUGHT decays to an IS-record absent re-evaluation, symmetric to the ingress claim that no IS-base entails an OUGHT — is not contained in any of the seven bodies of prior art the draft surveys, nor in the two additional bodies (TRBAC, temporal deontic logic) the draft omits. The paper is not a relabeling exercise. But it requires two mandatory prior-art additions before it is submittable, and several bounds must be stated explicitly to survive hostile review.

---

### What the prior art actually contains (adversarial ranking by distance)

**Rank 1 (closest, and missing from the draft): Temporal Role-Based Access Control (TRBAC)**

Bertino, Bonatti, and Ferrari, "TRBAC: A Temporal Role-Based Access Control Model," ACM Transactions on Information and System Security 4(3), 2001 — high confidence on existence and content. This paper is not cited in the draft and is the most dangerous omission.

TRBAC separates *role assignment* (a principal is granted a role — the conferral event) from *role activation* (the role is currently in effect — the live OUGHT). A role can be assigned but not yet active (outside its activation window), assigned and active (within its window), or assigned but expired (window closed). The model introduces periodic activation, context-triggered deactivation, and carryover rules. In the draft's vocabulary: a role outside its activation window is *met* — the conferral form is present, the animating status is absent. This is the access-control field's own model-layer implementation of the emet/met split, arrived at independently and without the deontic framing.

What TRBAC does not do: it does not name the underlying structure as OUGHT-decay to IS-record; it does not derive the egress-dual from a conferral-as-event thesis; it does not unify the failure taxonomy across replay, confused-deputy, ambient authority, and forgery under a single liveness invariant; and it does not identify the egress seam as structurally symmetric to the ingress membrane. The met-condition's contribution survives TRBAC, but the paper cannot go to review without citing and distancing it.

**Rank 2 (substantial, partially addressed): Temporal deontic logic**

The DEON workshop series, Sartor (1994) on legal argumentation, and Governatori and Rotolo's defeasible-deontic work on normative change explicitly model: when a norm is in force; what happens when a norm is adopted then retracted; whether an agent acting on a retracted norm has violated the normative system. This is the philosophical literature that most directly addresses the temporal indexing of OUGHT-validity.

The draft's framing — "a past OUGHT decays to an IS-record" — is philosophically adjacent to TDL's question "is this norm currently in force?" But TDL addresses legal obligations (O-type modalities) in legal reasoning contexts, not authorization permissions (P-type modalities) at the enforcement-point layer. The egress-dual structure (the actuation-layer application) and the four-family failure taxonomy are not contained in TDL. The paper needs one paragraph acknowledging TDL and explaining the distinction.

**Rank 3 (correctly assessed in draft): BAN logic freshness**

The draft's treatment of BAN in section 7.1 is the strongest part of the prior-art audit. BAN's fresh(X) is genuinely the formal ancestor of the liveness requirement, and the extension from authentication-message freshness to authorization-grant liveness is real. The additional limitations (BAN's known incompleteness for security proofs, its restriction to the authentication layer) are correctly noted. No revision needed here.

**Rank 4 (correctly assessed): Zero trust / NIST SP 800-207**

The draft correctly identifies ZTA as the most significant engineering-program prior art and correctly distinguishes it: ZTA is "verify continuously" as a mandate; the met-condition is "stored OUGHT decays to IS-record" as a formal deontic claim. The draft's section 7.2 on this is its second-best move. No revision needed.

**Rank 5 (correctly assessed): OAuth RFC ecosystem**

RFC 7662's active field is the protocol-level emet/met bit, and DPoP's per-request proof is the strongest re-said-aleph implementation. The draft correctly treats these as mechanism-level prior art and the deontic framing as the contribution beyond them. No revision needed.

**Rank 6 (correctly assessed): TOCTOU**

TOCTOU subsumption under the met-condition framework is a genuine cross-domain unification. The draft handles this well.

**Rank 7 (correctly assessed but low novelty contribution): Capability revocation**

The caretaker pattern in object-capability systems is correctly identified as the domain-specific implementation of post-revocation met-states. The draft is right that the contribution is generalization and deontic framing. However, the confused-deputy and ambient-authority analyses in the draft's section 4 are largely re-running the membrane paper's ingress analysis at the egress layer — the genuine novelty in the failure taxonomy is the temporal-decay family (replay/stale/revocation), not the confused-deputy and ambient-authority re-readings which already appear in the membrane paper.

---

### What is genuinely ownable (adversarial concession only)

Three things survive full hostile scrutiny:

**1. The deontic naming of OUGHT-decay (the IS-record claim)**

No prior literature names the underlying structure of token expiry, role deactivation, certificate revocation, and session timeout as: *a conferred OUGHT, absent re-evaluation, decays to an IS-record of a past conferral, and acting on the IS-record is met.* TRBAC has the model; ZTA has the mandate; OAuth has the protocol; OCSP has the PKI implementation; TDL has the formal temporal indexing of norm validity. None frames it as OUGHT-decay to IS-record, none names the actuation on the IS-record as the met-condition, and none derives this from the conferral-as-event thesis. This is the deontic-naming contribution, parallel to the membrane paper's naming of the ABLP bridge-premise gap as deontic.

Novelty confidence: moderate. Search access to DEON workshop proceedings, Artificial Intelligence and Law journal (Springer), and Logic Journal of the IGPL was not exhaustive. The negative claim is scoped to the literatures surveyed.

**2. The egress-dual structure**

The identification of the egress seam as structurally symmetric to the ingress seam — with OUGHT-decay as the mirror of OUGHT-generation — is a structural claim that is not made in the literatures surveyed. The dual is real, not forced: the ingress claim is about logical type (IS cannot generate OUGHT by inference); the egress claim is about temporal persistence (OUGHT does not persist as OUGHT without re-conferral). These are different claims at different levels, unified by the conferral-as-event thesis.

This contribution is conditional on the conferral-as-event thesis (P1). Per the dissertation's own P1-DEFENSE-verdict.md, P1 is at FORCES-CONVENTIONALLY-ONLY — the thin spatiotemporal index is earned, the thick perspectival index is a declared premise. The paper should name this conditionality.

**3. Cross-domain unification of the temporal-decay failure family**

The unification of replay attacks, stale-token exercise, and post-revocation use as a single met-state (temporally decayed aleph) under the liveness invariant is the paper's strongest new analytical contribution. Each is analyzed separately in its home literature (anti-replay in BAN/Kerberos; stale sessions in session management; post-revocation in OCSP/CRL). The formal unification under one decay-type analysis is not done in those literatures.

The confused-deputy and ambient-authority re-readings are weaker — they largely re-run the membrane paper's ingress analysis at the egress layer and add less than the temporal-decay unification.

---

### The strongest objection the paper must answer (not currently answered)

**The TRBAC collapse objection**: "TRBAC already separates role assignment from role activation, models activation windows and deactivation triggers, and distinguishes 'role granted' from 'role currently active.' Your emet/met distinction is TRBAC with a Golem metaphor attached."

The answer the paper must give (currently absent): TRBAC is a model-layer specification — it tells system designers *what states to model* (assigned, active, expired). The met-condition is a deontic analysis — it tells us *what kind of normative fact is missing* when an actuation proceeds from an inactive role (not a mechanical fact about model state, but the absence of a currently-conferred OUGHT). TRBAC's activation window is a mechanism for enforcing liveness; the met-condition names what TRBAC's mechanism is enforcing. The relationship is the same as XACML PDP/PIP to the membrane paper: the architecture is prior art; the deontic classification of what the architecture achieves is the framing contribution.

---

### The "too strong" objection and its current handling

The draft handles the "stored grant decays" objection adequately in section 2.3, but the informal language in the abstract and introduction is still loose. The abstract says "a once-conferred OUGHT decays to an IS-record" without the critical qualifier "absent re-evaluation within W(G,ctx)." A hostile referee reading only the abstract will object that every real system stores grants and works. The fix is a single clause in the abstract: "absent re-evaluation within the applicable freshness window."

---

### The egress-dual argument's dependency

Section 5.2 correctly argues the duality is real and non-forced. The argument from conferral-as-event (P1) to OUGHT-temporal-indexing is sound given P1. But P1's status in the dissertation is FORCES-CONVENTIONALLY-ONLY, meaning it is a declared premise that is earned but not proven from outside the practical standpoint. The paper should state this dependency explicitly rather than treating the conferral-as-event thesis as uncontested. The egress-dual holds whether P1 is forced or stipulated — the paper works either way — but transparency about which is being claimed is required for honest framing.

---

### Summary table

| Prior art | Mechanism it contains | What met-condition adds | Draft's handling |
|-----------|----------------------|-------------------------|-----------------|
| TRBAC (Bertino et al. 2001) | Role assignment vs. activation separation; activation windows | Deontic naming of OUGHT-decay; egress-dual; failure unification | MISSING — must add |
| Temporal deontic logic (Sartor, Governatori-Rotolo) | Temporal indexing of norm validity; norm retraction | Application to P-type permissions; PEP actuation layer; egress-dual | MISSING — must add |
| BAN freshness | Anti-replay freshness at authn layer | Extension to authz-grant liveness | Correctly handled |
| NIST SP 800-207 ZTA | Engineering mandate for per-request authz | Formal deontic analysis of why | Correctly handled |
| TRBAC (again) | Model-layer role lifecycle | Deontic classification of what lifecycle enforces | MISSING |
| RFC 7662 introspection | active=false as protocol met-bit | Deontic framing; egress-dual structure | Correctly handled |
| OCSP/CRL | Real-time certificate status | Generalization to authz layer; invariant | Correctly handled |
| TOCTOU | OS-level check-use race fix | Deontic reframing; cross-domain integration | Correctly handled |

**Net verdict**: the paper is a real contribution at moderate novelty, not a relabeling. It needs TRBAC and TDL citations added with distancing argument. It needs the abstract tightened to carry the freshness-window qualifier. It needs the conferral-as-event dependency flagged. Subject to these bounds, the ownable residue — deontic naming of OUGHT-decay, egress-dual structure, temporal-decay failure unification — is defensible.
