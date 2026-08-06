## Notebook 2 — Formation evaluation

This notebook takes Notebook 1's QC output and asks a different question: after QC, what parts of well 15/9-F-1 appear clean, porous, water-bearing, or
potentially hydrocarbon-bearing? 

It carries that question all the way through:
from confirming a defensible interpretation interval, through shale volume,
porosity, and water saturation, to interpretation flags, thickness and net-pay
summaries, cutoff and matrix-density sensitivity checks, a composite log panel,and exported results.

The workflow chooses a 2,770.0–3,270.0 m interpretation interval from log
character (GR drop, RT rise, complete RHOB/NPHI coverage), flags a Clean/Shalier split at 3,105.0 m for geological description and reporting, computes shale volume (VSH) from a gamma-ray index, density porosity (PHID) and effective porosity (PHIE) under a quartz matrix-density assumption (2.65 g/cm3, with 2.68/2.71 carried throughout as an explicit sensitivity range), and calculates water saturation with Archie's equation where VSH ≤ 0.5 and the Simandoux shaly-sand equation where VSH > 0.5 — selected per row, not by zone. 

Cutoffs are applied to build SAND_FLAG, RESERVOIR_FLAG, and POSSIBLE_PAY_FLAG, and the results are summarised by thickness, tested against three cutoff scenarios and three matrix-density candidates, and shown on a six-track composite log panel.

### Main results (Base-case cutoffs: VSH ≤ 0.5, PHIE ≥ 0.05, SW ≤ 0.5)

- Interpretation interval evaluated: 2,770.0–3,270.0 m (5,001 rows)
- Clean zone / Shalier zone gross thickness: 335.0 m / 165.0 m
- Rows passing SAND_FLAG (VSH ≤ 0.5): 3,616 of 5,001 (72.3%)
- Rows passing RESERVOIR_FLAG (+ PHIE ≥ 0.05): 1,580 of 5,001 (31.6%)
- Rows passing POSSIBLE_PAY_FLAG (+ SW ≤ 0.5, valid Sw model): 114 of 5,001 (2.3%)

- **Possible net pay: 11.4 m**, all within the Clean zone, across 4 depth
  clusters (Archie-modelled throughout)

- Cutoff-scenario range: 1.1 m (Conservative) – 11.4 m (Base) – 33.7 m (Optimistic)

- Matrix-density-alone range (Base cutoffs, 2.65/2.68/2.71): 11.4–40.9 m

- Rw = 0.0085 ohm·m, Rsh = 2.244 ohm·m, both derived from this well's own logs

### Lithology note

PEF, RHOB-PEF, and density-neutron evidence all show the Clean zone sitting off the pure-quartz reference and closest to the Limestone line. This is consistent with a calcareous or glauconitic sandstone. it matches the published regional description of the Hugin Formation. 

However the logs alone cannot confirm matrix mineralogy. Additionally the cross-plots share the density-tool measurements and assumptions, hence not fully independent of each other.

### Exported files

- `formation_evaluation_results.csv` — full interpretation-interval dataframe
  (5,001 rows, 22 columns), including VSH, PHID, PHIE, SW, SW_MODEL,
  SW_MODEL_VALID, and all flags

- `interval_summary.csv` — thickness/net-pay summary by zone and combined

- `uncertainty_scenarios.csv` — cutoff-scenario and matrix-density sensitivity
  tables, with the underlying assumption values as explicit columns

- `possible_pay_zones.csv` — the possible-pay depth clusters only, with
  per-cluster VSH/PHIE/SW/RT statistics

### Important rule

This interval is log-defined and not a confirmed formation interval. The formation tops were not integrated. All figures above describe what the logs
are *consistent with*, not confirmed hydrocarbon pay.

There is no pressure data, fluid-contact evidence, core calibration, or production-test evidence in this project. 

The possible-pay estimate is sensitive to the matrix-density, Rw, and VSH/PHIE/SW cutoff assumptions. All of these are shown as sensitivity ranges.