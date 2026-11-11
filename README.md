# Record Renewal Compatibility in Collatz Synchronization

**Paper N — Two-Gate Jump Targets, Local vs. Long-Range Obstructions, and the Arithmetic Memory Problem**

Completes the two-gate jump framework for Collatz synchronization records and clarifies the exact scope of the local obstruction theory developed in Papers F–M.

> This repository does not claim a proof of the Collatz conjecture.

---

## Erratum (2026-11-12)

**Theorem SR is withdrawn.** The claim "after a height-K >= 4 jump, the immediately subsequent jump has height < K" is false.

- Gate-1 counterexample: 1643 -> 2465 -> 1849 -> 1387 -> 2081 (a_t = 1, 5, 3, 1, 5).
- Gate-2 counterexample: 267 -> 401 -> 301 -> 113 (a_t = 1, 4, 2, 4).
- Source of the error: after a jump the odd core is q' = (3q + 1) / 2^K, not a power of 3 times the pre-jump core, so the cascade endpoint is not fixed by the record condition (see the erratum of Paper H).
- Theorem UPI is formulated on the same cascade-endpoint residue. Its proof is not in this repository and it should be treated as unverified.
- Unaffected: Theorem JE, Theorem JE2 and Theorem OC (q -> 3q inside a cascade, i.e. for steps with a_t >= 3).

The PDF in `paper/` is the original, uncorrected version.

---

## Overview

Establishes jump formulas for both gate-1 and gate-2 renewal events, and identifies the precise boundary between local (cascade-level) and global (record-to-record) obstructions. The central open question is whether the inter-record transformation mixes residue classes effectively enough to prevent an infinite increasing chain of height records.

The central results are:

- **Theorem JE2** (Jump from Gate 2): At a semi-renewal event with nₜ = 1 + 4qₜ, the next value is T(nₜ) = (3qₜ+1)/2^s and height K is achieved iff qₜ ≡ r_{K,s} (mod 2^{K+s})
- **Theorem OC** (Cascade transport exact): If aₜ = k ≥ 3, then aₜ₊ⱼ = k − 2j and qₜ₊ⱼ = 3^j qₜ
- **Theorem SR** (Paper I): ~~After a height-K ≥ 4 jump, the immediately subsequent jump has height < K~~ — withdrawn, see Erratum
- **Theorem JE** (Gate 1): Complete jump formula from gate-1 renewal events

---

## Main Results

### Proved (Rigorous)

| Result | Method | Status |
|--------|--------|--------|
| Theorem JE2: gate-2 jump formula | 2-adic valuation | ✓ proved |
| Theorem OC: exact cascade transport law | Direct computation | ✓ proved |
| Theorem SR: immediate post-cascade height strictly less | Cascade algebra | ✗ withdrawn — false, see Erratum |
| Theorem JE: gate-1 jump formula | Congruence | ✓ proved |
| Theorem UPI (Paper M): phase graph cannot return to 0 (mod 2^{K-2}) within cascade | Phase graph | unverified, see Erratum |

---

## Structure

```
§1   Introduction (two gate types; scope clarification; record chain problem)
§2   Theorem JE2: gate-2 jump formula                    ✓
§3   Scope of cascade phase theory (Papers J–M)
§4   The record chain problem                            open
§5   Numerical evidence (n₀ = 27 example)
```

---

## Open Problems

- **Record chain compatibility**: Can an infinite sequence of jump heights K₁ < K₂ < ··· be realised by a single orbit?
- **Arithmetic memory of renewals**: Does q_{τᵢ} influence q_{τᵢ₊₁} modulo 2^{Kᵢ₊₁} systematically?
- **Global obstruction**: Is there a global obstruction from iteratively applying the local Theorem SR?

---

## Repository Structure

```
collatz-record-renewal/
├── README.md
├── paper/
│   └── paper_n_record_renewal_compatibility.pdf
└── LICENSE
```

---

## Related Work

This paper is part of a series on Collatz dynamics:

- [collatz-act1](https://github.com/KAMANOI/collatz-act1) — Foundational paper: prime survival dynamics and Chen-type theorem (v11)
- [collatz-renewal-structure](https://github.com/KAMANOI/collatz-renewal-structure) — Paper A: exact operator structure and finite information memory
- [collatz-finite-mixing-geometry](https://github.com/KAMANOI/collatz-finite-mixing-geometry) — Paper B: finite-level mixing geometry
- [collatz-spectral-amplification](https://github.com/KAMANOI/collatz-spectral-amplification) — Paper C: spectral amplification
- [collatz-scale-coherence](https://github.com/KAMANOI/collatz-scale-coherence) — Paper D: scale-coherence rigidity
- [collatz-valuation-renewal](https://github.com/KAMANOI/collatz-valuation-renewal) — Valuation renewal, finite residue connectivity, and orbitwise gap
- [collatz-residual-core](https://github.com/KAMANOI/collatz-residual-core) — The residual core: structural decomposition
- [collatz-congruence-synchronization](https://github.com/KAMANOI/collatz-congruence-synchronization) — Paper H: nested congruence constraints on synchronization
- [collatz-record-renewal](https://github.com/KAMANOI/collatz-record-renewal) — Paper N: record renewal compatibility
- [collatz-hensel-escape](https://github.com/KAMANOI/collatz-hensel-escape) — Paper O: Hensel memory and 2-adic escape target
- [collatz-hensel-scarcity](https://github.com/KAMANOI/collatz-hensel-scarcity) — Paper T: Hensel conditional scarcity and telescoping contradiction
- [collatz-prefix-counting](https://github.com/KAMANOI/collatz-prefix-counting) — Paper V: direct prefix counting and synchronization collapse
- [collatz-first-passage](https://github.com/KAMANOI/collatz-first-passage) — Paper W: first-passage obstruction (closes series A–V)
- [collatz-series-summary](https://github.com/KAMANOI/collatz-series-summary) — Series summary: research program on Collatz synchronization dynamics
- [collatz-prime-survival](https://github.com/KAMANOI/collatz-prime-survival) — Paper X v20: prime survival in affine Collatz dynamics

---

## Author

Hiroki Kamanoi
hirokikamanoi@gmail.com
2026

---
Related research and services by HDR (Human Driven Reality): https://hdr-ai.com/#research
