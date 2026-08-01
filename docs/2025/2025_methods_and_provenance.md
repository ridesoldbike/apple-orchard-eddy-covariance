# 2025 processing methods and provenance

## Scope

The 2025 workflow processes half-hourly net ecosystem exchange (NEE) from the low-density and moderate-density apple orchards. Environmental drivers are based primarily on the LD tower biomet record, with Grant Enviroweather used as a fallback. The predefined footprint-sector exclusion is applied only to the LD orchard.

## EddyPro input

- EddyPro spike tolerance: 10%
- Full-output CSV files are discovered recursively in the LD and MD raw-data folders.
- LD tower biomet files are discovered recursively in the LD raw-data folder.
- NEE is calculated as turbulent CO2 flux plus storage when storage is available; otherwise turbulent CO2 flux is used.
- Sentinel values are converted to missing values before analysis.

## Screening

The recovered 2025 workflow applies:

1. LD footprint exclusion outside the retained 90-315 degree sector; MD receives no sector exclusion.
2. EddyPro quality-control removal for `qc_co2_flux >= 3`.
3. The 2025 positive physical limit and winter nighttime screening.
4. Large-negative, isolated-spike, and low-light/low-u* negative-artifact rules.
5. Completed positive and negative manual decisions, which override the automatic decision for matching timestamps.

The script verifies the recovered screening outcome against the preserved May 2025 counts and stops if those counts differ.

## Environmental drivers

Tower biomet measurements are used as the primary driver source. Grant Enviroweather data are used as fallback values when tower drivers are missing. The 2025 soil-probe quality-control exclusions retained in the working script are preserved in the publication copy.

## REddyProc

The final screened half-hour tables are passed to REddyProc for u* scenario estimation, marginal distribution sampling gap filling, and nighttime flux partitioning into GPP and ecosystem respiration (Reco). The primary reported scenario is U50.

## Growing season

The 2025 growing season is April 15 through October 31, inclusive (200 days).

## Provenance note

The publication copy is derived from `2025_EC_10_Outputs_Compare_VERIFY_v2.Rmd`, the reconstruction that recovered the preserved 2025 automatic and final screening counts. Computer-specific paths were replaced with repository-relative paths. Two nonfunctional diagnostic scratch lines were corrected, and run settings plus R session information are now saved with the processed outputs.
