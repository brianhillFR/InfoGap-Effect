# Info Gap Effect

This repository contains the raw survey CSV, data-preparation code, and analysis code needed to reproduce the Info Gap Effect analysis.

## Files

- `Info-Gap_effect-data.csv`: raw survey export used to construct the analysis dataset.
- `Prepare-dataset_ENG.Rmd`: cleans `Info-Gap_effect-data.csv` and writes `dataset_ENG.rds`.
- `Info-Gap-Effect.Rmd`: runs the analysis using `dataset_ENG.rds`.

The supplementary CEO-pay figure also uses the CSV files in `data/` and `issp_social_inequality_2019/outputs/`.

## From Raw CSV To `dataset_ENG.rds`

From the repository root, render the preparation file:

```r
rmarkdown::render("Prepare-dataset_ENG.Rmd")
```

This reads `Info-Gap_effect-data.csv`, removes incomplete/ineligible observations, harmonizes the inequality and emissions task variables, constructs WTP variables, creates socio-demographic and attitude variables, selects the analysis columns, and saves the result as:

```text
dataset_ENG.rds
```

## Run The Analysis

After `dataset_ENG.rds` has been created, render:

```r
rmarkdown::render("Info-Gap-Effect.Rmd")
```

Generated figures and tables are written under:

- `overleaf/halo_attitudes/figures/`
- `overleaf/halo_attitudes/tables/`

These output folders are included with placeholder files so the directory structure is present before rendering.
