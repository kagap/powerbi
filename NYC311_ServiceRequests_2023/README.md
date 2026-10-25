# NYC 311 requests in 2023: a service desk

A seven-page Power BI report on **a 2% sample of the 3.2 million 311 service requests that New Yorkers made in 2023**: 64,518 requests (every request whose id ends in 17 or 63), treated like the tickets of a service desk. 98.5% were closed, 69.8% within three days, but the median is only 0.3 days and the mean 20 days: a long tail, since 9.6% took more than 30 days.

The report is a **navy web app**: a dark title bar, a lighter sidebar with the pages and under them the **filters as dropdowns** (resolution, complaint group, borough and agency, the way a service-desk dashboard has them), bright blue accents, KPI tiles with a sparkline and a collapsible **Filters pane** on the right (date, resolution and more). Hovering over a bar, slice or point shows a small summary card (a tooltip page).

| Page | What it shows |
|---|---|
| Overview | Four KPI tiles with sparklines (requests, closed, closure rate, share closed within 3 days), requests by resolution band (donut), by complaint group, by borough and top agencies, requests by channel (donut), requests and closed requests by month and the share closed within 3 days by channel |
| Agencies | Every agency in the sample compared (requests, closure rate, share closed within 3 days, median days), median days to close by agency and a scatter of requests against median days |
| Time | A heat map of weekday by hour of the day, requests by hour (area) and by weekday |
| Complaints | A treemap of the complaint groups, median days to close for each, a table comparing them and the share of resolution bands in each |
| Boroughs | Requests by borough, the share of channels in each borough, a matrix of borough by resolution band and the share closed within 3 days |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: **the police and housing departments produce two requests in three** (NYPD 43%, HPD 21%, then sanitation 9%), and the commonest complaint is illegal parking (15%), ahead of residential noise (9%) and heat or hot water (7%). Speed depends on who is asked: the NYPD closes half of its requests in under an hour (median 0.03 days), while parks and recreation takes a median of 44 days, buildings 13 and housing 4.4; parking, blocked driveway and noise complaints are closed within three days in practically every case, plumbing (22%) and unsanitary conditions (14%) in far fewer. 43% of requests come online, 30% by phone and 19% through the mobile app (89% of those closed within three days, against 59% by phone; the channels differ in what people report). Brooklyn has 31% of the requests, Queens 24%, Manhattan 21% and the Bronx 19%. Requests peak between 9 and 11 in the morning (about 3,900 an hour in the sample), fall to 750 to 800 between 3 and 5 at night, are fewer on weekends (8,300 a day against 9,400 to 9,800) and peak in October (6,051) with February the quietest month (4,501).

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `NYC311.pbip` from this folder (or `NYC311.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 64,518 requests), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

NYC Open Data, *311 Service Requests from 2020 to Present* (<https://data.cityofnewyork.us/resource/erm2-nwe9>), City of New York; the dataset page lists no separate licence and the data is public. Retrieved on 25 October 2026 through the Socrata API.
Preparation, stated on the About page: a 2% systematic sample by request id (those ending in 17 or 63), labels in title case, the days to close (for requests with the status Closed and a valid closing date), a resolution band, the hour and weekday of the request, the eight largest agencies and the twelve most common complaint types kept and the rest grouped.
**Things to keep in mind.** Multiply the counts by about 50 to estimate the whole year; shares, medians and rankings do not depend on the sample size much. The three-day line is only a yardstick chosen here, not an official service target. 93 requests with a closing date before the request and 404 closed ones with no closing date have no time to close and count as not closed within three days.

## Measures

`Requests`, `Closed`, `Closure rate`, `Closed within 3 days`, `Share closed within 3 days`, `Median days to close`, `Average days to close`, `Not closed`, `Agencies` and `Complaint types` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
