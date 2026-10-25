# Airbnb in Barcelona: listings, prices and hosts

A seven-page Power BI report on 15,236 Airbnb listings in Barcelona (the Inside Airbnb scrape of 17 September 2026): 4,586 hosts, 70% of the listings are entire homes and 29% private rooms, the average rating is 4.61 and 25% of the listings belong to superhosts.

The report is a **light dashboard**: a lavender page, white cards with soft borders, a white sidebar with the title and the pages and a violet pill for the active page, and a collapsible **Filters pane** on the right (district, neighbourhood and room type). Hovering over a bar, slice or point shows a small summary card (a tooltip page). It is the light twin of the dark `orchid` look used for the electricity report in this repository.

| Page | What it shows |
|---|---|
| Dashboard | Five cards (listings, average price, average rating, share of superhosts, hosts), listings by year of the first review (area), listings by room type (donut), by price band, average price by district and listings by host type (donut) |
| Map | A dot map made without any map service: every 0.01-degree cell (about a kilometre) is a dot sized by the number of listings, plus listings by district and a table of the neighbourhoods |
| Prices | A heat table of average price by district and room type, the share of price bands in each district, average price against average rating for every neighbourhood (scatter) and the price per guest by group size |
| Hosts | Listings by host type (donut), the share of individual, small and professional hosts in each district, the hosts with the most listings (table) and the rating of superhosts and others |
| Stays | Listings by availability band and by rating band, reviews in the last 12 months by district and the share of licence status in each district |
| Details | The underlying rows |
| About | The data source, the preparation, the measures with their DAX, and how to use the report |

What the data says: **Eixample alone has 38% of the listings** (5,845) and the highest average price (322), against 103 in Nou Barris; Ciutat Vella has 21%. Hosts with 10 or more listings own 49% of the listings and the biggest, UKIO Spain and Acomodis Apartments, have 579 and 519 each; only 20% of the listings belong to a host with one listing. 36% of the listings show no licence, 23% show an exemption and 42% a registration number (the share without one is the highest in Nou Barris, 51%). Superhosts are rated 4.82 on average against 4.52 for other hosts. 65% of the listings had a review in the last 12 months (245,892 reviews in all, 46% of them in Eixample), 22% have never been reviewed and 29% are available almost all year (300 days or more). The number of listings by year of their first review dips in 2020 (396) and then climbs to 1,530 in 2025.

## Open it

This is a Power BI project (PBIP, text files), so it opens in **Power BI Desktop** (recent version):

1. Open `AirbnbBarcelona.pbip` from this folder (or `AirbnbBarcelona.Report/definition.pbir`).
2. Click **Refresh now** in the banner. The data is stored inside the model (one table, 15,236 listings), so there is nothing else to download and no file path to change.
3. To get a single file or to publish, use **File > Save as** (`.pbix`) or **Publish**. Before publishing, click the first tab: the published report opens on the page that was active.

Keep the folder path short: Windows stops at 260 characters and Power BI will refuse to read the project if the path to the deepest file is longer.

## Data

Inside Airbnb (<https://insideairbnb.com/get-the-data/>), Barcelona, `listings.csv.gz` of 17 September 2026, licensed under Creative Commons Attribution 4.0 (CC BY 4.0), retrieved on 25 October 2026.
Preparation, stated on the About page: about 30 of the 90 columns were kept, the price was turned into a number, and bands for price, rating, availability, host size and group size, a licence status (none listed, exempt or a registration number), the seven most common property types (the rest are Other property types) and a 0.01-degree cell were added.
**Things to keep in mind.** The price is the nightly price as published in the file (shown with a dollar sign; the file gives no currency), and 17% of the listings show no price, so price figures use the 12,610 that do. The data comes from the public pages of the platform: it shows what is offered, not what is booked or earned. Average prices are pulled up by a few very expensive listings (the median is 191 against an average of 253).

## Measures

`Listings`, `Average price`, `Median price`, `Average rating`, `Share of superhosts`, `Share of entire homes`, `Share of professional hosts`, `Average availability (days)`, `Reviews in the last 12 months`, `Hosts`, `Neighbourhoods`, `Cell longitude` and `Cell latitude` (the position of a dot on the map) and `Average price per guest` are defined in the model and listed with their DAX on the About page.
The project was generated with a script and checked in Power BI Desktop 2.158. The tooltips, the Filters pane and the page tabs are in the files but were not clicked through automatically, so try them once after opening.
