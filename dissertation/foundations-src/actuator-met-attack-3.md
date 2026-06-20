<!-- lens: OVERCLAIM AUDITOR; verdict=needs-bounding -->

## Overclaim Audit: Actuator-Met Condition

### Audit posture

Adversarial. Every site where the draft claims to be a law, theorem, conservation principle, novel, or unattested is treated as a falsifiable assertion requiring a hedge or retraction. The prior art audit in §7 is itself audited. Concessions are made only where the draft's position survives adversarial pressure.

---

### Overclaim site 1 — "The duality is real, not forced" (§5.2, heading and body)

**What the draft claims.** That the egress dual is structurally real and not merely analogical — that ingress and egress are "instances of the same underlying point: the deontic operator is not self-perpetuating."

**The problem.** The ingress claim is a logical theorem: Hume's Law / Pigden's autonomy of the deontic establishes that no IS-premise set entails an OUGHT-conclusion by valid inference. This is a claim about inference-type; it holds necessarily, independent of time.

The egress claim is a temporal empirical claim: a past OUGHT decays to an IS-record absent re-evaluation. This is a claim about normative validity over time. It is not a logical theorem. It depends on substantive premises about the structure of normative time — premises that differ by normative theory. Under some views (eternal normative facts, Platonist moral realism), conferred OUGHTs do not decay at all; under others (positivist, event-indexed views), they do. The paper assumes the conferral-as-event thesis to get the decay, but that thesis is the dissertation's own position, not a theorem.

Asserting that the two claims are "instances of the same underlying point" equates a logical theorem with a theory-dependent empirical claim. They are structurally analogous, not structurally identical. "The duality is real" overclaims; "the duality is structurally suggestive and holds under the conferral-as-event thesis" is the defensible form.

**Required bound.** Heading should read: "The egress analogy: structural suggestiveness under the conferral-as-event thesis." Body §5.2 must supply the temporal-logic formalism or explicitly flag its absence.

---

### Overclaim site 2 — "No prior literature names this structure in deontic terms" (§8, contribution 1)

**What the draft claims.** "No prior literature names this structure in deontic terms." This is the centerpiece novelty claim.

**The problem.** The paper itself acknowledges in §8 final paragraph: "A thorough search of the deontic-logic-meets-security literature... could surface prior statements." It then scopes the claim accordingly — but only in the final paragraph of §8, after repeatedly stating the contribution without that hedge. The hedge in §8 final paragraph is too late and too weak; it reads as an afterthought, not as a qualification woven into the claim.

More specifically: the temporal deontic logic literature — Governatori and Rotolo on normative change in defeasible logic, Thomason on combinations of tense and deontic logic, the IEEE TDSC literature on temporal authorization — is unaudited. This literature exists precisely at the intersection of "OUGHT over time" and "normative change," which is exactly where the OUGHT-decay claim lives. A claim made without auditing the directly relevant literature cannot be made at moderate confidence. It can be made at low confidence with an explicit unaudited-literature caveat.

**Required bound.** Every instance of "no prior literature" in §8 must be replaced with "no surveyed literature in the access-control engineering domain." The temporal deontic logic audit must be listed as future work required before the novelty claim can be elevated above low confidence.

---

### Overclaim site 3 — The freshness-window formalization as contribution (§2.2, implicit)

**What the draft claims.** Section 2.2 presents a three-condition formal definition of "G is live at time t" — valid at issuance, within W(G, ctx), no recorded revocation — as the "precisification" that makes the liveness claim defensible. The framing implies this formalization is a contribution.

**The problem.** The three conditions are a mathematical restatement of:
- Condition 1: RFC 6749 §4 (valid issuance by the authorization server)
- Condition 2: RFC 7519 `exp` claim (token expiry, the freshness window)
- Condition 3: RFC 7009 (token revocation) + RFC 6960 (certificate revocation)

Writing these three engineering requirements as a predicate `live(G, t)` is useful for exposition. It is not a formal contribution. The paper should say so explicitly, or the reader will take the formalization as the paper's formal result, which it is not.

**Required bound.** Add to §2.2: "This formalization is presentational. The three conditions restate engineering requirements that exist independently in RFC 7519, RFC 7009, and RFC 7662. The deontic framing (reading the conditions as conditions on a live OUGHT rather than conditions on a valid token) is the contribution, not the predicate itself."

---

### Overclaim site 4 — Conferral-as-event derives OUGHT-decay (§5.2, core argument)

**What the draft claims.** Section 5.2 uses the conferral-as-event thesis (conferral is a token event at a thin spatiotemporal index) to derive the egress decay claim: because conferral is an event, the OUGHT it produces is indexed to the conditions at t0, so changed conditions make the stored OUGHT an IS-record.

**The problem.** This is a non-sequitur as written. The argument structure is:

P1. A conferral is a token event occurring at t0, indexed to conditions that obtained at t0.
P2. [unstated] An OUGHT indexed to conditions at t0 is not valid at t1 when those conditions no longer obtain.
C. Therefore, a stored OUGHT becomes an IS-record when conditions change.

P2 is the load-bearing premise and it is never supplied. P2 is a substantive normative-logic claim — it asserts that OUGHTs are condition-relative in a specific temporal way, not merely event-indexed. Different deontic theories give different answers to P2. The draft smuggles P2 in by asserting the conclusion ("the conditions' change does not automatically update the OUGHT; it makes the stored OUGHT an IS-record") without establishing it. The conferral-as-event thesis establishes only that conferral is event-indexed, not that the OUGHT it produces expires when conditions change. The gap is real.

