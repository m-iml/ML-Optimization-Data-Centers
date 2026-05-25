# Data

## File

`Frontier HPC & Facility Data.xlsx` (sheet `Frontier2023`)

10 minute resolution operational telemetry from the Frontier exascale supercomputer for calendar year 2023, after cleaning and time ordering.

| Property | Value |
| --- | --- |
| Records | 49,869 |
| Period | 2023-01-01 00:00 to 2023-12-31 23:50 |
| Cadence | 10 minutes |
| Missing intervals | ≈5.1% (scheduled downtime and short telemetry gaps) |
| Missing values | Only in `Overall_average_Coolant_Return_Temp` (122 entries, ≈0.24%) |

## Variables used in the paper

| Symbol | Column | Description | Typical range |
| --- | --- | --- | --- |
| `P_IT` | `Frontier Compute Power` | IT load from the supercomputer racks | 8 to 29 MW |
| `P_acc` | `Frontier Facility accessory Power` | Power for cooling infrastructure (pumps, fans, etc.) | 0.5 to 1.1 MW |
| `T_sup` | Overall coolant supply temperature | Common warm water supply | 18 to 25 °C |
| `T_r,i` | Per subloop return temperatures (i = 1, 2, 3) | One column per loop | 25 to 40 °C |
| `Q_i` | Per subloop coolant flow rates (i = 1, 2, 3) | One column per loop | Variable |
| `Q_heat` | `Overall_WasteHeat` | Total thermal power removed | 5 to 25 MW |
| `PUE` | `Power Usage Effectiveness` | Total Power / Compute Power | 1.03 to 1.10 |

Additional derived features used in the surrogate (per loop ΔT, per loop heat, total flow, imbalance index, lagged values and rolling means, K-Means regime label) are computed at runtime by the `build_features()` function in `notebooks/02_surrogate_excess_counterfactual.ipynb`.

## Source

The dataset is published openly by Oak Ridge National Laboratory:

> Grant, D. et al. *Frontier HPC & Facility Data*. figshare (2024).
> [doi:10.6084/m9.figshare.24391240.v4](https://doi.org/10.6084/m9.figshare.24391240.v4)

It accompanies the *Scientific Data* article:

> Sun, J., Gao, Z., Grant, D. et al. Energy dataset of frontier supercomputer for waste heat recovery. *Sci Data* **11**, 1077 (2024). https://doi.org/10.1038/s41597-024-03913-w

A copy is included here for convenience and reproducibility. If you build on the data itself rather than this paper, please cite Sun et al. and Grant et al. directly.

## License

The Frontier HPC & Facility Data is redistributed under the same Creative Commons license used by the figshare deposit (CC BY 4.0 at time of writing; check the figshare record for the canonical, up to date terms). Attribution should go to the original authors and to Oak Ridge National Laboratory.
