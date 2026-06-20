# Membrane Identity — Novelty Verdict

*Independent, web-grounded priority check (third adversarial pass on the membrane
result). Converges with the metaethics and priority reviews in `MEMBRANE-REVIEWS.md`.*

**VERDICT: PARTIALLY-ANTICIPATED — moderate confidence.**

## Most defensible novelty claim (exact phrasing)

A *framing / pedagogical mapping* of the descriptive→normative (is/ought) distinction
onto access control — **NOT an "identity."** The authorization step is where a deontic
operator enters that no authentication fact entails, licensed only by a standing policy
that plays Hume's missing bridge premise. "Identity" overclaims: Hume's gap is about
sentence-type *derivability*; authn/authz is a distinction between *system operations* —
structurally homomorphic, not identical.

## Closest prior art, ranked

1. **Searle (1964 "How to Derive 'Ought' from 'Is'"; 1995/2010 social ontology)** —
   closest and most dangerous. "X counts as Y in context C" confers a status function
   carrying deontic powers; the policy is the constitutive rule, the "MAY" rides in on
   the conferral. **Searle does NOT refute the framing — he relocates the conferral.**
   His move denies the *strong* is/ought gap by showing facts entail oughts *relative
   to a constitutive rule*. The claim already concedes exactly this ("conferred by a
   standing policy"), so the two are compatible; Searle supplies the mechanism the
   claim attributes to "policy."
2. **Hume, *Treatise* 3.1.1** — the source the claim is downstream of, not competing with.
3. **Deontic logic of permission** (von Wright; Jones & Sergot, "institutionalised
   power," 1996) — formalize authorization-as-deontic in computer systems, but one step
   away: they assume the normative status rather than naming the fact→norm transition as
   the Hume gap.
4. **The ABLP authentication-logic line** (Lampson/Abadi/Burrows/Wobber 1992; Abadi/
   Burrows/Lampson/Plotkin 1993, "A Calculus for Access Control") — the nearest
   *formal* neighbour, surfaced by the priority review: authentication propositions
   ("A says s", the speaks-for relation A⇒B) are provably insufficient for an access
   decision without a separate ACL premise. That is the authn/authz separation as formal
   non-entailment. It never asks whether the missing premise is *deontic* — which is
   exactly the residue the membrane result may claim.
5. **IAM canon** (Saltzer–Schroeder informally; Entra/OWASP/NIST) — the informal
   ancestor; never reaches for Hume.

## Genuinely unattested

The *specific naming* — authn→authz as an instance of the autonomy of the deontic with
the policy as bridge premise, plus the consequences that follow only from that naming.
arXiv: `authn AND authz AND "is-ought"` = 0; `authorization AND Hume` = 0;
`"access control" AND deontic` = 2 (unrelated). OpenAlex five-term intersection ≈ 2,
both off-topic. Web engines collapse every philosophy-framed query to generic IAM docs.

## Residual risk (strongest rejection)

A hostile referee collapses it both ways at once — into Searle ("counts-as with the
serial numbers filed off") AND into the standard slogan ("authn = who, authz = what
you may do; every textbook teaches it, now with a philosopher's name attached"). It
survives only if it (1) drops "identity" for "framing," (2) credits Searle and the
ABLP separation and claims to *operationalize* the bridge rather than *discover* the
gap, and (3) generates consequences the slogan can't — confused-deputy / ambient-
authority / token-as-fact-vs-grant as category errors of treating an IS-fact as
carrying an OUGHT.

## Method caveat (low confidence on completeness)

Semantic Scholar rate-limited (429). Depth on informal sources (blogs, lecture notes)
is limited; a manual Google Scholar pass could still surface a stray prior statement.
The negative-search claim is therefore scoped to the literatures actually reachable and
labelled **moderate at best**.

**BOTTOM LINE: PARTIALLY-ANTICIPATED (moderate). Defensible only as a framing /
operationalization, not an identity; Searle's counts-as does not refute it but supplies
and relocates the conferral.**
