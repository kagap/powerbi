# Central Park since 1869: how New York's weather has changed

A seven-page Power BI report on 57,343 days of weather in New York's Central Park, from 1 January 1869 to 31 December 2025 (157 complete years): the daily high and low, precipitation and snowfall. The average temperature is 12.3 °C over the whole record; in 1869-1900 it was 11.3 °C and in 2016-2025 it was 13.8 °C, **2.5 °C warmer**.

The report is airy white and ice blue, with a **centred light title and underlined tabs**, hairline cards, and a collapsible **Filters pane** on the right (date range, decade, period and month). Hovering over a bar, slice or point shows a small summary card (a tooltip page).
Its signature is the **warming stripes**: one column for every year, coloured from deep blue (cooler than 1869-1900) to deep red (warmer), plus a **heat map of month by day of the month**.

| Page | What it shows |
|---|---|
| Overview | Days, average temperature, anomaly against 1869-1900, record high and low; the warming stripes; average temperature by year and the days that never thawed by decade |
| Stripes | Large warming stripes, a heat map of the anomaly by decade and month, and the anomaly by year |
| Calendar | A heat map of the average temperature by month and day of the month, one line per period for each month, and daily high and low by season |
| Extremes | Days with a high of 32 °C or more and days that never thawed, by decade; records and averages by decade (table); precipitation against temperature, a point a year |
| Rain and snow | Precipitation by year, the share of dry, rainy and snowy days by decade, snowfall by year and wet days by decade |
| Details | The underlying daily rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: the warmest years are 2023 (14.5 °C) and 2024 (14.4 °C), the coldest 1888 (9.7 °C); January averaged -1.0 °C in 1869-1900 and +1.0 °C in 1991-2025, July 24.1 °C and 25.3 °C. Days on which the temperature never rose above freezing fell from 300 in the 1880s to 134 in the 2010s, while days of 32 °C or more stay at about 100 to 200 a decade with no clear trend. The record high is 41.1 °C (9 July 1936) and the record low -26.1 °C (9 February 1934). Annual precipitation rose from about 1,094 mm in 1869-1900 to 1,261 mm in 1991-2025, while snowfall is about 71 cm a year in both periods. The station, its instruments and the city around it changed over 150 years, so the record mixes the climate with the growth of the city.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `NYCWeather.pbip` from this folder (or `NYCWeather.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 57,343 days), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

NOAA National Centers for Environmental Information, *Global Historical Climatology Network daily* (GHCN-Daily), station USW00094728 (New York City Central Park), public domain, retrieved on 22 October 2026: <https://www.ncei.noaa.gov/pub/data/ghcn/daily/by_station/>.
Preparation, stated on the About page: readings flagged by the quality checks (191) were dropped; tenths of a degree were converted to Celsius; the daily average is the mean of the high and the low; 2026 was left out so that every year is complete; 41 days without a temperature and 177 without a snow reading stay empty; decades, periods, month labels, seasons, weekdays and temperature and weather bands were added; and each year got the band of its own anomaly (`Year_band`, seven bands from below -1.0 to above +2.0 degrees) to colour its stripe. `Month` and `Year` are added in Power Query.

## Measures

`Days`, `Average temperature (C)`, `Anomaly vs 1869-1900 (C)` (the difference from the same months in 1869-1900, whatever the year, decade or period selected), `Average daily high (C)`, `Average daily low (C)`, `Precipitation (mm)`, `Snowfall (cm)`, `Days with a high of 32 C or more`, `Days that never thawed`, `Record high (C)`, `Record low (C)`, `Stripe` (a constant 1 for the stripes) and `Wet days (1 mm or more)` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
