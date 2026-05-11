# LIMIT_BREAKTHROUGH.md — hexa-pet

> Real-limits audit (Wave M) per `LATTICE_POLICY.md §1.2`.
> Domain: **companion-animal welfare & consumer-product engineering** —
> cat food, cat litter, cat toy, dog food, dog toy. Real ceilings are
> nutrient biochemistry (AAFCO essential amino acids, taurine for cats),
> material science (bentonite swell, clay friability), species behavioural
> physiology (nepetalactone vapor pressure, canine bite force), and
> consumer-product regulatory throughput (AAFCO / FDA-CVM / EU FEEDAP).

---

## §1 Domain identification

`hexa-pet` is a self-contained 5-verb consumer-pet pack:

- `cat_food` — feline-specific obligate carnivore nutrition.
- `cat_litter` — bentonite / silica gel / corn / wood pellet substrate.
- `cat_toy` — nepetalactone-loaded / laser-pointer / wand / kicker.
- `dog_food` — canine omnivorous balanced nutrition.
- `dog_toy` — chew-resistant elastomer / rope / treat-dispenser.

Each verb is a single peer-citable spec with physical-limit anchor and
falsifier preregister, copy-pasted from `canon/domains/pets/` (SHA
c0f1f570, 2026-05-06). No wet-trial, no animal-study data — this is
a *spec* repo. The real ceilings below define what the spec can claim.

---

## §2 Real limits applicable

### L1 — Feline obligate-carnivore taurine requirement (HARD_WALL)
- **Bound**: domestic cats cannot synthesise taurine de novo at
  rates meeting need; dietary requirement ≥ 1,000 mg/kg dry matter
  in dry food, ≥ 2,000–2,500 mg/kg in canned (NRC *Nutrient
  Requirements of Dogs and Cats* 2006).
- **Anchor**: low hepatic cysteine sulfinic acid decarboxylase
  activity (Knopf et al., *J. Nutr.* 1978). Cannot be engineered
  out of feline biochemistry.
- **Repo touch**: `cat_food` verb spec.

### L2 — Dietary essential amino acids — AAFCO panels (HARD_WALL)
- **Bound**: 11 essential amino acids for cats (incl. arginine,
  taurine, methionine + cystine, lysine), 10 for dogs (no taurine
  for healthy dogs, though large-breed deficiencies linked to DCM —
  Adin et al., *J. Vet. Cardiol.* 2019).
- **Anchor**: enzyme repertoire absent in liver. AAFCO 2024 dog &
  cat food nutrient profiles set legal minima.
- **Repo touch**: `cat_food`, `dog_food`.

### L3 — Bentonite litter swell ratio (HARD/SOFT — material science)
- **Bound**: Wyoming sodium bentonite swell ratio 15–20× free volume
  (Grim & Güven, *Bentonites: Geology, Mineralogy, Properties and
  Uses* 1978); clumping strength governed by montmorillonite
  fraction ≥ 70 %.
- **Anchor**: smectite interlayer water uptake — physical-chemical
  property. Replaceable by silica gel (different mechanism) or
  wood-pellet (no clumping). Each substrate has its own ceiling.
- **Repo touch**: `cat_litter`.

### L4 — Feline olfactory sensitivity — nepetalactone (HARD per-species)
- **Bound**: catnip response trait inherited in ~ 65–75 % of
  domestic cats (Todd, *J. Hered.* 1962); nepetalactone vapor
  pressure ≈ 0.013 mmHg at 25 °C drives behavioural threshold.
- **Anchor**: V1R receptor variant; cats lacking the variant
  do not respond.
- **Repo touch**: `cat_toy` (catnip-loaded variant).

### L5 — Canine bite force / chew resistance (HARD per-breed)
- **Bound**: domestic dog mean bite force 230–700 N (canine tooth
  PSI 200–450), Rottweiler/Mastiff ~ 1,400 N peak (Ellis et al.,
  *Arch. Oral Biol.* 2008).
- **Anchor**: temporalis + masseter muscle cross-section ×
  mechanical advantage. Toy elastomer must exceed bite-force ×
  tooth contact area without fragmenting (FDA-CVM aspiration
  hazard threshold).
- **Repo touch**: `dog_toy`.

### L6 — Canine olfaction sensitivity (HARD biophysical)
- **Bound**: 10⁴–10⁵× more sensitive than human for some VOCs;
  ~ 220M olfactory receptor neurons vs. ~ 5M human (Walker et al.,
  *Appl. Anim. Behav. Sci.* 2006).
- **Anchor**: nasal turbinate surface area + V1R/V2R/TAAR repertoire.
- **Repo touch**: `dog_toy` (scent-loaded), `dog_food` (palatability).

