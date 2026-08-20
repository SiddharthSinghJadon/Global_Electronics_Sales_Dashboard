# Global Electronics Sales Analytics — Excel Dashboard

## Overview

An end-to-end **Excel business analytics project** analyzing global electronics sales performance across customers, products, categories, markets, and time periods.

## Project File

[Download the Excel Analysis Workbook](./Global_Electronics_Analytics.xlsx)

## Dashboard Preview

<img width="2559" height="1430" alt="dashboard" src="https://github.com/user-attachments/assets/1fcf9e6f-6f47-4971-b8b9-9b3c19bbcd44" />


The project follows a practical analyst workflow:

**Data audit → Data cleaning → Analytical calculations → Data modeling → KPI analysis → Segmentation → Dashboard → Business insights**

### Business Objectives

The analysis answers five core questions:

1. How are revenue and profit changing over time?
2. Which markets and product categories drive performance?
3. How does customer value vary across markets?
4. Where is revenue and profit concentrated?
5. Can the analysis be communicated through an interactive executive dashboard?

---

## Dataset

The project uses a **Global Electronics retail dataset** with transactional sales data and supporting reference tables and was imported/downloaded from Maven Analytics.

### Main tables

- **Sales** — transaction-level sales data
- **Customers** — customer and geographic information
- **Products** — product, category, brand, and subcategory information
- **Stores** — store information
- **Exchange_Rates** — currency/exchange-rate information

### Key Sales Fields

- Order Number
- Line Item
- Order Date
- Delivery Date
- Customer Key
- Store Key
- Product Key
- Quantity
- Currency Code
- Unit Price USD
- Unit Cost USD

---

# Data Preparation

The dataset was audited before analysis to prevent incorrect aggregations and calculations.

Key preparation steps included:

- Correcting incorrectly typed fields
- Converting numeric fields stored as text into appropriate numeric datatypes
- Cleaning currency-formatted values before numerical calculations
- Validating dates and numerical fields
- Checking parsing errors and invalid records
- Verifying calculated values against source fields

This ensured that subsequent PivotTable aggregations and analytical calculations were based on valid numerical data.

---

# Analytical Calculations

The following business metrics were created.

### Revenue

`Revenue = Quantity × Unit Price USD`

### Cost

`Cost = Quantity × Unit Cost USD`

### Profit

`Profit = Revenue − Cost`

### Profit Margin

`Profit Margin = Profit / Revenue`

### Average Revenue per Customer

`Average Revenue per Customer = Total Revenue / Distinct Customers`

These metrics provide both **scale** and **profitability/customer-value** perspectives.

---

# Business Analysis

## 1. Executive Performance

Across the unfiltered dataset, the analysis produces approximately:

| KPI | Value |
|---|---:|
| Total Revenue | **$55.76M** |
| Total Profit | **$32.66M** |
| Total Orders | **26.3K** |
| Total Customers | **11.9K** |
| Average Profit Margin | **54.9%** |

These KPIs form the executive baseline for the dashboard.

> Dashboard values change dynamically when Year, Country, or Category filters are applied.

---

## 2. Revenue & Profit Trend

Revenue and profit increase substantially through **2019**, followed by a sharp decline in 2020 and another decline in 2021.

2019 is the strongest year in the dataset, with approximately:

- **$18.26M revenue**
- **$10.70M profit**

The post-2019 decline is a key diagnostic question. The dashboard allows the decline to be investigated by market and product category rather than treating the overall trend as the final conclusion.

---

## 3. Geographic Performance

The United States is the largest contributor to both revenue and profit.

Approximate US performance:

- **$23.75M revenue**
- **$13.92M profit**

Other major contributors include:

- Online
- United Kingdom
- Germany
- Canada

This indicates significant geographic concentration: performance in the largest markets has a substantial impact on total business results.

> `Online` is retained as a dataset category and should not be interpreted as a geographic country when making geographic conclusions.

---

## 4. Category Performance

**Computers** are the strongest product category by both revenue and profit.

Approximate performance:

- **$19.31M revenue**
- **$11.28M profit**

Other major categories include:

- Home Appliances
- Cameras and Camcorders
- Cell Phones
- TV and Video

Category-level analysis helps distinguish overall performance changes from product-mix effects.

---

## 5. Customer Value

Average Revenue per Customer varies significantly across markets.

Approximate values from the unfiltered dataset:

