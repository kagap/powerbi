# Seoul bike sharing: when do people ride?

A seven-page Power BI report on the hourly demand for rental bikes in Seoul from December 2017 to November 2018 (8,760 hours, about 6.2 million rentals), together with the weather at each hour.

The report has a dark navigation panel on the left, white cards with rounded corners, a three-colour palette (navy, teal and one orange accent), no gridlines, KPI cards with a small trend line (a sparkline of the last twelve months) behind the number, and a collapsible **Filters pane** on the right (the funnel tab) with the date range and category filters. Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| Overview | Hours, total rentals, average rentals per hour, average temperature and humidity, with rentals by month, the share of hours by season, rentals by hour of the day and by holiday |
| Breakdown | Total rentals by hour, season, holiday and whether the system was working |
| Compare | Total rentals against average rentals for every hour of the day, a treemap of hours by season, and rentals and temperature by group |
| Trends | Total rentals, average rentals per hour, average temperature and the number of hours by month |
| Matrix | A sorted bar of rentals by hour, a table of all measures by hour, and rentals by hour and season |
| Details | The underlying hourly rows |
| About | The data source, the measures with their DAX, and how to use the report |

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `SeoulBikes.pbip` from this folder (or `SeoulBikes.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 8,760 rows), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

UCI Machine Learning Repository, *Seoul Bike Sharing Demand* (Seoul Metropolitan Government and Data.go.kr; E and Park, 2020), licence CC BY 4.0: <https://archive.ics.uci.edu/dataset/560>.
Column names were cleaned (for example `Temperature(°C)` became `Temperature_C`); the values are as published. The date column is read as day/month/year. A `Month` and a `Year` column are added in Power Query for the time charts.

## Measures

`Rows`, `Total rentals`, `Average rentals per hour`, `Average temperature`, `Average humidity` and `Rainy hours share` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips and the Filters pane are in the files but were not clicked through automatically, so try them once after opening.