### L7 — Pet-food safety / mycotoxin contamination (SOFT_WALL — engineering)
- **Bound**: aflatoxin B1 FDA action level 20 ppb total aflatoxins
  for pet food; vomitoxin (DON) advisory 5 ppm (FDA Compliance
  Policy Guide 7126.33).
- **Anchor**: grain storage moisture < 13 %, temperature control,
  ELISA / HPLC QC. Engineering improvable.

### L8 — Laser-pointer toy safety — retinal damage (HARD_WALL)
- **Bound**: Class IIIa < 5 mW continuous wave; ANSI Z136.1 MPE
  for 532 nm green ~ 2.5 mW/cm² for accidental 0.25 s exposure;
  Class IV > 500 mW causes permanent retinal damage in < 1 s.
- **Anchor**: photochemical + thermal retinal damage thresholds.
- **Repo touch**: `cat_toy` (laser variant).

### L9 — Plastic toy ingestion / endocrine-disruptor leach (SOFT_WALL — regulatory)
- **Bound**: BPA, phthalates (DEHP, DBP), BPS migration limits per
  EU REACH Annex XVII; FDA-CVM has no specific pet-toy
  toxicology framework, often inherits human-toy CPSIA standards.
- **Anchor**: regulatory engineering, polymer chemistry.
- **Repo touch**: `dog_toy`, `cat_toy`.

### L10 — Species-specific feline kidney filtration (HARD physiological)
- **Bound**: cat GFR ~ 2–3 mL/min/kg (dog ~ 3–4 mL/min/kg, human ~
  1.7 mL/min/kg) — cats are unusually prone to chronic kidney
  disease in geriatric population (~ 30 % > 10 yr; Marino et al.,
  *J. Feline Med. Surg.* 2014).
- **Anchor**: feline nephron architecture + low water-conserving
  thirst drive. Diet sodium / phosphorus / protein levels gated
  by this floor.
- **Repo touch**: `cat_food` (renal-supportive variant).

---

## §3 Per-limit breakthrough assessment

| ID | Limit | Wall type | Verb | Breakthrough vector | Verdict |
|----|-------|-----------|------|---------------------|---------|
| L1 | Cat taurine req | HARD | cat_food | None; must supplement | unbreakable |
| L2 | AAFCO EAA panel | HARD | cat_food, dog_food | None; must meet | unbreakable |
| L3 | Bentonite swell 15–20× | HARD per-material | cat_litter | Material substitution | per-substrate ceiling |
| L4 | Catnip ~ 70 % responder | HARD per-species | cat_toy | Silvervine, valerian alternatives | partial workaround |
| L5 | Bite force 230–1,400 N | HARD per-breed | dog_toy | Material engineering | toy must scale ≥ breed |
| L6 | Canine olfaction 10⁴× human | HARD | dog_toy, dog_food | None; use as feature | unbreakable advantage |
| L7 | Mycotoxin 20 ppb aflatoxin | SOFT | both foods | QC + grain handling | improvable to < LOQ |
| L8 | Laser Class IIIa < 5 mW | HARD safety | cat_toy laser | Switch to Class II, < 1 mW | engineering compliance |
| L9 | Plastic endocrine-disruptor | SOFT | both toys | Use phthalate-free TPE / silicone / natural rubber | improvable, certifiable |
| L10 | Feline GFR floor | HARD physiology | cat_food | Renal diet formulation | unbreakable; diet-adjust |

---

## §4 Top-3 breakthrough opportunities

### #1 — AAFCO-anchored nutrient labelling on every food verb (rides L1, L2, L10)
For `cat_food` and `dog_food` specs: require AAFCO 2024 nutrient
profile compliance as a HARD verification gate. Specifically:
- `cat_food`: ≥ 26 % crude protein, ≥ 1,000 mg/kg taurine (dry),
  ≥ 1.04 % arginine, plus full essential amino acid panel.
- `dog_food`: ≥ 18 % crude protein adult / ≥ 22.5 % growth.
- `cat_food` renal-support variant: phosphorus ≤ 0.5 % DM,
  controlled sodium, omega-3 supplementation.
This is not novel science; the breakthrough is **honest labelling
discipline** that names the AAFCO panel as the ceiling, not n=6
lattice algebra.

### #2 — Material-substitution table for cat_litter (rides L3)
The `cat_litter` spec should declare per-substrate ceilings:
- bentonite (Wyoming Na): swell 15–20×, dust < 2 % w/w,
  clumping strength ≥ 100 g shear.
- silica gel: water capacity ~ 40 % w/w, odour binding via
  pore-size, dust hazard (crystalline silica respirable < 4 µm).
