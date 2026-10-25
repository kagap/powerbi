# Britain's electricity in 2025: who generates it and how clean it is

A six-page Power BI report on the electricity generation mix and the carbon intensity of Great Britain in every half-hour of 2025 (17,494 of the 17,520 half-hours; the API has small gaps). On average every kilowatt-hour came with **129 grams of carbon dioxide**, between 24 g in the cleanest half-hour and 293 g in the dirtiest; wind generated 32% of the power, gas 28%, nuclear 13%, imports 12.5%, biomass 7.6% and solar 6.3%.

The report is a **dark indigo dashboard**: a full-height sidebar with the title and the pages and a violet pill for the active one, deep-blue cards, violet, cyan and coral lines, KPI tiles with a sparkline and a collapsible **Filters pane** on the right (date, fuel and source type). Hovering over a bar, slice or point shows a small summary card (a tooltip page). It has a light twin, `lilac`, used for the Airbnb report in this repository.

| Page | What it shows |
|---|---|
| Overview | Five KPI tiles (average carbon intensity, low-carbon share, wind share, gas share, share of clean half-hours) with sparklines, carbon intensity by month, the generation mix (donut), the mix by month (stacked area) and carbon intensity by hour of the day |
| Mix | The share of every fuel by month (100% stacked area), the average share by source type and a heat map of carbon intensity by month and hour of the day |
| Rhythm | Carbon intensity by hour for each season (lines), solar and wind share by hour (area), carbon intensity by weekday and the mix by part of the day |
| Extremes | Half-hours by intensity index, carbon intensity against wind share for every day (scatter), a table of the days from the dirtiest to the cleanest and the cleanest and dirtiest half-hour of each month |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: low-carbon sources (wind, solar, hydro, nuclear and biomass) produced 59% of the power, renewables (wind, solar and hydro) 38%. January was the dirtiest month (169 g) and June the cleanest (99 g): gas supplies 39% of the power in January and 20% in June, wind 42% in December and 21% in July, and solar peaks in May (11%). Over the day carbon intensity is highest in the evening peak (162 g at 18:00) and lowest around midday (110 g at 12:00), and weekends are cleaner than weekdays (113 g against 136 g). The dirtiest days were 20 and 22 January (265 g, with gas at 66% and wind at 9% on the 20th) and the days with more wind are clearly cleaner: a falling diagonal in the scatter. 37.5% of the half-hours have a low or very low intensity index.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `UKGrid.pbip` from this folder (or `UKGrid.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 122,458 rows), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

Carbon Intensity API (National Grid ESO and partners, <https://api.carbonintensity.org.uk/>), licensed under CC BY 4.0, retrieved on 25 October 2026: generation mix and actual carbon intensity, 1 January to 31 December 2025 (UTC).
Preparation, stated on the About page: the two feeds were joined by half-hour; the table is long, with one row for every half-hour and fuel (so a half-hour appears once for each of the seven fuels); and hour, part of the day, weekday, weekend, month, season, source type and an intensity index were added.
**Things to keep in mind.** Shares are shares of all generation in Great Britain, including imports. Coal and the category other were zero all year and are left out; hydro appears in the data but is almost always zero, because the API does not report it as a separate fuel, so the renewable share (wind, solar and hydro) is in practice wind plus solar. 18 half-hours have no forecast and 26 are missing from the API, so the numbers cover 17,494 half-hours.

## Measures

`Half-hours`, `Average carbon intensity (g per kWh)`, `Renewable share`, `Low-carbon share`, `Gas share`, `Wind share`, `Solar share`, `Imports share`, `Nuclear share`, `Cleanest half-hour (g per kWh)`, `Dirtiest half-hour (g per kWh)`, `Average share of generation` and `Clean half-hours` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
