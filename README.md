# 📊 Power BI Portfolio

A collection of Power BI dashboards and reports built while exploring different public and open datasets — cost of living, military spending, pop culture, food trends, and social media activity. Each folder is a self-contained mini-project with its own `.pbix` report file and the raw data behind it.

## 📌 What's Inside

- **CostLivingIndex2022/** — `costlive.pbix` dashboard exploring the 2022 cost of living index, built from `cost of living index 2022.csv`.
- **HarryPotterMoviesAll/** — A dataset of the Harry Potter movies (`Movies.csv`, `Characters.csv`, `Chapters.csv`, `Dialogue.csv`, `Places.csv`, `Spells.csv`, plus a `Data_Dictionary.csv` and `LICENSE` for the dataset). No `.pbix` report is currently included in this folder.
- **MilitarySpend_1988_2021/** — `top10military.pbix` report visualizing military expenditure from 1988–2021, sourced from the `SIPRI Military Expenditure Database.xlsx`.
- **OlistEcommerce_BrazilianMarketplace/** — `olist_ecommerce.pbix`, a relational model (orders, order items, customers, sellers, products, payments, reviews) analyzing revenue, delivery performance and review scores for the Brazilian Olist marketplace. Source data isn't committed here — see the folder's own [README](OlistEcommerce_BrazilianMarketplace/README.md) for the data model, key DAX measures, and where to download the Kaggle dataset.
- **Nyc_pizza_2015-2022/** — `pizza_slices.pbix` dashboard on NYC pizza slice prices from 2015–2022, using `nyc_slice_rawdata.xlsx`.
- **SteamGames_PriceVsPopularity/** — `steam_games.pbix` dashboard exploring price, review score, genre and estimated ownership for 27,000+ Steam games, built from `steam.csv` (Kaggle "Steam Store Games" dataset).
- **TimeSpendByAge/** — `spendtime.pbix` report on how different age groups spend their time, based on `time-spent-with-relationships-by-age-us.csv`.
- **tweets_trends/** — `tweet_trends.pbix` dashboard analyzing tweet trends, built from a large raw tweets CSV export.

## 🚀 Getting Started

1. Clone the repository:
   ```
   git clone https://github.com/kagap/powerbi.git
   ```
2. Open the `.pbix` file inside the folder you're interested in using **Power BI Desktop**.
3. The source data file(s) in the same folder are what each report was built from, in case you want to explore or refresh the data yourself.

## Requirements

- [Power BI Desktop](https://www.microsoft.com/en-us/power-platform/products/power-bi/desktop) to open and interact with the `.pbix` files.
