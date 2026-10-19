# 📊 Power BI Portfolio

A collection of twenty-one Power BI projects built on public and open datasets: cost of living, military spending, e-commerce, video games, pop culture, food prices, how people spend their time, social media activity and Formula 1 (a Microsoft Fabric lakehouse project). Most folders are self-contained mini-projects with a `.pbix` report and the raw data behind it; the exceptions are noted below (`F1_Fabric` has a notebook and a PDF instead of a `.pbix`, `HarryPotterMoviesAll` has only the data, `OlistEcommerce_BrazilianMarketplace` has only the report).

## 📌 What's Inside

- **AdultCensus_IncomeOver50K/** — Power BI project (`AdultIncome.pbip`, six pages) on 32,561 adults from a 1994 US census extract: the share earning over 50K by occupation, education, marital status, sex and age. Data is stored in the model; see the folder's [README](AdultCensus_IncomeOver50K/README.md) for how to open it and where the data comes from (UCI, CC BY 4.0).
- **BeijingPM25_AirQuality/** — Power BI project (`BeijingPM25.pbip`, six pages, charcoal with an air-quality colour scale and a filter panel on the left) on 43,824 hourly PM2.5 readings in Beijing, 2010-2014, with the weather: how often the air is unhealthy by month, season, wind and heating season. Data is stored in the model; see the folder's [README](BeijingPM25_AirQuality/README.md) (UCI, CC BY 4.0).
- **CostLivingIndex2022/** — `costlive.pbix` dashboard exploring the 2022 cost of living index, built from `cost of living index 2022.csv`.
- **DiabetesReadmission_US130Hospitals/** — Power BI project (`HospitalReadmission.pbip`, six pages, cream paper look with a serif headline) on 69,970 first hospital stays of patients with diabetes in 130 US hospitals: who is readmitted within 30 days, by age, diagnosis, admission type and treatment, with a funnel, a ribbon chart, a waterfall and 100% stacked bars. Data is stored in the model; see the folder's [README](DiabetesReadmission_US130Hospitals/README.md) (UCI, CC BY 4.0).
- **F1_Fabric/** — End-to-end Microsoft Fabric project on 75 seasons of Formula 1: PySpark notebook (bronze/silver/gold lakehouse), star-schema Direct Lake model and a three-page Power BI report. See the folder's [README](F1_Fabric/README.md) for the architecture, report screenshots and lessons learned.
- **FuelEconomy_Cars1984_2026/** — Power BI project (`FuelEconomy.pbip`, six pages, cream and racing red with a floating dock for the pages) on 49,868 vehicle variants tested by the US EPA, model years 1984-2026: fuel economy and CO2 by class, brand and engine size, and the electric turn. Data is stored in the model; see the folder's [README](FuelEconomy_Cars1984_2026/README.md) (US DOE and EPA, public domain).
- **GarmentProductivity_TeamBoard/** — Power BI project (`GarmentProductivity.pbip`, six pages, light grey with a floating header card and safety yellow) on 1,197 team-days in a garment factory: which teams hit their target, with a ranked table with shaded cells, outcomes against target, and productivity by incentive, overtime and style changes. Data is stored in the model; see the folder's [README](GarmentProductivity_TeamBoard/README.md) (UCI, CC BY 4.0).
- **HarryPotterMoviesAll/** — A dataset of the Harry Potter movies (`Movies.csv`, `Characters.csv`, `Chapters.csv`, `Dialogue.csv`, `Places.csv`, `Spells.csv`, plus a `Data_Dictionary.csv` and `LICENSE` for the dataset). No `.pbix` report is currently included in this folder.
- **MetroTraffic_I94Volume/** — Power BI project (`TrafficVolume.pbip`, six pages, dark neon look with the page tabs along the bottom) on hourly traffic on Interstate 94 near Minneapolis and St Paul (40,575 hours, 2012-2018) with the weather: a weekday-by-hour heat map, a combo chart, a gauge, a waterfall and a ribbon chart. Data is stored in the model; see the folder's [README](MetroTraffic_I94Volume/README.md) (UCI, CC BY 4.0).
- **MilitarySpend_1988_2021/** — `top10military.pbix` report visualizing military expenditure from 1988–2021, sourced from the `SIPRI Military Expenditure Database.xlsx`.
- **OlistEcommerce_BrazilianMarketplace/** — `olist_ecommerce.pbix`, a relational model (orders, order items, customers, sellers, products, payments, reviews) analyzing revenue, delivery performance and review scores for the Brazilian Olist marketplace. Source data isn't committed here — see the folder's own [README](OlistEcommerce_BrazilianMarketplace/README.md) for the data model, key DAX measures, and where to download the Kaggle dataset.
- **Nyc_pizza_2015-2022/** — `pizza_slices.pbix` dashboard on NYC pizza slice prices from 2015–2022, using `nyc_slice_rawdata.xlsx`.
- **OnlineShoppers_PurchasingIntention/** — Power BI project (`OnlineShoppers.pbip`, six pages) on 12,330 browsing sessions of an online shop: conversion rate by month, visitor type and traffic source. Data is stored in the model; see the folder's [README](OnlineShoppers_PurchasingIntention/README.md) (UCI, CC BY 4.0).
- **SeoulBikeSharing_Demand/** — Power BI project (`SeoulBikes.pbip`, seven pages) on the hourly demand for rental bikes in Seoul (8,760 hours, 2017-2018) with the weather: rentals by hour, season, holiday and month. Data is stored in the model; see the folder's [README](SeoulBikeSharing_Demand/README.md) (UCI, CC BY 4.0).
- **SteamGames_PriceVsPopularity/** — `steam_games.pbix` dashboard exploring price, review score, genre and estimated ownership for 27,000+ Steam games, built from `steam.csv` (Kaggle "Steam Store Games" dataset).
- **StudentPerformance_FinalGrades/** — Power BI project (`StudentPerformance.pbip`, six pages, dark green board with chalk yellow and pink and numbered page chips) on 1,044 course enrolments of Portuguese secondary-school students: a commentary card with one big number beside the charts on each page. Data is stored in the model; see the folder's [README](StudentPerformance_FinalGrades/README.md) (UCI, CC BY 4.0).
- **TimeSpendByAge/** — `spendtime.pbix` report on how different age groups spend their time, based on `time-spent-with-relationships-by-age-us.csv`.
- **tweets_trends/** — `tweet_trends.pbix` dashboard analyzing tweet trends, built from a large raw tweets CSV export.
- **USMacro_Since1990/** — Power BI project (`USMacro.pbip`, six pages, amber monospace on black with function-key tabs, like a market terminal) on 441 months of the US economy, 1990-2026 (FRED): latest values and their change against a year earlier, rates and the yield curve, inflation and jobs, and recessions. Data is stored in the model; see the folder's [README](USMacro_Since1990/README.md) (FRED, see the note on terms).
- **USTornadoes_1950_2023/** — Power BI project (`USTornadoes.pbip`, seven pages, slate blue and lightning yellow with a numbered rail) on 70,022 US tornadoes, 1950-2023 (NOAA): a tile-grid map of the states built without any map service, a dot map of the violent tornadoes, strength from weak to violent, and when they strike. Data is stored in the model; see the folder's [README](USTornadoes_1950_2023/README.md) (NOAA SPC, public domain).
- **WineQuality_VinhoVerde/** — Power BI project (`WineQuality.pbip`, six pages, warm white with a burgundy menu on the right) on 6,497 Portuguese red and white Vinho Verde wines with eleven laboratory measurements and a taster's quality score: a gauge, a multi-row card, small multiples of the ingredients by quality, and red against white. Data is stored in the model; see the folder's [README](WineQuality_VinhoVerde/README.md) (UCI, CC BY 4.0).

## 🚀 Getting Started

1. Clone the repository:
   ```
   git clone https://github.com/kagap/powerbi.git
   ```
   The repository is about 80 MB, mostly two files: `olist_ecommerce.pbix` (42 MB) and the tweets CSV in `tweets_trends/` (17 MB).
2. Open the `.pbix` file inside the folder you're interested in using **Power BI Desktop**.
3. The source data file(s) in the same folder are what each report was built from, in case you want to explore or refresh the data yourself.

## Requirements

- [Power BI Desktop](https://www.microsoft.com/en-us/power-platform/products/power-bi/desktop) to open and interact with the `.pbix` files.
- `F1_Fabric` is documented as a pipeline with report screenshots and a PDF: its live report is a Direct Lake model that runs only inside Microsoft Fabric, so it cannot be opened from this repository.
