<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/HarperZ9/senses-and-sensibility/main/docs/art/hero-dark.svg">
  <img src="https://raw.githubusercontent.com/HarperZ9/senses-and-sensibility/main/docs/art/hero-light.svg" alt="senses-and-sensibility: A research program in intrinsic, bilateral accountability for agents. A fan of ruled sheets drawn in fine lines, the top sheet lit by a bright core." width="100%">
</picture>

# senses-and-sensibility

A research program in intrinsic, bilateral accountability for agents.

[![license](https://img.shields.io/badge/license-CC_BY_4.0%2C_MIT-e6e1d6?style=flat-square&labelColor=1a1712)](https://github.com/HarperZ9/senses-and-sensibility/blob/main/LICENSE)

> A research program in **intrinsic, bilateral accountability** — and the long-form
> philosophical corpus it is extracted from. Original scholarship by **Zain Dana Harper**.
> Text: CC BY 4.0. Code: MIT. Authored and dated 2026-06-20.

This is the *philosophy*. The accountability thesis it grounds is also built and
public — a tested, inspectable stack of organs at **[harperz9.github.io](https://harperz9.github.io)**
(see the [research page](https://harperz9.github.io/research.html)). The corpus argues
the position; the engineering instantiates it.

## The thesis, in one breath

Agentic systems perceive, decide, and act — but their claims about the world, and their
authority to change it, are *asserted*, not answerable to evidence. The claim here is that
accountability can be built as an **intrinsic, bilateral property**: every observation
carries provenance and can fail a self-test; every action passes a gate that can only
allow, deny, or escalate to a human; and the same evidentiary standard binds the maker,
not only the machine. Stated falsifiably, instantiated in a working proof-of-concept, and
honest about its own status — **pre-proof, with a stated path to a law.**

## Status — labeled, not inflated

A research program **in progress**. Chapters are at varying maturity; the central
conjecture is **pre-proof**; some arguments are load-bearing and some are still under
cross-examination (the corpus includes its own adversarial passes). Read it as live
scholarship staking its ground, not a finished dissertation.

## Where to start

- **`00-ABSTRACT.md`** — the abstract.
- **`THESIS.md`** — the concise statement of the principles and the accountable loop.
- **`INDEX.md`** · **`CATALOG.md`** — the map of the corpus.
- **`dissertation/`** — the long-form argument (the forcing argument, the membrane, the
  seam, comparative theology) and its `foundations-src/` attack↔defense dialectic.
- **`papers/`** · **`submission/`** — submission-shaped manuscripts.
- **`conferred-existence/`** — the source corpus the thesis is drawn from.

## Cloning on Windows

One file path in `dissertation/foundations-src/` is 140 characters long. Inside a deep
folder that pushes the full path past the 260-character Windows limit, and Git aborts
the checkout. Turn on long paths for the clone:

```sh
git clone -c core.longpaths=true https://github.com/HarperZ9/senses-and-sensibility.git
```

Or set it once for every repository with `git config --global core.longpaths true`.

## Priority & provenance

`MANIFEST.sha256` is a content-addressed record of every file here — a provable,
dated priority stake so the work is **citable and cannot be quietly appropriated**.
Verify with `sha256sum -c MANIFEST.sha256`.

The buildable security-architecture *implementation* and the internal research tooling
are **not** part of this corpus; what is published is the scholarship.

## Licence

Text: CC BY 4.0. Code: MIT.

The paper and the corpus are prose, so they carry a Creative Commons licence.
You may share and adapt them for any purpose if you credit Zain Dana Harper and
link the deposit at [doi.org/10.5281/zenodo.20773724](https://doi.org/10.5281/zenodo.20773724),
which Zenodo records under the same licence. The terms are in
[`LICENSE-TEXT`](LICENSE-TEXT). The repository holds no code today. Code added
later falls under the MIT terms in [`LICENSE`](LICENSE).

---

*Zain Dana Harper · [harperz9.github.io](https://harperz9.github.io) · Text CC BY 4.0, code MIT · 2026.*
*Proof before trust — including about authorship.*

---

Built by **[Zain Dana Harper](https://harperz9.github.io)** in Seattle: evidence-first tools that leave a re-checkable artifact behind. The full workbench is at [Project Telos](https://harperz9.github.io).
