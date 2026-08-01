# 2024 processing methods and provenance

## Scope

The 2024 workflow processes half-hourly net ecosystem exchange (NEE) from low-density and moderate-density apple orchards. The two sites share the same environmental driver layer, while the LD site additionally receives the predefined footprint-sector exclusion.

## EddyPro input

- EddyPro spike tolerance: 10%
- Three seasonal full-output files are combined for each orchard.
- NEE is calculated as turbulent CO2 flux plus storage when storage is available; otherwise turbulent CO2 flux is used.
- Sentinel values are converted to missing values before analysis.

## Screening

The script applies:

1. LD footprint exclusion outside the retained 90-315 degree sector.
2. EddyPro quality-control removal for `qc_co2_flux >= 3`.
3. Global physical bounds and winter nighttime screening.
4. Large-negative, isolated-spike, and low-light/low-u* negative-artifact rules.
5. Completed manual positive and negative decisions, which override the automatic decision for matching timestamps.

## Environmental drivers

Tower biomet measurements are used as the primary driver source. Grant Enviroweather data are used as fallback values when tower drivers are missing. Enviroweather is joined to the half-hour driver layer rather than modifying the raw EddyPro files.

## REddyProc

The final screened half-hour table is passed to REddyProc for u* scenario estimation, marginal distribution sampling gap filling, and nighttime flux partitioning into GPP and ecosystem respiration (Reco). The reported primary scenario is U50.

## Growing season

The 2024 growing season is March 28 through October 31, inclusive (218 days).

## Provenance note

The publication copy preserves the confirmed analytical logic while replacing computer-specific paths with repository-relative paths and removing a nonfunctional scratch block at the end of the working script. The completed manual-decision CSV files are required companion data.
