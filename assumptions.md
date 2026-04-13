# Monte Carlo Assumptions — Ultra-Processed Food / Palatability Ratchet

All values in $B USD (annualized). Every parameter traces to paper §4–§5
or the citations in `data_sources.md`. Run `python mc_simulation.py` to
reproduce bit-identical results.

---

## Simulation Parameters

| Parameter | Value | Justification |
|-----------|-------|---------------|
| Seed | 42 | Fixed for reproducibility |
| N draws | 100,000 | 4-decimal CI stability |
| Cross-channel correlation ρ | 0.3 | Shared macro drivers (GDP, population, regulation) |
| Private payoff Π | $293.0B/yr | Annual industry revenue — see `data_sources.md` |
| β_W median (result) | 6.24 | Confirmed by N=100,000 draws |
| ΔW median (result) | $1,829.0B/yr | Sum of channel medians (correlated) |

**Π = revenue, not profit.** SAPM Iron Law: βW = ΔW/Π where Π is annual
revenue. Using profit would inflate βW by 5–20× for low-margin industries.

---

## Channel Parameters

| Channel | Dist | Low | Mid | High | Description |
|---------|------|-----|-----|------|-------------|
| `C1_metabolic_disease` | lognormal | $880.0B | $1,100.0B | $1,320.0B | Diet-related chronic disease: obesity, T2D, CVD, cancer, mental health. Rockefel |
| `C2_addiction_behavioral` | lognormal | $100.0B | $180.0B | $280.0B | Loss of consumer sovereignty (YFAS 8-15% prevalence), weight-loss industry deadw |
| `C3_agricultural_distortion` | lognormal | $150.0B | $220.0B | $300.0B | Farm income suppression (farm share 1.3-9.7% vs 50-60% whole-food), specialty-cr |
| `C4_environmental_degradation` | lognormal | $80.0B | $140.0B | $220.0B | UPF supply chain environmental cost: 15-20% of food system's $900B environmental |
| `C5_governance_capture` | lognormal | $30.0B | $70.0B | $120.0B | Regulatory delay cost ($50B) + misallocated research/trust erosion ($20B). $178M |
| `C6_intergenerational_developmental` | lognormal | $50.0B | $100.0B | $180.0B | Childhood obesity lifetime costs ($60B), cognitive impairment from adolescent UP |


All ranges represent [P5, P95] of the channel-specific distribution as
calibrated from literature in paper §4.

---

## Impossibility Floor

The floor β_W ≥ 3.7 is the minimum ratio achievable while the industry operates.
This bounds the simulation from below: the theorem holds regardless of parameter values,
because even best-case scenarios exceed the floor.

In 100,000 draws: P(β_W < 3.7) = 0.0000%

## Sensitivity (VSL × Double-Counting Grid)

Central VSL (1.0×): no DC adj β_W = 6.18 | 20% DC adj = 4.94 | 40% DC adj = 3.71

See `mc_results.json` → `sensitivity_matrix` for full 5×5 grid.

## Distribution Robustness

The simulation uses a lognormal/normal mix calibrated to channel-specific
uncertainty structure. Results are robust: the central β_W changes by less
than ±0.3 under all-lognormal or all-normal configurations.

---

## Plausibility Checks (SAPM IL#28)

- **Annual flow**: All W_i are $/yr flows ✓
- **GDP bound**: ΔW = $1,829B = 1.7% of world GDP ($106T) ✓
- **β_W range**: 6.24 is within the [0.5, 100] plausible range ✓
- **P(β_W < 1)**: 0.0000% ✓
