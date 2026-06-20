## Hostile-examiner adjudication: The Actuator-Met Condition (egress dual of the Membrane)

### Verdict: framing-defensible (at the floor of that category; one citation away from defensible, and the novelty ceiling must drop to LOW)

The draft is not a relabel and not a result. It is a framing whose ownable residue is real but thin, and whose draft form overclaims in four places the attacks correctly identify. All three attacks converge on `more_than_relabel = true` with mandatory bounding, and that convergence is correct. I affirm it and sharpen it.

---

### 1. What survives, stated at its true strength

Three things, and only three, are ownable:

1. **The deontic naming.** Re-describing liveness failure as "a conferred OUGHT decays, absent re-evaluation, to an IS-record of a past conferral; acting on the IS-record is *met*." This is a genuine reframing of the engineering vocabulary (expired/revoked/stale/replayed) into the deontic register established by the membrane. It is the same *kind* of move the membrane made at ingress (ABLP non-entailment → "deontic bridge"), and it inherits the same ceiling: moderate at best, and here pushed to **low** by an unaudited literature (below).

2. **The egress-dual structure.** Pairing ingress non-derivability (no IS entails OUGHT) with egress non-persistence (OUGHT does not maintain itself) as two faces of one point — *the deontic operator is not self-perpetuating*. This is the strongest part of the residue because it is structural, not mechanistic, and no single freshness/zero-trust source states it. It is the actual contribution.

3. **The temporal-decay unification.** Treating replay = stale-token = post-revocation as one met-family (aleph-erasure by time), with forged-credential as the limit case (aleph never written). This is finer than any single domain's taxonomy.

That is the residue. Everything else in the draft is either prior art or presentational.

### 2. What does not survive — the overclaim sites

- **"The duality is real, not forced" / "same underlying structure" (§5.1–5.2).** Overclaim. Ingress is a *logical* theorem (Hume/Pigden, autonomy of the deontic — a claim about inference types). Egress is a *semantic* claim about dynamic normative systems (temporal non-persistence) that classical deontic logic does not contain — it requires a time-indexed, non-classical deontic semantics. A hostile reviewer breaks the "formal duality" instantly by noting classical deontic logic has no OUGHT-decay. The defensible form is *structural analogy at the level of non-self-perpetuation*; the duality is illuminating, not formal. The overclaim auditor's de-escalation to "structurally suggestive" is correct.

- **The decay claim "follows from the forcing argument" (§5.2).** Non-sequitur, as the overclaim auditor states. The forcing argument gives: conferral is a token event indexed to t0-conditions. The decay claim needs an *additional* premise — "an OUGHT indexed to t0-conditions is not valid at t1 when those conditions no longer obtain." That premise is substantive normative logic, not contained in the forcing argument. It must be defended or flagged as assumed. I verified the parent thesis (`conferred-existence-thesis.md`, Movements I, V, VI): it establishes conferral-as-event and "re-spoken each instant" as motifs, but it explicitly holds the binding as *bid-grade against the determined dissenter* and *conditional on inhabiting the practical standpoint* (Movement VI). The egress-dual therefore inherits a **conditional** status, not a forced one. The draft must say so.

- **The freshness-window formalization (§2.2) as a contribution.** It is not. The three conditions are RFC 6749 expiry + RFC 7009 revocation + RFC 7662 introspection in math notation. Presentational only. TRBAC activation windows and OCSP `nextUpdate` already implement resource/context-sensitive windows.

- **"No prior literature names this structure in deontic terms" (§8).** Stated without the hedge the paper itself mandates, and — more seriously — false-until-audited. See §3.

### 3. The two citations that change the verdict's confidence (the decisive finding)

The priority attack names the gap that the draft's own seven-body audit missed, and it is the load-bearing finding of this adjudication:

- **TRBAC (Bertino, Bonatti, Ferrari 2001, ACM TISSEC 4(3):191–233).** The access-control field's *own* model-layer formalization of role **assignment** (conferral-event) vs. role **activation** (current in-force status). This is structurally the emet/met split, with activation windows that are the freshness windows. **Uncited.** A security referee rejects on sight. Cite-and-distance is mandatory: TRBAC models *when* a role is active; it does not name the structure as OUGHT-decay-to-IS-record, does not build the egress-dual, does not derive from conferral-as-event, does not unify the failure taxonomy. The residue survives the distancing — but only after the cite exists.

