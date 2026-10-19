# US tornadoes 1950-2023: where, when and how strong

A seven-page Power BI report on 70,022 tornadoes reported in the United States from 1950 to 2023: where they touched down, in which month and hour, how strong they were, and how many people they killed (6,221 deaths and 98,372 injuries). 646 of them (0.9%) were violent (EF4 or EF5), and they caused 3,857 of the deaths (62%).

The report has a slate-blue page with lightning yellow and cyan, a slim **numbered rail** on the left for the pages, and a collapsible **Filters pane** on the right. Hovering over a bar, slice or point shows a small summary card (a tooltip page).
**There is no map service behind the maps.** Power BI's Bing maps are being retired and the newer Azure Maps visual does not work in Publish to web, so the first page uses a **tile-grid map** (one square for each state, laid out like the country, coloured by the number of tornadoes) and the Dots page plots the starting longitude against latitude of the violent tornadoes.

| Page | What it shows |
|---|---|
| Map | A tile-grid map of the states coloured by tornadoes, cards for tornadoes, deaths and violent tornadoes, tornadoes by decade and by strength group |
| States | Deaths by state, a treemap of tornadoes by state, and deaths against tornadoes by state (scatter) |
| Strength | A funnel of tornadoes by rating (EF0 to EF5), deaths by rating, the share of weak, strong and violent tornadoes by decade, and path width against path length by rating |
| Seasons | Tornadoes by month and strength, by hour of the day, and a heat map of decade by month |
| Dots | The violent tornadoes (EF4 and EF5) where they touched down, sized by deaths, with cards and charts by decade and by state |
| Details | The underlying tornado rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: Texas has the most tornadoes (9,345), then Kansas (4,474), Oklahoma (4,221) and Florida (3,620), but Alabama has the most deaths (677), ahead of Texas (602) and Mississippi (500); May is the peak month (15,225) and 17:00 the peak hour (8,273); 80% are weak (EF0-1); Oklahoma (59) and Texas (57) have the most violent tornadoes; 59 tornadoes were rated EF5. The count rises from 4,793 in the 1950s to about 12,000 a decade from the 1990s, mostly because weak tornadoes are reported more often than they used to be, so counts across decades are not a trend in tornado activity.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `USTornadoes.pbip` from this folder (or `USTornadoes.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 70,022 rows), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

NOAA Storm Prediction Center, Severe Weather Database (1950-2023 actual tornadoes), public domain: <https://www.spc.noaa.gov/wcm/#data>.
Preparation, stated on the About page: state codes were spelled out and given grid positions for the tile map; the 1,024 unrated tornadoes (code -9) are a group of their own; strength is the F scale until 2006 and the EF scale from 2007, grouped as weak (0-1), strong (2-3) and violent (4-5); zero coordinates were treated as missing; the dollar-loss columns were left out because their units changed over the years; a tornado id, hour and month label were added. Puerto Rico and the Virgin Islands are in the data and have a square at the bottom right of the tile map.

## Measures

`Tornadoes`, `Deaths`, `Total injuries`, `Average path length (mi)`, `Violent tornadoes (EF4-5)`, `Deadly tornado share`, `Average path width (yd)` and `State tile` (the label of a square on the tile map) are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
