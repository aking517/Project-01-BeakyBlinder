---

editor_options: 
  markdown: 
    wrap: 72
---

# "Many Penguins" Dataset Metadata

## Overview:

The Many Penguins dataset contains morphometric measurements from 93 penguins representing 18 species across 6 genera. The dataset includes measurements of physical characteristics such as beak dimensions, wing length, tarsus length, and tail length.

Each row represents an individual penguin, and each column represents a taxonomic characteristic, demographic attribute, or morphometric measurement.

## Provenance/Sources:

The dataset is derived from the global AVONET database described by Tobias et al. (2022). The version of the dataset used in this project was obtained through the TidyTuesday repository for July 14, 2026.

Source:

- Original data source: AVONET — Tobias, J.A., Sheard, C., Pigot, A.L., et al. (2022). "AVONET: morphological, ecological and geographical data for all birds." Ecology Letters, 25(3), 581–597. DOI: [10.1111/ele.13898].

  - The full AVONET database covers 90,020 individual birds across 11,009 species from 181 countries, with 11 continuous morphological traits and 6 ecological variables: <https://opentraits.org/datasets/avonet.html>

- TidyTuesday GitHub repository: <https://github.com/rfordatascience/tidytuesday>

- Specific dataset: TidyTuesday July 14, 2026 data: <https://raw.githubusercontent.com/rfordatascience/tidytuesday/main/data/2026/2026-07-14/many_penguins.csv>

## Codebook:

- **Filtering step**: Bolker's cleaning script pulled the raw AVONET measurement file (AVONET_Raw_Data.csv) and cross-referenced it against AVONET's species list, filtering to just Family.name == "Spheniscidae" (penguins), using the BirdLife taxonomic backbone (Species1_BirdLife).
- **Dimensions:** 93 rows (individual penguin specimens) × 14 columns — 4 categorical/identifier columns (species, genus, shortname, sex) and 10 continuous morphometric measurement columns, spanning 18 species across 6 genera.

### Variable Names, Classes and Descriptions:

| Variable | Class | Description |
|:-----------------------|:---------------:|-------------------------------|
| `species` | `factor` | Penguin species name. |
| `genus` | `factor` | Penguin genus name. |
| `shortname` | `factor` | Abbreviated species name. |
| `sex` | `factor` | Sex of the individual sampled: M = Male; F = Female; U = Unknown. |
| `beak.length_culmen` | `double` | Length from the tip of the beak to the base of the skull (mm). |
| `beak.length_nares` | `double` | Length from the anterior edge of the nostrils to the tip of the beak (mm). |
| `beak.width` | `double` | Width of the beak at the anterior edge of the nostrils (mm). |
| `beak.depth` | `double` | Depth of the beak at the anterior edge of the nostrils (mm). |
| `tarsus.length` | `double` | Length of the tarsus from the posterior notch between tibia and tarsus (mm). |
| `wing.length` | `double` | Length from the carpal joint (bend of the wing) to the tip of the longest primary on the unflattened wing (mm). |
| `kipps.distance` | `double` | Length from the tip of the first secondary feather to the tip of the longest primary (mm). |
| `secondary1` | `double` | Length from the carpal joint (bend of the wing) to the tip of the first secondary (mm). |
| `hand-wing.index` | `double` | 100 × DK/Lw, where DK is Kipp's distance and Lw is wing length (i.e., Kipp's distance corrected for wing size). Species average HWI differs from estimates in Sheard et al. (2020) because of much higher sampling of individuals in some species, as well as taxonomic effects in the BirdLife list (mm). |
| `tail.length` | `double` | Distance between the tip of the longest rectrix and the point at which the two central rectrices protrude from the skin, typically measured using a ruler inserted between the two central rectrices (mm). |

## Data Types:

- **Factor:** Categorical variable used to represent taxonomic or demographic categories.
- **Double:** Numeric variable stored as a double-precision value.

## Units and Measurements: 

Morphometric measurements are reported in millimeters (mm).

The `hand-wing.index` variable is a calculated index rather than a direct measurement. It represents Kipp's distance corrected for wing size.

## Concerns and Additional Information:

- **Missing data:** the readme explicitly notes up to 12% of some measurement types are missing, which is worth checking missingness patterns per variable/species before modeling, and considering how to handle it (imputation, complete-case analysis, models tolerant of missingness).

- **Age was dropped:** the cleaning script excluded an Age column because it was uninformative (0 for all but one bird).

- `hand-wing.index` **caveat:** the readme flags that species-average HWI values here differ from published estimates in Sheard et al. (2020), due to differing sampling intensity across species and taxonomic effects tied to the BirdLife species list used.

- **Uneven sampling:** 93 individuals across 18 species is not an even \~5 per species, in which some genera/species will have far fewer individuals, This can make comparisons between genera less reliable. It can also let well-sampled species dominate their genus. We will check sample sizes per genus and species before running our analyses and keep this in mind when interpreting the results.  

- **Flightless-bird reinterpretation:** traits designed around flight biomechanics in AVONET (wing length, Kipp's distance, hand-wing index) describe flipper shape and diving/swimming propulsion in penguins rather than aerial flight, which is worth stating explicitly in your writeup rather than importing typical "flight efficiency" framing.

- **Taxonomic backbone:** built on the BirdLife taxonomy specifically (Species1_BirdLife), so species names should be cross-checked if bring in outside phylogenetic or IUCN data using a different taxonomy (e.g., eBird/Clements or BirdTree).
