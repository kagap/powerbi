# Europe on holiday, 2013 to 2025

A seven-page Power BI report on the nights spent at tourist accommodation in 38 European countries, month by month from January 2013 to December 2025 (33,714 records of country, month, kind of guest and kind of accommodation). **Europe averaged 3,007 million nights a year; 45.9% were spent by foreign guests and 43.4% in June to August.** In 2020 the total fell to 1,642 million, 46% of 2019 (3,541 million).

The look is a seaside holiday: a sand page, a **deep teal filter panel on the left** with the lists of countries, guests and accommodation, coral tabs along the top and turquoise and sunshine yellow in the charts. A collapsible **Filters pane** is on the right too. Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| Overview | Four cards with sparklines (nights a year, foreign share, summer share, share of the 2019 level), nights month by month, by kind of accommodation (donut), by year and kind of guest and by country |
| Seasons | A heat table of every country by calendar month (the share of its year's nights), the same share by region group (lines) and the summer share by country |
| COVID | Every month against the same month of 2019, the 2020 to 2021 recovery by country, nights by year and a table of the countries since 2022 with their share of the 2019 level |
| Mix | The split between domestic and foreign guests in every country (100% stacked bars), the kinds of accommodation by region group and the foreign share by region group |
| Countries | A ranked table (nights, foreign share, summer share, recovery), a scatter of the summer share against the foreign share and the hotel share by country |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: **four countries have close to 400 million nights a year or more**: Spain (418 million), France (412), Italy (400) and Germany (384), ahead of the United Kingdom (298) and Türkiye (172). The mix of guests differs a lot: foreign guests are 94.1% of the nights in Malta, 92.5% in Cyprus and 91.5% in Croatia but 18.9% in Germany, 18.4% in Poland and 16.4% in Romania. **The season is sharpest on the Adriatic**: 73% of the nights in Croatia and 67% in Montenegro fall in June to August, with 32% of the year's nights in August in Croatia alone. The COVID years hit some countries much harder than others: in 2020 and 2021 the United Kingdom was at 22% of the 2019 level, Malta at 38%, Cyprus at 38% and Greece at 39%. In total 2022 had 3,115 million nights, 88% of 2019, and 2025 matches 2019 at 3,541 million nights, although the country set is not constant (see below). Camping and caravan sites take 13% of the nights, holiday rentals 22% and hotels 65%; in Cyprus and Türkiye 99.8% to 99.9% are hotel nights.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `TourismEurope.pbip` from this folder (or `TourismEurope.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 33,714 records), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

Eurostat, *Nights spent at tourist accommodation establishments, monthly data* (`tour_occ_nim`, <https://ec.europa.eu/eurostat/databrowser/view/tour_occ_nim>); Eurostat data may be re-used with acknowledgement (see <https://ec.europa.eu/eurostat/about-us/policies/copyright>). Retrieved on 28 October 2026 through the Eurostat dissemination API.
Preparation, stated on the About page: the JSON-stat cube was turned into rows, the aggregate rows (EU27, EU28 and others) and the all-accommodation total were dropped, the countries were put into five groups (Southern, Western, Northern, Central and Eastern Europe, and Turkey), and season, era and the 2019 comparison were added. The report starts in 2013 because before that the data does not cover all three kinds of accommodation in all countries, and it stops at the end of 2025 so that every year is complete.
**Things to keep in mind.** The EU totals are not included, so every sum is a sum of the countries listed, and a country that joins the data later (a few start in 2014 or 2017) adds to the totals from then on, which lifts the later years a little. The comparison with 2019 compares each country, kind of guest, kind of accommodation and calendar month with the same ones of 2019, and leaves out what has no 2019 figure. Seasons are meteorological (summer is June to August). Kosovo is shown without prejudice to positions on status. Nights are nights spent, not trips or visitors.

## Measures

`Nights a year (millions)`, `Foreign share`, `Summer share`, `Share of the 2019 level`, `Countries`, `Domestic nights a year (millions)`, `Foreign nights a year (millions)`, `Hotels share` and `Share of annual nights` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
