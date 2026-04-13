# SAPM Monte Carlo — Ultra-Processed Food / Palatability Ratchet

**Public replication repository for quantitative results in:**

> Postnieks, E. (2026). *Ultra-Processed Food (Palatability Ratchet).* SAPM Working Paper. SSRN.

This repository provides everything needed to independently reproduce, audit,
and extend the Monte Carlo simulation underlying the paper's core results.
The paper is available on SSRN.

---

## Results (N = 100,000 draws, seed = 42)

| Statistic | Value |
|-----------|-------|
| **β_W median** | **6.24** |
| β_W mean | 6.29 |
| β_W std | 0.74 |
| **90% CI** | **[5.2, 7.6]** |
| 99% CI | [4.8, 8.2] |
| P(β_W < 1) | 0.0000% |
| **ΔW median** | **$1,829.0B/yr** |
| Π (revenue) | $293.0B/yr |

**β_W = 6.24** means the ultra-processed food industry destroys **$6.24 in system
welfare for every $1.00 in revenue** — across 6 channels and 100,000 Monte Carlo draws.

**Classification**: Class 2 — Intractability

---

## What Is β_W?

```
β_W = ΔW / Π
```

- **ΔW** = total annualized welfare destruction ($B/yr) across all channels
- **Π** = annual industry **revenue** ($B/yr) — not profit

β_W > 1: industry destroys more welfare than it captures in revenue.
β_W > 3: Strong Intractability threshold — reform requires structural replacement.

---

## Quick Start

```bash
git clone https://github.com/epostnieks/sapm-mc-upf.git
cd sapm-mc-upf
pip install numpy scipy
python mc_simulation.py
```

Expected output: `β_W median : 6.24` and `ΔW median : $1,829.0B/yr`

---

## Welfare Channels

| Channel | Median ($B/yr) | 90% CI | Distribution |
|---------|---------------|--------|--------------|
| C1_metabolic_disease | $1,099.3B | [$915.5B, $1,319.1B] | Lognormal |
| C2_addiction_behavioral | $179.9B | [$115.5B, $280.9B] | Lognormal |
| C3_agricultural_distortion | $219.9B | [$161.4B, $299.9B] | Lognormal |
| C4_environmental_degradation | $140.1B | [$89.0B, $219.7B] | Lognormal |
| C5_governance_capture | $69.8B | [$40.9B, $119.5B] | Lognormal |
| C6_intergenerational_developmental | $99.9B | [$55.6B, $180.0B] | Lognormal |
| **Total ΔW** | **$1,829.0B** | **[$1,511.5B, $2,221.3B]** | Correlated (ρ=0.3) |

---

## Impossibility Floor

The floor β_W ≥ 3.7 cannot be breached by any policy while the
industry continues to operate. In 100,000 draws, only **0.0000%**
fall below this floor — confirming the structural constraint.

## Repository Contents

| File | Description |
|------|-------------|
| `mc_simulation.py` | Self-contained simulation — no private pipeline imports |
| `mc_results.json` | Pre-run results (100K draws, seed=42) — matches paper |
| `mc_histogram.json` | Binned β_W distribution (80 bins) for companion chart |
| `assumptions.md` | Every parameter: value, derivation, source |
| `data_sources.md` | Full citation list for all empirical inputs |

---

## Replication Notes

Results are seeded and deterministic. Tested with:
```
numpy==1.26.4  scipy==1.12.0  Python 3.11.9
```

The `median` and `ci_90` (to 1 decimal) match exactly across compatible versions.

---

## License

CC BY 4.0. Cite as:

> Postnieks, E. (2026). *SAPM Monte Carlo — Ultra-Processed Food (Palatability Ratchet)*.
> GitHub: epostnieks/sapm-mc-upf.
> https://github.com/epostnieks/sapm-mc-upf
