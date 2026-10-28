# LEGO since 1949: 26,932 sets

A six-page Power BI report on the 26,932 LEGO sets released from 1949 to 2025 in the Rebrickable database. **Rebrickable lists the parts of 19,359 of them, 4.3 million parts in all**: the average set has 222 parts but the median only 57, because 62% of the sets have fewer than 50 parts. **863 sets have 1,000 parts or more**, and 454 of those came out in the 2020s.

The look is a toy-brick catalogue: a yellow bar with a **row of studs along the top**, the title in black, the pages as red and white blocks, white cards with thin black borders and a collapsible **Filters pane** (root theme, decade, size band and more). Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| Bricks | Five cards (sets, total parts, average parts, largest set, themes), sets by year of release (columns), the average parts per set by year, a treemap of the root themes and the sets by size band (donut) |
| Themes | Sets by root theme (bars), a scatter of the average parts against the number of sets for every theme (a dot a theme, sized by the total parts) and a table of the themes by total parts |
| Growth | The share of size bands in each decade (100% stacked columns), the median parts per set by decade and sets by year and size band |
| Giants | The sets with the most parts (a table with a colour scale), the largest set by decade and the sets with 1,000 parts or more by decade |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: **the catalogue is dominated by small things**. The most sets belong to the root theme Gear (5,871, gear items rather than buildable models), then Duplo (1,443), Books (1,376), Educational and Dacta (1,114) and Star Wars (1,047); Star Wars also has the most parts of all themes (about 0.4 million), ahead of Technic and Creator. The year with the most sets is 2025 (1,437), and the 2010s alone have 9,287 sets, a third of the catalogue. **Sets got bigger at the top, not across the board**: the median set had 6 parts in the 1950s, 56 in the 1970s and 115 in the 2020s, yet about 63% of the sets of the 2020s still have fewer than 50 parts (91% in the 1950s), while the sets with 1,000 parts or more went from 1 in the 1980s to 454 in the 2020s. The biggest sets are **World Map (11,695 parts, 2021)**, the Eiffel Tower and The Ultimate Battle for Chima (10,001 parts each, 2022 and 2015), the Titanic (9,092), the Colosseum (9,036) and the Death Star (9,031).

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `LegoSets.pbip` from this folder (or `LegoSets.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 26,932 sets), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

Rebrickable (<https://rebrickable.com/downloads/>), the files `sets.csv` and `themes.csv`, retrieved on 28 October 2026. The files carry no separate licence text and Rebrickable asks to be credited as the source. LEGO is a trademark of the LEGO Group, which does not sponsor or endorse this report.
Preparation, stated on the About page: the theme tree was walked up to the top-level theme, sets announced for 2026 and 2027 were left out so that every year is complete, a parts count of zero was left empty, and decade and size bands were added.
**Things to keep in mind.** Rebrickable lists no parts for some items (gear, books, promotional items), so the number of parts is empty for 7,573 sets and the averages, medians and size bands use only the sets that have a parts count. The theme is the top-level theme of the set; themes were renamed and merged over the years. Years are years of release. The sets are a catalogue of what was released, not of what was sold, and a re-release counts as another set.

## Measures

`Total parts (millions)`, `Average parts per set`, `Median parts per set`, `Largest set (parts)`, `Themes`, `Sets with 1,000 parts or more`, `Share of sets with 1,000 parts or more`, `Sets with a parts count` and `First year` are defined in the model and listed with their DAX on the About page; the number of sets is a count of rows.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
