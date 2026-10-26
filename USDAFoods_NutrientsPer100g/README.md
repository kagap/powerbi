# What is in our food: 7,793 foods

A seven-page Power BI report on the composition of 7,793 foods from the USDA's SR Legacy database, every value per 100 grams. The average food has **220 kilocalories, 11.9 g of protein, 10.7 g of fat and 19.6 g of carbohydrate**; fats and oils are the most energy-dense group (619 kcal) and vegetables the lightest (64 kcal).

The look is a farmers' market: a cream page, forest green and tomato red, a bold title on the left and **the pages inside a rounded pill on the right**, white cards with soft corners and a collapsible **Filters pane** (food group, energy band, main energy source and more). Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| Overview | Five cards (foods, average energy, protein, fat, carbohydrate), a treemap of the food groups, average energy by group, protein against energy for every group (scatter) and the foods by main source of energy (donut) |
| Macros | The share of protein, fat and carbohydrate energy in each food group (100% stacked bars), and foods by energy band and main source of energy |
| Rankings | Three tables: the foods with the most protein, the most fibre and the most sodium per 100 g |
| Minerals | Average vitamin C, iron and calcium by food group, and a table of fibre, sodium, calcium, iron, vitamin C, saturated fat and cholesterol by group |
| Bands | The share of sugar bands and of fibre bands in each group, foods by sodium band and by protein band |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: **46% of the foods get most of their energy from carbohydrate, 29% from fat and 22% from protein**, and 16% have under 60 kcal. Fats and oils take 96% of their energy from fat, nuts and seeds 67% (an average of 496 kcal), sausages and luncheon meats 70%; fish takes 63% of its energy from protein, poultry 48% and beef 47%. The most protein is in soy protein isolate (88 g), dried gelatin (86 g) and dried egg white; the most fibre in corn bran (79 g). Salt is the extreme for sodium (38,758 mg), and soups, sauces and gravies (1,255 mg on average) and spices (1,237 mg) are the saltiest groups; 4.9% of the foods with a sodium value have 1,000 mg or more. Spices also top the lists for calcium (642 mg) and iron (21.7 mg, thyme 124 mg), breakfast cereals follow for iron (15 mg, many of them fortified), and the highest vitamin C averages belong to beverages (34 mg, fortified drinks), spices and fruit (31 mg).

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `USDAFoods.pbip` from this folder (or `USDAFoods.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 7,793 foods), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

U.S. Department of Agriculture, Agricultural Research Service, FoodData Central, *SR Legacy* (April 2018), in the public domain under CC0 1.0 (<https://fdc.nal.usda.gov/download-datasets>). Retrieved on 26 October 2026.
Preparation, stated on the About page: 24 of the 149 nutrients were turned from a long table into columns, the food groups come from the food category table, and energy, protein, sugar, fibre and sodium bands and the main source of energy of every food were added.
**Things to keep in mind.** Many foods lack some nutrients (sugars are missing for 23% of the foods, vitamin D for 33%, fibre for 7%) and an average uses only the foods that have a value. An average is an average over foods, not over what people eat: a group with many variants of one food counts them all, and the list includes dried, fortified and brand-name items that stand out in the rankings. The energy bars use the usual factors (4 kcal per gram of protein and carbohydrate, 9 per gram of fat) on the values in the table.

## Measures

`Foods`, `Average energy (kcal)`, `Average protein (g)`, `Average fat (g)`, `Average carbohydrate (g)`, `Average fibre (g)`, `Average sugars (g)`, `Average sodium (mg)`, `Protein energy`, `Fat energy` and `Carbohydrate energy` (sums used for the 100% stacked bars), `Average calcium (mg)`, `Average iron (mg)`, `Average vitamin C (mg)`, `Average saturated fat (g)` and `Average cholesterol (mg)` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
