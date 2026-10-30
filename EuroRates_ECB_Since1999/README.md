# The euro against 39 currencies since 1999

A seven-page Power BI report on the European Central Bank's euro reference rates: how many units of 39 foreign currencies one euro bought on every fixing day from 4 January 1999 to 30 October 2026, 221,702 rates in all. **The euro bought 1.1789 US dollars on its first day and 1.1172 on the last.** In between it reached 1.599 dollars on 15 July 2008 and fell to 0.8252 on 26 October 2000, and it was worth less than a dollar on 753 fixing days between 27 January 2000 and 10 November 2022.

The look is a banknote: pale mint paper, deep green bars at the top and the bottom with gold, and **the pages as tabs along the bottom edge**. White cards carry sparklines and a collapsible **Filters pane** (currency, region group, status and era). Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| Rates | Four cards with sparklines (US dollars, pounds, yen and Swiss francs per euro) and the number of currencies, the strength of eight big currencies against the euro by month (2015 = 100), the strength by region group, the dollar rate as an area and the volatility by era |
| Years | **A heat table of the euro's change over the year**: every currency by year, the stronger the colour the more the euro gained (the colours are capped at 30% so that one wild year does not wash out the rest) |
| Shocks | Currencies ranked by volatility with their biggest one-day rise and fall of the euro, the biggest moves of any currency by year (two lines) and the volatility by region group |
| Ranks | **A ribbon chart** that ranks the eight big currencies by strength against the euro every year, and the euro's change against the dollar and against the pound year by year |
| Lives | Every currency with its status, first and last fixing and number of rates, the currencies by status (donut) and by region group |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: **the euro against the dollar has no direction**: it gained in 12 of the 27 years with a change (+20.4% in 2003 and +19.0% in 2002) and lost the most in 2005 (-13.4%), 2014 (-12.0%) and 2015 (-10.3%). Against the pound the euro gained 29.9% in 2008, its best year, and its record (0.97855 pounds on 29 December 2008) is from that year; on 24 June 2016, the day after the UK's EU referendum, it rose 5.4% in one day. Against the yen it went from 133.73 to 175.68 and set a record of 187.72 on 17 April 2026, and against the Swiss franc from 1.6168 to 0.9194, with a low of 0.9008 on 9 March 2026; **on 15 January 2015 it fell 14.4% against the franc in one day**. The wildest days belong to small or troubled currencies: the Turkish lira (+68.2% on 22 February 2001), the Icelandic krona (+34.5% on 8 October 2008 and -32.8% on 6 November 2008) and the Russian rouble (+24.8% on 28 February 2022). By volatility the lira comes first (20.9% a year), then the krona (16.5%), the Brazilian real (16.1%), the rouble (15.6%) and the rand (14.7%), while the Danish krone (0.2%) and the Bulgarian lev (0.3%), which were tied to the euro, hardly move. Measured against 2015, the Turkish lira is worth 5 and the Israeli shekel 123, and in the year to 30 October 2026 the euro lost most against the Norwegian krone (-12.9%), the South Korean won (-12.1%) and the Chinese yuan (-9.6%).

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `EuroRates.pbip` from this folder (or `EuroRates.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 221,702 daily rates), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

European Central Bank, euro foreign exchange reference rates, the historical file `eurofxref-hist.zip` (<https://www.ecb.europa.eu/stats/eurofxref/eurofxref-hist.zip>). Retrieved on 30 October 2026. The ECB publishes the rates for free use on its website; its exact terms of reuse were not confirmed when this report was made, so check its copyright page before reusing the data.
Preparation, stated on the About page: the wide table was turned into one row for each currency and day, the old Romanian leu and Turkish lira (redenominated in 2005) were continued in the new units, and the daily change, the change over the year, the strength index (2015 = 100), the status, the region group and the era were added.
**Things to keep in mind.** The rates are reference rates fixed once a day, not the prices at which banks trade. A higher rate means a stronger euro. Nine currencies were replaced by the euro (the last one, the Bulgarian lev, on 1 January 2026) and the Russian rouble is no longer published (the last rate is from 1 March 2022). The Icelandic krona was not published from 9 December 2008 to 1 February 2018, so a daily change is left empty after a break of more than ten days and a change over the year is left empty when the year before has no rate. 2026 is the year to 30 October. The strength index is empty for currencies with no 2015 rates, and the average of the strength of several currencies depends on which currencies existed in a year.

## Measures

`Average rate`, `Strength index (2015 is 100)`, `Volatility a year`, `Euro change over the year`, `Biggest one-day rise of the euro`, `Biggest one-day fall of the euro`, `Currencies`, `First fixing`, `Last fixing`, `US dollars per euro`, `Pounds per euro`, `Yen per euro`, `Swiss francs per euro` and `Euro change for colour` are defined in the model and listed with their DAX on the About page; the number of rates is a count of rows.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
