# 🌱 Plant.co Sales Performance Dashboard (2023)

## 📊 Overview
This project is an interactive **Power BI dashboard** analyzing **Plant.co’s sales performance**.  
It focuses on **Year-to-Date (YTD)** performance, comparison against **Previous Year-to-Date (PYTD)**, profitability analysis (**Gross Profit %**), and trend identification across **time, geography, product types, and customer accounts**.

The dashboard is designed to support **executive-level decision-making** while still allowing **deep analytical exploration**.

---

## 🛠️ Tech Stack
- Power BI Desktop  
- Power Query (M Language)  
- DAX (Data Analysis Expressions)  
- Data Modeling (Star Schema)

---

## 📂 Data Source
**Sales Transactional Dataset (Plant.co)**

**Key Fields:**
- Sales revenue  
- Quantity sold  
- Gross profit  
- Product type  
- Customer account  
- Country  
- Date (Year / Quarter / Month)

---

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
```

## ✨ Features & Highlights

### KPI Cards
- YTD Sales  
- PYTD Sales  
- YTD vs PYTD Variance  
- Gross Profit %

### Monthly Performance
- Waterfall chart showing monthly increases and decreases in YTD sales

### Geographic Analysis
- Treemap highlighting **Bottom 10 countries** by YTD vs PYTD variance

### Product Performance
- Quarterly stacked column chart by **Product Type**
- PYTD trend line overlay for year-over-year comparison

### Customer Profitability
- Scatter plot of **YTD Sales vs Gross Profit %**
- Identifies high-sales / low-margin customer accounts

### Interactivity
- Year slicer  
- Metric selector (Sales / Quantity / Gross Profit)  
- Cross-filtering across all visuals

---

## 🎯 Business Value
- Enables executives to quickly assess **current performance vs last year**
- Identifies **underperforming regions and products**
- Highlights **profitability risks** in high-revenue customer accounts
- Supports **data-driven strategic decision-making**

