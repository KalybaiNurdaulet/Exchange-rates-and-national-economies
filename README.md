# Exchange Rates and National Economies

This repository is for our SIS 1 project about exchange rates and countries' GDP.

My API part is in `01_API_WorldBank_Qian.ipynb`. It downloads the World Bank
Data360 indicator `WB_WDI_PA_NUS_FCRF` for 2015–2025 and saves the result in
`data/exchange_rates_2015_2025.csv`.

To run the notebook in VS Code, install the packages in `requirements.txt`,
select a Python kernel, and run the cells from top to bottom. If the CSV already
exists, the notebook reads it instead of downloading the data again. Set
`download_again = True` in the notebook to refresh it.

The CSV has three columns: `year`, `country_code`, and `lcu_per_usd`. The last
column is the average number of local currency units per US dollar in that
year. Data360 gives rates by country, so the API does not include currency
codes or daily exchange rates.

API documentation: https://data360.worldbank.org/en/api

Indicator description: https://databank.worldbank.org/metadataglossary/world-development-indicators/series/PA.NUS.FCRF
