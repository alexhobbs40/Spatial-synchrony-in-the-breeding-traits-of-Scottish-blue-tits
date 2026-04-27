# Data

This directory holds the data files referenced by the analysis scripts.
**Raw data is not redistributed in this repository** as it was collected
by the Phenoweb research team at the University of Edinburgh and remains
under their stewardship. Site-specific weather data was provided by Dan
Hollis using a modified HadUK-Grid interpolation (Hollis et al. 2019).

## Expected files

The scripts expect the following files in this directory:

| File | Used by | Description |
|---|---|---|
| `Blue_tits_raw.csv` | 01 | Raw nest-level Phenoweb dataset (input). |
| `Blue_tits_cleaned.csv` | 02, 04, check | Produced by `01_data_cleaning.Rmd`. After duplicate removal and clutch-swap exclusion. |
| `Blue_tits_final.csv` | 02, 04, 06, check | Produced by `01`. After Tomatin exclusion and clutch size cap. |
| `FED_Blue_tits_exc_2020.csv` | 02, 04, check | Produced by `01`. Lay-date subset with 2020 excluded. |
| `site_means.csv` | 04, 05, 06 | Annual site-level means/medians per trait. |
| `site_details.csv` | 03, 04, 05, 06 | Site coordinates and metadata. |
| `Pairwise_distance_km.csv` | 02, 05 | Produced by `03_pairwise_distances.Rmd`. Great-circle distances (km) between all site pairs. |
| `Pairwise_correlations.csv` | 04, 05, 06 | Pairwise Pearson correlations between site time series. |
| `climate_data.csv` | 04, 06 | Daily site-specific temperature/precipitation. |
| `site_means_with_temp.csv` | 04, 06 | Annual site-level means with mean spring temperature appended. |
| `icc_baseline.csv` | 05, 06 | Produced by `04_results_synchrony_iccs.Rmd`. |
| `daily_maxtemp_Hollis.txt` | 06 | Daily maximum temperature, all sites. |
| `daily_mintemp_Hollis.txt` | 06 | Daily minimum temperature, all sites. |
| `daily_precipitation_Hollis.txt` | 06 | Daily precipitation, all sites. |

## Data access

To request access to the underlying data, please contact the Biological sciences department at the University of Edinburgh.
