# Diabetes patients: who comes back within 30 days?

A six-page Power BI report on 69,970 first hospital stays of patients with diabetes in 130 US hospitals between 1999 and 2008, and on whether they came back: 59.3% were never readmitted, 31.8% came back after more than 30 days and **9.0% within 30 days**.

The report has a cream paper look (a serif headline, a heavy rule, text tabs with an underline, sage green and terracotta) and a collapsible **Filters pane** on the right. Hovering over a bar, slice or point shows a small summary card (a tooltip page).
It is built to be different from the other reports in this repository: a funnel, a ribbon chart, a waterfall, a pie, a treemap and 100% stacked bars.

| Page | What it shows |
|---|---|
| Overview | Patients, the 30-day readmission rate, average days in hospital, average medications and average earlier inpatient visits; the readmission rate by diagnosis, a funnel of patients by readmission outcome, patients by admission type, the outcome within each age group (100% stacked bars) and a treemap of diagnoses |
| Patients | A ribbon chart of the diagnosis ranking by age, a pie of patients by sex, and the readmission rate by age and by race |
| Stay | Days in hospital against medications by diagnosis (scatter), a waterfall of total days by diagnosis, patients by length of stay, and days in hospital by admission type |
| Treatment | The readmission rate by insulin change, HbA1c test result, change of medication and whether diabetes medication was prescribed |
| Details | The underlying patient rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: the 30-day rate is 10.8% for people aged 80-89 and 4.9% for those aged 10-19; 10.8% after an injury as the main diagnosis and 7.3% after a respiratory one; and 26.5% for the 1.3% of patients who had three or more inpatient stays in the year before, against 8.1% for those with none. These are associations in a 1999-2008 sample, not causes.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `HospitalReadmission.pbip` from this folder (or `HospitalReadmission.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 69,970 rows), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

UCI Machine Learning Repository, *Diabetes 130-US hospitals for years 1999-2008* (Strack et al., 2014), licence CC BY 4.0: <https://archive.ics.uci.edu/dataset/296>.
Preparation, all stated on the About page: only the first stay of each patient was kept (101,766 stays became 71,518) so that patients are not counted twice; patients who died or went to hospice were removed because they cannot be readmitted (69,973 left); three stays with an unknown sex were dropped; 10 stays without a diagnosis code are counted under Other and a missing race is labelled Unknown; ICD-9 diagnosis codes were grouped into the nine groups of the original paper; the numeric codes for admission type and discharge were replaced by their names; and age brackets were relabelled (`[70-80)` became `70-79`). The columns that are mostly empty (weight, payer code, medical specialty) were left out.

## Measures

`Patients`, `Readmitted within 30 days`, `Average days in hospital`, `Average medications`, `Average prior inpatient visits` and `Total days in hospital` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
