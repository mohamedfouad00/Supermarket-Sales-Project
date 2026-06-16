# Supermarket Sales & Performance Analytics

![Status](https://img.shields.io/badge/Status-Completed-2E8B57?style=for-the-badge&logo=github&logoColor=white)
![Tools](https://img.shields.io/badge/Tools-Power%20BI%20%7C%20Excel-1D1D1D?style=for-the-badge&logo=microsoftpowerbi&logoColor=yellow)
![Database](https://img.shields.io/badge/Database-SQL%20Server-1D1D1D?style=for-the-badge&logo=microsoftsqlserver&logoColor=CC2927)
![Language](https://img.shields.io/badge/Language-SQL-1D1D1D?style=for-the-badge&logo=sqlite&logoColor=blue)

A complete retail analytics solution designed to evaluate supermarket sales performance, customer behavior, product profitability, and branch operations through SQL Server, Power BI, Excel, and dimensional modeling.

---

## Project Overview

This project transforms transactional supermarket data into business intelligence insights that support revenue growth and operational optimization.

### Business Problem

The supermarket operates across multiple branches and product categories but lacks visibility into:

- Which branches generate the highest profitability
- Which customer segments create the most value
- Which product categories drive revenue and profit
- How customer satisfaction impacts financial performance
- Which operational areas should be prioritized for improvement

The goal was to build an end-to-end analytics solution that enables data-driven decision making.

---

## Executive Summary

### Financial Performance

- **$322,966.75** Total Revenue
- **$15,379.37** Total Profit
- **4.76%** Net Profit Margin
- **5,510** Transactions Analyzed
- **6.97 / 10** Average Customer Rating

### Key Findings

- Large Orders generate **62% of total profit**
- Food & Beverages is the highest profit-generating category
- Female Members represent the highest-value customer segment
- Branch C (Naypyitaw) leads profitability performance
- Revenue distribution remains balanced across all branches

---

## Navigation Pane

- New to this project? → [Getting Started](#getting-started)
- Looking for dashboards? → [Dashboards](#dashboards)
- Interested in SQL analysis? → [SQL-Analysis](#sql-analysis)
- Looking for insights? → [Key Insights](#key-insights)
- Need contact details? → [Support & Contact](#support--contact)

---

# Dataset Overview

The dataset contains transactional retail records including:

### Sales Information

- Invoice ID
- Quantity Sold
- Unit Price
- Revenue
- Cost of Goods Sold
- Gross Income

### Customer Information

- Customer Type
- Gender
- Rating

### Product Information

- Product Line
- Branch
- City
- Payment Method

### Time Information

- Date
- Month
- Day Name
- Time

---

# Data Preparation

Data preparation was performed using SQL Server, Excel, and Power Query.

### Cleaning & Transformation

- Standardized product categories
- Created customer segmentation attributes
- Built order size classifications
- Created rating bands
- Built dimensional tables
- Validated transactional consistency
- Removed duplicate records
- Created analytical KPIs

---

# Data Model

## Star Schema Design

![Data Model](Dashboards/Model.png)

### Fact Table

**Fact_Sales**

Contains:

- Revenue
- Quantity
- Gross Income
- Tax
- Cost of Goods Sold

### Dimension Tables

#### Dim_Customers

- Customer Type
- Gender

#### Dim_Products

- Product Line

#### Dim_Branches

- Branch
- City

#### Dim_Date

- Day
- Month
- Year

---

# Project Architecture

```text
Raw Transaction Data
        ↓
Data Cleaning (SQL / Power Query)
        ↓
Star Schema Modeling
        ↓
SQL Analytics Layer
        ↓
Power BI Dashboards
        ↓
Business Insights & Recommendations
```

---

# Dashboards

## 1. Executive Dashboard

![Executive Dashboard](Dashboards/Main.png)

Provides a high-level overview of:

- Revenue
- Profit
- Margin
- Customer Ratings
- Branch Performance

### Key Metrics

- Total Revenue
- Total Profit
- Net Margin
- Transaction Volume
- Revenue by Branch

---

## 2. Detailed Analytics Dashboard

![Details Dashboard](Dashboards/Details.png)

Provides detailed analysis of:

- Product Performance
- Customer Satisfaction
- Sales Trends
- Product Mix
- Customer Segments

---

## 3. Excel Dashboard

![Excel Dashboard](Dashboards/Excel.png)

Interactive Excel dashboard built using:

- Power Query
- Pivot Tables
- Pivot Charts
- Slicers

---

# Key Insights

## Branch Performance

| Branch | Profit |
|----------|----------|
| Branch C | $5,265 |
| Branch A | $5,057 |
| Branch B | $5,057 |

### Insight

Branch profitability is highly balanced, reducing dependence on a single location.

---

## Product Performance

| Product Line | Profit |
|--------------|---------|
| Food & Beverages | $2,674 |
| Sports & Travel | $2,625 |
| Electronic Accessories | $2,588 |
| Fashion Accessories | $2,586 |
| Home & Lifestyle | $2,565 |
| Health & Beauty | $2,343 |

### Insight

Food & Beverages serves as the primary revenue driver while Sports & Travel contributes strongly to profitability.

---

## Customer Segments

### Top Performing Segment

**Female Members**

Characteristics:

- Highest profitability
- Strong repeat purchase behavior
- Higher average basket size

### Insight

Loyalty members consistently outperform normal customers in revenue contribution.

---

## Order Size Analysis

| Order Size | Profit Contribution |
|------------|-------------------|
| Large | 62% |
| Medium | 27% |
| Small | 11% |

### Insight

Large transactions represent the most significant profit opportunity.

---

# SQL Analysis

The project includes advanced SQL analytics covering:

### Core Queries

- Branch Profitability Analysis
- Customer Segmentation
- Product Performance Analysis
- Payment Method Analysis
- Customer Satisfaction Analytics
- Order Size Profitability
- Time-Based Sales Trends
- Revenue Distribution Analysis

Example:

```sql
SELECT
    db.Branch,
    db.City,
    COUNT(fs.[Invoice ID]) AS Orders,
    SUM(fs.Total) AS Revenue,
    SUM(fs.[gross income]) AS Profit
FROM Fact_Sales fs
INNER JOIN Dim_Branches db
ON fs.BranchKey = db.BranchKey
GROUP BY db.Branch, db.City
ORDER BY Profit DESC;
```

See the SQL folder for the complete analytical query collection.

---

# Business Recommendations

## Immediate Actions

### 1. Increase Large Order Adoption

Introduce:

- Bundle Discounts
- Multi-buy Promotions
- Loyalty Multipliers

Expected Outcome:

- Increased basket size
- Higher profitability

---

### 2. Expand Loyalty Programs

Target:

- Female Customers
- Frequent Buyers

Expected Outcome:

- Higher retention
- Increased customer lifetime value

---

### 3. Improve Customer Experience

Focus Areas:

- Checkout Efficiency
- Peak Hour Staffing
- Queue Management

Expected Outcome:

- Improved ratings
- Higher repeat purchases

---

### 4. Replicate Best Branch Practices

Use Branch C as the operational benchmark for:

- Store Layout
- Product Placement
- Workforce Allocation

---

# Tech Stack

| Component | Technology |
|------------|------------|
| Database | SQL Server |
| Visualization | Power BI |
| Spreadsheet Analytics | Excel |
| Data Modeling | Star Schema |
| Query Language | T-SQL |
| ETL | Power Query |

---

# Project Structure

```text
Supermarket-Sales-Analytics/
│
├── Dashboards/
│   ├── Main.png
│   ├── Details.png
│   ├── Excel.png
│   └── Model.png
│
├── SQL/
│   ├── Schema_Creation.sql
│   └── Analytical_Queries.sql
│
├── README.md
└── .gitignore
```

---

# Getting Started

## Prerequisites

- SQL Server 2019+
- Power BI Desktop
- Microsoft Excel
- Git

## Installation

```bash
git clone https://github.com/mohamedfouad00/Supermarket-Sales-Analytics.git

cd Supermarket-Sales-Analytics
```

Load database schema, import data, and refresh Power BI connections.

---

# Support & Contact

**Mohamed Fouad**  
**Data Analyst**

Email: m.fouad.business002@gmail.com

GitHub:
:contentReference[oaicite:0]{index=0}

LinkedIn:
:contentReference[oaicite:1]{index=1}

---

# License

This project is provided for educational, analytical, and portfolio purposes.
