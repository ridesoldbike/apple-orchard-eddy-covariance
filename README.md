# Apple Orchard Eddy-Covariance Dataset (2024–2025)

## Dataset overview

This repository contains eddy-covariance fluxes, supporting biometeorological
measurements, orchard-management information, phenological dates, harvest-carbon
estimates, and quality-control records from two conventionally managed commercial
apple orchards in western Michigan, USA. The orchards represent low-density (LD)
and moderate-density (MD) production systems and are located 2.4 km apart on
“The Ridge,” a major fruit-growing region in Michigan.

Continuous measurements used in this dataset cover 1 January 2024 through
31 December 2025. The comparison is observational and unreplicated: one orchard
represents each production system. Differences between LD and MD therefore may
reflect both orchard-system and site-specific effects and should not be interpreted
as replicated treatment effects.

Negative net ecosystem exchange (NEE) indicates net ecosystem carbon uptake, and
positive NEE indicates net carbon release to the atmosphere.

## Temporal coverage and phenology

The growing season began at grower-observed apple budburst and ended on 31 October.
The fixed end date was used because budburst is a discrete phenological event,
whereas autumn senescence is gradual and an exact end date is difficult to identify
from the flux record.

| Year | Growing-season start | Growing-season end | Duration |
|---|---|---|---:|
| 2024 | 2024-03-28 | 2024-10-31 | 218 days |
| 2025 | 2025-04-15 | 2025-10-31 | 200 days |

Seasonal summaries use the following periods:

- **NGS-1:** 1 January through the day before budburst;
- **Growing season (GS):** budburst through 31 October; and
- **NGS-2:** 1 November through 31 December.

Machine-readable phenology dates and their sources are provided in
`data/metadata/phenology_dates.csv`.

## Study sites and orchard characteristics

Both orchards are at approximately 265 m elevation and occur on
Owosso–Marlette sandy loam. The soil is approximately 65.3% sand, 23.2% silt,
and 11.5% clay, with a field capacity of 0.213 m³ m⁻³. A mixture of perennial
grasses was established in the alleys and mowed three to four times annually.
Pruned limbs were flail-mowed and left to decompose in the alleys. Neither orchard
was irrigated.

| Characteristic | Low-density orchard (LD)    | Moderate-density orchard (MD)|
|----------------|-----------------------------|------------------------------|
| Coordinates    | 43.25137329, −85.76477051   | 43.264937, −85.78726         |
| Primary training system | Central Leader     | Vertical Axis                |
| Primary tree density | 336 trees ha⁻¹        | 1,922 trees ha⁻¹             |
| Tree spacing   | 4.9 × 6.1 m                 | 1.2 × 4.25 m                 |
| Establishment years represented in footprint | 1973 and 2010 | 1973 and 2011 |
| Primary canopy height| Approximately 5.0 m   | Approximately 4.7 m; approximately 5.0 m in the older Central Leader blocks |
| Cultivars|Honeycrisp, Ida Red, McIntosh, Rome| Jonagold, Gala, Honeycrisp, Red & Golden Delicious |
| Rootstocks     |   7A   | Nic 29, G.11, M.9-337, G-935, M.7, and grafted 7A |
| Row orientation | East–west                  | North–south                  |
| Herbicide-strip width | 2.44 m               | 1.83 m                       |
| Orchard floor covered by alley grasses | 60% | 57%                          |
| Full-canopy light interception | 56%         | 50%                          |
| Urea application | 35.1 kg ha⁻¹ yr⁻¹         | 40.1 kg ha⁻¹ yr⁻¹            |
| Potash application | 101.7 kg ha⁻¹ yr⁻¹      | 130.8 kg ha⁻¹ yr⁻¹           |
| Insecticide application | 21.6 kg ha⁻¹ yr⁻¹  | 16.5 kg ha⁻¹ yr⁻¹            |
| Fungicide application | 28.1 kg ha⁻¹ yr⁻¹    | 21.4 kg ha⁻¹ yr⁻¹            |
| Herbicide application | 7.7 kg ha⁻¹ yr⁻¹     | 9.7 kg ha⁻¹ yr⁻¹             |
| Total soil combustible carbon | 1.85%        | 1.02%                        |
| Soil bulk density | 1.33 g cm⁻³              | 1.46 g cm⁻³                  |