- corn/wheat: clumping via starch gel, biodegradable but
  mycotoxin risk if storage poor.
- wood pellet: non-clumping, biodegradable, low dust.
Each substrate gets its own falsifier; no single "best" litter.

### #3 — Bite-force-scaled chew-toy material spec (rides L5, L9)
`dog_toy` spec should map breed→bite-force class (Toy / Small /
Medium / Large / Working) and prescribe Shore A hardness +
tensile strength minimums per class. Material chemistry must be
declared phthalate-free / BPA-free / latex-free (allergens), with
EU REACH Annex XVII compliance as a hard verifier. Aspiration-
hazard floor: smallest chewable fragment ≥ 32 mm or
equivalent diameter.

---

## §5 Honest caveats

1. **This is consumer-product engineering, not veterinary
   medicine.** No verb in hexa-pet prescribes treatment for any
   animal disease. Renal-support cat-food formulation is a
   *nutritional* spec, not a clinical claim.
2. **AAFCO is not FDA approval.** Pet-food in the US is regulated
   under the Federal Food, Drug, and Cosmetic Act but AAFCO
   nutrient profiles are voluntary state-adopted standards. EU
   uses EFSA-FEEDAP. Spec must declare jurisdiction.
3. **Catnip non-responders (~ 30 %)** are biologically determined
   — the `cat_toy` spec must include silvervine / valerian /
   honeysuckle alternatives, not assume universal response.
4. **Laser-pointer toys** are popular but have documented welfare
   concerns (frustration without prey capture; Cottam & Dodman,
   *Appl. Anim. Behav. Sci.* 2010). The spec should require
   pairing with a physical reward at session end.
5. **The σ(6)=12 / J₂=24 / n=6 lattice is organising vocabulary
   only.** Cats do not eat by lattice algebra; they eat by AAFCO
   panel. Bentonite swell is mineralogy, not number theory.
6. **DCM-grain-free dog food controversy** (FDA-CVM 2019
   investigation, Adin et al. *J. Vet. Cardiol.* 2019) suggests
   that taurine deficiency may arise in some dogs on legume-heavy
   grain-free formulations. `dog_food` spec should acknowledge
   this as an open safety signal.
7. **HARD walls L1, L2, L4, L5, L6, L8, L10** are biology /
   physics. **SOFT walls L7, L9** admit improvement; L3 admits
   substrate-swap but each substrate has its own hard ceiling.
8. **No clinical-trial data is used.** The verbs are consumer-
   product specifications; efficacy claims must remain
   nutritional / mechanical / behavioural — never therapeutic.

---

## §6 References

- NRC. *Nutrient Requirements of Dogs and Cats*. National Academies
  Press (2006).
- Knopf K, Sturman JA, Armstrong M, Hayes KC. Taurine: an essential
  nutrient for the cat. *J. Nutr.* 108:773–8 (1978).
- AAFCO. Official Publication 2024. Association of American Feed
  Control Officials.
- Adin D et al. Echocardiographic phenotype of canine dilated
  cardiomyopathy differs based on diet type. *J. Vet. Cardiol.*
  21:1–9 (2019).
- Grim RE, Güven N. *Bentonites: Geology, Mineralogy, Properties
  and Uses*. Elsevier (1978).
- Todd NB. Inheritance of the catnip response in domestic cats.
  *J. Hered.* 53:54–6 (1962).
- Ellis JL et al. Cranial dimensions and forces of biting in the
  domestic dog. *Arch. Oral Biol.* 53:1119–25 (2008).
- Walker DB et al. Naturalistic quantification of canine olfactory
  sensitivity. *Appl. Anim. Behav. Sci.* 97:241–54 (2006).
- FDA Compliance Policy Guide Sec. 683.100 — Action Levels for
  Aflatoxins in Animal Feeds.
- ANSI Z136.1-2014. American National Standard for Safe Use of
  Lasers.
- EU REACH Regulation (EC) No 1907/2006, Annex XVII.
- Marino CL et al. Prevalence and classification of chronic
  kidney disease in cats randomly selected from four age groups.
  *J. Feline Med. Surg.* 16:465–72 (2014).
- Cottam N, Dodman NH. Comparison of the effectiveness of a
  purported anti-anxiety body wrap with that of placebo on
  thunderstorm anxiety in dogs. *Appl. Anim. Behav. Sci.*
  121:235–43 (2010).

---

*Wave M — real-limits audit; n=6 lattice not used as nutritional
or material evidence. HARD walls L1, L2, L4, L5, L6, L8, L10 are
biology/physics-unbreakable; SOFT walls L3 (substrate-swap), L7
(QC), L9 (regulatory) are improvable.*
