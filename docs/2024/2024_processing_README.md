# 2024 eddy-covariance processing

This folder documents the authoritative 2024 processing workflow for the low-density (LD) and moderate-density (MD) apple orchards. EddyPro outputs were generated with a 10% spike-tolerance setting and then screened, manually reviewed, gap-filled, and partitioned with REddyProc.

## Main script

Run `scripts/processing/02_process_ec_2024.Rmd` from within the repository. The script uses `here::here()` and therefore does not contain computer-specific absolute paths.

## Required inputs

Place these items under `data/raw/2024/`:

- `Low-density_10spike_2024/` with the three seasonal EddyPro folders used by the script
- `Moderate-density_10spike_2024/` with the three seasonal EddyPro folders used by the script
- `2024_biomet.csv`
- `envwx_2024.csv`

Place the completed review folders under `data/manual_review/2024/`:

- `HighPositiveReview_2024/HighPositiveReview_manual_decisions_TEMPLATE_2024.csv`
- `LargeNegativeReview_2024/LargeNegativeReview_manual_decisions_TEMPLATE_2024.csv`

The publication script stops with an error if either completed manual-decision file is missing. This prevents an accidental automatic-screening-only run.

## Output location

Generated files are written to `data/processed/2024/`, with `LD/`, `MD/`, and `compare/` subfolders.

## Verification targets

The completed manual-review summary should reproduce these screening counts:

| Site | Half-hours | Auto removed | Final removed | Positive remove | Negative remove | Positive keep | Negative keep |
|---|---:|---:|---:|---:|---:|---:|---:|
| LD | 17,567 | 3,478 | 3,563 | 51 | 34 | 3 | 8 |
| MD | 17,567 | 96 | 175 | 47 | 32 | 12 | 8 |

The historical U50 results were approximately:

| Site | Annual NEE | Growing-season NEE |
|---|---:|---:|
| LD | -299 | -461 |
| MD | -363 | -524 |

Units are g C m^-2. The REddyProc u* bootstrap used 100 samples and did not have a recorded fixed random seed in the historical workflow, so reruns can differ slightly while screening counts remain exact.

## Primary publication outputs

- `Daily_LD_MD_Fluxes_plus_Drivers_plus_VPD_2024_U50.csv`
- `Yearly_and_GS_flux_summary_2024_U50.csv`
- `Final_annual_GS_summary_2024_U50.csv`
- `ManualReview_effect_summary_2024.csv`
- `Results_table_2024_U50.csv`
- `LD_uStar_thresholds_2024.csv`
- `MD_uStar_thresholds_2024.csv`
- `Run_settings_2024.csv`
- `sessionInfo_2024.txt`
