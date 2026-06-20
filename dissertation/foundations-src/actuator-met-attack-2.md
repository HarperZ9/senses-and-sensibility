<!-- lens: CONCEPTUAL SOUNDNESS; verdict=needs-bounding -->

## Conceptual Soundness Verdict: NEEDS-BOUNDING

The thesis survives the adversarial reading in its core claim, but requires five specific bounds before it is defensible. Here is the full attack and what it yields.

### What breaks under attack

**Attack on "storage is death" (the too-strong form)**

The strong claim does not survive. The draft correctly walks it back at §2.3, and the weak form — storage within W is emet; storage past W without re-evaluation is met — is defensible. The problem is consistency: the abstract says "a once-conferred OUGHT decays, absent re-evaluation, to an IS-record," which is the correct form, but the paper's terminology ("stored grant decays to an IS-record," §1.2 heading language) allows the strong reading to creep back. Every use of "met" for a stored grant must carry the freshness-window qualification, not just the section that explicitly walks the claim back.

**Attack on "live at the act" — precision of the predicate**

The three-condition definition at §2.2 is structurally adequate but the predicate is semi-well-defined, not well-defined. W(G, ctx) is policy-delegated (the draft acknowledges this at §3.3), and condition (3) — "no revocation event recorded before t" — is subject to revocation-propagation latency: the revocation may have occurred but not propagated. The draft waves past this at §2.2 by saying W should be set short enough. That is correct engineering guidance but is not a formal solution. The liveness invariant is a policy-bounded schema, not a mathematically sharp predicate. A hostile reviewer can break the claim that the invariant is "stated precisely" (Abstract) by pointing to W's underspecification. The required retreat: state explicitly that the invariant is a schema that achieves sharpness only relative to a policy-determined W and a revocation-propagation bound.

**Attack on the egress-dual — strongest structural objection**

This is the hardest attack. The ingress unmeasurability (MEMBRANE-PAPER-v3.md) is a logical theorem: no valid deductive argument from IS-premises alone yields an OUGHT-conclusion (Pigden / Hume). It operates at the level of logical type. The egress claim is not a logical theorem — it is a claim about the semantics of dynamic normative systems: OUGHTs indexed to conditions do not persist when those conditions change. This requires a non-classical, time-indexed deontic semantics (something like temporal deontic logic, e.g., Åqvist and Hoepelman 1981, or the more recent dynamic deontic logic literature). Classical deontic logic has no OUGHT-decay — if O(p) holds in a model, it holds regardless of what IS-facts obtain. The egress thesis implicitly presupposes a dynamic semantics where OUGHTs are event-indexed, but it does not name this presupposition.

The draft at §5.2 correctly identifies the asymmetry: "The ingress claim is a claim about logical entailment... The egress claim is a claim about temporal persistence." This is exactly right. But the very next sentence says "Both claims follow from the same underlying structure: the deontic operator is not self-perpetuating." This "same underlying structure" move is where the duality is overstated. A classical deontic logician would say: the deontic operator IS self-perpetuating in the classical semantics; the egress thesis requires rejecting that semantics in favor of a dynamic one. The ingress claim does not require any particular temporal semantics — it works in classical deontic logic. The egress claim requires a non-classical semantics. They do not both follow from "the deontic operator is not self-perpetuating" — they operate at different formal levels.

What survives: the structural parallel is real and illuminating. Both gaps concern the deontic operator's behavior at the seams of the access-control system. The duality is genuine at the intuitive level. But it is a structural analogy between a logical result and a semantic result about a particular class of dynamic systems — not a proven formal duality. The paper needs one explicit retreat on this claim.

**Attack on the theology's role**