The main MD planting comprised 88.5% of the tower footprint. The remaining 11.5%
contained older Central Leader Red Delicious and Golden Delicious blocks planted
at 538 trees ha⁻¹. Additional site, block, cultivar, soil-sampling, and management
information is provided in `data/metadata/site_metadata.csv`.

Full-canopy light interception was measured on 20 August 2024 with an LP-80
AccuPAR PAR/LAI Ceptometer. Soil carbon and bulk density were measured from
0–0.08 m composite samples collected on 27 November 2023 and analyzed by dry
combustion.

## Eddy-covariance installations

| Installation characteristic | LD | MD |
|---|---:|---:|
| Analyzer height | 7.9 m | 7.9 m |
| Approximate height above canopy | 2.9 m | 3.2 m above the primary canopy |
| Wind directions retained | 90°–315° | All directions |
| Measurement period used here | 2024-01-01 to 2025-12-31 | 2024-01-01 to 2025-12-31 |

The LD tower was located in the interior corner of an L-shaped orchard. Only
winds originating from 90° through 315° were retained to exclude substantial
non-orchard fetch to the northeast. The MD tower was centrally located in a more
uniform orchard block, and all wind directions were retained.

Both systems used:

- LI-7500DS open-path CO₂/H₂O analyzers (LI-COR Biosciences, Lincoln,
  Nebraska, USA);
- Gill WindMaster Pro sonic anemometers (Gill Instruments, Lymington,
  Hampshire, United Kingdom);
- SmartFlux 3 data-logging systems (LI-COR Biosciences);
- 10 Hz high-frequency sampling;
- 30-minute flux averaging; and
- six-month analyzer calibration intervals.

The LD system was installed on 1 January 2023 and the MD system on 1 August
2023. Both were removed on 1 March 2026. Sensor models, serial numbers, heights,
and deployment dates should be recorded in `data/metadata/sensor_metadata.csv`.

## Biometeorological measurements

Biometeorological sensors were deployed only at the LD orchard. Because the
orchards are 2.37 km apart, the LD measurements were used as meteorological
drivers for both orchards. Missing LD driver values were filled from the Michigan
Enviroweather station at Grant, Michigan; available tower measurements were not
overwritten. The processed driver tables identify the source of each half-hourly
driver value.

| Variable | Instrument | Deployment |
|---|---|---|
| Incoming shortwave radiation (Rg) | LI-200R pyranometer | LD tower |
| Net radiation (Rn) | NR Lite2 net radiometer | LD tower |
| Photosynthetically active radiation (PAR) | LI-190R quantum sensor | LD tower |
| Air temperature and relative humidity | Vaisala HUMICAP HMP155 | LD tower |
| Liquid precipitation | TR-525M tipping-bucket rain gauge | LD tower |
| Soil heat flux | Three Hukseflux HFP01 plates | 0.05 m depth |
| Soil temperature | Three LI-COR 7900-180 sensors | 0.05 m depth |
| Volumetric soil water content | Two METER Group ECH₂O EC-5 sensors | 0.05 m depth |

The soil sensors represented grassy alley, beneath-tree, and between-tree
locations. Two locations included soil temperature, soil water content, and soil
heat flux; the third included soil temperature and soil heat flux. Implausible
soil-sensor observations were removed by manual quality control, and the remaining
sensors were averaged to represent heterogeneous orchard-floor conditions.

## EddyPro processing

Raw 10 Hz eddy-covariance data were processed with EddyPro version 7.0.9
(LI-COR Biosciences). Processing included:

- 30-minute averaging;
- planar-fit coordinate rotation;
- Webb–Pearman–Leuning density corrections;
- low- and high-frequency spectral corrections;
- automatic time-lag compensation by covariance maximization;
- statistical quality tests implemented by EddyPro; and
- high-frequency despiking with a 10% spike-detection threshold.

Planar-fit coordinate rotation used terrain-specific sectors with a minimum of
30 records per sector:

| Orchard | Sector | Terrain characteristic |
|---|---:|---|
| LD | 315°–90° (crossing north) | Downhill grassy field |
| LD | 90°–270° | South-slope orchard |
| LD | 270°–315° | West-slope orchard |
| MD | 0°–135° | Northeast upslope |
| MD | 135°–270° | Flat terrain |
| MD | 270°–360° | West downslope |

These planar-fit sectors describe the coordinate-rotation configuration. They
are distinct from the subsequent LD fetch filter, which retained only fluxes
with wind directions from 90° through 315°.

