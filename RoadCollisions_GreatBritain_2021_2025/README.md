# Britain's roads: 513,801 collisions, 2021 to 2025

A seven-page Power BI report on the road collisions in Great Britain that were reported to the police and in which someone was injured, January 2021 to December 2025: **513,801 collisions, 652,821 casualties and 937,265 vehicles**. 7,553 of the collisions were fatal (1.5%) and 116,813 serious (22.7%), so **24.2% were fatal or serious**, and there were 14.7 fatal collisions for every 1,000. The yearly count hardly moves: 101,087 in 2021, 106,004 in 2022, 104,258 in 2023, 100,927 in 2024 and 101,525 in 2025.

The look is a road: a **tarmac bar with a dashed yellow centre line** and the pages as road signs (blue, with the open page in yellow), a light grey page and white cards. A collapsible **Filters pane** is on the right (police force, severity, road class, speed limit, light and more). Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| Roads | Five cards with sparklines (collisions, casualties, fatal collisions, the fatal or serious share and casualties per collision), collisions by month with the fatal or serious share as a line, severity (donut), collisions by calendar month with a line for each year, and fatal collisions per 1,000 by nation |
| Time | **A heat table of weekday by hour**, collisions by hour of the day stacked by severity, the fatal or serious share by hour and fatal collisions per 1,000 by time of day |
| Conditions | The fatal or serious share by light, by weather and by road surface (three bar charts), collisions by weather (funnel) and the share of each severity by light |
| Speed | Collisions, fatal collisions per 1,000 and casualties per collision by speed limit, a heat table of road class by speed limit and a treemap of the road types |
| Places | **A bubble map of the 44 police forces** of Great Britain (size: collisions; colour: nation) and a table comparing the forces |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: **speed is what kills**. Fatal collisions per 1,000 rise from 4.7 on 20 mph roads and 8.7 on 30 mph roads to 18.0 at 40 mph, 28.9 at 50 mph, 38.4 at 60 mph and 33.7 at 70 mph, even though 52% of all collisions (267,325) happen on 30 mph roads. Rural roads have 32.8% of the collisions and 28.3 fatal ones per 1,000, urban roads 8.0. **Night is the dangerous time**: 34.8 fatal per 1,000 between midnight and 5:59, against 11.3 to 13.0 in the rush hours and the day, and 30.8% of the 3 a.m. collisions are fatal or serious against 19.4% at 8 a.m. Collisions peak with the afternoon traffic: 25.3% fall between 15:00 and 17:59, the busiest weekday and hour is Friday at 15:00 (7,671 collisions in five years), and the quietest are 3 to 4 a.m. on weekdays. 28.3% of the collisions happen in the dark, and the fatal or serious share is 34.9% on roads without street lighting against 23.2% in daylight. 80.5% of the collisions happen in fine weather and 25.2% on a wet, icy or snowy surface. The Metropolitan Police area has 110,585 collisions (21.5%) but, of the large forces, the fewest fatal ones per 1,000 (4.3; only the tiny City of London force is lower, at 3.4). The three nations differ widely (fatal collisions per 1,000: England 13.4, Wales 26.7, Scotland 34.9), but the share of serious collisions in the Scottish and some Welsh forces (42.5% for Police Scotland, 36.4% for North Wales) is so much higher than in London (16.4%) that part of the gap may come from which injuries are reported, and not only from the roads.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `RoadCollisions.pbip` from this folder (or `RoadCollisions.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 484,971 groups of collisions), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

Department for Transport, Road Safety Data (STATS19), the collision file for the last 5 years (<https://data.dft.gov.uk/road-accidents-safety-data/dft-road-casualty-statistics-collision-last-5-years.csv>). Retrieved on 30 October 2026. The DfT statistics pages on GOV.UK are published under the Open Government Licence v3.0; no licence line was found on the data file itself.
Preparation, stated on the About page: the standard STATS19 codes were turned into words (the police force names were checked against the positions of the collisions of each force), the hour was taken from the time, and the collisions were grouped: every row is the number of collisions (with their casualties and vehicles) that share the same month, weekday, hour, police force, severity, road class, road type, speed limit, light, weather, road surface and urban or rural area. Nothing was dropped or sampled, and the totals of the groups equal the totals of the file. The map dots sit at the middle of each force's collisions.
**Things to keep in mind.** Only collisions with an injury that the police recorded are in the data, so damage-only collisions and many slight injuries are missing, and the recording practice differs between forces. Northern Ireland is not covered. A row on the Details page is a group of collisions and not one collision. The date is the first day of the month. A few collisions list very many casualties (the largest lists 142), which lifts the averages a little. Severity is the police's own, and the fatal or serious share counts collisions and not casualties.

## Measures

`Collisions`, `Casualties`, `Fatal collisions`, `Serious collisions`, `Fatal or serious share`, `Casualties per collision`, `Vehicles per collision`, `Dark share`, `Wet or icy share`, `Fatal collisions per 1,000`, `Force latitude` and `Force longitude` (the position of a dot on the map), `Collisions a month` and `Rural share` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
