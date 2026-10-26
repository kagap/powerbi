# Chicago's L: 25 years of ridership

A seven-page Power BI report on the boardings at the 148 stations of Chicago's L, month by month from January 2001 to December 2025 (42,786 station-months). Ridership grew from **151.7 million boardings in 2001 to a peak of 198.0 million in 2015**, was 179.1 million in 2019, **fell to 62.3 million in 2020** and has climbed back to **117.5 million in 2025, 65.6% of the 2019 level**.

The look is transit signage: a black bar with the title and **one bullet for every page, each in a colour of the CTA map** (red, blue, green, orange, purple, brown, pink), a light page and a collapsible **Filters pane** on the right (date, line group, era and more). Hovering over a bar, slice or point shows a small summary card (a tooltip page). The charts use the real line colours, and the **dot map of the stations** (longitude and latitude, no map service) draws the shape of the network.

| Page | What it shows |
|---|---|
| Overview | Four tiles with sparklines (rides, average daily boardings per station, stations, share of the 2019 level), rides by month, rides by line group (donut), rides by year in three eras and average daily boardings by line group |
| Recovery | Every month against the same month of 2019, the share of the 2019 level by line group in 2022 to 2025 and a table of all stations since 2022 with their recovery |
| Stations | The map of the stations in 2022 to 2025, a dot for each, sized by the rides and coloured by the line, and a table of the busiest stations |
| Lines | Rides by year for every line group (lines), their share of all rides (100% stacked columns), accessible and other stations, and stations still open in 2025 |
| Rhythm | The share of weekday, Saturday and Sunday or holiday rides by year, the weekday share by line, a heat table of era by month and one line for every era by calendar month |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: the lowest month was May 2020, with 1.83 million boardings, 12% of May 2019; December 2025 was at 64% of December 2019. **The downtown stations lost the most and the airport the least**: Lake/State, the busiest station, had 6.45 million boardings in 2019 and 3.6 million in 2025 (56%), Monroe/State recovered to 46%, while O'Hare Airport went from 3.81 to 3.31 million (87%), the best of the 20 busiest stations of 2019. By line (all stations of the line, 2019 to 2025) the Red Line fell from 52.8 to 32.9 million (62%) and the Blue Line from 43.4 to 28.1 million (65%); the Pink Line recovered the most (77%) and the Yellow Line the least. The rhythm of the week changed too: weekdays were 82.9% of the rides in 2019 and are 77.7% in 2025, with Saturdays up from 9.3% to 12.1% and Sundays and holidays from 7.8% to 10.2%. An average station had 3,429 boardings a day in 2019 and 2,235 in 2025; the busiest month of the year is October, the quietest December and February.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `ChicagoL.pbip` from this folder (or `ChicagoL.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 42,786 station-months), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

Chicago Transit Authority through the City of Chicago Data Portal: *CTA - Ridership - 'L' Station Entries - Daily Totals* (<https://data.cityofchicago.org/resource/5neh-572f>) and *CTA - System Information - List of 'L' Stops* (<https://data.cityofchicago.org/resource/8pix-ypme>); public data published under the portal's terms of use. Retrieved on 26 October 2026.
Preparation, stated on the About page: the daily totals were added up by month, station and day type (weekday, Saturday, Sunday or holiday), joined to the stops by station id, and an era, a line group (one line, or Multiple lines for a transfer station), the 2019 comparison and the status in 2025 were added. 2026 is left out because the year is not complete.
**Things to keep in mind.** A ride is a person entering a station, not a trip. Four stations in the data have since closed or been replaced and have no line data; they stay under Closed station. The share of the 2019 level compares every station and month with the same station and calendar month of 2019, and a station with no 2019 figure is left out of the comparison. Station names are those of the CTA list at the time of retrieval.

## Measures

`Rides`, `Average daily boardings per station`, `Stations`, `Weekday share`, `Share of the 2019 level`, `Station latitude` and `Station longitude` (the position of a dot on the map), `Weekday rides`, `Saturday rides` and `Sunday and holiday rides` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
