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


```DAX
Total_Revenue = SUM(Data[Revenue])
```
```DAX
Total_Budget_Revenue = SUM(Data[Revenue Budget])
```
```DAX
Budget_Variance = [Total_Revenue]-[Total_Budget_Revenue]
```
```DAX
Total_Budget_variance% = DIVIDE([Budget_Variance],[Total_Budget_Revenue])
```
```DAX
Total_Gross_profit = sum(Data[Gross Profit])
```
```DAX
Gross_Margin% = DIVIDE([Total_Gross_profit],[Total_Revenue])
```
```DAX
Total_EBITDA = sum(Data[EBITDA])
```
```DAX
EBITDA% = DIVIDE([Total_EBITDA],[Total_Revenue])
```
```DAX

Total_Cash_Inflow = SUM(Data[Cash Inflows])
```
```DAX
Total_Cash_Outflow = SUM(Data[Cash Outflows] )
```
```DAX
Net_Cash = SUM(Data[Cash Inflows])-SUM(Data[Cash Outflows])
```
```DAX

Cash_Conversion_Rate = [Net_Cash]/[Total_EBITDA]
```
```DAX

Receivable_Bucket = 
SWITCH(
TRUE(),
Data[Receivables Aging (Days)] <= 30,"0-30",
Data[Receivables Aging (Days)] <= 60,"31-60",
Data[Receivables Aging (Days)] <= 90,"61-90",
"90+"
)
```
```DAX

Payable_Bucket = 
SWITCH(
TRUE(),
Data[Payables Aging (Days)] <= 30,"0-30",
Data[Payables Aging (Days)] <= 60,"31-60",
Data[Payables Aging (Days)] <= 90,"61-90",
"90+"
)
```


## Screenshots:

<img width="887" height="500" alt="Executive_Financial_Performance" src="https://github.com/user-attachments/assets/a92080fb-318d-4c87-a1e8-37c730e3b960" />

<img width="884" height="498" alt="Operational_Perfromance" src="https://github.com/user-attachments/assets/89f4624d-3053-44fa-bf17-5ebe08065c4b" />


---

## Key Insights

*	Elite Core Margins: The model highlights an exceptionally robust business structure, yielding a ~46% Gross Margin and a ~25% EBITDA. The resulting 20% overhead spread reflects highly disciplined cost controls.
*	The ~12% CCR Crisis: Despite strong profitability, the Cash Conversion Rate (CCR) plummets to ~12%. This exposes a severe structural bottleneck. ~88% of accounting profits are trapped as "paper wealth" in unpaid invoices rather than converting to liquid cash.
*	Credit Cycle Mismatch: While cash cycles appear synchronized on the surface, a micro-gap exists where Receivables Aging (76% in 31–60 days) lags behind Payable Aging (74% in 31–60 days). Customers hold company funds longer than the company holds vendor funds, starving the business of working capital.
*	The November 2024 Anomaly: A major revenue-to-cash disconnect occurs in November 2024, booking peak revenue of ₹1,134k while net cash flows collapse into the bottom five lowest months at a meagre ₹13k. This signals an aggressive, uncollected credit push.
*	Systemic Budget Deficits: The Company consistently underperforms against revenue budgets. The commercial variance peaks in October 2024 (₹450k deficit) and February 2024 (₹440k deficit), highlighting a breakdown in forecasting or sales execution.
*	Segment Performance Traps: The South Region is the weakest top-line link (24.40% contribution) and the highest budget shortfall driver. Granular modelling isolates five specific regional product/service pairs driving over ₹2.7 Million in cumulative negative variance, led directly by East - Product A and West - Service Y.


---

## Tools & Technologies

* Power BI Desktop
* Power Query
* DAX (Data Analysis Expressions)
* Data Modeling
* Interactive Dashboard Design

---

## Business Impact

This dashboard enables stakeholders to monitor profitability, budget adherence, cash flow position, and operational performance through a single interactive reporting solution. The project demonstrates practical skills in data modeling, DAX development, dashboard design, and business intelligence reporting using Power BI.

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