Net ecosystem exchange was calculated at the half-hourly scale as the sum of the
turbulent CO₂ flux and the measured CO₂ storage flux. When storage flux was
unavailable, turbulent CO₂ flux alone was used.

## Quality control and preprocessing

Processing and statistical analysis were conducted in R version 4.4.0. EddyPro
tables were imported into R, timestamps were aligned to exact 30-minute intervals,
duplicate records were collapsed to one observation per interval, and instrument
sentinel values were converted to `NA`.

Nighttime was defined as incoming shortwave radiation below 10 W m⁻².
Transition-light periods were defined as 10 ≤ Rg < 50 W m⁻².

### Automatic NEE screening

| Screen | Rule |
|---|---|
| EddyPro quality control | Exclude CO₂-flux QC flags ≥ 3 |
| LD fetch | Exclude wind directions outside 90°–315° |
| Extreme positive flux | Exclude NEE > +150 µmol CO₂ m⁻² s⁻¹ |
| Winter stable-condition artifact | Exclude winter nighttime NEE < −5 µmol CO₂ m⁻² s⁻¹ when u\* < 0.10 m s⁻¹ |
| Extreme negative artifact | Exclude NEE < −120 µmol CO₂ m⁻² s⁻¹ when Rg < 100 W m⁻² or u\* < 0.25 m s⁻¹ |

The final harmonized positive-flux cap is +150 µmol CO₂ m⁻² s⁻¹ for both years.
An earlier 2025 workflow and an earlier draft of supplemental Table S3 listed
+80 µmol CO₂ m⁻² s⁻¹. That setting is superseded by the final +150 cap and the
documented supplemental review described below.

A sensitivity analysis compared the selected extreme-negative screen with a more
permissive rule (NEE < −150 µmol CO₂ m⁻² s⁻¹, Rg < 50 W m⁻², and
u\* < 0.20 m s⁻¹). Differences in annual and growing-season NEE were less than
10 g C m⁻².

### Manual NEE review

Four classes of observations received manual review:

1. high-positive fluxes;
2. large-negative fluxes;
3. winter nighttime negative fluxes; and
4. winter nighttime positive fluxes.

| Review category | Candidate rule |
|---|---|
| High-positive nighttime flux | NEE > +50 µmol CO₂ m⁻² s⁻¹ at night |
| Winter nighttime positive flux | NEE > +12 µmol CO₂ m⁻² s⁻¹ during winter nighttime |
| Large-negative daytime flux | NEE < −50 µmol CO₂ m⁻² s⁻¹ during growing-season daytime |
| Large-negative transition-light flux | NEE < −30 µmol CO₂ m⁻² s⁻¹ when 10 ≤ Rg < 50 W m⁻² |
| Large-negative nighttime flux | NEE < −10 µmol CO₂ m⁻² s⁻¹ when Rg < 10 W m⁻² |
| Winter nighttime negative flux | Remaining NEE < −5 µmol CO₂ m⁻² s⁻¹ during winter nighttime |

Winter-negative candidates included nighttime observations below
−5 µmol CO₂ m⁻² s⁻¹ that remained after automatic screening. Winter-positive
candidates included retained winter nighttime observations above
+12 µmol CO₂ m⁻² s⁻¹.

Each candidate was displayed in a six-hour contextual diagnostic extending three
hours before and three hours after the flagged half-hour. The diagnostics included
NEE, Rg, friction velocity (u\*), signal strength, EddyPro CO₂-flux quality flag,
wind direction, and air temperature. Decisions considered seasonality, radiation,
turbulence, adjacent observations, abrupt sign reversals, oscillatory behavior,
and isolated or unstable spikes. Coherent daytime assimilation and nighttime
respiration events were retained. Every candidate received an explicit `keep` or
`remove` decision before gap filling and partitioning.

To harmonize the 2025 positive-flux cap with the +150 µmol CO₂ m⁻² s⁻¹ cap used
in 2024, nine additional 2025 observations between +80 and +150 µmol CO₂ m⁻² s⁻¹
were reviewed. All nine were classified as artifacts and removed. Consequently,
harmonizing the positive cap did not change the final screened 2025 NEE inputs.

Completed decision files in `data/manual_review/<year>/` are permanent processing
inputs and are not overwritten by publication-processing runs. Recreated candidate
lists, plot indexes, and contextual PDFs are written to
`data/processed/<year>/manual_review_diagnostics/`.

## Gap filling, partitioning, and uncertainty

