# Wine quality: what makes a good wine?

A six-page Power BI report on 6,497 Portuguese Vinho Verde wines (1,599 red and 4,898 white), each with eleven laboratory measurements and a quality score from 3 to 9 given by tasters. The average score is 5.82 and 19.7% of the wines score 7 or more.

The report has a warm white page with a burgundy menu on the **right-hand side**, round white cards, and a burgundy, gold and sage palette; a collapsible **Filters pane** is on the far right. Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is built to be different from the other reports in this repository: a gauge, a multi-row card, small multiples of line charts, a 100% stacked column chart and a scatter of scores.

| Page | What it shows |
|---|---|
| Overview | A gauge of the average quality on its 3 to 9 scale, a multi-row card (wines, alcohol, volatile acidity, sugar, share of good wines), wines by score split into red and white, each score's alcohol against volatile acidity (scatter), a treemap of alcohol bands, quality bands within each alcohol band, and red against white |
| Chemistry | Four small multiples: average alcohol, volatile acidity, sulphates and residual sugar for each quality score, red against white |
| Compare | Each score's share of red and white (100% stacked), a table of measures by type, the share of good wines by alcohol band and type, and quality by sugar band and type |
| Bands | Average quality by alcohol band and by sugar band, wines by quality band and type, and a treemap of sugar bands |
| Details | The underlying wine rows |
| About | The data source, the measures with their DAX, and how to use the report |

What the data says: average quality rises steadily with alcohol, from 5.45 for wines under 10% to 6.54 for 12% and over, while it hardly moves with sugar (5.76 to 5.88). Better wines have less volatile acidity (0.29 g/l for good wines, 0.40 for below average). White wines score a little higher than red (5.88 against 5.64; 21.6% good against 13.6%) and red wines carry about twice the volatile acidity (0.53 against 0.28). These are correlations in one region's samples, not recipes.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `WineQuality.pbip` from this folder (or `WineQuality.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 6,497 rows), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

UCI Machine Learning Repository, *Wine Quality* (Cortez et al., 2009), licence CC BY 4.0: <https://archive.ics.uci.edu/dataset/186>.
The red and white files were combined with a `Type` column; values are as published (937 white and 240 red rows repeat other rows, and they were kept). Quality, alcohol and residual sugar were also grouped into bands for the charts (band labels start with a number so they sort in order), and column names were cleaned (for example `fixed acidity` became `Fixed_acidity`).

## Measures

`Wines`, `Average quality`, `Average alcohol`, `Average volatile acidity`, `Average residual sugar`, `Share of good wines` (score 7 or more) and `Average sulphates` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page menu are in the files but were not clicked through automatically, so try them once after opening.
