# I-94 traffic: when is the road busy?

A six-page Power BI report on hourly traffic volume on the westbound lane of Interstate 94 between Minneapolis and St Paul, from October 2012 to September 2018 (40,575 hours), with the weather and holidays for each hour. The average hour sees 3,291 vehicles and the busiest one 7,280.

The report has a near-black neon look (cyan, magenta and lime on dark navy), a slim header and the page tabs along the bottom edge, and a collapsible **Filters pane** on the right. Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is built to be different from the other reports in this repository: a heat map, a combo chart, a gauge, a waterfall, a ribbon chart and a 100% stacked column chart.

| Page | What it shows |
|---|---|
| Overview | Average traffic per hour, average temperature and rainy-hours share with trend lines, the busiest hour and total vehicles; a combo chart (traffic as columns, temperature as a line) by month, a gauge of the average against the busiest hour, one line per weekday across the hours of the day, and traffic by part of the day |
| Rhythm | A heat map of average traffic by hour and weekday, traffic by weekday, and a waterfall of how the total builds up across the parts of the day |
| Weather | Share of hours by weather type in each month (100% stacked columns), traffic by weather type, traffic against temperature by weather type (scatter), and a ribbon chart of which weather carries most vehicles in each year |
| Seasons | Traffic by month and by year, temperature by month, and the hours recorded per month |
| Details | The underlying hourly rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: traffic peaks on weekday afternoons (about 5,700 vehicles an hour at 16:00, against about 370 at 03:00); an average Friday carries 3,675 vehicles an hour and a Sunday 2,426.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `TrafficVolume.pbip` from this folder (or `TrafficVolume.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 40,575 hours), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

UCI Machine Learning Repository, *Metro Interstate Traffic Volume* (John Hogue; Minnesota DoT automatic traffic recorder, station 301), licence CC BY 4.0: <https://archive.ics.uci.edu/dataset/492>.
Preparation, all stated on the About page: several weather records that shared one timestamp were reduced to the first (48,204 rows became 40,575 distinct hours); temperatures of 0 K and one rainfall of 9,831 mm were treated as missing; temperature was converted from kelvin to Celsius; `Hour`, `Weekday` (numbered so that it sorts) and `Daypart` were derived from the timestamp; `Month` and `Year` are added in Power Query.
**The record has gaps.** There is no data at all for September 2014 to May 2015, and August 2014 (123 hours) and June 2015 (149) are thin, so totals dip there; the report therefore leads with averages per hour and shows the recorded hours per month on the Seasons page.

## Measures

`Hours of data`, `Average traffic per hour`, `Total vehicles`, `Average temperature`, `Busiest hour` and `Rainy hours share` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