**Required bound.** Section 5.2 must either (a) state P2 explicitly as an assumed premise of the framework ("we assume, as a framework axiom, that OUGHTs produced by conferral events are condition-relative in the following sense: ...") or (b) derive P2 from a temporal deontic formalism. Option (a) is honest and defensible; option (b) is the fully rigorous form the paper does not yet achieve.

---

### Overclaim site 5 — ABLP undercited in §7.1

**What the draft claims.** Section 7.1 says BAN "has no concept of policy change, attribute change, or contextual shift between the time of grant and the time of use" and treats the extension to the authorization layer as the paper's contribution.

**The problem.** ABLP (Lampson, Abadi, Burrows, Wobber 1992) already extends BAN to authorization, including the concept of delegation chains whose validity is contingent on the delegator's current authority ("A speaks for B" is a currently valid relation, not a permanent one). ABLP's treatment of authority delegation implicitly time-indexes authority. The paper cites ABLP only in the references (carried from the Membrane Framing) but does not audit ABLP for its temporal authority treatment. If ABLP already captures authority-as-currently-valid, the extension claim weakens further.

**Required bound.** Section 7.1 must include an explicit analysis of ABLP's treatment of temporal authority and delegation validity, and qualify the extension claim accordingly. Low-to-moderate confidence on the extension being a contribution until that audit is complete.

---

### Overclaim site 6 — "Met-policy" (§3.3) — scope creep or genuine extension?

**What the draft claims.** "A system with W = ∞ (grants never expire, revocations are never propagated) is not merely operationally risky; it is structurally *met* — every actuation in it is underwritten by IS-records of past OUGHTs, not by live OUGHTs. The policy W = ∞ is a met-policy."

**The problem.** The liveness invariant as stated applies to actuations, not to policies. Extending "met" to characterize a policy (rather than an actuation under the policy) either (a) silently extends the framework's scope or (b) is a corollary that follows trivially from the invariant. As stated, it reads as an extension, but it is presented without the extension being flagged as such. If trivial, say so. If non-trivial, argue it separately.

**Required bound.** Add: "This characterization of W = ∞ as a met-policy extends the liveness invariant from individual actuations to system-level policy configurations. This extension is stated without independent argument; it follows as a corollary if the invariant is accepted for individual actuations."

---

### What survives adversarial pressure

The following claims survive:

1. **The failure taxonomy's structure** (§4, the four met-states and their four distinct modes of aleph-absence) is genuinely useful and does not appear to be a direct restatement of prior single-domain taxonomies. The confused-deputy, ambient authority, replay/stale/revocation, and forgery categories are known individually; their analysis as four modes of a single aleph-absence structure under a unifying liveness invariant is the paper's organizing contribution. This survives at moderate confidence (not low, not high).

2. **The deontic naming of the decay phenomenon** survives as a contribution in the access-control engineering literature specifically. BAN freshness is protocol-level. Zero trust is an engineering mandate. RFC 7662 active/inactive is a protocol field. None of these names the underlying structure as OUGHT-decay to IS-record in deontic terms. Whether the temporal deontic logic literature has the naming is unknown; pending that audit, the contribution survives at low-to-moderate confidence in the deontic-logic literature and moderate confidence in the access-control engineering literature.

3. **The egress-dual framing** survives as a useful organizing structure — the observation that there are two seams, and that the paper addresses the second, is correct and worth stating. The strength of the "duality is real" claim is what fails; the framing itself is fine.

4. **The emet/met/aleph naming** survives as illumination. The paper correctly maintains this is not premise. No overclaim here.

5. **The honest prior-art verdict in §7.8** is accurate and appropriately hedged. The table is the strongest part of the paper.

---

### Verdict summary

The paper is not an overclaim in the sense of claiming to have discovered a mechanism. It correctly locates its contribution at the naming-and-framing level. The overclaims are at the internal argumentation level: the duality-is-real assertion lacks the temporal-logic scaffolding it needs; the novelty claim is stated without auditing the one literature (temporal deontic logic) where a prior statement is most likely; the freshness-window formalization is presented with more weight than it bears; and the conferral-as-event-to-OUGHT-decay derivation has a missing premise. These are correctable. The verdict is needs-bounding, not overclaim or mostly-relabel, because the ownable residue is real — it just needs the honest size.

---

### Mandated language changes (summary for revision)

| Location | Current language | Required replacement |
|----------|-----------------|----------------------|
| §5.2 heading | "Why the duality is real, not forced" | "The egress analogy: structural suggestiveness under the conferral-as-event thesis" |
| §5.1 final para | "Both gaps are instances of the same underlying point" | "Both gaps are structurally analogous; establishing the egress claim at the rigor level of the ingress claim requires a temporal deontic formalism this paper does not supply" |
| §8 contribution 1 | "No prior literature names this structure in deontic terms" | "No surveyed literature in the access-control engineering domain names this structure in deontic terms; the temporal deontic logic literature has not been audited" |
| §2.2 anywhere implying the formalization is a contribution | [implicit] | Add explicit statement: formalization is presentational, not substantive |
| §5.2 OUGHT-decay derivation | "the conditions' change...makes the stored OUGHT an IS-record" | Flag as assumed framework premise, not derived conclusion |
| §3.3 met-policy | presented without scope flag | Flag as corollary extension, not independently argued |
