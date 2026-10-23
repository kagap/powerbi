# Earthquakes of magnitude 6 and over, 1950 to 2025

A seven-page Power BI report on 10,319 earthquakes of magnitude 6.0 and over between 1950 and 2025: about 136 a year, 1,012 of them of magnitude 7 or more and 62 of 8 or more. The strongest in the catalogue is the 1960 Chile earthquake (9.5), followed by Alaska 1964 (9.2) and Sumatra 2004 and Tohoku 2011 (both 9.1).

The report is light grey with a **slim basalt rail** on the left whose numbered buttons (with a tiny caption each) are the page tabs, lava-red accents, and a collapsible **Filters pane** on the right (date, magnitude band, depth class). Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is built around a **dot map made without any map service**: the quakes are counted in 5-degree cells and drawn on longitude and latitude axes, so it works in Publish to web, plus a magnitude chart that shows the **base-10 logarithm** of the counts, where the Gutenberg-Richter law becomes a straight line.

| Page | What it shows |
|---|---|
| Map | Five cards (earthquakes, magnitude 7 and over, largest magnitude, average depth, regions) and the map: one dot for every 5-degree cell, sized by the number of quakes and coloured by depth class |
| Magnitude | A funnel of the five magnitude bands, the base-10 logarithm of the number of quakes for each tenth of a magnitude (a straight line down to magnitude 8.3, then noise from very few events), magnitude 7 and over by year and quakes by decade |
| Depth | Quakes by depth band and depth class, and for every region the share of shallow, intermediate and deep quakes and the average depth |
| Regions | Quakes by region group (bars), a treemap of the regions and a table comparing them (quakes, largest magnitude, average depth, magnitude 7 and over) |
| Time | A heat map of decade by magnitude band, quakes by year, and a table of the great earthquakes (magnitude 8 and over), strongest first |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: every whole point of magnitude means about ten times fewer quakes (9,307 between 6.0 and 6.9, 950 between 7.0 and 7.9, 62 of 8 or more), and 69% of all of them are below 6.5. The count a year stays between 83 (1981) and 207 (2011) with no clear trend; magnitude 7 and over ranges from 6 to 24 a year (2010 has the most). Eighty-two per cent of the quakes are shallower than 70 km and only 6% are deeper than 300 km; the deep ones are in a few places, above all Fiji (217 of the 605 deep quakes), followed by Japan (67), Indonesia (49) and Argentina (36). Indonesia (960), Japan (838), Papua New Guinea (754) and Russia (599) have the most; Chile has the most of magnitude 8 and over (8), ahead of Indonesia (7) and Japan (6). The busiest 5-degree cell is the one around New Britain in Papua New Guinea (287 quakes).

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `Earthquakes.pbip` from this folder (or `Earthquakes.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 10,319 earthquakes), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

US Geological Survey (USGS), ANSS Comprehensive Earthquake Catalog, read through the FDSN event web service (<https://earthquake.usgs.gov/fdsnws/event/1/>), retrieved on 23 October 2026. USGS information and data are generally in the public domain (see <https://www.usgs.gov/legal>); please credit the USGS.
Preparation, stated on the About page: the query was run in slices of up to 15 years (the service returns at most 20,000 events a query), 70 nuclear and other explosions were dropped, and magnitude bands and tenths, depth classes and bands (shallow is under 70 km, deep over 300 km), regions, 5-degree cells (569 of them), decades and hemispheres were added.
**Things to keep in mind.** The catalogue mixes magnitude types (mostly moment magnitude, with surface-wave and body-wave magnitudes for the older events), so magnitudes of different decades are not perfectly comparable. The region is read from the place text (the part after the last comma; the regions of the mid-ocean ridges are grouped and the 20 busiest regions kept, the rest are Other regions), so it is an approximation and not an official boundary. The data has no casualties or damage.

## Measures

`Earthquakes`, `Average magnitude`, `Largest magnitude`, `Average depth (km)`, `Magnitude 7 and over`, `Magnitude 8 and over`, `Share deeper than 300 km`, `Share shallower than 70 km`, `Cell longitude` and `Cell latitude` (the position of a dot on the map), `Regions` and `Log10 of earthquakes` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
