# Who lives in America: age, sex and generations

A seven-page Power BI report on the civilian resident population of the 50 states and the District of Columbia on 1 July of 2020 to 2024, by single year of age and sex (43,860 rows). In 2024 there are 339.1 million people with an average age of 39.7 (39.0 in 2020); 18.0% are 65 or older (16.5% in 2020) and 17.6% are under 15.

The report has pink and lavender pastels, **very round cards**, a **floating side card** with the pages, and a collapsible **Filters pane** on the right (year, region, state and sex). Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is built around **population pyramids**: stacked bars with men mirrored to the left and women to the right, plus a tile-grid map of the states made without any map service.

| Page | What it shows |
|---|---|
| Pyramid | Residents, average age, shares of 65 and over and of under 15, women per 100 men; the pyramid by five-year age group, residents by single year of age and by life stage |
| Years | The pyramids of 2020 and of 2024 side by side, and the change by age group between them |
| States | A tile-grid map of the states coloured by the share of people 65 and over, that share against the share under 15 (scatter) and average age by state |
| Regions | Four pyramids: Northeast, Midwest, South and West |
| Generations | Residents by age group and generation, by year and generation, and a treemap of regions |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: between 2020 and 2024 the population grew 2.6%, but people aged 65 and over grew from 54.5 to 61.2 million while children under 15 fell from 61.3 to 59.7 million; the biggest gain is in the 75-79 group (+2.3 million) and the biggest loss in the 55-59 group (-1.7 million). Maine is the oldest state (average age 43.6, 23.5% aged 65 and over) and Utah the youngest (34.7; 12.4% aged 65 and over, 21.6% under 15). There are 104 boys for every 100 girls at age 0 but 167 women for every 100 men aged 85 and over. Millennials are the largest generation (21.7%), ahead of Gen Z (20.7%), baby boomers (19.7%) and Gen X (19.3%).

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `USPopulation.pbip` from this folder (or `USPopulation.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 43,860 rows), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

US Census Bureau, Population Estimates Program, *State Population by Characteristics: 2020-2024* (file `sc-est2024-agesex-civ.csv`, vintage 2024, civilian population), public domain, retrieved on 22 October 2026: <https://www.census.gov/data/tables/time-series/demo/popest/2020s-state-detail.html>.
Preparation, stated on the About page: the wide table (one column a year) was turned into rows, the national and sex-total rows were left out, state names got postal codes and a position on a tile grid, and age groups, life stages and generations (from the year of birth, the estimate year minus the age) were added. Everyone aged 85 and over is in the age 85 group, so the average age is slightly low.
**Every measure counts one year at a time**, the latest in the current selection (2024 unless the Filters pane or a visual says otherwise), because the table holds five years of the same people.

## Measures

`Records`, `Residents`, `Women`, `Men`, `Men (mirrored)` (negative, shown without a sign, for the left side of the pyramid), `Average age`, `Share 65 and over`, `Share under 15`, `Women per 100 men`, `Dependants per 100 of working age`, `State tile` (the label of a square on the tile map) and `Change 2020 to 2024` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
