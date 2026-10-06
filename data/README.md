# Data
-   **[Dataset]**: This "Many Penguins" dataset, derived from the global AVONET database 
(Tobias et al., 2022), allow us to explore an evolutionary question: do closely related 
groups that share a similar lifestyle develop similar physical characteristics? The 
dataset contains 10 distinct morphmetric measurements, or physical body measurements, 
collected from 93 penguins representing 18 species across 6 genera. Because the dataset 
is cross-sectional, it provides a snapshot of present-day penguin species rather than
documenting how their physical characteristics have changed over time. Our goal is to 
describe and compare differences in beak shape and wing structure across penguin genera 
and examine whether these genera remain physically distinct despite sharing an aquatic 
lifestyle. 

# Codebook for [Many Penguins] Dataset
-   **Description**: This is the "Many Penguins" dataset, featured in TidyTuesday on 2026-07-14 
(week 28), curated by Ben Bolker of McMaster University. It was created as a richer 
alternative to the Palmer Penguins dataset that includes only 3 species. Many Penguins 
dataset contains the penguins (Spheniscidae) records from the much larger AVONET database 
and includes 18 species. 

-   **Provenance/Sources**:
  - Source: AVONET — Tobias, J.A., Sheard, C., Pigot, A.L., et al. (2022). "AVONET: morphological, 
  ecological and geographical data for all birds." Ecology Letters, 25(3), 581–597. DOI: 10.1111/ele.13898. 
  The full AVONET database covers 90,020 individual birds across 11,009 species from 181 countries, 
  with 11 continuous morphological traits and 6 ecological variables: opentraits.org/datasets/avonet.html.
  - Filtering step: Bolker's cleaning script pulled the raw AVONET measurement file (AVONET_Raw_Data.csv) 
  and cross-referenced it against AVONET's species list, filtering to just Family.name == "Spheniscidae" 
  (penguins), using the BirdLife taxonomic backbone (Species1_BirdLife). 
  - This dataset: github.com/rfordatascience/tidytuesday, data/2026/2026-07-14, file many_penguins.csv, 
  downloadable directly at: 
  https://raw.githubusercontent.com/rfordatascience/tidytuesday/main/data/2026/2026-07-14/many_penguins.csv 

-   **Dimensions**:
93 rows (individual penguin specimens) × 14 columns — 4 categorical/identifier columns (species, genus, 
shortname, sex) and 10 continuous morphometric measurement columns, spanning 18 species across 6 genera.

## Variable Names and Descriptions:

-   **variable**: Description

## Data Types:

-   **Column**: data type