The REddyProc package was used for friction-velocity filtering, gap filling, and
flux partitioning. Missing NEE was gap-filled with marginal distribution sampling
(MDS). NEE was partitioned into gross primary productivity (GPP) and ecosystem
respiration (Reco) using the nighttime method of Reichstein et al. (2005).

Annual u\* thresholds were estimated with the bootstrapped moving-point method
using 100 bootstrap samples. Threshold scenarios were retained at the 5th, 50th,
and 95th percentiles (U05, U50, and U95). A single annual threshold was applied
throughout each site-year. The median U50 scenario is the reported scenario.
Scenario-specific threshold and flux files are stored under
`data/processed/<year>/<site>/`; exact filenames and processing provenance are
listed in `data/metadata/processing_history.md`.

| Year | Orchard | U05 (m s⁻¹) | U50 (m s⁻¹) | U95 (m s⁻¹) |
|---|---|---:|---:|---:|
| 2024 | LD | 0.198 | 0.229 | 0.293 |
| 2024 | MD | 0.161 | 0.214 | 0.256 |
| 2025 | LD | 0.197 | 0.232 | 0.339 |
| 2025 | MD | 0.176 | 0.216 | 0.336 |

Random-number seeds were fixed by year and orchard to make REddyProc bootstrap
uncertainty estimates reproducible across runs. The LD seed was the study year,
and the MD seed was the study year plus 1,000. The seeds were therefore 2024 and
3024 for LD and MD in 2024 and 2025 and 3025 for LD and MD in 2025.

Daily NEE, GPP, and Reco values were retained only when at least 70% of the
expected 48 half-hourly intervals were available. Daily mean radiation was
retained only when at least 75% of expected observations were available.

Uncertainty in annual and growing-season NEE combined EddyPro random measurement
error with structural uncertainty associated with the u\* threshold. The latter
was quantified from variation among U05, U50, and U95 NEE estimates. Total NEE
uncertainty was calculated as the root sum of squares of the component standard
deviations.

The final U50 NEE products and gap-filled fractions were:

| Year | Orchard | Period | Days | NEE (g C m⁻²) | Total SD (g C m⁻²) | Gap-filled |
|---|---|---|---:|---:|---:|---:|
| 2024 | LD | Full year | 366 | −320 | 14 | 41% |
| 2024 | LD | Growing season | 218 | −462 | 12 | 34% |
| 2024 | MD | Full year | 366 | −365 | 15 | 11% |
| 2024 | MD | Growing season | 218 | −523 | 12 | 9% |
| 2025 | LD | Full year | 365 | −312 | 13 | 37% |
| 2025 | LD | Growing season | 200 | −505 | 11 | 38% |
| 2025 | MD | Full year | 365 | −485 | 12 | 13% |
| 2025 | MD | Growing season | 200 | −590 | 11 | 4% |

## Aggregation and statistical comparisons

Half-hourly fluxes were converted to daily totals and reported in
g C m⁻² d⁻¹. Period totals are reported in g C m⁻². Annual, NGS-1, growing-season,
and NGS-2 totals were calculated by summing daily values within each period.

Daily NEE, GPP, and Reco were compared between orchards using matched dates with
valid observations at both sites. Analyses were conducted separately by year and
period. Paired differences were calculated as MD minus LD and evaluated with
two-sided paired t-tests at α = 0.05. Annual cumulative NEE and NECB are single
orchard-level estimates and were not themselves subjected to statistical testing.
Because only one orchard represented each system, inference is limited to these
sites.

## Energy-balance closure

Energy-balance closure was evaluated by regressing turbulent energy fluxes
(H + LE) against available energy (Rn − G₀), where H is sensible heat flux, LE is
latent heat flux, Rn is net radiation, and G₀ is surface ground heat flux corrected
for heat storage above the 0.05 m soil heat-flux plates:

- `G₀ = Gplate + Gstorage`
- `available energy = Rn − G₀`
- `turbulent energy = H + LE`

Volumetric heat capacity used the measured LD soil bulk density of
1.33 g cm⁻³, assumed constant during the study. Closure was evaluated for daytime
observations with Rg > 10 W m⁻² and for midday growing-season observations from
11:00 through 15:00 with Rg > 300 W m⁻². Energy-balance closure was diagnostic
only; no energy-balance correction was applied to CO₂ fluxes.

