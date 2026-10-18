# Students: what goes with a good final grade?

A six-page Power BI report built like a story, with a commentary card beside the charts, on 1,044 course enrolments of secondary-school students in two Portuguese schools in 2005-2006 (395 in mathematics, 649 in Portuguese language). The average final grade is 11.3 out of 20 and 78% of enrolments end with a pass (10 or more).

The report has a dark green board with chalk yellow and pink, numbered chips for the pages in the header, and a collapsible **Filters pane** on the right. Hovering over a bar, slice or point shows a small summary card (a tooltip page).
Each chapter page opens with one big number and a sentence, followed by the charts that show it.

| Page | What it shows |
|---|---|
| Overview | Three commentary cards (pass rate, mathematics against Portuguese, study time), first-period and final grade by study time, and the share of passes and fails within each level of mother's education |
| Study | Past failures and study time against the final grade and the pass rate, and grade against absences by study time |
| Home | Mother's education, internet at home and the wish to continue to higher education against the grade |
| Habits | Weekend alcohol use, going out and absences against the grade |
| Details | The underlying enrolment rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: the pass rate is 67% in mathematics and 85% in Portuguese; 85% for students with no past failures against 33% for those with two; the average final grade is 10.6 for students who study under 2 hours a week and 12.5 for those who study 5 to 10 hours, 10.2 when the mother has only primary education against 12.5 with higher education, and 11.7 at very low weekend alcohol use against 10.4 at very high. These are associations, not causes, and some groups are small (30 enrolments with three or more failures).

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `{pbip}` from this folder (or `{rep}/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model ({rows}), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the **Overview** tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

UCI Machine Learning Repository, *Student Performance* (Cortez and Silva, 2008), licence CC BY 4.0: <https://archive.ics.uci.edu/dataset/320>.
About 380 students take both subjects, so a student can appear twice: a row is an enrolment, not a student. Preparation: the two files were combined with a `Subject` column; coded answers (1 to 5, 1 to 4) were replaced by labelled levels that sort in order; a `Result` column (passed with a final grade of 10 or more, the Portuguese pass mark) and an absence band were added.

## Measures

`Enrolments`, `Average final grade`, `Pass rate`, `Average absences`, `Average first-period grade` and `Aiming for higher education` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
