# The Actuator-Met Condition: Liveness Decay and the Egress Analogue of the Membrane

## Abstract

The Membrane Framing establishes the ingress seam of the access-control system: the step from authentication (IS) to authorization (OUGHT) requires a deontic bridge premise not derivable from any set of authentication facts. This paper argues for a structurally parallel egress phenomenon and bounds it carefully. At egress — the Policy Enforcement Point, where an authorization verdict (OUGHT) becomes an actuation (IS) — a once-conferred OUGHT is indexed to the conditions obtaining at its conferral-event; absent re-evaluation it persists only as an *IS-record* of a past conferral. Acting on that IS-record rather than on a currently re-confirmed conferral is the **met-condition**. This is offered as a defensible **framing**, not a result, a law, or a formal duality.

The ownable residue is exactly three things, at low-to-moderate confidence and nothing stronger: (1) the deontic **naming** of the liveness-failure phenomenon as OUGHT-decaying-to-IS-record, distinct from the engineering vocabulary of "expired/revoked/stale"; (2) the egress **structural analogy** — pairing ingress non-derivability with egress non-persistence as two faces of one point, the deontic operator is not self-perpetuating; (3) the temporal-decay **unification** of replay, stale-token, and post-revocation exercise under one met-structure, with forged-credential as the limit case of never-written. The paper states a **liveness invariant** explicitly as a policy-bounded *schema*, not a determinate predicate, with three mandatory bounds (schema-sharpness, temporal-decay-primacy, and dependence on the conferral-as-event premise). An honest prior-art audit credits BAN freshness, ABLP delegation, zero-trust/continuous authorization, capability revocation, OAuth expiry/introspection/revocation, proof-of-possession, OCSP/CRL, and TOCTOU — and, decisively, **TRBAC** (Bertino, Bonatti, Ferrari 2001) and **temporal deontic / normative-change logic** (Governatori–Rotolo, Sartor, Thomason), which already formalize the conferral-vs-in-force split at the model layer and temporally-indexed defeasible norms respectively. Every mechanism surveyed is prior art. The novelty ceiling is therefore **low**, and the deontic-naming claim is a negative claim bounded to the literatures surveyed, with the temporal-deontic-logic venues only partly audited.

---

## 1. The Egress Structure: OUGHT Becoming IS Again

### 1.1 The membrane's ingress seam

The Membrane Framing identified one deciding seam in the access-control system: the ingress seam between authentication and authorization. Authentication answers IS-questions (is this credential genuine? is this principal who it claims to be?); authorization answers an OUGHT-question (may this principal act?). The seam is the policy layer, where a standing normative commitment — not derivable from any authentication fact — bridges the two. That framing took ABLP's non-entailment position (Lampson et al. 1992 [high confidence]) as prior art establishing the gap, named the gap's occupant as a deontic permission, and derived an unmeasurability result: the gap is logical, not epistemic, so no authentication improvement closes it. Ingress non-derivability is a **logical** claim — a theorem about inference types in the Hume/Pigden tradition (Pigden 1989 [high confidence]).

### 1.2 The egress phenomenon

There is a second point of interest, structurally parallel: the **egress** point, where an authorization verdict (OUGHT) becomes an actuation (IS) — where the policy-relative permission is exercised and something happens in the world. The **actuator** is the mechanism there: the Policy Enforcement Point (PEP) in XACML parlance, or the effector in any architecture that separates decision from enforcement.

Authorization verdicts are not instantaneous. A verdict is issued at t₀ and acted upon at t₁ > t₀. Between them the world can change: the policy may have changed, the grant may have been revoked, the principal's warranting attributes may have changed, the resource's classification may have changed, the ambient context may have shifted. If any such change has occurred, the OUGHT issued at t₀ is no longer the current state of the normative world at t₁. The PEP that executes at t₁ on the basis of the t₀ grant — absent re-evaluation — is acting on an IS-record of a past OUGHT.

The egress claim is therefore **not** a logical theorem. It is a **semantic** claim about dynamic normative systems — about the temporal persistence of a conferral — and establishing it at ingress-rigor would require a non-classical, time-indexed deontic semantics that classical deontic logic lacks and that this paper does not supply. This is flagged here, not papered over.

