# Spatial synchrony in the breeding traits of Scottish blue tits

Code accompanying the Senior Honours Project dissertation by Alexander Hobbs (University of Edinburgh, 2026): *Spatial synchrony in the breeding traits of Scottish blue tits*.

## Overview

This repository contains the R Markdown scripts used to quantify spatial
synchrony in blue tit (*Cyanistes caeruleus*) breeding traits — lay
date, clutch size, and fledgling success across a 220 km Phenoweb
transect in Scotland (2014–2025). Analyses include intraclass correlation
coefficients (ICCs) from linear mixed-effects models, Gaussian spatial
autocorrelation models for distance-decay (following Engen et al. 2005;
Vriend et al. 2022), and weather-variable analyses.

All of the code present was adapted from within the RMD files created to complete this project - some aspects were directly provided by Sanjana Ravindran.

## Scripts

The scripts run in numerical order, with each script's outputs feeding
the next:

| # | Script | Purpose |
|---|---|---|
| 01 | `01_data_cleaning.Rmd` | Apply exclusion criteria from Methods 2.2 (TOM site, 2020 lay date, clutch swap experiment, duplicate clutches, clutches > 16 eggs). |
| 02 | `02_data_summary.Rmd` | Reports overall and trait-specific sample sizes and completeness statistics. |
| 03 | `03_pairwise_distances.Rmd` | Computes great-circle pairwise distances between all sites (Haversine formula). Produces Appendix Figure 6. |
| 04 | `04_results_synchrony_iccs.Rmd` | Fits LMMs and computes ICCs. Reproduces Tables 1–2 and Figures 2–3. |
| 05 | `05_results_distance_decay.Rmd` | Fits Gaussian spatial autocorrelation models. Reproduces Table 3 and Figure 4. |
| 06 | `06_results_weather_drivers.Rmd` | Tests weather (mean spring temperature and precipitation) as drivers of lay-date synchrony. Reproduces Table 4. |

The `checks/` subfolder contains diagnostic / sensitivity scripts:

- `checks/2020_exclusion_check.Rmd` — quantifies the 2020 lay-date data
  gap and refits cascade models with vs without 2020 to confirm the
  exclusion has negligible impact.

## Data

Raw data is held by the University of
Edinburgh and is not publicly redistributed here. The repository contains analysis code only. See `data/README.md` for the list of files each
script expects. For data access, contact the Biological sciences department of the Univeristy of Edinburgh

## Requirements

- R 4.4.2 or later
- R packages used across the scripts: `tidyverse`, `lme4`, `lmerTest`,
  `lmeresampler`, `broom.mixed`, `broom`, `ncf`, `mvtnorm`, `matrixStats`,
  `geosphere`, `corrr`, `reshape2`, `progress`, `patchwork`, `scales`,
  `ggforce`, `viridis`, `knitr`, `kableExtra`

## Reproducibility

- All parametric bootstraps use `B = 5000` replicates.
- A random seed (`set.seed(42)`) is set at the top of each bootstrap
  chunk, so re-running these scripts on the same data produces the
  exact values reported in the dissertation.
- Bootstrap results are cached as `.rds` files (`icc_boot_results.rds`,
  `t2_boot_results.rds`, `boot_results_aim2.rds`,
  `icc_boot_t3_results.rds`) — delete these files if held to regenerate and reproduce results.

## Citation

Hobbs, A. (2026). *Spatial synchrony in the breeding traits of Scottish
blue tits.* Senior Honours Project, University of Edinburgh.

## Acknowledgements

Thanks again to the Phenoweb data collection by the team led by Albert Phillimore (Phenoweb.org). Site-specific
weather data provided by Dan Hollis. Project supervised by Hannah Froy
and Sanjana Ravindran (Institute of Ecology and Evolution, University of
Edinburgh).
