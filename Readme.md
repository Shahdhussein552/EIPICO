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
| **Records** | 135,666 transaction lines (42,212 unique accounts/customers) |
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

> *The landing view featuring branding, project title, author credentials, and interactive page navigation.*

### 2. Sales Overview
<p align="center">
  <img src="D2.PNG" alt="Sales Overview" width="90%" />
</p>

> *High-level executive cockpit: Total Revenue, Units Sold, Average Price, monthly sales trajectory (Jan–Mar), and channel distribution split (Store, Retail, Tender).*

### 3. Product Analysis
<p align="center">
  <img src="D3.PNG" alt="Product Analysis" width="90%" />
</p>

> *Therapeutic line performance comparison, top-revenue generating brands, price-to-volume velocity, and granular SKU-level performance metrics.*

### 4. Geographic Coverage
<p align="center">
  <img src="D4.PNG" alt="Geographic Coverage" width="90%" />
</p>

> *Regional breakdown across 7 administrative zones, top 10 commercial micro-territories, distributor contribution shares, and key healthcare account concentration.*

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
| **`P Price`** | Decimal | Pharmacy unit purchase price in EGP. |
| **`SALES VALUE`** | Decimal | Gross sales revenue in EGP (`Quantity × Unit Price`). |
| **`SALES TYPE`** | Text | Classification of sale (`RETAIL`, `STORE`, `Tender`). |
| **`key`** | Text | Unique relational surrogate key combining date, region, and product. |

---

## 🧹 Data Preparation & Modeling

**Power Query** was utilized to clean, transform, and structure the data:

1. **Schema Standardization & Type Casting:** Converted financial values (`SALES VALUE`, `P Price`) into decimal currency, standardized unit quantities, and structured timestamps to calendar month-ends.
2. **Data Cleansing:** Imputed missing values for non-coded institutional stores and standardized naming conventions across bilingual pharmacy and hospital records.
3. **Surrogate Key Verification:** Validated compound keys (`key`) linking composite dimensional attributes (Period + Region + Product) for time and geographic integrity.
4. **Hierarchical Modeling:** Established natural drill-down paths from **Region ➔ Territory ➔ Customer** and from **Line Name ➔ Product Name**.

---

## 🗂️ Dashboard Pages

| # | Page | Purpose |
| :-: | :--- | :--- |
| 1 | **Cover Page** | Executive welcome screen with project metadata, branding, and direct navigation links. |
| 2 | **Sales Overview** | Macro commercial KPIs (Revenue, Packs, Average Price, Accounts), monthly growth trend, and sales channel contribution. |
| 3 | **Product Analysis** | Therapeutic line comparison, top revenue-generating brands, unit volume ranking, and price-to-volume matrix. |
| 4 | **Geographic Coverage** | Regional revenue rankings, micro-territory deep dive (46 territories), distributor channel shares, and key account tables. |

---

## ✨ Key Features

- 🧭 **Seamless Navigation:** Integrated action buttons, page links, and interactive reset filters on every view.
- 🎛️ **Synchronized Slicers:** Dynamic filtering by Month, Therapeutic Line, Region, Territory, and Distributor with synchronized cross-highlighting.
- 🎨 **Corporate Pharma Branding:** Clean, medical-grade color palette balancing deep navy, teal, and slate gray for optimal readability.
- 📊 **Multivariate Visualizations:** Clustered bar charts, 100% stacked channel charts, monthly trend lines, and KPI cards with conditional alerts.
- 🧮 **Optimized DAX Measures:** Centralized measures table for dynamic volume, pricing, customer reach, and revenue aggregations.

---

## 📈 Key Performance Indicators

| KPI | Value | Description |
| :--- | :---: | :--- |
| **Total Sales Value (Revenue)** | **EGP 108.91M** | Total gross commercial revenue generated in Q1 2025 |
| **Total Units Sold** | **3.17M Packs** | Cumulative quantity of pharmaceutical units distributed |
| **Average Unit Price (Listed)** | **EGP 49.89** | Arithmetic mean of pharmacy purchasing prices |
| **Weighted Average Realized Price** | **EGP 34.33** | Actual realized price per unit sold across the entire portfolio |
| **Active Customer Accounts** | **42,212 Accounts** | Distinct pharmacies, hospitals, and medical centers billed |
| **Therapeutic Sales Lines** | **7 Lines** | Core product lines operating across commercial divisions |
| **Nationwide Territories** | **46 Territories** | Field coverage across all 7 operational regions in Egypt |

