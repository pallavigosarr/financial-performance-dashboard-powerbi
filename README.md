# financial-performance-dashboard-powerbi
This project presents an interactive Financial Performance Dashboard developed in Power BI to monitor the overall financial health of a business. The dashboard integrates Profit &amp; Loss (P&amp;L), Cash Flow, Budget vs Actual performance, Product/Service sales, and Receivables &amp; Payables aging analysis into a single reporting solution.
The objective of the dashboard is to provide management with actionable insights into revenue growth, profitability, liquidity, and operational efficiency through dynamic visualizations and drill-through capabilities.

---

## Business Problem

Financial stakeholders require a centralized reporting solution to track key financial metrics and evaluate business performance across products, regions, and time periods. Traditional spreadsheet-based reporting makes it difficult to identify trends, monitor budget performance, and assess cash flow health efficiently.

This dashboard addresses these challenges by providing an interactive and data-driven view of financial performance.

---

## Dataset Information

The dataset contains monthly financial records from January 2023 to December 2024.

### Key Fields

* Month
* Region
* Product/Service
* Revenue
* COGS
* Gross Profit
* Opex
* EBITDA
* Cash Inflows
* Cash Outflows
* Receivables Aging (Days)
* Payables Aging (Days)
* Revenue Budget
* Budget Variance %

---

## Dashboard Features

### Executive KPI Monitoring

* Total Revenue
* Gross Margin %
* EBITDA %
* Net Cash Position

### Financial Analysis

* Revenue vs EBITDA Trend Analysis
* Budget vs Actual Comparison
* Budget Variance Tracking
* Cash Flow Waterfall Analysis

### Operational Performance

* Product/Service Performance Analysis
* Regional Revenue Contribution
* Receivables Aging Distribution
* Payables Aging Distribution

### Interactive Features

* Year, Quarter, and Month Slicers
* Region Filter
* Product/Service Filter
* Drill-Down Functionality
* Drill-Through Detail Analysis Page

---

## Data Preparation

Data cleaning and transformation were performed using Power Query:

* Verified data completeness
* Validated data types
* Created Date Dimension Table
* Established model relationships
* Created aging buckets for receivables and payables
* Implemented calculated measures using DAX

---

## DAX Measures Used

### Revenue

```DAX
Revenue = SUM(Finance[Revenue])
```

### Gross Margin %

```DAX
Gross Margin % =
DIVIDE(
[Gross Profit],
[Revenue]
)
```

### EBITDA %

```DAX
EBITDA % =
DIVIDE(
[EBITDA],
[Revenue]
)
```

### Net Cash

```DAX
Net Cash =
SUM(Finance[Cash Inflows]) -
SUM(Finance[Cash Outflows])
```

### Budget Variance %

```DAX
Budget Variance % =
DIVIDE(
[Revenue] - [Revenue Budget],
[Revenue Budget]
)
```

---

## Key Insights

* Revenue trends can be monitored across months, quarters, and years.
* Budget performance is evaluated through variance analysis.
* Product-level profitability highlights top-performing offerings.
* Regional analysis identifies high-contributing markets.
* Aging reports help assess collection and payment efficiency.
* Cash flow visualization provides insight into business liquidity.

---

## Tools & Technologies

* Power BI Desktop
* Power Query
* DAX (Data Analysis Expressions)
* Data Modeling
* Interactive Dashboard Design

---

## Project Structure

```text
financial-performance-dashboard-powerbi/
│
├── data/
│   └── Financial_Data.xlsx
│
├── dashboard/
│   └── Financial_Dashboard.pbix
│
├── Dashboard_Screenshots/
│   ├── Executive_Financial_Performance.png
│   └── Operational_Perfromance.png
│
├── Documentation/
│   └── Executive_Summary.pdf
│
└── README.md
```

---

## Business Impact

This dashboard enables stakeholders to monitor profitability, budget adherence, cash flow position, and operational performance through a single interactive reporting solution. The project demonstrates practical skills in data modeling, DAX development, dashboard design, and business intelligence reporting using Power BI.
