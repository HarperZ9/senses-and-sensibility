# Syllabus — *Conferred Existence: From Ontological Nihilism to the Limits of Authentication*

A one-term graduate seminar (13 weeks) bridging metaphysics, philosophical
theology, philosophy of mind, and security architecture. Cross-listed:
Philosophy / Computer Science (security) / Science-and-Technology Studies.

## Description

A single thesis carried across two fields: that existence is *conferred* rather
than possessed, that the act of conferral (the *for*, authorization, will) cannot
be reduced to a property of the thing conferred, and that this metaphysical claim
becomes a precise structural constraint on what an authentication system can
do. Students leave able to (a) state and defend the no-aseity reading of
ontological nihilism, (b) distinguish authentication from authorization at the
level of category, and (c) read a security architecture for the boundary between
what construction can secure and what only process can hold.

**Sprint 1 status note.** The seminar should be taught with `THE-STRAIGHT-LINE.md`:
convergence is abductive and bounded; theorem vocabulary is treated as a claim
to test, not an established result.

## Prerequisites

Introductory analytic metaphysics *or* graduate security; willingness to work
across both. No cryptography background assumed beyond definitions.

## Learning outcomes

1. Defend the no-aseity thesis against the self-refutation objection.
2. Reconstruct creation-as-evidence-*for*-nihilism (*esse ab alio*).
3. Separate the open-future and constructed-past claims; place each in its
   literature.
4. Apply the intrinsic-over-extrinsic and construction-over-detection design laws.
5. Run a threat-model teardown that distinguishes the irreducible roots from the
   human seams.
6. State the terminus argument for free authorship and explain why determinism
   is orthogonal to it.
7. Tell discovery from enumeration — and defend an *authored* stop.

## Modules

- **Wk 1 — The two nihilisms.** "Nothing exists" vs. "no aseity." Why only the
  second survives. *Read:* Westerhoff (2020), intro; Nāgārjuna (sel.); van
  Inwagen (1990), ch. on composition. *(Laws L1)*
- **Wk 2 — Existence as speech-act.** *kun*; *emet/met/aleph*; *Sefer Yetzirah*.
  *Read:* Qur'an 36:82, 2:117; Shabbat 55a; Scholem on the Golem (instructor
  handout). *(Abstracts: emet/met/aleph, kun)*
- **Wk 3 — Creation as evidence *for* nihilism.** *esse ab alio*; occasionalism;
  the *waḥdat al-wujūd* correction. *Read:* Aquinas, *De Ente* (sel.); al-Ghazālī,
  17th Discussion; Ibn al-ʿArabī (sel.). *(L1; Abstract: occasionalism)*
- **Wk 4 — The open future and the constructed past.** *Read:* Aristotle, *De
  Int.* 9; Dummett, "The Reality of the Past"; Benjamin, "On the Concept of
  History"; Maimonides III.20 (omniscience tension). *(Time)*
- **Wk 5 — The *for* is spoken.** Seed vs. tending; direction-neutral
  generativity; selection's criterion. *Read:* Campbell (1974); Popper (sel.).
  *(L2–L4)*
- **Wk 6 — Made or grown?** Artifact vs. cultivated; standing without origin.
  *Read:* Aristotle, *Physics* II.1; Heidegger (1954); Simondon (sel.); Kant,
  *Groundwork* (Formula of Humanity); Parfit (1984), non-identity. *(L5)*
- **Wk 7 — The bridge: is/ought and authn/authz.** *Read:* Hume, *Treatise* III
  (is/ought); Searle (1964); Austin (1962); Brentano (1874), sel. *(L8)*
- **Wk 8 — Intrinsic over extrinsic.** Capability, ZK, content-addressing.
  *Read:* Hardy (1988); Miller (2006), sel.; Goldwasser–Micali–Rackoff (1989),
  defn.; Merkle. *(L6–L7; Primitives)*
- **Wk 9 — The witness and the veto.** CMC; ErrP; continuous identity; fuzzy
  extractors. *Read:* Conway et al. (1995); Gehring et al. (1993); Dodis–Reyzin–
  Smith (2004); Ratha et al. (2001). *(Primitives)*
- **Wk 10 — Teardown I: the roots.** Enrollment vs. TCB; side-channels feeding
  biological permanence; the two clocks. *Read:* Kocher (1996/1999);
  Foreshadow/Plundervolt (sel.). *(L9; the four roots)*
- **Wk 11 — Teardown II: the human seam.** Coercion, perception-blind deception,
  drift, holder-compromise, will-shaping. *Read:* Frankfurt (1971); Christman
  (1991); Libet (1983) + Schurger (2012). *(Will-shaping; L12)*
- **Wk 12 — The formal terminus.** The two transits; degenerate constructors; the
  terminus argument; why determinism is orthogonal; the gap as *shape*, not
  defense. *Read:* corpus Part IV; Hume + Brentano revisited. *(L13)*
- **Wk 13 — The authored stop.** Discovery vs. enumeration; process over
  property; the honest spec. *Read:* corpus Parts III–IV; capstone presentations.
  *(L11, L14)*

## Assignments

1. **Position paper (Wk 4):** Defend or refute "creation theology is evidence
   *for* no-aseity, not against it." (~2,500 words.)
2. **Design memo (Wk 9):** Take one extrinsic check in a system you know and
   propose its intrinsic substitution; name the residual assumption (L7).
3. **Teardown (Wk 11):** Threat-model a chosen authorization boundary; classify
   every finding as irreducible-root or human-seam; do not oversell.
4. **Capstone (Wk 13):** Either (a) attempt to construct a node-mover and show
   honestly where it returns to the node, or (b) extend the honest spec to a new
   deployment. Graded on rigor and refusal-to-oversell, not on breaking the node.

## Assessment

Position paper 20% · Design memo 15% · Teardown 25% · Capstone 30% ·
Seminar participation 10%. **Standing policy:** an argument that names its own
confidence and its own residual assumption outscores a cleaner one that hides
them.