| Year | Window | n | Slope | Intercept (W m⁻²) | r² |
|---|---|---:|---:|---:|---:|
| 2024 | Daytime | 6,628 | 0.79 | 26.2 | 0.82 |
| 2024 | Midday growing season | 1,615 | 0.69 | 69.7 | 0.62 |
| 2025 | Daytime | 5,962 | 0.88 | 25.5 | 0.83 |
| 2025 | Midday growing season | 1,460 | 0.75 | 83.5 | 0.65 |

## Harvest carbon and net ecosystem carbon balance

NEE and net ecosystem carbon balance (NECB) are not interchangeable. NEE
represents atmosphere–ecosystem CO₂ exchange, whereas NECB also accounts for
carbon exported from the orchard in harvested fruit.

With the NEE sign convention used here, annual NECB was calculated as:

`NECB = annual NEE + harvested-fruit carbon export`

Harvested-fruit carbon export is entered as a positive quantity. Negative NECB
therefore indicates that the orchard retained more carbon than was exported in
harvested fruit.

Grower records supplied annual yield in apple bushels for the blocks represented
within each flux footprint. Yield was scaled by the relevant footprint area and
converted using 42 lb bushel⁻¹. For 2024, wet fruit mass was converted to dry mass
using a dry-matter fraction of 0.14. Dry mass was converted to carbon using a
carbon fraction of 0.4036.

For 2025, the dry-matter fraction was measured directly from a
cultivar-weighted apple sample collected one week before harvest. Sampled trees
were selected randomly, and fruit were distributed among canopy heights and
interior/exterior positions. Apples were weighed fresh, diced, dried at 60 °C
until mass was stable over a six-hour interval, and reweighed. Cultivar-specific
dry-matter fractions were weighted by cultivar contribution to the tower
footprint.

The 2025 dry-matter dataset contained 82 apples. Cultivar means ranged from
13.9% for McIntosh to 18.8% for Jonagold, and the overall sample mean was 16.4%.

Dropped and unharvested fruit remained within the orchard and were not treated as
harvested carbon export. In 2025, preharvest and postharvest fruit counts were
used to characterize the fraction of fruit left in each orchard. Honeycrisp was
excluded from orchard-level percentage summaries because frost damage and
incomplete preharvest and postharvest records prevented a comparable estimate.
These measurements describe an important sampling limitation and source of
uncertainty in harvest-carbon accounting.

## Growing-season environmental summary

Environmental summaries were calculated for dates with concurrent daily NEE
estimates from both orchards. Growing-season NEE in this table is the sum of the
daily mean of LD and MD NEE on those paired dates and therefore is not an
orchard-specific total.

| Year | GS length (d) | Paired-date GS NEE (g C m⁻²) | Σ daily Rg (W m⁻²) | Mean Tair (°C) | Days >30 °C | Mean soil temperature (°C) | Precipitation (mm) | Mean SWC (m³ m⁻³) |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 2024 | 218 | −492 | 46,691 | 16.4 | 6 | 14.9 | 351 | 0.245 |
| 2025 | 200 | −553 | 42,549 | 17.0 | 21 | 16.7 | 439 | 0.212 |

Soil temperature and soil water content were measured at LD.

## Soil-sensor exclusions

Abnormal soil-probe readings were excluded before sensor aggregation. The
machine-readable exclusion record should be maintained in
`data/metadata/quality_control_flags.csv`.

| Probe | Excluded interval(s) |
|---|---|
| `TS_2_1_1` | 2025-08-02 through 2025-12-31 |
| `TS_3_1_1` | 2024-01-01 through 2024-04-09; 2024-06-01 through 2024-07-16 |
| `SWC_1_1_1` | All of 2024; 2025-05-11 through 2025-12-31 |
| `SWC_2_1_1` | 2024-01-01 through 2024-04-08; 2024-05-26 through 2024-08-12 |
| `SHF_1_1_1` | 2024-03-01 through 2024-04-12; 2025-10-13 through 2025-12-31 |
| `SHF_2_1_1` | 2025-05-15 through 2025-12-31 |
| `SHF_3_1_1` | All of 2025 |

## Repository organization

