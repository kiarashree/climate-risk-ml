# Data

This folder contains processed/model-ready datasets and representative samples used in the project.

## Included processed datasets
- `clean_ff3.csv` — cleaned Fama-French factors.
- `clean_momentum.csv` — cleaned momentum factor.
- `clean_monthly_panel.csv` — model-ready monthly panel.
- `clean_quarterly_panel.csv` — processed quarterly panel.

## Sample datasets
The complete firm-level datasets are substantially larger, so reproducible 1,000-row samples are provided:
- `sample/clean_firmyear_sample.csv`
- `sample/clean_firmquarter_sample.csv`

Samples were drawn with `random_state=42`.

The full raw/source datasets are not redistributed in this repository due to file-size and redistribution considerations.
