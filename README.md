# Africa Visa Liberation

This project applies regression and network analysis to explore the relationship between visa openness, passport power, and economic development across African countries, with a focus on Sub-Saharan Africa. It combines datasets on:

- Africa Visa Openness Index (2019, 2023)
- Passport Index (2019, 2023)
- Henley Passport Index (2025)
- GDP per capita (2019–2023)
- Country metadata (region, income group)


## Key Questions

- How open are African countries to each other and the world?
- Does increased visa openness or passport strength associate with higher GDP per capita?
- Which countries are most central in Africa’s mobility network?
- How has access changed from 2019 to 2023?


## Methods

- **Data Cleaning + Merging**  
  All datasets are joined by ISO3 country codes into a unified panel

- **Statistical Modeling**  
  Regressions of log GDP per capita on:
  - Visa openness score
  - Henley score
  - Centrality measures (Katz, PageRank, etc.)
  - With controls for region and income group

- **Network Analysis**  
  Directed graphs built from passport data (origin → destination access).  
  Centrality measures computed using NetworkX

- **Visualization**  
  Mobility networks rendered using matplotlib and NetworkX, with nodes colored by income group and sized by GDP


## Inputs

- `input/africa_visa_openness_2019.csv`
- `input/africa_visa_openness_2023.csv`
- `input/country_region_income_group.csv`
- `input/gdp_per_capita_2019_2023.csv`
- `input/henley_passport_index_2025.csv`
- `input/passport-index-2019.csv`
- `input/passport-index-2023.csv`

## Outputs

- `output/dataset.csv` — Unified country-level dataset (cleaned and merged)
- `output/sub_saharan_africa_network.png` — Network of visa access in Sub-Saharan Africa (2023)
- `output/avoi_score_north_africa_2023.png` — Visa Openness Score by Country: North Africa (2023)
- `output/avoi_score_sub_saharan_africa_2023.png` — Visa Openness Score by Country: Sub-Saharan Africa (2023)
- `output/correlations_2019.png` — Correlation heatmap of mobility and ranking metrics (2019)
- `output/correlations_2023.png` — Correlation heatmap of mobility and ranking metrics (2023)
- `output/countries_by_income.png` — Histogram of countries by income group
- `output/countries_by_region.png` — Histogram of countries by region
- `output/henley_score_2025.png` — Henley Passport Index scores by country (2025)
- `output/passport_index_pagerank_2023.png` — Scatterplot of Passport PageRank vs. Log GDP per capita (2023)


## Data Sources

- [AU Africa Visa Openness Index](https://www.visaopenness.org/)
- [Henley Passport Index](https://www.henleyglobal.com/passport-index)
- [Passport Index](https://www.passportindex.org/)
- [World Bank GDP per Capita](https://data.worldbank.org/)
- World Bank Country Metadata