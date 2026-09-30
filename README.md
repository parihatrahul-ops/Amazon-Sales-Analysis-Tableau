# Amazon India Sales & Operations Dashboard

An interactive Tableau dashboard analyzing order-level sales data for an Amazon India D2C clothing seller — built to answer four questions: **what** drives revenue, **how well** operations perform, **when** sales happen, and **where** customers are.

**Live dashboard:** [View Dashboard](https://public.tableau.com/views/AmazonIndiaSalesandOperationDashboard/MyDashboard?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## Dataset

**Raw Data Source:** [E-Commerce Sales Dataset (India, multi-platform) — Kaggle](https://www.kaggle.com/datasets/thedevastator/unlock-profits-with-e-commerce-sales-data)[cite: 13]
*The raw multi-platform dataset covers Indian e-commerce sales data across Amazon, Flipkart, Myntra, Ajio, Limeroad, and Paytm, including MRP by platform, quantity, gross amount, B2B status, and fulfillment details.[cite: 13] For this project, the data was filtered to focus exclusively on Amazon operations. The raw data was first cleaned and structured in Microsoft Excel before being transferred into Tableau for analysis.*

| Attribute | Details |
| --- | --- |
| Rows | ~120,000 orders (Amazon subset) |
| Period | April – June 2022 |
| Market | Amazon India |
| Business | D2C clothing seller |

Key fields used: `Date`, `Status`, `Category`, `Fulfilment`, `Amount`, `Qty`, `Ship-State`, `Ship-Country`.

## What the dashboard shows

**KPI row:** Total Sales, Total Orders, Average Order Value, and Cancellation Rate, each with a sparkline showing its trend over the order period.

**Category Pareto — "Set and Kurta drive ~77% of sales across categories"**
A bar-and-cumulative-line chart (Pareto analysis) showing that 2 of 9 product categories generate the large majority of revenue, with an 80% reference line.

**Order Status — "16% of orders are cancelled or returned"**
A sorted breakdown of order outcomes (Shipped, Delivered, Cancelled, Returned, Pending), with the problem statuses highlighted in orange.

**Sales Trend — "Sales peaked the week of April 17, then dropped sharply by early May"**
A weekly area chart with the peak and low points labeled, built with a calculated field (`WINDOW_MAX` / `WINDOW_MIN`) so the labels stay accurate under any filter.

**Geographic Map — "Maharashtra leads unit sales across India"**
A proportional-symbol map of units sold by state, with the top 5 states labeled using a calculated `RANK()` field.

## Interactivity

Three filters (Date range, Fulfilment method, Category) are grouped behind a show/hide toggle so the dashboard stays clean by default. Filters apply across all views except where doing so would make a chart's headline finding inaccurate — for example, the Category filter excludes the Category Pareto chart, since that chart's entire purpose is showing the mix across *all* categories.

## Design choices

* **Color:** A two-color system (Amazon navy `#232F3E` and Amazon orange `#FF9900`) used consistently — orange always marks "the thing to pay attention to" (cancellations, the top-2 categories, the trend line, the leading state), never used decoratively.
* **Titles as findings:** Every chart title states the insight it contains, not just what it shows.
* **Calculated fields:** Custom fields for cumulative % of total, status grouping, peak/low labeling, and top-N ranking, built rather than relying on defaults.
* **Scoped accuracy:** The Sales Trend chart is filtered to April–June, the period with complete order data, rather than including partial months that would distort the story.

## Tools

* **Microsoft Excel:** Initial data cleaning, filtering, and formatting.
* **Tableau Desktop / Tableau Public:** Data visualization, calculated fields, and dashboard design.

## Skills demonstrated

Data cleaning (Excel) · Pareto analysis · KPI dashboard design · geographic visualization · calculated fields & table calculations · dashboard interactivity (filters, actions, show/hide containers) · data storytelling · visual design systems

---

*Portfolio project — not affiliated with or endorsed by Amazon.*