- **Temporal deontic / normative-change logic (Governatori–Rotolo on abrogation/annulment in defeasible logic; Sartor 1994; Thomason 1981).** The nearest *philosophical* neighbor. It already formalizes temporally-indexed norms and a norm valid at t0 failing to be in force at t1 — the egress decay claim at the rigor the draft lacks. **Uncited.** Because the draft supplies no temporal-deontic formalism of its own, it cannot claim the decay result at TDL's level, and its novelty-negative claim is unchecked against DEON, AI & Law, and Logic Journal of the IGPL.

These two gaps are why **novelty_confidence = low**, not moderate. The deontic-naming and unification novelty cannot be asserted above low until those literatures are audited. The egress-dual *structure* may be held at moderate; the naming and unification may not.

### 4. The conceptual bounds that must hold

- **Hold the weak form consistently.** "A stored grant is a met-grant" must never reappear after §2.3. The only admissible form: decays *absent re-evaluation within W*. The abstract already has the right form; it must be the only form.
- **The invariant is a schema, not a determinate predicate.** Its sharpness is bounded by W's accuracy and revocation-propagation latency. It holds exactly only if W is set correctly and revocations propagate within W; otherwise approximately. Condition (3) imports the OCSP/CRL propagation problem and must not imply false precision.
- **Confused deputy is a scoping failure, not temporal decay.** §4.1 is the weakest mapping: G_A is temporally live; the failure is principal-scope misattribution. Either widen the invariant to "correctly-attributed, scope-appropriate, temporally-live grant" (temporal decay paradigm, misattribution distinct mode) or split it into a separate scoping invariant. Note capability-security already unified confused-deputy + ambient authority at the design layer — so only the replay/stale/revocation temporal family is the genuinely new egress unification.
- **Replace "near-nothing" with artifact-indistinguishability.** The reason *met* is dangerous is that a met token is artifact-identical to an emet token (same bytes, valid signature, parseable structure); liveness is a relational property between artifact and current policy-state, not a property of the artifact. Theology stays illumination, never mechanism.
- **Resolve the W=∞ "met-policy" (§3.3).** Policies are not actuations. Scope the invariant to actuations with met-policy as a corollary, or extend to policies and argue that separately.
- **Precisely bound BAN-vs-ABLP (§7.1).** ABLP (Lampson et al. 1992) already extends BAN to authorization with time-dependent delegation chains. The "BAN-to-authorization extension is our work" claim must concede ABLP's prior position.

### 5. Is it more than freshness?

Yes — but the margin is framing, naming, and structure, never mechanism, and it is thin. BAN freshness is authentication-layer binary anti-replay; the met-condition is authorization-layer and covers policy/attribute/context change BAN cannot express. The egress-dual is a real structural contribution no single source states. But every mechanism is prior art throughout (BAN, NIST 800-207, RFC 7662 `active`, RFC 7009, RFC 9449 DPoP, OCSP `nextUpdate`, TOCTOU), TRBAC already splits conferral from activation at the model layer, and RFC 7662's `active=true/false` is the live/dead distinction in deployed code. So: more than freshness, but freshness-plus-naming-plus-egress-structure, ceiling moderate for the structure and **low** for the naming/unification pending audit.

### 6. Disposition

`framing-defensible`, at the floor of the category. The paper is publishable as a framing contribution *if and only if* it (a) cites and distances TRBAC and temporal deontic logic, (b) drops the duality from "real/formal" to "structural analogy," (c) drops the freshness-window formalization from contribution to presentation, (d) flags the conferral-as-event dependency and the missing temporal-logic premise, (e) holds the weak form of the decay claim consistently, and (f) scopes the novelty to **low, negative-claim-bounded-to-literatures-surveyed**. Without (a) it is rejected for missing obvious prior art. With all bounds applied, a genuine but modest residue stands: the egress-dual structure and the deontic naming of OUGHT-decay — not the mechanism, which is prior art everywhere, and not a law, duality, or conservation principle.

**Confidence in this adjudication: high** on the verdict and the residue identification; **high** that TRBAC and temporal deontic logic are the decisive uncited prior art; **moderate** that the egress-dual structure is genuinely unsaid in the access-control literature; **low** that the deontic naming is unsaid across the unaudited temporal-deontic venues.
