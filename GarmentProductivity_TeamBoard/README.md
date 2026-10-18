# Garment factory: which teams hit their target?

A six-page Power BI report on 1,197 team-days in a garment factory (1 January to 11 March 2015): the sewing and finishing teams, their targeted and actual productivity, overtime, incentive pay and style changes. On average the teams reach 73.5% against a 73.0% target, and 73.1% of team-days meet their target.

The report has a light grey page with a floating header card and round pills for the pages, safety yellow and charcoal, and a collapsible **Filters pane** on the right. Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is a scoreboard: a ranked table with shaded cells, bars of outcomes against target, and actual-against-target lines.

| Page | What it shows |
|---|---|
| Overview | Team days, average productivity, share of team-days on target, average target, overtime per worker and average incentive; a table ranking the teams (shaded by productivity), team days on and off target by team, the target met share by department and productivity by weekday |
| Teams | Productivity by team, productivity against incentive by team (scatter), the target met share by team, and productivity and target by week |
| Drivers | Productivity by incentive band, by overtime-per-worker band and by number of style changes, and productivity against overtime by team |
| Trend | Actual against target day by day, average incentive by day, and the target met share by week |
| Details | The underlying team-day rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: Team 01 is on top (82.1%, on target 85.7% of days) and Team 07 at the bottom (66.8%, 58.3%). The sewing department meets its target on 82.9% of team-days, finishing on 59.7%, although finishing is slightly more productive on average (75.3% against 72.2%), because its targets are higher. Days with an incentive above 60 average 85.7% productivity against 71.3% with none, but the lowest band (up to 40) is lower still (64.3%), so the link is not simple. Days with a style change average 61.5% and 66.2% (one and two changes) against 75.0% with none. These are associations in 59 days at one factory, not causes.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `{pbip}` from this folder (or `{rep}/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model ({rows}), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the **Overview** tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

UCI Machine Learning Repository, *Productivity Prediction of Garment Employees* (Imran et al., 2019), licence CC BY 4.0: <https://archive.ics.uci.edu/dataset/597>.
Preparation: department names were cleaned (`sweing`, and `finishing` with a trailing space), days and weeks were numbered so that they sort (there is no Friday in the data), a `Target` outcome (met when actual productivity is at least the target) and the incentive and overtime-per-worker bands were added, and column names were cleaned. Work in progress is empty for the finishing department in the source.

## Measures

`Team days`, `Average productivity`, `Target met share`, `Average target`, `Overtime per worker (min)` and `Average incentive` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
