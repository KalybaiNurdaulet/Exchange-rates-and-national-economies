# Exchange Rates and National Economies

SIS 1 — Data Collection & Preparation.
Relationship between currency exchange rates and the economic size (nominal GDP) of countries.

## Team and responsibilities

| Member | ID | Part |
|---|---|---|
| Dauletkhan Qian | 23B031082 | Part 1 — API data collection (World Bank) |
| Kalybay Nurdaulet | 23B031515 | Part 2 — Web scraping (Wikipedia GDP table) |
| Dauirkhankyzy Balnur | 23B031274 | Part 3 — Data cleaning and merging |
| Abibulla Kundyz | 23B030352 | Part 4 — Analysis and visualization |

## Data sources
- **API:** [World Bank Indicators API](https://api.worldbank.org/v2) — exchange rate (`PA.NUS.FCRF`), inflation (`FP.CPI.TOTL.ZG`) and country metadata, 2015–2025
- **Web page:** [Wikipedia — List of countries by GDP (nominal)](https://en.wikipedia.org/wiki/List_of_countries_by_GDP_(nominal)) — scraped with `requests` + `BeautifulSoup`

## Repository
The work is split into **4 notebooks — one per team member**. Each notebook saves its result to `data/` as CSV, and the next one reads it.

```
01_API_WorldBank_Qian.ipynb             -> data/wb_countries_raw.csv, data/wb_indicators_raw.csv
02_WebScraping_Wikipedia_Nurdaulet.ipynb -> data/gdp_raw.csv
03_Cleaning_Merging_Balnur.ipynb        -> data/fx_rates_clean.csv, data/gdp_clean.csv,
                                           data/merged_dataset.csv, data/by_currency.csv
04_Analysis_Visualization_Kundyz.ipynb  -> figures/*.png, data/correlations_spearman.csv,
                                           data/income_group_summary.csv
```

| File / folder | Content |
|---|---|
| `01_…` – `04_…` | the 4 part notebooks |
| `SIS_TeamFX_Exchange_Rates_GDP.ipynb` | all 4 parts in one notebook (submission file) |
| `report_TeamFX.pdf` | written report (2 pages) |
| `data/` | raw, cleaned and merged CSV files |
| `figures/` | the 6 plots |
| `requirements.txt` | Python libraries |

## How to run
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```
Run the notebooks in order 01 → 04 (01 and 02 need internet and can run in any order; 03 needs both; 04 needs 03).
Or run `SIS_TeamFX_Exchange_Rates_GDP.ipynb` from top to bottom.
