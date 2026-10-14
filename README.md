# Exchange rates and national economies

SIS 1, Data Collection and Preparation.

We checked if the size of an economy (GDP) is connected with how its currency changed against the US dollar in 2015-2025.

**Short answer:** no. The size of the economy almost does not matter. Inflation matters much more.

## Team

| Member | ID | Part | Notebook |
|---|---|---|---|
| Dauletkhan Qian | 23B031082 | 1. Data from the World Bank API | `01_API_WorldBank_Qian.ipynb` |
| Kalybay Nurdaulet | 23B031515 | 2. Web scraping GDP from Wikipedia | `02_WebScraping_Wikipedia_Nurdaulet.ipynb` |
| Dauirkhankyzy Balnur | 23B031274 | 3. Cleaning and merging | `03_Cleaning_Merging_Balnur.ipynb` |
| Abibulla Kundyz | 23B030352 | 4. Analysis and plots | `04_Analysis_Visualization_Kundyz.ipynb` |

`SIS_TeamFX_Exchange_Rates_GDP.ipynb` has all 4 parts in one notebook (this is the file for submission).

## Data

- **API:** [World Bank](https://api.worldbank.org/v2). Exchange rate (`PA.NUS.FCRF`), inflation (`FP.CPI.TOTL.ZG`), region and income group of every country.
- **Web scraping:** [Wikipedia, List of countries by GDP (nominal)](https://en.wikipedia.org/wiki/List_of_countries_by_GDP_(nominal)). GDP from IMF, World Bank and UN, scraped with `requests` and `BeautifulSoup`.

## How the parts are connected

Every notebook saves its result into the `data/` folder, and the next notebook reads it.

| Notebook | Reads | Saves |
|---|---|---|
| 01 | World Bank API | `wb_countries_raw.csv`, `wb_indicators_raw.csv` |
| 02 | Wikipedia page | `gdp_raw.csv` |
| 03 | files from 01 and 02 | `fx_rates_clean.csv`, `gdp_clean.csv`, `merged_dataset.csv`, `by_currency.csv` |
| 04 | files from 03 | plots in `figures/`, `correlations_spearman.csv`, `income_group_summary.csv` |

## Main results

- Final table: 166 countries.
- 49% of currencies became weaker against the dollar. The biggest losses: Argentina, Lebanon, Turkey.
- GDP and currency change: correlation -0.04 (no connection).
- Inflation and currency change: correlation -0.65 (strong connection).

All details are in `report_TeamFX.pdf`.

## How to run

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

Run the notebooks in order: 01, 02, 03, 04. Notebooks 01 and 02 need internet.
Or just run `SIS_TeamFX_Exchange_Rates_GDP.ipynb` from top to bottom.

Note: the World Bank and Wikipedia update their data, so a new run can give slightly different numbers.
