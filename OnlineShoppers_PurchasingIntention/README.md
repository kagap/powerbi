# Online shoppers: who buys?

A six-page Power BI report on 12,330 browsing sessions of an online shop over one year: which visitors, months and traffic sources turn into purchases.
15.5% of the sessions end with a purchase, and the report shows where that rate is higher or lower.

The report has a dark navigation panel on the left, white cards with rounded corners, a three-colour palette (navy, teal and one orange accent), no gridlines, and a collapsible **Filters pane** on the right (the funnel tab) with the category filters. Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| Overview | Sessions, conversion rate, purchasing sessions, average page value and bounce rate, conversion by month, the visitor split, purchases by weekend and conversion by traffic type |
| Breakdown | Conversion rate by month, visitor type, weekend and traffic type |
| Compare | Conversion rate against purchasing sessions for each month (scatter), a treemap of sessions by visitor type, and the other measures by category |
| Matrix | A sorted bar of conversion by month, a table of all measures by month, and conversion by month and visitor type |
| Details | The underlying sessions |
| About | The data source, the measures with their DAX, and how to use the report |

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `OnlineShoppers.pbip` from this folder (or `OnlineShoppers.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 12,330 rows), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

UCI Machine Learning Repository, *Online Shoppers Purchasing Intention Dataset* (Sakar et al., 2018), licence CC BY 4.0: <https://archive.ics.uci.edu/dataset/468>.
One row is one session of a different user. The columns `Revenue` (purchase or not), `Weekend`, `Month`, `VisitorType`, `TrafficType`, `Region`, `Browser` and the page and duration counters are used as published.

## Measures

`Rows`, `Conversion rate` (purchasing sessions divided by sessions), `Purchasing sessions`, `Average page value`, `Average bounce rate` and `Average product pages` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips and the Filters pane are in the files but were not clicked through automatically, so try them once after opening.
