# TAPE-AUDIT — hexa-pet

**Date:** 2026-05-14 · **Lens:** `.tape` (typed events + `<DOMAIN>.tape` placement).

## A. Audit-class ledgers

`state/markers/*.marker` — minimal dancinlab boot-hook markers (5 checks + `hexa-pet_*`), **CARGO**. No `.jsonl`, no audit scripts.

## B. Identity surface

`hexa.toml` no `[identity]` (regex). Pet-product substrate (food / litter / toy for cat·dog), not per-agent.

## C. Domain.md files

**5 UPPERCASE.md** (after excluding RELEASE_NOTES): `CAT-FOOD.md` (82 KB), `CAT-LITTER.md` (54 KB), `CAT-TOY.md` (66 KB), `DOG-FOOD.md` (69 KB), `DOG-TOY.md` (67 KB). **Strong domain-convention adoption** — every verb has a full UPPERCASE.md spec at root. The hyphenated `CAT-FOOD` / `DOG-TOY` form matches the `<UPPERCASE>(+<UPPERCASE>)*.md` meta-domain convention (governance #4) semantically — though hyphens here read as compound-noun rather than `+` meta-conjunction.

## D. Per-run / per-event history

None — boot-hook markers only. No per-product / per-pet-feeding event stream. `firmware/` exists (one of the few in this audit) — implies real device firmware roll-up potential but no ledger today.

## E. Promotion candidates

- **`<DOMAIN>.tape`** (MEDIUM): each `CAT-FOOD.md` / `DOG-TOY.md` could grow a sibling `.tape` for product-revision events / safety-recall / batch-test results. Currently the 80 KB prose carries all evolution.
- **`.tape` device-telemetry**: `firmware/` suggests future IoT pet-device event streams (smart-feeder · smart-litter-box) — `@H` per-feeding, `@R` per-weight-measurement. Pre-impl.
- **n6 atoms**: pet-nutrition lattice cells possible but real-veterinary-science dominates.

## Verdict

**MEDIUM** — strong domain.md convention adoption (5 large UPPERCASE.md spec files, one per product-verb), `firmware/` hints at future device ledgers. State surface today is marker-cargo only. Best domain-convention adopter outside hexa-grid in this audit set.
