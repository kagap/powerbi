# Olist Brazilian E-Commerce — Price, Delivery & Reviews

Relational Power BI model analyzing revenue, delivery performance and review scores for the Olist Brazilian marketplace. Unlike the single-CSV projects elsewhere in this repo, this one uses a real multi-table star-schema model.

## Data

Source: [Brazilian E-Commerce Public Dataset by Olist (Kaggle)](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

Raw data isn't committed here (keeps the repo lean) — download these files from Kaggle and point Power Query at them:

- `olist_orders_dataset.csv`
- `olist_order_items_dataset.csv`
- `olist_customers_dataset.csv`
- `olist_products_dataset.csv`
- `olist_sellers_dataset.csv`
- `olist_order_payments_dataset.csv`
- `olist_order_reviews_dataset.csv`
- `product_category_name_translation.csv`

`olist_geolocation_dataset.csv` is not used in this model (one zip code prefix maps to many lat/lng pairs — too messy for a quick join).

## Data model

- **Fact table**: `olist_order_items_dataset` (grain: one row per order line item)
- **Dimensions**: `olist_orders_dataset`, `olist_customers_dataset`, `olist_products_dataset` (+ `product_category_name_translation` for English category names), `olist_sellers_dataset`
- Related via `order_id`: `olist_order_payments_dataset`, `olist_order_reviews_dataset` — watch the relationship direction here, an order can have more than one payment installment or review, so a bidirectional filter causes fan-out (inflated sums)
- A disconnected `Calendar` table (`CALENDAR(MIN(...), MAX(...))`), marked as the model's date table, drives the time-intelligence measures

**Gotcha worth knowing**: `customer_id` in `olist_orders_dataset` is unique per *order*, not per *person*. For genuine repeat-customer analysis, use `customer_unique_id` from `olist_customers_dataset` instead.

## Key measures

```DAX
Total Revenue = SUM(olist_order_items_dataset[price]) + SUM(olist_order_items_dataset[freight_value])

Avg Delivery Days = AVERAGEX(
    olist_orders_dataset,
    DATEDIFF(olist_orders_dataset[order_purchase_timestamp], olist_orders_dataset[order_delivered_customer_date], DAY)
)

Late Deliveries % = DIVIDE(
    CALCULATE(COUNTROWS(olist_orders_dataset), olist_orders_dataset[order_delivered_customer_date] > olist_orders_dataset[order_estimated_delivery_date]),
    COUNTROWS(olist_orders_dataset)
)

Revenue LY = CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Calendar'[Date]))
Revenue YoY % = DIVIDE([Total Revenue] - [Revenue LY], [Revenue LY])

Seller Rank = RANKX(ALL(olist_sellers_dataset[seller_id]), [Total Revenue], , DESC)
```

## Report pages

1. **Overview** — revenue / orders / delivery KPI cards, choropleth map of revenue by state, monthly revenue trend with YoY
2. **Sellers & Products** — top 10 sellers by revenue, revenue by category treemap, review score vs. delivery speed scatter
3. **Customer Experience** — review score distribution, on-time vs. late delivery impact on review score, payment type breakdown

## Requirements

[Power BI Desktop](https://www.microsoft.com/en-us/power-platform/products/power-bi/desktop) to open `olist_ecommerce.pbix`.
