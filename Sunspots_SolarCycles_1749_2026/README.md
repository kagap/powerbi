# Sunspots since 1749: the Sun's cycles

A seven-page Power BI report on 3,333 months of the international sunspot number, from January 1749 to September 2026, split into the 25 solar cycles it contains. The monthly number averages 82.2; a cycle lasts 11.0 years on average (from 9.0 years for cycle 2 to 13.6 for cycle 4) and the strongest, cycle 19, peaked at 285 in 1958.

The report is deep indigo with an orange and yellow palette, **a glowing sun next to the title and the pages as dots on an orbit line**, round cards, and a collapsible **Filters pane** on the right (date, cycle, decade and more). Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is built around **one line for every cycle drawn from its own minimum** (so the cycles can be laid on top of each other) and a **heat map of cycle by year of the cycle**.

| Page | What it shows |
|---|---|
| Overview | Five cards (months, average number, highest month, cycles, share of quiet months), the monthly number with its 13-month smoothed line, the peak of every cycle and the months by activity band (donut) |
| Cycles | The smoothed number of cycles 1 to 12 and of cycles 13 to 25, each line starting at that cycle's minimum, the typical cycle (average by year of the cycle) and the length of every completed cycle |
| Heat map | Every cycle (row) by year of the cycle (column), coloured by the average monthly number |
| Strength | Peak against cycle length (a dot for every cycle), a table of the cycles by peak, the highest month in each cycle and the average by century |
| Quiet times | The share of months by activity band for every decade, quiet months by decade and the average by calendar month |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: the strongest cycles are 19 (285.0, March 1958), 3 (264.2) and 8 (244.9) and the weakest are cycles 5 and 6 (82.0 and 81.2, the Dalton minimum, when 36% of the months from 1800 to 1829 were quiet against 21% over the whole record), then cycle 14 (107.1) and cycle 24 (116.4, the weakest since cycle 14). Cycle 25 has so far peaked at 160.9 in October 2024, well above cycle 24. A cycle reaches its maximum on average 4.4 years after its minimum (47 months in cycle 19, 64 in cycle 24), so the rise is faster than the decline. The highest single month is May 1778 (398.2) but from before 1849, when observations were sparse; since 1849 it is October 1957 (359.4). The calendar month makes no difference (79.0 to 83.9 on average), the Sun has no seasons.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `Sunspots.pbip` from this folder (or `Sunspots.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 3,333 months), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

SILSO World Data Center, Royal Observatory of Belgium: monthly mean total sunspot number, version 2.0 (<https://www.sidc.be/SILSO/INFO/snmtotcsv.php>), licence CC BY-NC (the SILSO data policy), retrieved on 23 October 2026.
Preparation, stated on the About page: the missing standard deviations and observation counts of the early years were left empty, and the 13-month smoothed number, the solar cycle, the year of the cycle, the cycle length and peak, decades, centuries, activity bands (quiet is under 20) and a data-quality flag were added.
**Things to keep in mind.** The smoothed number is calculated here with the usual weights (half weight on the two end months), so it is empty for the first and last six months. The cycle boundaries are found from the data, as the month with the lowest smoothed number around each of the 25 known solar minima, and may differ by a few months from the published dates. Cycle 25 is still running, so its peak is the peak so far and it has no length yet. Before 1849 the observations are sparse and the numbers less certain, and the last three months are provisional.

## Measures

`Months`, `Average sunspot number`, `Smoothed number (13 months)`, `Highest month`, `Peak of the smoothed number`, `Cycles`, `Cycle length (years)`, `Share of quiet months` and `Quiet months` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