### 1.3 The weak form, held consistently

The defensible claim is the **weak** form, and it is the only form admitted anywhere in this paper, including abstract and introduction:

> A once-conferred OUGHT decays, **absent re-evaluation within a freshness window W(G, ctx)**, to an IS-record of a past conferral. Acting on that IS-record rather than on a currently re-confirmed conferral is the met-condition.

The strong form — "every stored grant is a met-grant" — is **false and is not asserted**. Every real system stores grants (tokens, ACL entries, capability references, session state) and works correctly. Storage is the correct engineering response to the operational infeasibility of instantaneous re-evaluation; storage per se is not death. What is *met* is acting **without** re-confirmation within the applicable window, not the fact of storage.

### 1.4 The egress as a structural analogy (not a formal duality)

The ingress and egress claims are structurally parallel at the level of the deontic operator's non-self-perpetuating character:

| Dimension | Ingress (Membrane) | Egress (Actuator) |
|-----------|-------------------|--------------------|
| Direction | IS → OUGHT | OUGHT → IS |
| Status of the claim | **Logical** theorem (inference types) | **Semantic** claim about dynamic normative systems |
| The gap | No IS-base entails an OUGHT (non-derivability) | A past OUGHT does not maintain itself (non-persistence) |
| The error | Treating IS-facts as licensing the OUGHT | Treating an IS-record of a past OUGHT as a live OUGHT |
| Named failure | Deontic inference failure | Met-condition |

The two are **two faces of one point**: the deontic operator is not self-perpetuating. At ingress it cannot be introduced by any accumulation of IS-facts; at egress, once introduced, it does not persist indefinitely through the record of its introduction. This pairing is **illuminating, not formal**. It is a structural analogy, not a proven duality: ingress is a logical result about inference, egress a semantic result about temporal persistence. The earlier draft's claim that "the duality is real, not forced" and that both rest on the "same underlying structure" overreaches and is retracted. Establishing egress at ingress-rigor requires a temporal deontic formalism this paper does not provide.

---

## 2. The Met-Condition, Stated Precisely

### 2.1 Informal statement

An actuation is **emet** (alive, truth-bearing) iff it is underwritten by a currently-live conferral — an OUGHT valid at the moment of the act, traceable to a grant that was evaluated, or whose continued applicability was re-confirmed, at or sufficiently near the moment of action.

An actuation is **met** (the form persists, the animating conferral does not) iff it proceeds from a conferral that is not live at the act — because the grant has expired, been revoked, or was never valid, or because it was valid at a past moment but has not been re-evaluated within the applicable freshness window.

The distinction tracks the difference between a present OUGHT and an IS-record of a past OUGHT. That a grant *was* issued is a true fact; it is not the same as the grant's *being currently valid*. The met-condition is precisely the confusion of these two.

