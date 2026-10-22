# America's biggest cities, 1790 to 2020

A seven-page Power BI report on the ten most populous places in the United States at each of the 24 censuses from 1790 to 2020: 241 entries (the tenth place was shared in 1790) and 32 different places. **New York is first in all 24 censuses**: 33,131 people in 1790 and 8,804,190 in 2020.

The report looks like a newspaper front page: a serif masthead between double rules, small-caps sections instead of tabs, black and red on newsprint, flat square cards, and a collapsible **Filters pane** on the right. Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is built around a **bump chart** (rank over time, 1 at the top), which no other report in this repository has, plus ribbons, a heat table of ranks and a table of the latest top 10.

| Page | What it shows |
|---|---|
| Bump chart | Four cards (places, entries, average growth, largest city); the rank of the places that stayed in the top 10 for six censuses or more (a bump chart, 1 is the largest), places in the top 10 by region and the number of censuses each place stayed |
| Flows | Ribbons of population by census (who overtook whom), the share of new entrants in each census, and growth against the previous census |
| Rank table | A table of every place by census, showing its rank, coloured so that the nearer the top, the stronger the red |
| Staying power | Rank change summed over the censuses, average rank against the number of censuses (scatter), and places by region |
| Size | Population of the regular places by census, a treemap of the latest top 10 and a table of that top 10 |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: Philadelphia was second in the first four censuses, Baltimore second from 1830 to 1850, Philadelphia again from 1860 to 1880 (after its 1854 consolidation), **Chicago second from 1890 to 1980** (it first appears in 1860) and Los Angeles second since 1990 (it first appears in 1920). The Northeast held nine of the ten places in 1790 and two in 2020; the first western place is San Francisco in 1870 and the West holds four in 2020 (Los Angeles, Phoenix, San Diego, San Jose). The biggest jump in the data is Detroit from 9th to 4th in 1920, the biggest fall Charleston from 6th to 10th in 1840. Houston first appears in 1960 and Phoenix in 1980.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `USCities.pbip` from this folder (or `USCities.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 241 entries), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

Wikipedia, *List of most populous cities in the United States by decade* (<https://en.wikipedia.org/wiki/List_of_most_populous_cities_in_the_United_States_by_decade>), text licensed CC BY-SA 4.0, compiled from US Census Bureau counts; retrieved on 22 October 2026.
Preparation, stated on the About page: footnote marks and notes were removed and the population counts read as numbers; the tied tenth place of 1790 (Marblehead and Southwark) is kept as two entries; regions follow the Census Bureau (the Territory of Orleans and the District of Columbia count as South); and previous rank, rank change, growth, the number of appearances and a group (a regular is in the top 10 for six censuses or more) were added.
**Places are as they were counted then.** Brooklyn, Northern Liberties, Southwark and Spring Garden appear on their own before they became part of larger cities, and a city's jump in growth can come from a merger (Philadelphia's +366% in 1860 follows its 1854 consolidation) rather than from people arriving.

## Measures

`Entries`, `Rank (1 is the largest)` (shown without the minus sign so that 1 is at the top), `Residents`, `Average rank`, `Best rank`, `Censuses in the top 10`, `Rank change vs previous census`, `Growth vs previous census (%)`, `Cities`, `Rank score (11 minus rank)` (only for the colours), `Largest city (people)` and `Rank in the census` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
