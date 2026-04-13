# Data Sources — Ultra-Processed Food Monte Carlo Simulation

Channel parameters in `mc_simulation.py` trace to the sources listed here.
The paper (Ultra-Processed Food: Palatability Ratchet) is available on SSRN and contains the full
reference list and §4 calibration narrative.

---

## Channel Sources

### `C1_metabolic_disease`

Diet-related chronic disease: obesity, T2D, CVD, cancer, mental health. Rockefeller Foundation $1.1T base × 25% UPF PAF. Hall et al. 2019 RCT: 500 kcal/day overconsumption. Sources: Rockefeller Foundation 2021, Lane et al. 2024, UK Parliamentary PAF.

*Full citations: paper §4 (available SSRN).*

### `C2_addiction_behavioral`

Loss of consumer sovereignty (YFAS 8-15% prevalence), weight-loss industry deadweight ($72B×0.40), child marketing welfare cost ($20B). Bliss-point optimization hijacks dopaminergic reward. Sources: Gearhardt et al. 2023, FTC.

*Full citations: paper §4 (available SSRN).*

### `C3_agricultural_distortion`

Farm income suppression (farm share 1.3-9.7% vs 50-60% whole-food), specialty-crop price distortion (40% inflation), ABCD oligopoly rents. Sources: USDA ERS, Hendrickson et al. 2020.

*Full citations: paper §4 (available SSRN).*

### `C4_environmental_degradation`

UPF supply chain environmental cost: 15-20% of food system's $900B environmental externalities. Commodity-crop monoculture, GHG, water, biodiversity. Sources: Rockefeller Foundation 2021, UNEP.

*Full citations: paper §4 (available SSRN).*

### `C5_governance_capture`

Regulatory delay cost ($50B) + misallocated research/trust erosion ($20B). $178M/yr agribusiness lobbying, 95% COI on DGAC, revolving door. Sources: OpenSecrets, DGAC conflict analysis, Chile/Mexico regulatory counterfactual.

*Full citations: paper §4 (available SSRN).*

### `C6_intergenerational_developmental`

Childhood obesity lifetime costs ($60B), cognitive impairment from adolescent UPF ($25B, Gonçalves et al. 2023), taste-preference lock-in ($15B). Sources: World Obesity Federation, ELSA-Brasil cohort.

*Full citations: paper §4 (available SSRN).*

---

## Industry Revenue (Π)

The private payoff Π = $293.0B/yr is global annual industry revenue.
Source: paper §2 and §4. See paper §DA-1 (Decision Audit Field 7) for full
revenue source documentation.

---

## SAPM Framework

- Postnieks, E. (2026). *The Private Pareto Theorem*. SAPM Foundation Paper. SSRN.
- Postnieks, E. (2026). *Ultra-Processed Food (Palatability Ratchet)*. SAPM Working Paper. SSRN.

---

## Distribution Methodology

- Iman, R. L., & Conover, W. J. (1982). A distribution-free approach to
  inducing rank correlation among input variables. *Communications in
  Statistics — Simulation and Computation*, 11(3), 311–334.
- Cooke, R. M. (1991). *Experts in Uncertainty*. Oxford University Press.
