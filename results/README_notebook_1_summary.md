## Notebook 1 — Well-log data loading and quality control

This notebook checks whether the well-log measurements are reliable enough to
interpret before calculating shale volume, porosity or water saturation.

The workflow preserves the raw LAS data, checks depth continuity, records the
coverage and missing gaps of every curve, validates units, screens unusual
values, compares caliper with bit size, evaluates density reliability using
DRHO and borehole condition, reviews density–neutron behaviour, and identifies
duplicated resistivity curves.

### Main QC results

- Raw rows preserved: 34,861
- Curves/columns loaded: 21
- Rows with GR, RHOB, NPHI and RT: 10,018
- Rows passing the interpretation-ready screen: 10,007
- Interpretation-ready depth range: 2605.0–3606.7 m

### Important rule

A QC flag does not automatically mean that a measurement is wrong. It means
that the value needs additional review. Likewise, passing QC does not prove a
gas, oil or lithology interpretation. Those decisions are made in the later
formation-evaluation notebook using several curves and geological context.

No raw measurements were deleted. All warnings remain attached to the data so
that the workflow is transparent and auditable.