---

## 💡 Key Insights

### 📈 Commercial Sales & Channel Dynamics
- **Total Revenue:** Reached **EGP 108.91M** across Q1 2025, with peak sales observed in **February (EGP 44.04M / 1.22M units)** compared to **January (EGP 32.76M)** and **March (EGP 32.12M)**.
- **Channel Contribution:** Institutional warehouse stores (**STORE**) account for **EGP 73.90M (~67.8%)** of total sales value, direct community retail pharmacies (**RETAIL**) generate **EGP 34.55M (~31.7%)**, while Institutional Tenders contribute **EGP 460.5K**.

### 💊 Therapeutic Lines & Product Portfolio
- **Core Drivers:** **Line 2** dominates the portfolio, generating **EGP 36.79M (1.60M units)**, followed by **Line 1** at **EGP 24.19M (538.9K units)**. Together, these two lines account for **56% of total company revenue**.
- **Top Brand Performers:**
  - **Lamifen Cream 15gm** is the company's leading revenue and volume engine: **EGP 15.57M** from **1.33M units sold**.
  - **Flacort 30mg 20 tab.** ranks second in value at **EGP 10.55M** (93.3K units) due to higher unit value.
  - **Aqua Plus 100ml** generated **EGP 8.96M** (306.3K units).
  - **Perfectodil 5%** contributed **EGP 8.77M** (143.6K units).
  - **Lamifen 250 14 Tab.** achieved **EGP 7.00M** (96.1K units).
- **Price vs. Volume Insights:** High revenue in dermatological anti-fungals (*Lamifen*) is volume-driven, whereas corticosteroids (*Flacort*) and cardiovascular agents (*Vildabetes*) are margin/value-driven.

### 🌍 Regional Penetration & Distributors
- **Regional Performance:** 
  - **Alex 2** leads nationwide sales with **EGP 22.88M (562.9K units)**.
  - **Upper Egypt (UE)** closely follows at **EGP 20.74M (601.7K units)**, demonstrating deep southern market penetration.
  - **Alex 1** ranks third at **EGP 18.43M (537.0K units)**, followed by **Giza (EGP 12.84M)**, **Delta 2 (EGP 12.68M)**, **Delta 1 (EGP 10.74M)**, and **Cairo (EGP 10.60M)**.
- **Top Territories:** The leading micro-territories by commercial revenue are **Gharbia III (EGP 6.06M)**, **Gharbia I (EGP 3.93M)**, **Behera I (EGP 3.69M)**, **Alex I (EGP 3.38M)**, and **Dakahlia I (EGP 3.34M)**.
- **Distributor Network:** **STORES** and Point-of-Sale (**POS** at **EGP 16.46M**) represent the primary supply path, complemented by **Direct Pharmacy Accounts (EGP 7.98M)**, **Ibn Sina Pharma (EGP 3.62M)**, and **Egyptian Co. / EGY (EGP 2.44M)**.

---

## 🧮 DAX Measures

The foundational DAX logic powering the report's metrics:

```DAX
// 1. Total Commercial Revenue
Total Sales Value = 
SUM ( 'Q1 Sales Performance'[SALES VALUE] )

// 2. Total Volume Sold (Packs)
Total Sales Units = 
SUM ( 'Q1 Sales Performance'[SALES UNITS] )

// 3. Average Unit Price (Catalog Average)
Average Unit Price = 
AVERAGE ( 'Q1 Sales Performance'[P Price] )

// 4. Weighted Realized Unit Price
Weighted Realized Price = 
DIVIDE ( [Total Sales Value], [Total Sales Units], 0 )

// 5. Total Billed Accounts
Total Active Customers = 
DISTINCTCOUNT ( 'Q1 Sales Performance'[CUSTOMER CODE] )

// 6. Total Unique Products
Active Products Count = 
DISTINCTCOUNT ( 'Q1 Sales Performance'[EGPI Product Name] )

// 7. Store Sales Value
Store Sales Value = 
CALCULATE (
    [Total Sales Value],
    'Q1 Sales Performance'[SALES TYPE] = "STORE"
)

// 8. Retail Sales Value
Retail Sales Value = 
CALCULATE (
    [Total Sales Value],
    'Q1 Sales Performance'[SALES TYPE] = "RETAIL"
)