The emet/met vocabulary is not merely illustrative — it is the paper's primary conceptual apparatus. This is declared at §6 ("illumination, not premise") but the vocabulary does structural work throughout. Most of this is defensible: the illumination is genuine, and no logical error follows from using theological vocabulary. The one place where a premise appears to be smuggled is the "near-nothing character of the aleph" explanation for why the met-condition is dangerous. This imports an aesthetic claim from the legend (small letters are easily overlooked) where the actual explanation is technical: a met token is artifact-identical to an emet token. The bytes are the same, the signature verifies, the structure parses correctly. Liveness is a relational property between the artifact and the current policy-system state, not a property of the artifact itself. Systems that check artifacts rather than policy-state relationships miss the met-condition. This is the correct explanation and it follows from the formal structure; the "near-nothing" explanation does not.

**Attack on confused deputy as a met-state**

The confused deputy mapping is the weakest of the four. G_A is temporally live at the moment of the confused-deputy act; the failure is principal-scope misattribution. The liveness invariant as stated — "every actuation must carry a live, re-said conferral traceable to a valid grant at or near the moment of action" — does not straightforwardly cover this case unless "correctly attributed" is folded into "live." Temporal freshness and correct attribution are distinct validity dimensions. The paper should either acknowledge that the invariant covers both (by extending "liveness" to include scope-correctness, with that extension made explicit) or treat confused deputy as a family-resemblance case rather than a clean instance.

### What survives the attack

The core thesis — that acting on an IS-record of a past OUGHT is the met-condition, and that the liveness invariant (G must be live-at-the-act, where "live" is freshness-window precisified) names what all real expiry/revocation/introspection mechanisms are implementing — survives. The cross-domain unification is the most defensible contribution: no single prior work unifies BAN freshness, zero-trust/continuous authorization, capability revocation, OAuth token management, OCSP, and TOCTOU under one deontic invariant. Each domain has its implementation; the met-condition framework names the common structure.

The honest novelty residue is exactly what the draft claims at §8: deontic naming of OUGHT-decay, the egress-dual structure (at moderate confidence, as a structural analogy rather than formal duality), and cross-domain unification. Not the mechanism.

### The ABLP gap the draft should fill

The draft cites ABLP only for the ingress unmeasurability. But the ABLP speaks-for formalism is directly relevant to the egress thesis as the formal starting point the thesis corrects: ABLP treats speaks-for grants as atemporal. There is no temporal index on delegation in ABLP's formalism. This is precisely the gap the liveness invariant fills. The paper should make this explicit rather than leaving ABLP's role confined to the ingress seam.

### RFC 7662 as the closest artifact of the met-condition

The `active` field in RFC 7662 (OAuth Token Introspection) is arguably the closest existing formalization of the met/emet distinction at the protocol level: active=false is the met-condition, active=true is the emet-condition. The introspection endpoint is the mechanism that converts a stored token (IS-record of a past OUGHT) into a current authorization state query (live OUGHT check). The paper should name this as the closest prior implementation artifact, more precisely than the current §7.4 treatment, and use it to sharpen the distinction between the mechanism (RFC 7662 already has it) and the deontic naming (which RFC 7662 does not provide).

### Five required bounds

1. Hold the weak form consistently throughout: every use of "met" for a stored grant must carry the freshness-window qualification or refer back to §2.3's definition.
2. Retreat one step on the duality: "structural analogy between a logical result and a semantic result about dynamic normative systems" — not "same underlying structure."
3. State the invariant is a policy-bounded schema: W is policy-delegated; revocation-propagation latency introduces irreducible approximation; the invariant's sharpness is bounded by both.
4. Acknowledge confused deputy as primarily a scoping failure that the liveness invariant covers only by extending "live" to include "correctly attributed."
5. Replace the "near-nothing" explanatory role with the technical explanation: met tokens are artifact-identical to emet tokens; liveness is a relational property of the token against the current policy-system state, not a property of the artifact.

### Verdict summary

Sound framing needing tighter bounds. The thesis is not mostly a relabel: the cross-domain unification and the OUGHT-decay deontic naming are genuine contributions beyond freshness/zero-trust/revocation relabeling. But "egress dual" is currently overstated as a formal result when it is a structural analogy, and two other claims (invariant sharpness; confused-deputy mapping) need explicit qualification. With the five bounds applied, the paper is publishable at the novelty level it claims.
