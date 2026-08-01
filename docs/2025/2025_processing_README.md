# 2025 eddy-covariance processing

This folder documents the recovered and verified 2025 processing workflow for the low-density (LD) and moderate-density (MD) apple orchards. EddyPro outputs were generated with a 10% spike-tolerance setting and then screened, manually reviewed, gap-filled, and partitioned with REddyProc.

## Main script

Run `scripts/processing/03_process_ec_2025.Rmd` from within the repository. The script uses `here::here()` and contains no computer-specific absolute paths.

## Required inputs

Place these items under `data/raw/2025/`:

- `low-density_10spike/` containing the LD EddyPro full-output files and the tower biomet CSV files
- `moderate-density_10spike/` containing the MD EddyPro full-output files
- `envwx_2025.csv`

The script discovers all `full_output` CSV files recursively within each orchard folder. It also discovers the half-hourly biomet CSV files recursively within `low-density_10spike/` and excludes files whose names contain `biomet_daily`.

Place the completed review folders under `data/manual_review/2025/`:

- `HighPositiveReview_2025/HighPositiveReview_manual_decisions_TEMPLATE_2025.csv`
- `LargeNegativeReview_2025/LargeNegativeReview_manual_decisions_TEMPLATE_2025.csv`

The publication script stops with an error if either completed manual-decision file is missing. It also stops if the final screening counts do not reproduce the preserved 2025 workflow.

## Output location

Generated files are written to `data/processed/2025/`, with `LD/`, `MD/`, and `compare/` subfolders.

## Verification targets

The completed manual-review summary should reproduce these counts:

| Site | Half-hours | Auto removed | Final removed | Positive remove | Negative remove | Positive keep | Negative keep |
|---|---:|---:|---:|---:|---:|---:|---:|
| LD | 17,519 | 4,360 | 4,420 | 36 | 24 | 7 | 9 |
| MD | 17,519 | 66 | 92 | 11 | 15 | 14 | 0 |

A verified reference run produced approximately:

| Site | Annual NEE | Growing-season NEE | Annual GPP | Growing-season GPP | Annual Reco | Growing-season Reco |
|---|---:|---:|---:|---:|---:|---:|
| LD | -313 | -519 | 1,876 | 1,738 | 1,563 | 1,219 |
| MD | -481 | -588 | 2,146 | 1,977 | 1,666 | 1,389 |

Units are g C m^-2. The REddyProc u* procedure uses 100 bootstrap samples and the historical workflow did not record a fixed random seed, so rerun flux totals can differ modestly while the screening counts remain exact.

## Primary publication outputs

- `Daily_LD_MD_Fluxes_plus_Drivers_plus_VPD_2025_U50.csv`
- `Yearly_and_GS_flux_summary_2025_U50.csv`
- `Final_annual_GS_summary_2025_U50.csv`
- `ManualReview_effect_summary_2025.csv`
- `Results_table_2025_U50.csv`
- `LD_uStar_thresholds_2025.csv`
- `MD_uStar_thresholds_2025.csv`
- `Verification_screening_counts_2025.csv`
- `Run_settings_2025.csv`
- `sessionInfo_2025.txt`
