# Who earns over 50K? US census adults

A six-page Power BI report on 32,561 adults from a 1994 US census extract: how the share earning more than 50,000 dollars a year changes with occupation, education, marital status, sex and age.
24.1% of the people in the data are above that line.

| Page | What it shows |
|---|---|
| Overview | People, high-income share, average age, hours per week and education years, with the share by occupation and education and the split by sex |
| Breakdown | High-income share by occupation, education, marital status and sex |
| Compare | High-income share against average age for each occupation, a treemap of people by education, and age and hours worked by group |
| Matrix | All measures by occupation, and the share by occupation and education |
| Details | The underlying rows |
| About | The data source, the measures with their DAX, and how to use the slicers |

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `AdultIncome.pbip` from this folder (or `AdultIncome.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 32,561 rows), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

UCI Machine Learning Repository, *Adult* (Census Income) dataset (Becker and Kohavi, 1996), licence CC BY 4.0: <https://archive.ics.uci.edu/dataset/2>. This is the `adult.data` file (the training part). The `fnlwgt` sampling-weight column was dropped, and the `?` marks for unknown values were turned into empty cells (1,836 for work class, 1,843 for occupation and 583 for country), so some charts show an empty category.

## Measures

`Rows`, `High-income share`, `Average age`, `Average hours per week`, `Average education years` and `Capital gain per person` are defined in the model and listed with their DAX on the About page.
The data is a 1994 snapshot, so the figures describe that population and not today's. The project was generated with a script and checked in Power BI Desktop 2.158.
