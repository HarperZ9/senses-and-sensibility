# Membrane Paper — Errata (required before submission)

*Three independent adversarial passes — the metaethics review, the priority review
(`MEMBRANE-REVIEWS.md`), and the web-grounded novelty check (`MEMBRANE-NOVELTY.md`) —
converge on the same corrections. The draft `MEMBRANE-PAPER.md` is retained as written;
these errata bound what it may claim. The headline must change before the paper is
submittable.*

## 1. Reframe "identity" → "framing / operationalization"

The authn→authz step is **not identical** to Hume's *categorical* guillotine. The
authorization "ought" is a **policy-relative deontic permission** (von Wright's ¬O¬p),
and a policy-relative permission *is* derivable from is-facts plus the descriptive fact
that policy P is in force — exactly what Searle wanted, and exactly what Hume's
*categorical* gap is not about. What the result actually instantiates is the **general
autonomy of the deontic** — **Pigden's** formalization of Hume's law (valid inference
introduces no new non-logical vocabulary), shared with chess ("checkmate"), grammar,
and tax law. Claim the **framing**, not the identity. Drop "this IS Hume's guillotine"
for "this operationalizes the autonomy of the deontic in an engineered system."

## 2. Credit and distance the prior art (the uncited nearest neighbours)

The *separation* of authentication-facts from the authorization-decision is prior art:

- **Informally** — Saltzer & Schroeder; the entire IAM canon.
- **Formally** — the **ABLP calculus** (Lampson/Abadi/Burrows/Wobber 1992; Abadi/
  Burrows/Lampson/Plotkin 1993): authentication propositions ("A says s", speaks-for
  A⇒B) are provably insufficient for access without a separate ACL premise. **This is
  the nearest neighbour and must be cited and distinguished.**
- **Architecturally** — XACML's PDP/PIP split.
- **In deontic logic** — von Wright; Jones & Sergot ("institutionalised power," 1996).
- **The conferral mechanism** — Searle's counts-as (1964; 1995).

ABLP never asks whether the missing premise is **deontic**. That is the gap to claim.

## 3. The exact defensible contribution (claim this, nothing stronger)

> The separation is prior art. This paper contributes the explicit identification of
> the required extra premise as **deontic** (a permission), the subsumption of the
> authn→authz step under the autonomy of the deontic, and — *only* from that naming —
> two consequences the slogan cannot generate: (a) the **unmeasurability result** (the
> gap is logical, not epistemic; no authentication improvement closes it), and (b) the
> **failure taxonomy** — confused-deputy, ambient authority, and token-as-fact-vs-grant
> as **category errors of treating an IS-fact as carrying an OUGHT**. The contribution
> is the meta-ethical classification of an already-separated structure, not the
> discovery of the separation.

literatures surveyed). Label the negative-search claim; do not write "apparently
unattested" unqualified.

## 4. The Searle adjudication (keep, with the boomerang named)

Searle does not refute the framing; he **relocates** the conferral (the constitutive
rule is the policy; the MAY rides in on the enactment — Hare/Hudson: the rule smuggles
the ought). But the same Hare/Hudson move reveals the authz "ought" is **inert** — a
PDP "permit" binds no one to act and motivates nothing. So the paper cannot have it
both ways: it needs the *strong* (endorsement-laden) ought to beat Searle and the
*weak* (policy-relative, inert) ought to stay inside its own scope limits. Resolution:
concede the weak ought, claim Pigden not Hume, and locate the only live normative
entry at the **human act of stipulating the policy / root of trust** (= Hare/Hudson
"subscribing").


Objection: in object-capability systems, *possessing the token IS authorization* — does
this collapse the is/ought split? **No — it relocates the seam.** A capability is a
**materialized grant**: an ought made bearer-portable. The is/ought seam sits at the
moment of **issuance / delegation**, not at presentation. The capability is not an
is-fact that entails its own permission; it is the *record* of a prior conferral. ACL
and capability architectures therefore both exhibit the seam; they differ only in
*where* the conferral is recorded (in a policy table vs. in the token itself). This is
the §5.1 "relocates, does not eliminate" move, applied correctly.

## 6. Citation debts to clear

Searle 1964 (the actual target, not only *Speech Acts* / *Construction*); Hare 1964
("The Promising Game"); Hudson 1969 (*The Is-Ought Question*); **Pigden 1989**
(dispositive — vindicates the formal point, deflates the profundity); von Wright;
Jones & Sergot 1996; the ABLP papers (1992, 1993); Saltzer & Schroeder.