| Path | Contents |
|---|---|
| `README.md` | Dataset overview, methods summary, and reuse guidance |
| `data/raw/` | Local raw EddyPro and environmental inputs, if distributed |
| `data/intermediate/` | Reproducible intermediate products, when retained |
| `data/manual_review/` | Permanent completed `keep`/`remove` decision files |
| `data/processed/` | QC-filtered, gap-filled, partitioned, and summarized data |
| `data/metadata/` | Site, sensor, variable, phenology, and QC metadata |
| `scripts/processing/` | Annual flux-processing workflows |
| `scripts/tables/` | Manuscript-table generation |
| `scripts/publication/` | Publication figures and statistical analyses |
| `figures/processing_diagnostics/` | Generated processing and QC figures |
| `manuscript_tables/` | Generated manuscript tables |
| `docs/` | Detailed processing history and supporting documentation |

Raw EddyPro inputs are maintained locally and are not distributed through GitHub
unless explicitly included in a release. The repository contains processing code,
completed manual-review records, metadata, and processed data products. Archived
releases should be identified by a DOI when available.

## Metadata files

Machine-readable metadata are stored in:

```text
data/metadata/
├── site_metadata.csv
├── sensor_metadata.csv
├── variable_dictionary.csv
├── phenology_dates.csv
├── quality_control_flags.csv
└── processing_history.md
```

The variable dictionary should document each exact column name, definition, unit,
temporal resolution, site applicability, missing-value code, sign convention,
source, and processing level.

## Time and missing-data conventions

R processing used the `America/Toronto` time zone, and REddyProc was configured
with a UTC−5 site offset. Distributed timestamps and the convention identifying
the beginning or end of each half-hour interval are documented in
`data/metadata/variable_dictionary.csv`. Users should consult that file before
joining these data to external records.

EddyPro sentinel values, including −9999 and related missing-value codes, were
converted to `NA`. Missing values in distributed tabular files are represented by
`NA`.

## Software and reproducibility

Primary processing was conducted with R 4.4.0 and the `REddyProc`, `dplyr`,
`readr`, `lubridate`, `purrr`, `tidyr`, `ggplot2`, `zoo`, and `here` packages.
Scripts should be run from the repository’s RStudio project so that
`here::here()` resolves paths from the repository root.

Run the annual processing scripts before running manuscript-table and
publication-figure scripts. Generated diagnostic products may be recreated, but
completed manual-review decision files under `data/manual_review/` must not be
deleted or overwritten. Package versions and the processing history should be
recorded in `data/metadata/processing_history.md` or a lockfile.

## Limitations and appropriate use

- The study is an observational, unreplicated comparison of two orchard sites.
- Environmental sensors were installed only at LD; LD tower measurements and
  Grant weather-station data supplied drivers for both orchards.
- Annual cumulative fluxes and NECB values are single orchard-level estimates.
- Gap filling, u\* filtering, flux partitioning, and modeled-data fractions add
  uncertainty to cumulative flux estimates.
- Harvest-carbon estimates depend on grower yield records, footprint scaling,
  dry-matter conversion, carbon fraction, and limited fruit sampling.
- Comparisons should not be generalized to all low- and moderate-density apple
  orchards without additional replicated studies.

## Contact

**Principal investigator:** Julianna Wilson, PhD — jkwilson@msu.edu
**Repository maintainer:** Kevin Postma, PhD — postmak2@msu.edu
**Institution:** Michigan State University

## Funding

This research was supported by Nestlé-Gerber, the Michigan Tree Fruit Commission,
and Michigan State University AgBioResearch.

## License

[Specify the data and code license, for example CC BY 4.0 for data and MIT for
code.]

## Preferred citation

[Dataset citation]

## Related publication

“citation pending”]

## Version and archival record

**Repository version:** [version]  
**Release date:** [YYYY-MM-DD]  
**DOI or Zenodo accession:** [DOI when available]

## References cited in processing

- Fratini, G., and Mauder, M. (2014). Eddy covariance software and processing
  methodology.
- Mauder, M., et al. (2013). Eddy-covariance quality assessment.
- Moncrieff, J. B., et al. (1997, 2004). Frequency-response corrections for
  eddy-covariance measurements.
- Reichstein, M., et al. (2005). MDS gap filling and nighttime flux partitioning.
- Vickers, D., and Mahrt, L. (1997). Quality control and flux-sampling problems.
- Webb, E. K., Pearman, G. I., and Leuning, R. (1980). Density corrections for
  eddy-covariance fluxes.
- Wilczak, J. M., Oncley, S. P., and Stage, S. A. (2001). Planar-fit coordinate
  rotation.
- Wutzler, T., et al. (2018). The `REddyProc` package.

Full bibliographic details are provided in the related manuscript.
