# Customer Analytics & Performance Report: End-to-End Data Project
**Swynex Technologies — Data Analytics Internship Capstone Project**

---

## 1. Problem Statement
Retail organizations generate transactional data across diverse touchpoints, often introducing data quality issues such as inconsistent survey scales, corrupted numerical values, missing entries, and outlier transactions. 

The objective of this project is to:
- Clean and normalize an unstandardized retail dataset.
- Perform exploratory data analysis (EDA) to uncover sales patterns and demographic distributions.
- Build an interactive executive dashboard to monitor business KPIs.
- Deliver actionable, data-driven business recommendations.

---

## 2. Dataset Information
The dataset comprises retail transaction logs representing customer demographics, purchase behavior, and satisfaction feedback across multiple urban centers.

- **Total Records:** 124 transactions
- **Core Attributes:**
  - `CustomerID`: Unique customer identification
  - `Name`, `Gender`, `Age`: Customer demographic attributes
  - `City`: Geographical market (Varanasi, Kolkata, Delhi, Bengaluru, Mumbai, Chennai, Hyderabad, Pune)
  - `JoinDate`, `JoinYear`, `JoinMonth`: Account acquisition timeline (2021–2024)
  - `ProductCategory`: Merchandise segment (Groceries, Books, Clothing, Electronics, Furniture, Other)
  - `PurchaseAmount`: Order transaction value (INR)
  - `Rating`: Customer satisfaction score

---

## 3. Data Cleaning & Preparation Process (Task 1)
Using Python and Pandas, the raw transaction dataset underwent systematic data quality handling:
1. **Missing Value Imputation:** Handled missing geographic and category fields; standardized categorical casing and whitespace.
2. **Anomaly Correction (Age):** Addressed data entry errors (such as typographical extreme age values) by validating authentic ranges (18 to 63 years).
3. **Date Parsing & Feature Engineering:** Extracted `JoinYear` and `JoinMonth` from datetime stamps to enable chronological grouping.
4. **Rating Scale Analysis:** Flagged inconsistency where standard ratings ranged from 0.0 to 5.0, but select feedback entries were recorded at 10.0 due to mixed survey formats.
5. **Data Export:** Validated schema consistency and exported clean records to `cleaned_data.csv`.

---

## 4. Exploratory Data Analysis & Findings (Task 2)
Statistical profiling and visualization using Pandas, Matplotlib, and Seaborn identified key patterns:

- **Revenue Asymmetry:** 
  - Mean Purchase Amount: ₹3,406.15
  - Median Purchase Amount: ₹2,577.04
  - A significant revenue outlier of ₹99,999.99 was detected in Varanasi under the "Other" category. Due to this extreme value, median purchase metrics reflect actual customer purchasing behavior more reliably than the mean.
- **Category Volume vs. Basket Size:**
  - **Volume Drivers:** Groceries (₹74,389) and Books (₹71,617) generate the highest order frequency.
  - **Basket Size:** Clothing yielded the highest average order value (₹3,023.17 per order), highlighting high basket profitability.
- **Geographic Concentration:** Over 46.8% of the customer base is situated in Kolkata, Varanasi, and Delhi.

---

## 5. Executive Interactive Dashboard (Task 3)
An interactive business intelligence dashboard was constructed in **Power BI Desktop** to provide stakeholders with multi-dimensional exploration.

### Core Metrics (KPIs):
- **Total Customers:** 124 distinct customers
- **Total Revenue:** ₹422.36K
- **Average Order Value (AOV):** ₹3.41K

### Interactive Features:
- Dropdown slicers for **City**, **Gender**, and **Year** enable instant report filtering across all visuals.
- Single-page layout containing:
  - Horizontal Bar Chart: Customer distribution by City.
  - Vertical Column Chart: Revenue by City highlighting geographic volume.
  - Pie / Share Visual: Revenue breakdown by Product Category.
  - Trend Charts: Acquisition volume and revenue trajectory from 2021 to 2024.

---

## 6. Strategic Business Recommendations
1. **Implement Outlier & Fraud Detection:** Introduce threshold alerts for transactions exceeding standard limits (such as the ₹99,999.99 anomaly) to verify bulk orders or catch logging errors.
2. **Scale Survey Standardization:** Harmonize customer feedback interfaces strictly to a 5-star scale at entry to prevent survey scale mixing.
3. **Targeted Regional Marketing:** Capitalize on established traction in Varanasi, Kolkata, and Delhi through localized campaigns and optimized fulfillment networks.
4. **Category Cross-Selling:** Pair high-volume categories (Groceries, Books) with high-AOV categories (Clothing) to grow total order values.

---

## 7. Project Deliverables
- `SWYNEX_Task2_Exploratory_Data_Analysis.ipynb`: Python EDA notebook.
- `SWYNEX_Task3_Interactive_Dashboard.pbix`: Power BI report file.
- `cleaned_data.csv`: Cleaned dataset.
- `dashboard_overview.png`: Dashboard report preview.
