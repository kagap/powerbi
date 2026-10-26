# Near-Earth objects: 42,796 rocks near our orbit

A seven-page Power BI report on 42,796 near-Earth asteroids from the JPL Small-Body Database (26 October 2026): **2,550 are classed as potentially hazardous (6.0%) and 935 are larger than a kilometre**, and the median object is only about 54 metres across. 83% of them were first observed since 2010: the year with most is 2025 (3,157), before 2000 only 1,346 were known.

The report is a **radar screen**: green-black, phosphor mint and amber, a dark rail with the pages on the right, a radar disc at the foot of the rail and a collapsible **Filters pane** (orbit class, hazard flag, size band and more). Hovering over a bar, slice or point shows a small summary card (a tooltip page). The orbit map is drawn from the data itself: a dot for every cell of semi-major axis and eccentricity, with no map service involved.

| Page | What it shows |
|---|---|
| Sky | Five cards (objects, potentially hazardous, larger than 1 km, median size, share hazardous), objects by year of the first observation and size band (stacked columns), by orbit class, by size band and by hazard flag |
| Orbits | **Orbit space**: semi-major axis (in AU) against eccentricity, a dot for every cell sized by the objects and coloured by orbit class, objects by tilt of the orbit and by orbit shape |
| Size | The share of size bands by discovery decade, measured against estimated sizes, objects by absolute magnitude and the median size by discovery decade |
| Hazards | The potentially hazardous objects ranked by size (with the closest orbit gap and the year first seen), hazardous objects by orbit class and objects by orbit gap |
| Discovery | Objects by year of the first observation since 1980, the share of orbit classes by decade and objects by how well the orbit is known |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: **the survey found the big ones first**. Half of the objects first seen in the 1980s are larger than a kilometre (median size 1,006 m), against 6% in the 2000s and 0.7% in the 2010s; the median size of the objects of the 2020s is 35 m. 57% of the objects are Apollo asteroids, 35% Amor, 8% Aten and 39 are Atira. The potentially hazardous ones are mostly Apollos (2,188 of the 2,550), with a median size of 274 m, and 159 of them are larger than a kilometre. The largest object in the table is 1036 Ganymed (about 38 km), then 3552 Don Quixote (19 km) and 433 Eros (17 km), all Amors. Most orbits are elongated (59% have an eccentricity of 0.4 or more) and tilted only a little (72% under 15 degrees), and only 26% of the orbits are well determined (condition code 0 to 2) against 64% poorly known (6 to 9).

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `NearEarthObjects.pbip` from this folder (or `NearEarthObjects.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 42,796 objects), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

NASA/JPL Solar System Dynamics, Small-Body Database Query API (<https://ssd-api.jpl.nasa.gov/doc/sbdb_query.html>), NASA data; the API page states no separate licence, please credit the JPL Small-Body Database. Retrieved on 26 October 2026.
Preparation, stated on the About page: the four near-Earth orbit classes (Amor, Apollo, Aten, Atira), objects with a known absolute magnitude and a first observation, the year of the first observation, the estimated size (1329 / sqrt(0.14) * 10^(-H/5) kilometres), the orbit gap in lunar distances, and bands for size, discovery decade, orbit shape, tilt and orbit certainty (the JPL condition code).
**Things to keep in mind.** Only 1,244 objects have a measured diameter; for the other 41,552 the size is estimated from brightness with an assumed albedo of 0.14, a rough guess that can be off by a factor of two or more, and the small ones are the hardest to judge. The year of discovery is the year of the first observation on record, which can include old images found later. Potentially hazardous is the JPL flag (an orbit that comes within 0.05 AU of the Earth's and an object larger than about 140 m) and does not say that an impact is expected. The orbit gap is the closest the two orbits come, not the distance of a predicted pass. The few hundred objects with a semi-major axis above 3.6 AU are off the orbit map.

## Measures

`Objects`, `Potentially hazardous`, `Share potentially hazardous`, `Larger than 1 km`, `Median size (m)`, `Average eccentricity`, `Average inclination (degrees)`, `Average semi-major axis (AU)`, `Cell semi-major axis` and `Cell eccentricity` (the position of a dot on the orbit map), `Closest orbit gap (lunar distances)` and `First seen` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
