<div align="center">

# 💊 EIPICO Commercial Sales Dashboard | Power BI
### Turning Pharmaceutical Sales Data into Strategic Market Insights

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Data%20Analysis%20Expressions-0078D4?style=for-the-badge)](https://learn.microsoft.com/en-us/dax/)
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)](#)

<p align="center">
  <b>An interactive Business Intelligence project analyzing EIPICO Q1 commercial sales performance across therapeutic lines, product portfolios, regional territories, and nationwide distribution channels.</b>
  <br />
  <i>Track. Analyze. Expand. — Nationwide Commercial Intelligence in One Screen.</i>
</p>

</div>

---

## 📌 Project Overview

The **EIPICO Commercial Sales Dashboard** is an interactive Power BI solution built to analyze wholesale and retail pharmaceutical sales velocity, pricing dynamics, regional market penetration, and supply-chain channel efficiency across Egypt.

The project transforms **135,666 transactional sales records** into structured, executive-ready insights. It empowers commercial directors, brand managers, and district sales leads to monitor revenue milestones, evaluate therapeutic line contributions, assess unit volume velocity, and address regional demand gaps across all Egyptian governorates.

### 📋 Project at a Glance

| Project Detail | Description |
| :--- | :--- |
| **Project Name** | EIPICO Commercial Sales Performance Dashboard |
| **Domain** | Pharmaceutical Commercial & Distribution Analytics |
| **Sales Period** | 01 Jan 2025 – 31 Mar 2025 (Q1 2025) |
| **Product Scope** | 47 Commercial Pharmaceutical Products across 7 Therapeutic Lines |
| **Records** | 135,666 transaction lines (43K customer accounts) |
| **Dashboard Pages** | 4 (Cover Page, Sales Overview, Product Analysis, Geographic Coverage) |
| **Main Tool** | Microsoft Power BI Desktop |
| **Data Preparation** | Power Query (schema validation, custom key formulation, type casting) |
| **Calculations** | DAX (explicit measures, dynamic revenue, volume metrics, weighted pricing) |

> **Important:** Each row in the dataset represents a distinct sales transaction per customer, line, territory, and product. Revenue is calculated from `SALES VALUE` and units sold from `SALES UNITS`.

---

## 📸 Dashboard Preview

### 1. Cover Page
<p align="center">
  <img src="D1.PNG" alt="Cover Page" width="90%" />
</p>

> *The landing view featuring EIPICO branding, project title, author credit (Shahd Hussein), and direct navigation links to all report pages.*

### 2. Sales Overview
<p align="center">
  <img src="D2.PNG" alt="Sales Overview" width="90%" />
</p>

> *High-level executive cockpit: Total Sales ($108.91M), Total Units (3M), AVG Sales Per Unit ($802.78), Total Customers (43K), Sales by Region, Gauge Milestone, Monthly Trend (Jan–Mar), and Sales Type split (Store: 67.85%, Retail: 31.73%, Tender).*

### 3. Product Analysis
<p align="center">
  <img src="D3.PNG" alt="Product Analysis" width="90%" />
</p>

> *Portfolio-focused view: Total Products (47), Average P Price (49.89), Sales Value by Line Name, Top Products by Sales Value (led by Lamifen cr. 15gm at 15.6M), Units by Product, and Sales Value by Sales Type.*

### 4. Geographic Coverage
<p align="center">
  <img src="D4.PNG" alt="Geographic Coverage" width="90%" />
</p>

> *Territory and distribution analysis: Total Lines (7), Total Distributors (15), Total Customers (43K), Total Territories (46), Total Regions (7), Regional rankings, Territory Treemap, Line volume/value comparison, and Distributor share donut chart (Stores, POS, Direct, Ibn Sina).*

---

## 📑 Table of Contents
- [Project Overview](#-project-overview)
- [Dashboard Preview](#-dashboard-preview)
- [Business Objectives](#-business-objectives)
- [Dataset Architecture](#-dataset-architecture)
- [Data Preparation & Modeling](#-data-preparation--modeling)
- [Dashboard Pages](#-dashboard-pages)
- [Key Features](#-key-features)
- [Key Performance Indicators](#-key-performance-indicators)
- [Key Insights](#-key-insights)
- [DAX Measures](#-dax-measures)
- [Project Demonstration](#-project-demonstration)
- [Download Dashboard](#-download-dashboard)
- [Repository Structure](#-repository-structure)
- [Limitations & Considerations](#-limitations--considerations)
- [About the Author](#-about-the-author)
- [Feedback](#-feedback)

---

## 🎯 Business Objectives

The dashboard addresses critical commercial questions in pharmaceutical distribution:

- **Revenue Velocity:** What are the total sales revenue and volume for Q1, and how did sales progress month-over-month?
- **Portfolio Drivers:** Which therapeutic lines (Line 1–5, CVM, Tender) and pharmaceutical products drive the majority of commercial cash flow?
- **Price vs. Volume Elasticity:** Are revenue gains driven by high-ticket unit prices or rapid inventory turnover?
- **Channel Dynamics:** How does revenue distribute across Institutional Stores (`STORE`), Community Pharmacies (`RETAIL`), and Institutional Tenders (`Tender`)?
- **Geographic Penetration:** How do sales divide across Egypt's 7 regions and 46 micro-territories, and where are the fastest-growing territories?
- **Distributor Contribution:** What is the sales share handled by major national distributors (`POS`, `IBN SINA`, `EGY`, `SOFICO`) vs. direct retail billing?

---

## 📂 Dataset Architecture

The dataset captures transactional commercial pharmaceutical activity during the first quarter of 2025.

### Data Attributes

| Column Name | Data Type | Description |
| :--- | :---: | :--- |
| **`Month`** | DateTime | Transaction month end date (31 Jan, 28 Feb, 31 Mar 2025). |
| **`BU`** | Text | Business Unit code (`PVT` - Private Sector Commercial Operations). |
| **`DISTRIBUTOR`** | Text | Distributor or channel partner name (15 channels including IBN SINA, POS, EGY, SOFICO, STORES). |
| **`CUSTOMER CODE`** | Text | Unique identifier for the account, pharmacy, or procurement entity. |
| **`CUSTOMER NAME`** | Text | Formal commercial name of the pharmacy, hospital, clinic, or distribution hub. |
| **`Territory`** | Text | Micro-market sales territory (46 zones including Gharbia III, Behera I, Alex I, Sohag S). |
| **`REGION`** | Text | Administrative regional zone (Cairo, Giza, Alex 1, Alex 2, Delta 1, Delta 2, UE). |
| **`Line Name`** | Text | Therapeutic sales line (Line 1, Line 2, Line 3, Line 4, Line 5, CVM, Tender). |
| **`EGPI Product Name`** | Text | Commercial pharmaceutical brand/SKU name (47 unique formulations). |
| **`SALES UNITS`** | Decimal | Quantity of packs/units sold in the transaction. |
| **`P Price`** | Decimal | Pharmacy unit purchase price in EGP / USD equivalent. |
| **`SALES VALUE`** | Decimal | Gross sales revenue (`Quantity × Unit Price`). |
| **`SALES TYPE`** | Text | Classification of sale (`RETAIL`, `STORE`, `Tender`). |
| **`key`** | Text | Unique relational surrogate key combining date, region, and product. |

---

## 🧹 Data Preparation & Modeling

**Power Query** was utilized to clean, transform, and structure the data:

1. **Schema Standardization & Type Casting:** Converted financial values (`SALES VALUE`, `P Price`) into decimal currency, standardized unit quantities, and structured timestamps to calendar month-ends.
2. **Data Cleansing:** Standardized naming conventions across bilingual pharmacy and hospital records, verifying non-coded institutional store transactions.
3. **Surrogate Key Verification:** Validated compound keys (`key`) linking composite dimensional attributes (Period + Region + Product) for time and geographic integrity.
4. **Hierarchical Modeling:** Established natural drill-down paths from **Region ➔ Territory ➔ Customer** and from **Line Name ➔ Product Name**.

---

## 🗂️ Dashboard Pages

| # | Page | Purpose |
| :-: | :--- | :--- |
| 1 | **Cover Page** | Executive welcome screen with EIPICO branding, metadata, author credentials, and direct page navigation links. |
| 2 | **Sales Overview** | Macro commercial KPIs (Total Sales, Total Units, AVG Sales Per Unit, Customers), target gauge, monthly trend, and sales channel contribution. |
| 3 | **Product Analysis** | Therapeutic line comparison, top revenue-generating brands, unit volume ranking, and price-to-volume metrics. |
| 4 | **Geographic Coverage** | Regional revenue rankings, micro-territory treemap (46 territories), distributor channel shares, and line-level comparisons. |

---

## ✨ Key Features

- 🧭 **Seamless Navigation:** Top header navigation buttons (`Sales Overview`, `Product Analysis`, `Geographic Coverage`), Home button, and Reset Slicers action on every view.
- 🎛️ **Interactive Slicers:** Synchronized filter pane and visual cross-highlighting across Region, Territory, Line, and Month.
- 🎨 **Corporate Pharma Branding:** Medical-grade blue palette customized with EIPICO corporate identity.
- 📊 **Multivariate Visualizations:** Horizontal bar charts, Treemaps, Donut charts, Gauge targets, Monthly curve lines, and metric KPI cards.
- 🧮 **Optimized DAX Measures:** Dynamic volume, pricing, customer reach, and revenue aggregations.

---

## 📈 Key Performance Indicators

| KPI | Value | Description |
| :--- | :---: | :--- |
| **Total Sales Value (Revenue)** | **$108.91M** | Total gross commercial revenue generated in Q1 2025 |
| **Total Units Sold** | **3M Units** | Cumulative quantity of pharmaceutical packs distributed |
| **Average Unit Price (P Price)** | **49.89** | Arithmetic mean of catalog pharmacy purchase prices |
| **AVG Sales Per Unit** | **$802.78** | Average transaction sales realization per billing entry |
| **Total Customers** | **43K Accounts** | Distinct pharmacies, hospitals, and procurement accounts billed |
| **Therapeutic Sales Lines** | **7 Lines** | Core product lines operating across commercial divisions |
| **Nationwide Territories** | **46 Territories** | Field coverage across all 7 operational regions in Egypt |
| **Distribution Partners** | **15 Channels** | National distributors, direct supplies, and store networks |

---

## 💡 Key Insights

### 📈 Commercial Sales & Channel Dynamics
- **Total Revenue:** Reached **$108.91M** across Q1 2025, peaking in **February (~$44M)** compared to **January (~$33M)** and **March (~$32M)**.
- **Channel Contribution:** Institutional warehouse stores (**STORE**) account for **$73.90M (67.85%)** of total sales value, direct community retail pharmacies (**RETAIL**) generate **$34.55M (31.73%)**, while Institutional Tenders represent the remaining balance.

### 💊 Therapeutic Lines & Product Portfolio
- **Core Drivers:** **Line 2** dominates the portfolio, generating **$37M**, followed by **Line 1** at **$24M**, **Line 4** at **$14M**, **Line 3** at **$13M**, and **CVM** at **$12M**.
- **Top Brand Performers:**
  - **Lamifen cr. 15gm** is the leading revenue and volume engine: **$15.6M** in revenue and **1.33M units sold**.
  - **Flacort 30mg 20 tab.** ranks second in value at **$10.5M** (0.09M units).
  - **Aqua plus 100ml** generated **$9.0M** (0.31M units).
  - **Perfectodil 5%** contributed **$8.8M** (0.14M units).
  - **Lamifen 250 14 Tab.** achieved **$7.0M** (0.10M units).

### 🌍 Regional Penetration & Distributors
- **Regional Performance:** 
  - **Alex 2** leads nationwide sales with **$22.9M**.
  - **Upper Egypt (UE)** closely follows at **$20.7M**, demonstrating deep southern market penetration.
  - **Alex 1** ranks third at **$18.4M**, followed by **Giza ($12.8M)**, **Delta 2 ($12.7M)**, **Delta 1 ($10.7M)**, and **Cairo ($10.6M)**.
- **Top Territories:** The leading micro-territories by commercial revenue are **Gharbia III**, **Gharbia I**, **Behera I**, **Alex I**, and **Dakahlia I**.
- **Distributor Network:** **STORES** accounts for **$73.9M (67.85%)**, followed by Point-of-Sale (**POS** at **$16.46M / 15.11%**), **DIRECT Accounts ($7.98M / 7.33%)**, and **IBN SINA Pharma**.

---

## 🧮 DAX Measures

The foundational DAX logic powering the report's metrics:

```DAX
// 1. Total Commercial Revenue
Total Sales = 
SUM ( 'Q1 Sales Performance'[SALES VALUE] )

// 2. Total Volume Sold (Packs)
Total Units = 
SUM ( 'Q1 Sales Performance'[SALES UNITS] )

// 3. Average Price
Average of P Price = 
AVERAGE ( 'Q1 Sales Performance'[P Price] )

// 4. Average Sales Realization Per Unit
AVG Sales Per Unit = 
DIVIDE ( [Total Sales], [Total Units], 0 )

// 5. Total Customer Accounts
Total Customers = 
DISTINCTCOUNT ( 'Q1 Sales Performance'[CUSTOMER CODE] )

// 6. Active Lines Count
Total Lines = 
DISTINCTCOUNT ( 'Q1 Sales Performance'[Line Name] )

// 7. Store Sales Value
Store Sales Value = 
CALCULATE (
    [Total Sales],
    'Q1 Sales Performance'[SALES TYPE] = "STORE"
)

// 8. Retail Sales Value
Retail Sales Value = 
CALCULATE (
    [Total Sales],
    'Q1 Sales Performance'[SALES TYPE] = "RETAIL"
)
