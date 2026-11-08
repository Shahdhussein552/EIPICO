# 💊 EIPICO Commercial Sales Performance Dashboard (Q1)

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)](https://products.office.com/excel)
[![DAX](https://img.shields.io/badge/Data_Analysis-DAX-blue)](https://docs.microsoft.com/en-us/dax/)

An end-to-end commercial business intelligence dashboard developed in **Power BI** to monitor and analyze the Q1 sales performance for **EIPICO** (Egyptian International Pharmaceutical Industries Co.). 

The dashboard ingests and transforms over **135,000+ transactional records** to provide pharmaceutical executives, sales directors, and regional managers with granular visibility into revenue streams, therapeutic line velocity, price-to-volume dynamics, and nationwide territory penetration.

---

## 📌 Executive Summary & Key Metrics

* **Total Sales Value:** ~EGP 108.9M
* **Total Volume Sold:** ~3.17M units
* **Average Unit Price:** ~EGP 49.89
* **Product Portfolio:** 47 commercial products categorized across 7 specialized therapeutic lines
* **Field Scope:** 7 administrative regions covering 46 micro-territories across Egypt
* **Distribution Footprint:** 15 distinct distributors and commercial sales channels

---

## 📊 Dashboard Architecture & Views

The report is structured into three dedicated interactive views:

### 1. 📈 Sales Overview
* **Executive Cockpit:** High-level KPI cards displaying Total Revenue, Total Units Sold, Average Price per Unit, and Active Accounts.
* **Monthly Trajectory:** Tracks sales progression across January, February, and March to evaluate quarter momentum and revenue velocity.
* **Channel Distribution:** Analyzes commercial distribution across channels (`RETAIL`, `STORE`, and `Tender`).

### 2. 💊 Product Analysis
* **Line Performance:** Evaluates performance across 7 pharmaceutical lines, identifying core revenue drivers (*Line 2* and *Line 1*).
* **Top & Bottom Performers:** Ranks top revenue-generating brands (*Lamifen Cream*, *Flacort*, *Aqua Plus*, *Perfectodil*) vs. slower-moving items.
* **Price vs. Volume Dynamics:** Assesses whether product growth is value-driven or volume-driven to inform pricing strategies.
* **Product Matrix:** Granular view of unit volumes, average prices, and revenue contribution per SKU.

### 3. 🗺️ Geographic Coverage
* **Regional Breakdown:** Ranks top-performing administrative regions led by *Alex 2* (~EGP 22.9M) and *Upper Egypt (UE)* (~EGP 20.7M).
* **Territory Drill-Down:** Micro-market level performance (e.g., *Gharbia III*, *Behera*, *Dakahlia*, *Alex I*).
* **Distributor Efficiency:** Monitors distribution share across national distributors and pharmacy chains (*POS*, *Ibn Sina*, *EGY*, *Sofico*).
* **Account Performance:** Highlights key pharmacy clients and healthcare institution procurement.

---

## 🛠️ Tech Stack & Skills

* **BI Platform:** Microsoft Power BI Desktop
* **Data Preparation & ETL:** Power Query (Data cleaning, handling missing values, custom key generation, schema modeling)
* **Data Modeling & Calculations:** DAX (Aggregations, dynamic KPIs, time-intelligence, volume/value measures)
* **Visual Design:** Professional layout design, interactive slicers (Line, Region, Month), drill-down hierarchies, and layer management.

---

## 📂 Repository Structure

```text
├── Data/
│   └── sales performance.xlsx     # Source sales dataset
├── Dashboard/
│   └── EIPICO_Sales_Analysis.pbix # Power BI project file
├── Screenshots/
│   ├── 01_sales_overview.png      # Sales Overview dashboard view
│   ├── 02_product_analysis.png    # Product Analysis view
│   └── 03_geographic_coverage.png # Geographic Coverage view
└── README.md                      # Project documentation
