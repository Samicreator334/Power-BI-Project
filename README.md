# Power-BI-Project
# 🌱 Plant.co Sales Performance Dashboard (2023)

## 📊 Overview
This project is an interactive **Power BI dashboard** that analyzes **Plant.co’s sales performance for 2023**.  
It focuses on **Year-to-Date (YTD)** performance, comparison against **Previous Year-to-Date (PYTD)**, profitability analysis (**Gross Profit %**), and trend identification across **time, geography, product types, and customer accounts**.

The dashboard is designed to support **executive-level decision making** while still allowing **detailed analytical exploration**.

---

## 🛠️ Tech Stack
```txt
- Power BI Desktop
- Power Query (M Language)
- DAX (Data Analysis Expressions)
- Data Modeling (Star Schema)

## 📂 Data Source
```txt
Sales transactional dataset (Plant.co)

Data fields include:
- Sales revenue
- Quantity sold
- Gross profit
- Product type
- Customer account
- Country
- Date (Year / Quarter / Month)

## 📐 Core Measures (DAX)
```DAX
Sales :=
SUM ( Fact_Sales[Sales] )

Quantity :=
SUM ( Fact_Sales[Quantity] )

Gross Profit :=
SUM ( Fact_Sales[Gross_Profit] )

GP% :=
DIVIDE ( [Gross Profit], [Sales] )

S_YTD :=
TOTALYTD ( [Sales], Dim_Date[Date] )

S_PYTD :=
CALCULATE (
    [S_YTD],
    SAMEPERIODLASTYEAR ( Dim_Date[Date] )
)

YTD_VS_PYTD :=
[S_YTD] - [S_PYTD]

## ✨ Features & Highlights
```txt
- KPI Cards
  * YTD Sales
  * PYTD Sales
  * YTD vs PYTD variance
  * Gross Profit %

- Monthly Performance
  * Waterfall chart showing increase and decrease by month

- Geographic Analysis
  * Treemap of Bottom 10 countries by YTD vs PYTD variance

- Product Performance
  * Quarterly stacked columns by Product Type
  * PYTD trend line overlay

- Customer Profitability
  * Scatter plot of S_YTD vs GP%
  * Identifies high-sales / low-margin accounts

- Interactivity
  * Year slicer
  * Metric selector (Sales / Quantity / Gross Profit)
  * Cross-filtering across all visuals

