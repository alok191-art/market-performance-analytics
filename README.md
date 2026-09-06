# Marketing Performance Analytics

An end-to-end marketing analytics project using **SQL, Python, and Power BI** to evaluate campaign performance, channel efficiency, conversion behavior, budget utilization, and lead quality.

## Project Overview

This project analyzes marketing campaign data across multiple channels and campaigns to identify:

* Which marketing channels generate the best returns
* How efficiently marketing spend converts into purchases
* How campaign objectives affect performance
* How performance changes over time
* Whether lead quality is associated with purchase behavior and revenue
* How campaign budgets are being utilized

## Dataset

The dataset contains four related tables:

* **campaigns** — campaign information, channel, objective, dates, and budget
* **daily_spend** — daily impressions, clicks, and marketing spend
* **leads** — individual leads and their lead scores
* **conversions** — conversion type and revenue information

The dataset contains:

* 120 campaigns
* 11,240 daily spend records
* 261,684 leads
* 39,696 conversions
* 5 marketing channels
* Data covering 2023–2025

## Tools & Technologies

* **SQL / SQLite** — data extraction, transformation, KPI calculation, and aggregation
* **Python** — exploratory data analysis and validation
* **Pandas** — data manipulation
* **Matplotlib** — visualization
* **Power BI** — interactive dashboard and business reporting

## SQL Analysis

The SQL analysis covers:

1. Data quality and integrity checks
2. Marketing spend by channel
3. Revenue by channel
4. ROAS by channel
5. Leads and conversions by channel
6. Conversion and purchase rates
7. Revenue by conversion type
8. Cost per purchase
9. Campaign-level performance
10. Performance by campaign objective
11. Monthly spend, revenue, and ROAS
12. Budget utilization
13. Lead quality and purchase behavior
14. Lead quality performance across channels

A key consideration throughout the analysis was the different grain of the source tables. Spend, leads, and conversions were aggregated to compatible levels before being combined to avoid double-counting.

## Key Findings

### Channel Performance

**Affiliate** generated the highest overall ROAS at **6.54×**, followed by **Paid Search at 6.06×**.

**Video** had the lowest ROAS at **2.52×**.

### Purchase Efficiency

Affiliate had the lowest cost per purchase at approximately **198**, while Video had the highest at approximately **506**.

### Channel Conversion Rates

Overall purchase rates were relatively similar across channels, ranging from approximately **6.33% to 6.44%**.

This suggests that the large differences in ROAS were not primarily caused by major differences in overall purchase conversion rates.

### Lead Quality

Lead quality showed a strong relationship with purchase behavior:

| Lead Quality | Purchase Rate | Revenue per Lead |
| ------------ | ------------: | ---------------: |
| Low          |         3.19% |            40.94 |
| Medium       |         5.32% |            68.93 |
| High         |         7.43% |            95.22 |
| Very High    |         9.56% |           124.27 |

Very-high-quality leads generated approximately **3× the purchase rate** and **3× the revenue per lead** of low-quality leads.

These findings indicate that lead quality is strongly associated with purchase propensity and revenue generation in the dataset.

## Python Analysis

Python is used after the SQL transformation layer for:

* Dataset validation
* Descriptive statistics
* Correlation analysis
* Campaign-level exploratory analysis
* Spend vs. revenue analysis
* Lead quality vs. purchase-rate analysis
* Identification of high-performing campaigns

## Power BI Dashboard

The Power BI stage will convert the analytical datasets into an interactive marketing performance dashboard covering:

* Overall marketing KPIs
* Channel performance
* Campaign performance
* ROAS
* Revenue
* Spend
* Purchase rate
* Cost per purchase
* Monthly performance trends
* Lead quality performance

## Project Structure

```text
marketing-performance-analytics/
│
├── README.md
├── marketing-campaigns.sqlite
│
├── data/
│   └── processed/
│       ├── campaign_performance.csv
│       ├── channel_performance.csv
│       ├── monthly_performance.csv
│       └── lead_quality.csv
│
├── notebooks/
│   ├── 01_SQL_Marketing_Analysis.ipynb
│   └── 02_Python_Analysis.ipynb
│
└── powerbi/
    └── marketing_performance_dashboard.pbix
```

## Business Takeaways

The analysis suggests that marketing budget decisions should not rely on a single KPI such as spend or conversion rate.

A stronger evaluation combines:

**ROAS + Cost per Purchase + Purchase Volume + Lead Quality + Campaign Scale**

This provides a more balanced view of both marketing efficiency and the quality of leads being generated.

## Disclaimer

The dataset is synthetic and is intended for educational and analytical purposes. Findings should therefore be interpreted as analytical insights from the dataset rather than real-world marketing recommendations.
