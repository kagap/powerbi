# Cars since 1984: what a gallon buys

A six-page Power BI report on 49,868 vehicle variants tested by the US EPA for model years 1984 to 2026: fuel economy, tailpipe CO2, the EPA's annual fuel cost estimate and, for electric cars, the range. The average non-electric variant does 20.8 miles per gallon (19.9 in 1984, 24.2 in 2026).

The report has a cream page with racing red, big italic titles, round white cards and a **floating dock at the bottom** for the pages; a collapsible **Filters pane** is on the right. Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is built to be different from the other reports in this repository: a catalogue of brands with a shaded ranking table, 100% stacked columns of the fuel mix, a gauge and a ranking of electric range by make.

| Page | What it shows |
|---|---|
| Overview | Vehicles, average MPG (not electric), CO2, annual fuel cost, electric range and electric share; MPG by model year with one line per class, variants by fuel type (donut), the share of fuel types by model year (100% stacked columns), and MPG by class |
| Brands | A table of makes ranked by number of models with the MPG column shaded, a treemap of variants by make, and MPG against CO2 by class (scatter) |
| Engines | Variants by cylinders and fuel type (stacked columns), MPG by cylinders, and MPG and CO2 by engine-size band |
| Electric | Average electric range and the number of electric models by model year, a gauge of the average range (scale 0 to 500), and range by make |
| Details | The underlying variant rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: SUVs and pickups were 21% of the variants listed for 1984 and 63% for 2026; pickups average 16.9 MPG and small cars 23.2; four-cylinder engines average 24.9 MPG and eight-cylinder ones 15.6; average tailpipe CO2 fell from 492 g per mile in the 1980s to 399 in the 2020s. The first electric car in the data is from 1998 (range 62 miles); the 2026 average is 302 miles, and electric variants are 27% of the 2026 listings against 3% in 2020. Rows are model variants on offer, not cars sold, so these shares describe the choice, not sales.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `FuelEconomy.pbip` from this folder (or `FuelEconomy.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 49,868 rows), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

US Department of Energy and US EPA, *Fuel Economy Data* (`vehicles.csv` from <https://www.fueleconomy.gov/feg/ws/>), public domain, retrieved on 19 October 2026.
Preparation, stated on the About page: model year 2027 (539 early listings) was left out; vehicle classes, fuel types, drive and transmission were simplified (class and band labels start with a number so that they sort); the electric range and kWh per 100 miles are kept only for electric cars; the annual fuel cost of hydrogen cars (listed as zero) is left empty. Miles per gallon of electric cars is an equivalent (MPGe), so the MPG measures leave electric cars out.

## Measures

`Vehicles`, `Average MPG (not electric)`, `Average CO2 (g per mile)`, `Average annual fuel cost ($)`, `Average EV range (mi)`, `Electric share of models`, `Hybrid and electric share` and `Electric models` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
