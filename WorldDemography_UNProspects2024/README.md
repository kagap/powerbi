# The world's people, 1950 to 2100

A seven-page Power BI report on the United Nations *World Population Prospects 2024* (medium variant): 237 countries and areas for every year from 1950 to 2100, 35,787 country-years. **The world had 2,493 million people in 1950 and has 8,092 million in 2023. The UN projects a peak of 10,289 million in 2084, and 10,180 million in 2100.** Fertility falls from 4.85 children per woman in 1950 to 2.25 in 2023 and 1.84 in 2100, life expectancy rises from 46.4 to 73.2 and 81.7 years, and the median age from 22.2 to 30.4 and 42.1 years.

The look is an atlas report: a pale blue-grey page, UN blue and navy, a title with **the pages as folder tabs hanging on a thick blue rule**, white cards and a collapsible **Filters pane** (region, subregion, period, decade and more). Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| World | Five cards (population 2023 and 2100, life expectancy, fertility and median age in 2023), the population by year and region (stacked areas), 2023 against 2100 by region (bars), and the fertility and life expectancy of every region by year (lines) |
| Countries | **A bubble chart with a play axis**: a bubble for every country, fertility against life expectancy, sized by population and coloured by region, with a year slider and a play button from 1950 to 2100 |
| Ageing | A heat table of the median age of every subregion by decade, the median age by region, the share of countries by age band and decade and the median age of the world |
| Growth | Two ranked tables: the countries that grow most and shrink most between 2023 and 2100, with the change as a colour scale |
| Lives | Infant mortality by region and year, and four donuts of the countries by fertility band and by life expectancy band in 2023 and 2100 |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: **the growth moves to Africa**. Africa goes from 1,481 million in 2023 to 3,814 million in 2100 (about 37% of the world), Asia from 4,778 to 4,613 million, Europe from 746 to 592 and Latin America and the Caribbean from 659 to 613 million; Northern America grows from 383 to 475 million. Of the 161 countries with 1 million people or more in 2023, **63 have fewer people in 2100**, and 111 of all 237 countries and areas shrink. Among the countries of 1 million or more, the biggest growth is Angola (+308%), the Democratic Republic of the Congo (+307%) and Tanzania (+295%), the biggest decline is Hong Kong SAR (-72%), Puerto Rico (-69%) and Jamaica (-62%); China goes from 1,423 to 633 million (-55%). All of this is a scenario: the medium variant assumes paths for fertility, mortality and migration, and the further the year, the wider the uncertainty.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `WorldDemography.pbip` from this folder (or `WorldDemography.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 35,787 country-years), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

United Nations, Department of Economic and Social Affairs, Population Division, *World Population Prospects 2024*, Demographic Indicators, medium variant (<https://population.un.org/wpp/>). The Population Division publishes the data under the Creative Commons licence CC BY 3.0 IGO; this is stated from its terms of use and the page was not re-read when this report was made, so check it before reusing the data. Retrieved on 28 October 2026.
Preparation, stated on the About page: only the 237 countries and areas for 1950 to 2100, 22 of the indicators, the region and subregion from the UN's hierarchy (Northern America is its own region, as the UN's geographic regions split the Americas), the UN's aggregates joined to every country row, and bands for fertility, life expectancy, median age and population size.
**Things to keep in mind.** The years to 2023 are the UN's estimates, which in many countries rest on censuses, surveys and models rather than a count; the years from 2024 are a projection. Population is the population on 1 July, in thousands. The world, region and subregion figures for fertility, life expectancy, median age and infant mortality are the UN's own aggregates, so they are not simple averages of the countries, while sums of population are sums of the countries. The bubble chart uses the figures of each country. Names are the UN's names (for example China, Hong Kong SAR), and small areas are included, which is why some countries show 0 million in the tables of the Growth page.

## Measures

`Population (millions)`, `Population 2023 (millions)`, `Population 2100 (millions)`, `Change 2023 to 2100`, `World fertility`, `World life expectancy`, `World median age`, `Region fertility`, `Region life expectancy`, `Region median age`, `Subregion median age`, `Country fertility`, `Country life expectancy`, `Births (millions)`, `Deaths (millions)`, `World infant mortality`, `Region infant mortality`, `Countries`, `Life expectancy 2023`, `Fertility 2023`, `Median age 2023` and `Median age 2100` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
