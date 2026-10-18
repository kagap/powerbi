# Beijing air: how often is it unhealthy?

A six-page Power BI report on 43,824 hourly readings of fine particles (PM2.5) in Beijing from 2010 to 2014, with the weather at each hour. The average reading is 99 micrograms per cubic metre, the worst hour reached 994, and **59.0% of the hours with a reading were above 55**, the level at which the US EPA scale turns to unhealthy.

The report has a charcoal page with an air-quality scale from green to maroon, a **filter panel on the left** (season, wind direction and concentration band, applied to every page) and the page tabs across the top. A collapsible **Filters pane** on the right holds the date range. Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is built from stacked columns and bars over the concentration bands.

| Page | What it shows |
|---|---|
| Overview | Average PM2.5, the share of hours above 55 and the average temperature with trend lines, the worst hour and wind speed; PM2.5 by month, hours by concentration band (donut), hours by year and band, and by season and band |
| Bands | Hours by month and band (stacked columns), by wind direction and band, and PM2.5 by hour of the day for the heating season and the rest of the year |
| Seasons | PM2.5 by month and by season, by heating season, and one line per season across the hours of the day |
| Wind | PM2.5 by wind direction, a treemap of hours by wind, PM2.5 against wind speed, and the share of hours by wind and band |
| Details | The underlying hourly rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: winter averages 113 against 87 in spring, and the heating season (15 November to 15 March) 112 against 92 for the rest of the year; the air is worst when the wind is calm or variable (126) or from the south-east (111) and best with a north-west wind (70); and there is no clear yearly trend (104 in 2010, 91 in 2012, 98 in 2014). Readings are from one monitor at the US embassy, so they describe that spot.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `{pbip}` from this folder (or `{rep}/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model ({rows}), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the **Overview** tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

UCI Machine Learning Repository, *Beijing PM2.5 Data* (Liang et al., 2015), licence CC BY 4.0: <https://archive.ics.uci.edu/dataset/381>.
Preparation: the date was assembled from year, month and day; PM2.5 is missing for 2,067 hours (4.7%), which keep an empty value and fall in a band called No reading; the concentration bands follow the US EPA breakpoints, applied to hourly readings, which is an approximation of the 24-hour standard; the heating season is 15 November to 15 March, when Beijing's central heating runs; wind directions were spelled out (calm or variable is `cv` in the source). A `Month` and a `Year` column are added in Power Query for the time charts.

## Measures

`Hours of data`, `Average PM2.5`, `Share of hours above 55`, `Average temperature`, `Worst hour` and `Average wind speed` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
