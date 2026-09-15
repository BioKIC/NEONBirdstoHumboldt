# Mapping NEON Survey Monitoring Data to the Humboldt Extension for Ecological Inventories

This repository provides a worked example of mapping **NEON Breeding landbird point counts** to **Darwin Core** and the [Humboldt Extension for Ecological Inventories](https://eco.tdwg.org/).  

The workflow was developed using the **RELEASE-2026** NEON data products.

---

## Contents

- `NEONBirdstoHumboldt.Rmd` – main workflow document (R Markdown)
- `outputs/` – generated Darwin Core–formatted tables:
  - `event.csv`
  - `humboldtecologicalinventory.csv`
  - `occurrence.csv`
  - `extendedMeasurementOrFact.csv`
- `data/` – local cache of downloaded NEON datasets

---

## Data Sources

The workflow draws on the following NEON data product:  

- **Breeding landbird point counts** ([DP1.10003.001](https://doi.org/10.48443/v6hs-mx57))  

See the [NEON bird data resource](https://www.neonscience.org/data-collection/birds) for details.

---

## Running the Workflow

1. Clone this repository:  
   ```bash
   git clone https://github.com/sunray1/NEONBirdstoHumboldt.git
   cd NEONBirdstoHumboldt
   ```
2. Open NEONBirdstoHumboldt.Rmd in RStudio.
3. Install required R packages if not already present:
    ```r
    install.packages(c("neonUtilities", "dplyr"))
    ```
3. Knit the R Markdown document to reproduce the outputs.

> **Note:** Note: You must set a NEON API token (Sys.setenv(NEON_TOKEN="your_token")) to download data.

---

## Outputs

The workflow generates Darwin Core–formatted tables, saved in the [`outputs/`](https://github.com/BioKIC/NEONBirdstoHumboldt/tree/master/outputs) folder:

- **`event.csv`** – hierarchical survey event structure (project, domain, site, plot, and visit levels)
- **`humboldtecologicalinventory.csv`** – hierarchical survey event structure  
- **`occurrence.csv`** – tick specimen records and pathogen testing results  
- **`extendedMeasurementOrFact.csv`** – additional measurements and metadata (e.g., counts, sample codes, conditions)
