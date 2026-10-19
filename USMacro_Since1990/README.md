# US economy since 1990: prices, jobs and interest rates

A six-page Power BI report on 441 months of the US economy, January 1990 to September 2026: unemployment, inflation, payrolls, the Fed funds rate, the 2-year and 10-year Treasury yields, the 30-year mortgage rate and NBER recession months. The first page is a row of **latest values** with the **change against a year earlier** underneath: in the last month of the data unemployment is 4.2% (down 0.2 points on the year), the Fed funds rate 3.75% (down 0.47), the 10-year yield 4.99% (up 0.87), inflation 3.7% (up 0.7) and the 30-year mortgage rate 6.86% (up 0.51).

The report looks like a market terminal: black screen, amber monospace text, thin amber borders and **function-key tabs (F1 to F6)** along the top, with a collapsible **Filters pane** on the right. The latest values follow the date range in the Filters pane. Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| F1 Overview | Six latest values and six changes against a year earlier; unemployment (columns) and inflation (line) by month; Fed funds, 10-year yield and mortgage rate; the 10y-2y spread (an area that dips below zero when the yield curve is inverted); inflation against unemployment, one point a year |
| F2 Rates | The 10-year yield, the 2-year yield and the Fed funds rate on one chart, the spread, and the mortgage rate by decade |
| F3 Inflation | Inflation by month and by decade, unemployment by inflation band, and payroll growth |
| F4 Cycles | Averages in recessions and expansions, averages by decade (a table), unemployment and inflation by Fed stance (cutting, holding, raising), and a heat map of unemployment by decade and phase of the cycle |
| F5 Details | The underlying monthly rows |
| F6 About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: unemployment peaked at 14.8% in April 2020 and bottomed at 3.4% in April 2023; inflation (12-month change in CPI) peaked at 9.0% in June 2022; the 30-year mortgage rate fell from 10.5% (May 1990) to 2.7% (December 2020); the 10-year yield was below the 2-year in 52 of the 441 months; average unemployment is 6.4% in recession months against 5.6% in expansions; the Fed funds rate averaged 5.2% in the 1990s, 3.0% in the 2000s, 0.6% in the 2010s and 2.9% in the 2020s. The last observations are as FRED published them on 19 October 2026.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `USMacro.pbip` from this folder (or `USMacro.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 441 months), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

Federal Reserve Bank of St. Louis, FRED: UNRATE, FEDFUNDS, GS10, GS2, CPIAUCSL, PAYEMS and USREC (monthly), and MORTGAGE30US (Freddie Mac, weekly, averaged by month), retrieved on 19 October 2026 from <https://fred.stlouisfed.org>. **FRED data may be copyrighted by the original sources: see <https://fred.stlouisfed.org/legal> before reusing it.**
Preparation, stated on the About page: inflation is the 12-month change of CPIAUCSL and payroll growth the 12-month change of PAYEMS, both computed on the full series before cutting at 1990; the spread is the 10-year minus the 2-year yield; the inflation bands and the Fed stance (12-month change of the Fed funds rate of at least 0.25 points up or down) were added; `Month` and `Year` are added in Power Query.

## Measures

`Months`, six latest values, six changes against a year earlier (they use the last month in the current date range and the same month a year earlier) and averages of unemployment, inflation, the Fed funds rate, the 10-year and 2-year yields, the mortgage rate, the 10y-2y spread and payroll growth are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