| Market | Average Revenue / Customer |
|---|---:|
| United States | ~$4,589 |
| Italy | ~$4,335 |
| Germany | ~$4,213 |
| United Kingdom | ~$4,038 |
| Canada | ~$3,466 |
| Netherlands | ~$3,295 |
| Australia | ~$3,195 |
| France | ~$3,161 |
| Online | ~$2,508 |

This demonstrates why market evaluation should consider both **customer volume** and **revenue per customer**, rather than relying on total revenue alone.

---

# Dashboard

The final dashboard provides an interactive executive view of the analysis.

### KPI Cards

- Total Revenue
- Total Profit
- Total Orders
- Total Customers

### Visualizations

1. **Yearly Revenue & Profit Trend**
2. **Country-wise Revenue & Profit**
3. **Category-wise Revenue & Profit**
4. **Average Revenue per Customer by Country**

### Interactive Slicers

- **Order Year**
- **Country**
- **Category**

The slicers are connected to the relevant Data Model PivotTables, allowing the dashboard to be filtered dynamically.

---

# Key Business Insights

### 1. Revenue is highly concentrated

The United States is the dominant market and therefore has a disproportionate influence on overall business performance.

### 2. Computers are the primary category

Computers contribute the largest share of revenue and profit among the analyzed categories.

### 3. 2019 is the peak performance period

Revenue and profit reach their highest levels around 2019 before declining substantially afterward.

### 4. Customer value differs by market

Average revenue per customer varies materially between markets, showing that customer count alone is insufficient for evaluating market quality.

### 5. Revenue and profit broadly move together

The strongest revenue years are also generally the strongest profit years, indicating that major performance changes affect both scale and absolute profitability.

### 6. The post-2019 decline requires diagnostic analysis

The next analytical question is **which markets and categories caused the decline**, rather than simply observing that total revenue decreased.

---

# Tools & Techniques

### Excel

- Excel Tables
- Power Query
- Data cleaning and datatype validation
- PivotTables
- Power Pivot / Data Model
- Calculated columns
- Measures
- PivotCharts
- Slicers
- Dashboard design
- Numerical and currency formatting

### Analytical Skills

- KPI development
- Time-series analysis
- Geographic segmentation
- Product/category analysis
- Customer-value analysis
- Revenue and profitability analysis
- Interactive filtering
- Business insight generation

---

# Workbook Structure

```text
Global_Electronics_Analytics.xlsx
│
├── README
├── Data_Audit
├── Customers
├── Products
├── Stores
├── Sales
├── Exchange_Rates
├── Calculations
├── Pivot_Tables
├── Customer_Performance
└── Dashboard
```

### Sheet Purpose

| Sheet | Purpose |
|---|---|
| `Data_Audit` | Data-quality checks and validation |
| `Customers` | Customer reference data |
| `Products` | Product/category reference data |
| `Stores` | Store reference data |
| `Sales` | Core transaction data |
| `Exchange_Rates` | Currency/exchange-rate reference data |
| `Calculations` | Derived metrics and analytical calculations |
| `Pivot_Tables` | Supporting business analysis |
| `Customer_Performance` | Customer-level analysis |
| `Dashboard` | Interactive executive reporting |

---

# Analyst Perspective

This project demonstrates a complete descriptive/diagnostic analytics workflow:

**Understand the data → validate it → define metrics → segment performance → identify patterns → communicate insights.**

The focus is not simply on producing charts. The analysis connects metrics and visualizations to business questions and enables users to explore the results interactively.

The project demonstrates practical application of:

- SQL-style analytical thinking
- Excel-based data analysis
- Data modeling
- KPI development
- Segmentation
- Trend analysis
- Customer analytics
- Business interpretation
- Dashboard communication

It complements a broader analytics toolkit involving **SQL, Python, Pandas, NumPy, hypothesis testing, Excel, KPI tracking, funnel analysis, A/B testing, and data-driven decision making**.

---

# Potential Extensions

The current workbook establishes the descriptive and diagnostic layer. Further analysis could include:

- Root-cause analysis of the post-2019 decline
- Customer retention and cohort analysis
- Repeat-purchase analysis
- Customer segmentation
- Category-level margin analysis
- Market growth-rate analysis
- High-value customer identification
- Python-based statistical analysis
- Predictive sales or customer-value modeling

---

## Project Classification

**Business Analytics | Sales Analytics | Customer Analytics | Excel Dashboard**

**Primary Tool:** Microsoft Excel

**Analysis Type:** Descriptive & Diagnostic Analytics
