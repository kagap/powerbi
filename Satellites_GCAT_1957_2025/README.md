# Satellites since 1957: 25,278 payloads

A seven-page Power BI report on the 25,278 payloads (satellites, probes and other spacecraft) launched from 1957 to 2025 in Jonathan McDowell's General Catalog of Artificial Space Objects: **6,730 launches, 34,145 tonnes of mass and 121 countries and agencies**. 16,248 of the payloads (64.3%) have no decay date in the catalogue, 89.4% went into low Earth orbit and the median payload weighs 370 kg, while 3,113 weigh under 10 kg.

The look is a blueprint: drawing-board blue with pale lines, cyan and orange, **a dark menu on the left with the open page in orange**, square outlined cards and a collapsible **Filters pane** (country, constellation, orbit, mass band and more). Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| Launches | Five cards with sparklines (payloads, launches, share still up, mass launched in tonnes, countries), payloads by year of launch stacked by orbit, by country group (donut), by constellation and by fate (donut) |
| Constellations | **A stacked area of the constellations since 1995**, payloads per launch by year, **a ribbon chart** of the rocket families by decade and a table comparing the constellations |
| Orbits | Low Earth orbit: the average altitude against the average inclination for every constellation (a scatter), the payloads by orbit (donut), a heat table of altitude band by inclination band and the share of inclination bands by decade |
| Countries | **A 100% stacked area** of the share of payloads by country group and year, mass launched by decade and country, and a table of the countries and agencies |
| Rockets | Payloads by rocket family and payloads per launch by rocket family, payloads by mass band (funnel) and the heaviest payloads |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: **2025 is the busiest year by far, with 4,511 payloads** (232 in 2015 and 1,248 in 2020) and 315 launches. The reason is Starlink: its 10,749 payloads are 42.5% of everything ever launched (the first in 2019) and 70.3% of those of 2025, and 83.2% of them are still up. Payloads per launch were 1.0 to 1.6 until the 2000s, 3.1 in the 2010s and are 13.1 in the 2020s, and Falcon rockets, with 22.4 payloads per launch, carried 81.3% of the payloads launched since 2020. The United States launched 15,528 payloads (61%), the Soviet Union 3,347 (from 1957 to 1991), China 1,725 (from 1970) and Russia 1,189. 1,348 payloads went to geostationary and geosynchronous orbits. Small constellations differ in how long they last: 99.7% of OneWeb and 96.7% of Kuiper payloads are still up, but only 16.0% of Flock and none of the SpaceBEE cubesats. The heaviest payloads in the catalogue are Space Shuttle orbiters, led by Discovery (STS-102, 2001) and Columbia (STS-109, 2002) at 104,420 kg each, and 236 payloads weigh 10 tonnes or more.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `Satellites.pbip` from this folder (or `Satellites.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 25,278 payloads), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

Jonathan C. McDowell, General Catalog of Artificial Space Objects (GCAT, <https://planet4589.org/space/gcat/>): the files `satcat.tsv`, `launchlog.tsv` and `orgs.tsv`, data update of 29 October 2026, retrieved on 30 October 2026. No licence text was found on the GCAT pages that were read; the catalogue is the work of Jonathan McDowell and should be credited to him.
Preparation, stated on the About page: only the objects of type P (payloads) launched up to 2025 (rocket stages, debris and other pieces are left out, and so are the launches of 2026), the state names from the organisations file, the perigee, apogee, inclination and mass turned into numbers, and bands, the orbit group, the fate, the constellation and the rocket family added.
**Things to keep in mind.** The orbit group is a rule of this report applied to the catalogue's canonical perigee and apogee (low Earth orbit is an apogee under 2,000 km, medium Earth orbit a perigee of 2,000 km or more and an apogee under 34,000 km, geostationary and geosynchronous is what GCAT marks as a geostationary-type orbit, and the rest is elliptical or transfer), not the catalogue's own class. Still up means the catalogue lists no decay date, and decayed or re-entered means it does. The country is the state of the owner or operator, and the Soviet Union and Russia are separate. The constellation is read from the first letters of the payload name, so a payload with an unusual name falls under Other, and the rocket family comes from the launch log. A launch counts once however many payloads it carried. Masses are the catalogue's best figures and many of them are estimates.

## Measures

`Launches`, `Payloads still up`, `Share still up`, `Mass launched (tonnes)`, `Average mass (kg)`, `Median mass (kg)`, `Countries`, `Average altitude (km)`, `Average inclination (degrees)`, `Starlink payloads`, `Starlink share`, `Heaviest payload (kg)`, `Payloads per launch` and `First year` are defined in the model and listed with their DAX on the About page; the number of payloads is a count of rows.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
