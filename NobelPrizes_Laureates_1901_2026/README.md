# Nobel Prizes 1901 to 2026: who wins

A seven-page Power BI report on 1,036 Nobel Prize entries from 1901 to 2026, one for every laureate and prize: 1,028 different laureates, 31 of them organizations, and 639 prizes. The average laureate was 60.6 years old, 6.8% of the entries are women and the laureates were born in 86 countries.

The report is near-black with ivory text and gold, a **serif title on the left and the pages in small capitals on the right** under a double gold rule, and a collapsible **Filters pane** on the right (category, decade, gender and more). Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is built around a **dot plot of ages** (one dot for every laureate, coloured by field), a **100% stacked area chart** of the continents, a heat table of countries and fields, and ranked tables of the oldest, the youngest and the women.

| Page | What it shows |
|---|---|
| Overview | Five cards (laureates, prizes, share of women, average age, countries), laureates by decade and field (stacked columns), the share of each continent by decade (100% stacked area), laureates by country of birth and the age dot plot |
| Age | The dot plot at full size, average age by decade for each field (lines), laureates by age band, and two tables: the oldest (80 and over) and the youngest (under 40) |
| Women | Share of women by decade, women by field, the share of men, women and organizations by decade, and a table of every woman laureate, latest first |
| Places | A heat table of country group by field, a treemap of the countries of birth, laureates by continent and the share of the main countries by era |
| Shared | How the prizes came to be shared: the share of entries by number of laureates and decade, laureates per prize by decade, and laureates by field and sharing |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: the average age at the award grew from 54.6 in 1901-1945 to 58.1 in 1946-1989 and 66.0 in 1990-2026; economists (67.2) and writers (65.0) are the oldest and physicists (57.8) the youngest. The youngest is Malala Yousafzai (17, Peace, 2014), the oldest John B. Goodenough (97, Chemistry, 2019). The United States is the birthplace of 309 laureates (30%), ahead of the United Kingdom (97), Germany (86) and France (66), and its share rose from 12% of the entries in 1901-1945 to 38% in 1990-2026; since 2000 North America (131) has overtaken Europe (117). The first woman appears in 1903, there are none in the 1950s, and the share of women reaches 10.7% in the 2010s and 18.6% in the 2020s (so far; Peace has the most, 21 of 70, and Literature 19). Sharing changed completely: 64% of the entries of 1901-1945 belonged to a prize with a sole laureate, against 20% in 1990-2026, when 53% belonged to a prize shared by three.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `NobelLaureates.pbip` from this folder (or `NobelLaureates.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 1,036 rows), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

NobelPrize.org, API 2.1 (<https://api.nobelprize.org/2.1/laureates>), free to use under the Creative Commons Zero (CC0) licence according to the API terms (<https://www.nobelprize.org/about/terms-of-use-for-api-nobelprize-org-and-data-nobelprize-org/>), retrieved on 23 October 2026. The 2026 prizes are included as the API listed them on that day.
Preparation, stated on the About page: the nested records were flattened to one row for every laureate and prize, and decades, eras, age bands, the number of laureates sharing the prize (`Prize_shared`), a unique prize key (`Prize`) and a country group (the 14 countries with most laureates, the others as Other) were added.
**Things to keep in mind.** A person who won twice (or the Red Cross three times) is counted once for each prize. Age at the award is the award year minus the birth year, so it can be one year too high, and organizations have no age. The country is the current country of birth as named by the API (the place of founding for an organization), so places that changed hands appear under today's country. Economics is the Sveriges Riksbank Prize in Economic Sciences in Memory of Alfred Nobel, first awarded in 1969.

## Measures

`Laureates`, `Prizes awarded`, `Share of women`, `Women`, `Average age`, `Median age`, `Countries`, `Laureates per prize`, `Youngest`, `Oldest` and `Award year` (the average year, used on the dot plot) are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