**Why met is dangerous — artifact-indistinguishability (not "near-nothing").** A met token is *artifact-identical* to an emet token: the same bytes, a valid signature, a parseable structure. Liveness is a **relational** property between the artifact and the current policy-state, not a property of the artifact itself. No inspection of the token alone distinguishes live from dead; only relating it to the present normative state does. (The Golem aleph's smallness, §6, *illustrates* this — it is illumination, never the mechanism.)

### 2.2 The freshness window — presentational, not a contribution

"Live at the act" is precisified by a freshness window W(G, ctx): a policy-determined duration during which a grant G issued in context ctx is presumed valid without re-evaluation. The window is resource-sensitive (high-risk operations get short or zero windows), context-sensitive (a posture or threat-level change can collapse it to zero), and grant-type-sensitive.

A grant G is **live at time t** iff:
1. G was a genuine conferral at its issuance time t₀;
2. t − t₀ ≤ W(G, ctx); and
3. no revocation of G is known at t.

An actuation at t is **emet** iff underwritten by such a G, **met** otherwise.

This formalization is **presentational, not a substantive contribution.** The three conditions repackage RFC 6749 token expiry, RFC 7009 revocation, and RFC 7662 introspection in notation. TRBAC role-activation windows and OCSP `nextUpdate` already implement resource- and context-sensitive freshness windows. Condition (3) does not require perfect revocation propagation; it requires W set short enough that expected propagation latency does not produce material exposure. The schema's sharpness is bounded accordingly (see §3.1).

### 2.3 The decay claim needs an added premise

The forcing argument (the parent thesis's conferral-as-event movement) establishes that a conferral is a **token event** indexed to the conditions obtaining at t₀. It does **not**, by itself, yield decay. The decay claim requires an additional, substantive premise from normative logic:

> **(Decay premise.)** An OUGHT indexed to t₀-conditions is not valid at t₁ when those conditions no longer obtain.

This premise is **not contained in the forcing argument**. It is a claim about the temporal validity of norms — the proper subject of temporal deontic / normative-change logic (§7.9). This paper assumes it, and flags it as **an assumed premise, not a derived conclusion**. Anyone who grants conferral-as-event but denies the decay premise (holding that a conferral, once made, fixes a standing permission insensitive to later condition-change) blocks the met-condition. The met-condition is therefore conditional on both conferral-as-event and the decay premise.

---

## 3. The Liveness Invariant (a Schema)

### 3.1 Statement and mandatory bounds

**Liveness Invariant (schema).** Every actuation at the PEP must be underwritten by a grant G that is live at the act, where "live at t" is given by §2.2. An actuation underwritten by no live G is *met*.

This is a **schema**, not a determinate predicate, and three bounds are mandatory or it overclaims:

**(a) Schema-sharpness bound.** Its sharpness is bounded by the accuracy of W(G, ctx) and by revocation-propagation latency. It holds exactly only if W is set correctly and revocations propagate within W; otherwise it holds approximately. It does not require instantaneous propagation; it requires W set to bound exposure from propagation latency.

**(b) Temporal-decay-primary bound.** The invariant is primarily about **temporal** liveness. Confused-deputy (principal/scope misattribution) and ambient authority (scope over-breadth) are **not** temporal-liveness failures — the grant in play can be temporally live. They must be admitted either under a widened reading ("a correctly-attributed, scope-appropriate, temporally-live grant") with temporal decay as the paradigm case, or split off as a separate **scoping invariant**. This paper takes the widened reading and marks the split explicitly (§4). Capability-security already unified misattribution and ambient authority at the design layer, so only the replay/stale/post-revocation **temporal** family is the genuinely new egress unification.

**(c) Conferral-as-event bound.** The invariant is conditional on the conferral-as-event premise (and the §2.3 decay premise). If conferral is a standing property of the token rather than a token event indexed to t₀-conditions, the decay claim does not follow. The invariant therefore inherits the parent thesis's status: **binding within the practical standpoint, declinable by denying conferral-as-event.** Per the parent thesis, conferral-binding is bid-grade against a determined dissenter; the egress invariant inherits exactly this conditional status. Conferral-as-event is here **stipulated** as the operating standpoint, not claimed as forced.

So qualified, an invariant survives. Unqualified — "every stored grant is met" — it does not.

### 3.2 Stored-and-live vs. stored-and-met

The invariant's scope is **not** "no storage" but "storage with bounded drift." A grant stored at t₀ and used at t is *emet* if t is within W(G, ctx) of t₀, or if the grant was re-validated at some t′ with t − t′ ≤ W′(G, ctx); it is *met* if t exceeds the window with no re-validation, or a revocation occurred and is known at t, or warranting conditions have changed and no context-change detection has triggered re-evaluation. Token expiry, session timeouts, Kerberos ticket lifetimes, TLS `notAfter`, and OCSP `nextUpdate` are exactly the mechanisms that keep actuations within W.

### 3.3 The W = ∞ case — a corollary about policies, scoped explicitly

The invariant above is scoped to **actuations**. A separate observation concerns **policies**: a policy that sets W = ∞ (grants never expire, revocations never propagate) makes every actuation under it rest on an IS-record rather than a re-confirmed conferral. Calling such a policy "met" **extends** the term from actuations to policies, and that extension is a **distinct corollary**, argued separately — not a second result smuggled in under the actuation invariant. It is presented as a corollary, not asserted as a finding. (Policies are not actuations; the extension must be made on its own terms or not at all.)

---

## 4. The Failure Taxonomy: Two Modes, One Temporal Family

The egress failures fall into a **temporal-decay family** (the genuine egress unification) and a **scoping family** (already unified at the design layer by capability security, admitted here under bound (b)). Forgery is the limit case of never-written.

| Failure | Aleph status | Mode |
|---------|-------------|------|
| Replay / stale-token / post-revocation | Once present, no longer valid | **Temporal decay** (the egress family) |
| Confused deputy | Live, but belongs to a different conferral-chain | **Scope/principal misattribution** (scoping, not temporal) |
| Ambient authority | Live, but written for a broader scope | **Scope over-breadth** (scoping, not temporal) |
| Forged credential | Never present | **Fabrication** (limit case) |

### 4.1 The temporal-decay family (the genuine egress unification)

**Replay.** A token valid at t₀ is re-presented at t₁ > t₀ + W. The conferral was genuine at t₀; at t₁ the window has closed. The token is now an IS-record of a past OUGHT; the actuation is *met*.

**Stale-token exercise.** A session token or capability reference is used after the conditions that warranted it have changed (role change, resource re-classification, new policy). The token records the original conferral accurately, but the recorded OUGHT no longer reflects the present normative state. *Met.*

**Post-revocation exercise.** A token is revoked at t_rev; the policy-holder has re-conferred the OUGHT back to zero. Any act at t > t_rev on the token's basis is *met*: the token carries only the record of a withdrawn conferral, modulo revocation-propagation latency (bound (a)).

These three share one structure — a conferral genuine at t₀ that is no longer valid at t — and their unification under a single temporal-decay met-structure is the genuinely new egress contribution. Note that **TRBAC** (§7.8) already models *when* a role assignment is operationally active versus merely assigned; the unification here is the deontic naming and gathering, not the temporal mechanism.

### 4.2 The scoping family (admitted as distinct, not temporal)

**Confused deputy** (Hardy 1988 [high confidence]). Principal A holds a temporally-live grant G_A; B causes A to act on B's behalf. G_A is *temporally live* — within its window, not revoked. The failure is **not** temporal decay; it is **principal-scope misattribution**: G_A belongs to A's conferral-chain, not to B's request, which carries no grant for the requested operation. Admitted under bound (b) as a distinct scoping mode.

**Ambient authority** (object-capability literature; Miller, Shapiro et al. [moderate confidence]). An operation is performed using authority the principal holds for unrelated purposes because that authority pervades the context rather than being explicitly carried by the request. The grant can be temporally live; the failure is **scope over-breadth**, not temporal liveness. Capability security already unified confused-deputy and ambient authority at the design layer; this paper does not claim that unification.

### 4.3 Forgery (limit case)

A forged credential was never genuinely conferral-bearing — no legitimate policy-holder ever wrote the grant. The actuation is *met* not because a conferral decayed but because it was never present: an IS-record of a non-event. This is the limit case of never-written.

---

## 5. The Emet / Met / Aleph Framing (Illumination Only)

The Golem legend supplies the governing image: *emet* (אמת, "truth") inscribed on the brow animates the clay; erase the *aleph* (א) and *emet* becomes *met* (מת, "dead"). The form persists (מת ⊂ אמת); the life is gone.

Mapped onto authorization, and offered strictly as illumination:

- The **token** is the clay form — material, persistent through time.
- The **conferral** is the inscription — a legitimate policy-holder writing the grant.
- The **met-condition** is the state where the form remains (signature verifies, structure parses) but the animating conferral has expired, been revoked, or was never written.
- The aleph's near-invisibility *illustrates* §2.1's mechanism — **artifact-indistinguishability**. A met token looks identical to a live one; only relating it to the current policy-state reveals the difference. The smallness is the illustration; artifact-indistinguishability is the mechanism.

This framing names a structure that the engineering vocabulary ("expired," "revoked," "stale") leaves un-unified. It is **never a premise.** The thesis stands or falls on the liveness schema and its bounds, not on the legend.

---

## 6. Prior Art: An Honest Self-Audit

The discipline is explicit: do not inflate this into a law or a conservation principle; test it against the prior art most likely to contain the mechanism. Every mechanism surveyed below is prior art. Two bodies — TRBAC and temporal deontic logic — are decisive and are treated first in §6.8–6.9 because the earlier draft's seven-body audit missed them.

### 6.1 BAN logic freshness

Burrows, Abadi, Needham, "A Logic of Authentication," *Proc. R. Soc. Lond. A* 426(1871):233–271, 1989 [high confidence]. BAN's `fresh(X)` predicate fires the rule "if P believes (Q said X) and P believes fresh(X), then P believes (Q believes X)." Freshness is a first-class, **binary anti-replay** requirement at the **authentication** layer. It has no concept of policy change, attribute change, or context shift between grant and use. The met-condition operates at the **authorization-grant** layer, covering policy/attribute/context decay, and unifies failures BAN does not address. BAN's known mid-1990s limitations (protocols "verified" yet insecure) are not inherited, since the met-condition is a deontic classification, not a protocol-verification logic. *Confidence BAN lacks the full met-condition: high.*

### 6.2 ABLP delegation (and the BAN-vs-authorization claim, bounded)

Lampson, Abadi, Burrows, Wobber, "Authentication in Distributed Systems," *ACM TOCS* 10(4):265–310, 1992 [high confidence]. ABLP **already** extends BAN-style reasoning to authorization with delegation chains whose validity depends on the delegator's current authority — making validity **implicitly time-indexed**. Any claim that "extending freshness from authentication to authorization is this paper's work" must therefore acknowledge ABLP's prior position. The met-condition's increment over ABLP is the deontic **naming** (OUGHT-decay-to-IS-record) and the cross-domain gathering, not the extension to authorization, which ABLP already occupies. *Confidence ABLP lacks the deontic naming: moderate.*

### 6.3 Zero trust / continuous authorization

Rose, Borchert, Mitchell, Connelly, *Zero Trust Architecture*, NIST SP 800-207, 2020 [high confidence]; Kindervag, Forrester, 2010 [high confidence]; Ward & Beyer, "BeyondCorp," *USENIX ;login:*, 2014 [high confidence]. Zero trust mandates "accurate, per-request access decisions" — the **engineering** statement of the liveness requirement. It is an architectural program, not a formal analysis: it does not name the structure as OUGHT-decay-to-IS-record, supplies no formal invariant, and does not unify the failure taxonomy deontically. *Confidence zero trust lacks the deontic naming: high.*

### 6.4 Capability revocation

Dennis & Van Horn 1966; Hardy 1988 [high confidence]; Miller, Yee, Shapiro, "Capability Myths Demolished," SRL2003-02, JHU, 2003 [moderate confidence]. Forwarder/caretaker patterns make a capability *met* by severing forwarding after revocation: the reference persists, reachability is gone. This is a direct domain implementation. It does not frame revocation as OUGHT-decay, does not present it as one instance of a broader liveness invariant, and (per §4.2) already unifies confused-deputy and ambient authority at the design layer. *Confidence it lacks the deontic generalization: high.*

### 6.5 OAuth expiry / introspection / revocation

RFC 6749 (Hardt 2012); RFC 6750 (Jones & Hardt 2012); RFC 7009 (Lodderstedt et al. 2013); RFC 7519 (Jones et al. 2015); RFC 7662 (Richer 2015) — all [high confidence]. RFC 7662's `active` field — "whether or not the presented token is currently active" — **is the live/dead distinction in deployed code**, distinguishing a live OUGHT from an IS-record of an expired or revoked one. Expiry encodes W in the token; revocation lists implement condition (3); introspection re-queries at use. These are mechanisms; the met-condition's increment is the unifying deontic frame, not the mechanism. *Confidence the ecosystem lacks the deontic framing: high.*

### 6.6 Proof of possession (DPoP, mTLS-bound tokens)

RFC 9449 (Fett et al. 2023) [high confidence]; RFC 8705 (Campbell et al. 2020) [high confidence on number/year]. DPoP requires a fresh, request-bound proof at each call; mTLS binds the token to the client certificate. These implement "re-confirm at the act" cryptographically. The increment is naming what the proof achieves at the OUGHT-liveness level, not the binding mechanism.

### 6.7 Certificate revocation (OCSP / CRL) and TOCTOU

RFC 5280 (Cooper et al. 2008); RFC 6960 (Santesson et al. 2013) [high confidence]. OCSP converts a stored certificate into a current status check; its `nextUpdate` is a freshness window, and OCSP-replay (a captured "good" response replayed post-revocation) is exactly the temporal-decay structure — an IS-record of a past status. TOCTOU (Bishop & Dilger 1996 [moderate confidence]) is the OS-level analogue: a property checked at t₀ and used at t₁, stale if the environment changed between. The security literature treats TOCTOU as a **race condition**, not a deontic persistence problem. The increment is the deontic reframing and integration into the authorization taxonomy, not a new mechanism.

### 6.8 TRBAC — the decisive access-control prior art (cite and distance)

Bertino, Bonatti, Ferrari, "TRBAC: A Temporal Role-Based Access Control Model," *ACM TISSEC* 4(3):191–233, 2001 [high confidence on existence and substance; moderate on exact pagination]. **This is the access-control field's own model-layer formalization of the conferral-vs-in-force split.** TRBAC distinguishes role **assignment** from role **activation**, with temporal constraints (periodic enabling/disabling, activation windows) governing *when* an assigned role is operationally active. Without citing TRBAC the present paper would be rejected for missing obvious prior art.

**Distancing.** TRBAC models *when roles are operationally active*; it does **not** name the structure as OUGHT-decay-to-IS-record, does **not** build an egress analogy from conferral-as-event, and does **not** unify the cross-domain failure taxonomy (replay/stale/revocation, plus the scoping family) under one deontic liveness schema. TRBAC supplies the temporal mechanism at the model layer; the met-condition supplies the deontic naming and the cross-domain gathering. Because TRBAC already occupies the conferral-vs-in-force model-layer split, the deontic-naming claim's novelty is **low**, not moderate.

### 6.9 Temporal deontic / normative-change logic — the nearest philosophical neighbor (acknowledged, audit incomplete)

Governatori & Rotolo (defeasible deontic logic, norm-change); Sartor (legal temporal reasoning); Thomason (deontic/temporal interactions) [moderate confidence on attribution; this literature is **only partly audited**]. This is the nearest neighbor to the §2.3 decay premise: it formalizes **temporally-indexed, defeasible norms** and how obligations/permissions change validity over time.

**Distinguishing.** Temporal deontic logic chiefly addresses **O-type** obligation validity-over-time in legal contexts; the met-condition addresses **P-type** permission liveness at the **PEP enforcement layer**, together with the egress structural analogy this literature does not contain. But this is exactly the literature that would already contain the §2.3 decay premise, and possibly the naming. **This audit is incomplete.** The deontic-naming novelty is therefore stated at **low** confidence, and any "no prior literature names this" is replaced by: *no surveyed access-control-engineering literature names this; the temporal deontic logic literature has not been fully audited, and that audit must precede any confidence above low.*

### 6.10 Summary

| Prior art | What it has | What the met-condition adds |
|-----------|-------------|----------------------------|
| BAN freshness | Binary anti-replay at authn layer | Authz-layer scope; deontic naming; temporal-family unification |
| ABLP delegation | Authorization with implicitly time-indexed delegation | Deontic naming only — extension itself is ABLP's |
| Zero trust / continuous authz | Per-request engineering mandate | Deontic *why* behind the mandate |
| Capability revocation | Forwarder/caretaker revocability | Deontic generalization (scoping family already unified) |
| OAuth expiry/introspect/revoke | `exp`, `active`, revocation in code | Unifying deontic frame |
| DPoP / mTLS PoP | Per-request cryptographic re-confirmation | Naming at the OUGHT-liveness level |
| OCSP/CRL, TOCTOU | Status checks; race-condition fixes | Deontic reframing; taxonomy integration |
| **TRBAC** | **Model-layer conferral-vs-in-force split** | Deontic naming; egress analogy; cross-domain unification |
| **Temporal deontic logic** | **Temporally-indexed defeasible norms** | P-type/PEP-layer focus + egress pairing (audit incomplete) |

**Honest verdict.** The liveness mechanism is prior art in every domain surveyed; TRBAC already formalizes the conferral-vs-in-force split at the model layer; temporal deontic logic already formalizes temporally-indexed norms (and is only partly audited). The framework does not discover the liveness requirement; it **names** it deontically, pairs it with ingress as a structural analogy, and unifies the temporal family. *Confidence in this verdict: high.*

---

## 7. What Is Genuinely Ownable

Three things, at **low-to-moderate** confidence and nothing stronger:

1. **The deontic naming** of the decay phenomenon as OUGHT-decaying-to-IS-record, distinct from "expired/revoked/stale." Novelty **low**, pending the temporal-deontic-logic audit (§6.9). Negative claim bounded to literatures surveyed.

2. **The egress structural analogy** — ingress non-derivability paired with egress non-persistence as two faces of the deontic operator not being self-perpetuating. Held at **moderate**, and explicitly as a **structural analogy, not a formal duality** (§1.4): ingress logical, egress semantic; no single freshness/zero-trust/TRBAC source states the pairing.

3. **The temporal-decay unification** of replay/stale/post-revocation under one met-structure, with forgery as the never-written limit case. Novelty **low** (TRBAC occupies the model-layer mechanism). The scoping family (confused-deputy, ambient authority) is **not** claimed as new unification — capability security already unified it.

**Not ownable, and not claimed:** the freshness mechanism; the freshness-window formalization (presentational, §2.2); the W = ∞ "met-policy" corollary as a separate result (it is a scoped corollary, §3.3); any claim that this is a law, a conservation principle, or a formal duality; the decay premise as a *derived* conclusion (it is assumed, §2.3).

---

## 8. Conclusion

The access-control system has an ingress seam — no IS-base entails an OUGHT (a logical result) — and a structurally parallel egress phenomenon: a once-conferred OUGHT, **absent re-evaluation within W(G, ctx)**, persists only as an IS-record of a past conferral, and acting on that record is *met* (a semantic claim about dynamic normative systems). The pairing is an illuminating **structural analogy**, not a formal duality.

The liveness invariant is a **policy-bounded schema** with three mandatory bounds: its sharpness depends on W and revocation-propagation latency; it is temporal-decay-primary, admitting confused-deputy and ambient authority only as a distinct scoping mode; and it is conditional on conferral-as-event (stipulated, not forced) plus the assumed decay premise, inheriting the parent thesis's declinable-by-the-dissenter status. The met token is dangerous because it is **artifact-identical** to a live one; liveness is relational, not intrinsic.

Every mechanism is prior art — BAN, ABLP, zero trust, capability revocation, OAuth, DPoP, OCSP/CRL, TOCTOU — and, decisively, **TRBAC** already formalizes the conferral-vs-in-force split and **temporal deontic logic** already formalizes temporally-indexed norms (audit incomplete). The novelty ceiling is therefore **low**. The ownable residue is exactly three things at low-to-moderate confidence: the deontic naming, the egress structural analogy, and the temporal-decay unification — not the mechanism, and nothing stronger. The Golem aleph illuminates artifact-indistinguishability; it is never the premise.

---

## References

Bertino, E., Bonatti, P. A., and Ferrari, E. (2001). TRBAC: A temporal role-based access control model. *ACM Transactions on Information and System Security*, 4(3), 191–233. [High confidence on existence and substance; moderate on exact pagination.]

Bishop, M., and Dilger, M. (1996). Checking for race conditions in file accesses. *Computing Systems*, 9(2), 131–152. [Moderate confidence on venue and pagination; the TOCTOU class is well established.]

Burrows, M., Abadi, M., and Needham, R. (1989). A logic of authentication. *Proceedings of the Royal Society of London, Series A*, 426(1871), 233–271. Also DEC SRC Technical Report 39. [High confidence.]

Campbell, B., Bradley, J., Sakimura, N., and Lodderstedt, T. (2020). *OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens*. RFC 8705. IETF. [High confidence on number and year.]

Cooper, D., Santesson, S., Farrell, S., Boeyen, S., Housley, R., and Polk, W. (2008). *Internet X.509 PKI Certificate and CRL Profile*. RFC 5280. IETF. [High confidence.]

Dennis, J. B., and Van Horn, E. C. (1966). Programming semantics for multiprogrammed computations. *Communications of the ACM*, 9(3), 143–155. [High confidence.]

Fett, D., Campbell, B., Bradley, J., Lodderstedt, T., Jones, M., and Waite, D. (2023). *OAuth 2.0 Demonstrating Proof of Possession (DPoP)*. RFC 9449. IETF. [High confidence.]

Governatori, G., and Rotolo, A. (2010). Changing legal systems: Legal abrogations and annulments in defeasible logic. *Logic Journal of the IGPL*, 18(1), 157–194. [Moderate confidence; representative of the norm-change literature, only partly audited.]

Hardt, D. (ed.). (2012). *The OAuth 2.0 Authorization Framework*. RFC 6749. IETF. [High confidence.]

Hardy, N. (1988). The confused deputy. *ACM SIGOPS Operating Systems Review*, 22(4), 36–38. [High confidence.]

Jones, M., and Hardt, D. (2012). *The OAuth 2.0 Authorization Framework: Bearer Token Usage*. RFC 6750. IETF. [High confidence.]

Jones, M., Bradley, J., and Sakimura, N. (2015). *JSON Web Token (JWT)*. RFC 7519. IETF. [High confidence.]

Kindervag, J. (2010). Build security into your network's DNA: The zero trust network architecture. Forrester Research. [High confidence.]

Lampson, B., Abadi, M., Burrows, M., and Wobber, E. (1992). Authentication in distributed systems: Theory and practice. *ACM Transactions on Computer Systems*, 10(4), 265–310. [High confidence.]

Lodderstedt, T., McGloin, M., and Hunt, P. (2013). *OAuth 2.0 Token Revocation*. RFC 7009. IETF. [High confidence.]

Miller, M. S., Yee, K.-P., and Shapiro, J. S. (2003). Capability myths demolished. Technical Report SRL2003-02, Johns Hopkins University. [Moderate confidence; grey literature.]

Neuman, C., Yu, T., Hartman, S., and Raeburn, K. (2005). *The Kerberos Network Authentication Service (V5)*. RFC 4120. IETF. [High confidence.]

Pigden, C. R. (1989). Logic and the autonomy of ethics. *Australasian Journal of Philosophy*, 67(2), 127–151. [High confidence.]

Richer, J. (ed.). (2015). *OAuth 2.0 Token Introspection*. RFC 7662. IETF. [High confidence.]

Rose, S., Borchert, O., Mitchell, S., and Connelly, S. (2020). *Zero Trust Architecture*. NIST Special Publication 800-207. NIST. [High confidence.]

Santesson, S., Myers, M., Ankney, R., Malpani, A., Galperin, S., and Adams, C. (2013). *X.509 Internet PKI Online Certificate Status Protocol — OCSP*. RFC 6960. IETF. [High confidence on number and year.]

Sartor, G. (2005). *Legal Reasoning: A Cognitive Approach to the Law*. Springer. [Moderate confidence; representative of temporally-indexed legal-norm reasoning, only partly audited.]

Thomason, R. H. (1981). Deontic logic and the role of freedom in moral deliberation. In R. Hilpinen (ed.), *New Studies in Deontic Logic*. Reidel. [Moderate confidence; representative of deontic/temporal interaction, only partly audited.]

Ward, B., and Beyer, B. (2014). BeyondCorp: A new approach to enterprise security. *USENIX ;login:*, 39(6). [High confidence.]
