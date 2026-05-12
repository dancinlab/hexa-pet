# 🐱 hexa-pet — 반려동물 toolkit

> 5-verb consumer-pet-care substrate organized around the **n=6 invariant
> lattice**: cat-food / cat-litter / cat-toy / dog-food / dog-toy.
> Friendly self-contained pack — no other hexa-* repo required.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20102614.svg)](https://doi.org/10.5281/zenodo.20102614)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-informational.svg)](CHANGELOG.md)
[![Verbs: 5 spec](https://img.shields.io/badge/verbs-5_spec_(working_CLI_TBD)-blue.svg)](#verbs)
[![n=6 lattice](https://img.shields.io/badge/n%3D6-σ%3D12_τ%3D4_φ%3D2_J₂%3D24-purple.svg)](#why)

---

## Why

**hexa-pet** is the consumer-friendliest member of the HEXA family. The five
verbs cover the day-to-day surface of cat and dog ownership — food, litter,
toys — at the intersection of consumer-product engineering, animal behavior,
and small-scale material science.

This is the most self-contained pack in the family on purpose: every verb is
a single peer-citable spec doc with physical-limit anchors and a falsifier
preregister, copy-pasted out of the upstream
[`canon/domains/pets/`](https://github.com/dancinlab/canon)
tree (SHA `c0f1f570`, 2026-05-06). No other `hexa-*` repo is needed to use
this one — clone it, read it, hack it.

Why n=6? The HEXA-family lattice gives every verb the same algebraic backbone
(σ(6)=12, τ(6)=4, φ(6)=2, J₂(6)=24), and each verb's spec doc projects that
lattice onto its own physical-limit anchor — bentonite swell ratio, AAFCO
amino-acid registry, nepetalactone vapor pressure, canine bite mechanics,
and so on.

```
                       ┌──────────────────┐
                       │   companion-     │
                       │   animal care    │
                       └────────┬─────────┘
                                │
        ┌───────────────────────┼───────────────────────┐
        │           │           │           │           │
   ┌────▼────┐ ┌────▼────┐ ┌────▼────┐ ┌────▼────┐ ┌────▼────┐
   │cat_food │ │cat_litter│ │ cat_toy │ │dog_food │ │ dog_toy │
   └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘
     [SPEC]       [SPEC]      [SPEC]      [SPEC]      [SPEC]
```

---

## Verbs

| #   | Verb         | Domain                                          | Physical-limit anchor                                       | n=6 projection                              | Falsifier MVP gate            |
| --- | ------------ | ----------------------------------------------- | ----------------------------------------------------------- | ------------------------------------------- | ----------------------------- |
| 1   | `cat_food`   | feline obligate-carnivore food                  | AAFCO 26% protein / 0.1% taurine + Atwater 4-9-4 + Maillard | σ=12 raw-strategy registry                  | F-CF-MVP-1..5 2026-07~09-30   |
| 2   | `cat_litter` | bentonite + zeolite + carbon hygiene material   | Wyoming Na-bentonite swell 12× (Grim 1968)                  | σ=12 swell ratio · τ=4 odor tier            | F-CL-MVP-1..4 2026-07~08-30   |
| 3   | `cat_toy`    | nepetalactone-driven prey-mimic toys            | Antoine 1888 nepetalactone vapor pressure + Kevlar 29 fiber | per-verb projection                         | F-CT-MVP-* (TBD)              |
| 4   | `dog_food`   | facultative-carnivore canine food               | AAFCO 18% protein / 10 EAA + low-GI grain agronomy          | per-verb projection                         | F-DF-MVP-* (TBD)              |
| 5   | `dog_toy`    | Kevlar-core rope + rubber chew toys             | Lindner 1995 canine bite 1-4 MPa + Hertz 1881 contact       | per-verb projection                         | F-DT-MVP-* (TBD)              |

Each verb's `<verb>/<verb>.md` is a peer-citable spec — open it, read it,
cite it. The CLI router prints the first 30 lines of each doc as a quick
preview.

---

## Status

> **5-verb 반려동물 substrate. Spec-first (working `.hexa` CLI TBD).
> Consumer-friendly self-contained pack.**

What ships at v1.0.0:

- 5 peer-citable spec docs (one `.md` per verb), extracted unchanged from
  `canon@c0f1f570`. These are the source of truth.
- A placeholder CLI dispatcher (`cli/hexa-pet.hexa`) that prints each spec
  doc headline + a 5-verb count selftest.
- `install.hexa` hx hook (mirrors the `hexa-bio` install pattern).
- MIT license — friendly for downstream consumer products + maker remix.

What does NOT ship at v1.0.0 (honest C3 caveats):

1. **No working numerical sandbox yet.** Every verb is spec-only; the CLI
   subcommands print spec headlines, not simulator output. Working `.hexa`
   modules are TBD per the per-verb F-*-MVP-* deadlines (cat-litter and
   cat-food first wave 2026-07-30 ~ 09-30).
2. **Physical-limit anchors are theoretical-analytical.** AAFCO numbers,
   Atwater factors, Wyoming-bentonite swell ratios, nepetalactone vapor
   pressure — all literature-anchored, none lab-measured by this repo yet.
3. **n=6 lattice projections are per-verb hypotheses.** Only the lattice
   itself (σ(6)=12 etc.) is mathematically verified; each verb's projection
   onto that lattice is a working hypothesis pending Bayesian audit per
   F-* gates.
4. **No regulatory pathway.** AAFCO / WSAVA / FAO endorsement is post-MVP;
   nothing here is a medical, veterinary, or nutritional claim.
5. **Consumer-friendly ≠ consumer-tested.** This is a builder substrate, not
   a finished product. No animal trials have been conducted.

---

## Install

```bash
# 1. Install hexa-lang (gives you `hexa` + `hx` package manager)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/dancinlab/hexa-lang/main/install.sh)"

# 2. Install hexa-pet
hx install hexa-pet
```

---

## Run

```bash
hexa-pet cat_food            # feline obligate-carnivore food spec       [SPEC]
hexa-pet cat_litter          # Wyoming bentonite hygiene material spec   [SPEC]
hexa-pet cat_toy             # nepetalactone prey-mimic toy spec         [SPEC]
hexa-pet dog_food            # facultative-carnivore canine food spec    [SPEC]
hexa-pet dog_toy             # Kevlar/rubber canine chew toy spec        [SPEC]
hexa-pet status              # 5-verb status table + verdict + caveats
hexa-pet selftest            # 5-verb spec doc presence count check
hexa-pet --version           # show version
hexa-pet --help              # full usage
```

---

## Provenance

Extracted 2026-05-06 from
[`canon`](https://github.com/dancinlab/canon)
SHA `c0f1f570` (`domains/pets/` subtree). Source files unchanged; directory
slugs converted to `snake_case` per hexa-lang raw#11 (`cat-food/` →
`cat_food/` etc.). Sister extraction of:

- [`hexa-bio`](https://github.com/dancinlab/hexa-bio) — molecular
  toolkit (4-verb HEXA family, 1/4 wired)

---

## License

MIT — see [LICENSE](LICENSE).

Author: 박민우 <nerve011235@gmail.com>
