<div align="center">

# 💊 EIPICO Commercial Sales Dashboard | Power BI
### Turning Pharmaceutical Sales Data into Strategic Market Insights

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Data%20Analysis%20Expressions-0078D4?style=for-the-badge)](https://learn.microsoft.com/en-us/dax/)
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)](#)

<p align="center">
  <b>An interactive Business Intelligence project exploring EIPICO Q1 commercial sales performance across therapeutic lines, product portfolios, regional footprints, customer demographics, and distribution channels.</b>
  <br />
  <i>Track. Analyze. Grow. — Nationwide Commercial Intelligence in One Screen.</i>
</p>

</div>

---

## 📌 Project Overview

The **EIPICO Commercial Sales Dashboard** is an interactive Power BI project built to explore pharmaceutical sales performance across product lines, geographic locations, and customer groups.

The project transforms raw pharmaceutical transaction records into visual insights, helping decision-makers investigate performance trends, evaluate therapeutic line velocity, track sales volume, and explore market penetration across Egyptian regions, governorates, and micro-territories.

### 📋 Project at a Glance

| Project Detail | Description |
| :--- | :--- |
| **Project Name** | EIPICO Commercial Sales Performance Dashboard |
| **Domain** | Pharmaceutical Commercial & Distribution Sales Analytics |
| **Sales Period** | 01 Jan 2025 – 31 Mar 2025 (Q1 2025) |
| **Categories** | 7 Therapeutic Lines (Line 1, Line 2, Line 3, Line 4, Line 5, CVM, Tender) |
| **Records** | 135,666 sales lines (42,212 unique accounts / 43K Customers) |
| **Dashboard Pages** | 4 (Home Page, Sales Overview, Product Analysis, Geographic Coverage) |
| **Main Tool** | Microsoft Power BI Desktop |
| **Data Preparation** | Power Query (type casting, surrogate key relationships, data cleaning) |
| **Calculations** | DAX (explicit measures, average price per unit, customer count) |

> **Important:** Each row in `sales performnce.xlsx` represents a single transaction line item. Revenue is calculated from `SALES VALUE`, and units sold from the sum of `SALES UNITS`.

---

## 📸 Dashboard Preview

### 1. Cover / Home Page
<p align="center">
  <img src="D1.PNG" alt="Home Page" width="90%" />
</p>

> *The landing page with project title, author credit (Shahd Hussein), and navigation buttons to every report page.*

### 2. Sales Overview
<p align="center">
  <img src="D2.PNG" alt="Sales Overview" width="90%" />
</p>

> *High-level KPIs (Total Sales: $108.91M, Total Units: 3M, AVG Sales Per Unit: $802.78, Total Customers: 43K), sales by region, sales by month trajectory (Jan–Mar), sales type split (STORE: 67.85%, RETAIL: 31.73%, Tender), and a gauge tracking total sales against a milestone target ($120.00M).*

### 3. Product Analysis
<p align="center">
  <img src="D3.PNG" alt="Product Analysis" width="90%" />
</p>

> *Product-side view: Total Products (47), Average of P Price (49.89), Total Customers (43K), AVG Sales Per Unit ($802.78); sales value by line name, top products by sales value (led by Lamifen cr. 15gm at 15.6M), units by product, and sales value by sales type.*

### 4. Geographic Coverage
<p align="center">
  <img src="D4.PNG" alt="Geographic Coverage" width="90%" />
</p>

> *Geographic view: Total Lines (7), Total Distributors (15), Total Customers (43K), Total Territories (46), Total Regions (7); sales by region, territory treemap, sales value and units by line name, and distributor share donut chart (Stores: 67.85%, POS: 15.11%, Direct: 7.33%, Ibn Sina).*

---

## 📑 Table of Contents
- [Project Overview](#-project-overview)
- [Dashboard Preview](#-dashboard-preview)
- [Business Objectives](#-business-objectives)
- [Dataset](#-dataset)
- [Data Preparation](#-data-preparation)
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

The project explores the following analytical questions:

- **Revenue & Volume:** What are the total sales revenue, total units sold, and average price realization?
- **Line Contribution:** Which therapeutic lines (Line 1–5, CVM, Tender) drive the most commercial revenue and unit velocity?
- **Product Performance:** Which pharmaceutical products generate the most revenue, and which move the highest pack volumes?
- **Regional Distribution:** How are sales distributed across geographical regions (Alex 1 & 2, Upper Egypt, Giza, Delta 1 & 2, Cairo) and 46 micro-territories?
- **Channel Dynamics:** How does revenue split across commercial sales channels (Institutional Stores, Retail Pharmacies, Tenders)?
- **Distributor Concentration:** What is the sales share handled by primary distribution channels (POS, Ibn Sina, EGY, Sofico) versus direct supply?

---

## 📂 Dataset

The data model represents a commercial pharmaceutical distribution ecosystem: a comprehensive transaction table capturing private-sector sales across products, territories, and supply partners.

### Dataset Table

| Table | File | Rows | Description |
| :--- | :--- | :---: | :--- |
| **`Q1 Sales Performance`** | [`sales performnce.xlsx`](sales%20performnce.xlsx) | 135,666 | Transaction lines: `Month`, `BU`, `DISTRIBUTOR`, `CUSTOMER CODE`, `CUSTOMER NAME`, `Territory`, `REGION`, `Line Name`, `EGPI Product Name`, `SALES UNITS`, `P Price`, `SALES VALUE`, `SALES TYPE`, `key`. |

---

## 🧹 Data Preparation

**Power Query** was used to prepare and model the dataset before reporting:

1. **Importing & Schema Verification:** Loaded transactional sales data and verified data integrity across 135K+ rows.
2. **Data Type Casting:** Applied fixed decimal currency formatting to financial values (`SALES VALUE`, `P Price`), whole numbers to quantities (`SALES UNITS`), and date formats to month-end dates.
3. **Relationships & Key Formulations:** Verified composite surrogate keys (`key`) combining date, region, and product SKU to ensure dimensional consistency across time and territory.

---

## 🗂️ Dashboard Pages

| # | Page | Purpose |
| :-: | :--- | :--- |
| 1 | **Home Page** | Cover page with EIPICO branding, project title, author credit, and navigation buttons. |
| 2 | **Sales Overview** | Total Sales, Total Units, AVG Sales Per Unit, Customers; sales by region; monthly trend; sales type split; and sales milestone gauge. |
| 3 | **Product Analysis** | Total products, average catalog price; sales value by line; top products by revenue; pack volume ranking; and sales type comparison. |
| 4 | **Geographic Coverage** | Total lines, distributors, territories, and regions; sales by region; territory treemap; line performance; and distributor market share. |

---

## ✨ Key Features

- 🧭 **Custom navigation:** page buttons, home button, and reset slicers action on every page.
- 🎛️ **Interactive filtering:** an expandable filter pane (collapsible bookmark slicers) and visual cross-highlighting.
- 🎨 **Consistent branding:** medical-grade corporate blue and white color palette across all pages.
- 📊 **Multiple visual types:** horizontal bar charts, line charts, donut charts, gauge, treemap, and KPI cards.
- 🧮 **Explicit DAX measures** for total sales, units, customer counts, line totals, and average unit realizations.

---

## 📈 Key Performance Indicators

| KPI | Value |
| :--- | :---: |
| **Total Sales (Revenue)** | $108.91M |
| **Total Units Sold** | 3M Units |
| **AVG Sales Per Unit** | $802.78 |
| **Average of P Price** | 49.89 |
| **Total Customers** | 43K |
| **Total Products** | 47 |
| **Total Lines** | 7 |
| **Total Territories** | 46 |
| **Total Regions** | 7 |
| **Total Distributors** | 15 |

---

## 💡 Key Insights

### 🛒 Sales & Lines
- **Line 2** leads company sales with **$37M**, followed by **Line 1** at **$24M**, **Line 4** at **$14M**, **Line 3** at **$13M**, and **CVM** at **$12M**. Together, Line 2 and Line 1 generate over 56% of total revenue.
- **Line 5 ($8M)** and **Tenders ($1M)** represent niche and institutional volume segments.
- Sales peaked in **February (~$44M)** compared to **January (~$33M)** and **March (~$32M)**.
- By sales type, **STORE (67.85% / $73.90M)** dominates wholesale and institutional distribution, while direct pharmacy **RETAIL (31.73% / $34.55M)** accounts for nearly one-third.

### 📦 Products
- **Lamifen cr. 15gm** is the top-selling brand, generating **$15.6M** in revenue and **1.33M units sold**.
- It is followed by **Flacort 30mg 20 tab. ($10.5M)**, **Aqua plus 100ml ($9.0M)**, and **Perfectodil 5% ($8.8M)**.
- Products exhibit distinct volume vs. price dynamics: dermatological treatments (*Lamifen*) drive high unit velocity, whereas corticosteroids (*Flacort*) achieve higher value per pack.

### 🌍 Locations & Distributors
- **Alex 2** is the largest commercial region at **$22.9M**, followed closely by **Upper Egypt (UE)** at **$20.7M** and **Alex 1** at **$18.4M**.
- Urban metropolitan governorates follow: **Giza ($12.8M)**, **Delta 2 ($12.7M)**, **Delta 1 ($10.7M)**, and **Cairo ($10.6M)**.
- Across 46 micro-territories, **Gharbia III**, **Gharbia I**, **Behera I**, **Alex I**, and **Dakahlia I** are top contributors.
- **STORES ($73.9M / 67.85%)** and Point-of-Sale (**POS at $16.46M / 15.11%**) form the backbone of distribution, supplemented by **DIRECT ($7.98M / 7.33%)** and **IBN SINA Pharma**.

---

## 🧮 DAX Measures

The measures below reflect the logic behind the dashboard KPIs. The full, exact versions are inside the `.pbix` file.

```DAX
Total Sales = SUM ( 'Q1 Sales Performance'[SALES VALUE] )

Total Units = SUM ( 'Q1 Sales Performance'[SALES UNITS] )

AVG Sales Per Unit = DIVIDE ( [Total Sales], [Total Units] )

Total Customers = DISTINCTCOUNT ( 'Q1 Sales Performance'[CUSTOMER CODE] )

Total Products = DISTINCTCOUNT ( 'Q1 Sales Performance'[EGPI Product Name] )

Total Lines = DISTINCTCOUNT ( 'Q1 Sales Performance'[Line Name] )

Total Territory = DISTINCTCOUNT ( 'Q1 Sales Performance'[Territory] )

Total Regions = DISTINCTCOUNT ( 'Q1 Sales Performance'[REGION] )

Total Distributor = DISTINCTCOUNT ( 'Q1 Sales Performance'[DISTRIBUTOR] )
