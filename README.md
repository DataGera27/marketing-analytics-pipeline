# E-Commerce Sales Dashboard: End-to-End BI Solution

<img width="748" height="429" alt="image" src="https://github.com/user-attachments/assets/47348ed2-9c4d-4743-869f-e8bb3f9b9236" />


![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)

An advanced Business Intelligence and Data Engineering project that extracts, cleans, models, and visualizes transactional e-commerce data. This repository documents the entire lifecycle of the data, from raw cloud storage processing to a fully optimized Star Schema data model in Power BI.

---

## 🛠️ Step-by-Step Project Breakdown

### Phase 1: Cloud Extraction & Directory Setup (Google Colab)
* **Environment Connection:** Connected a Google Colab notebook to the cloud environment to securely access raw transactional sources.
* **Format Migration:** Processed and prepared the files to be mirrored into a structured local directory architecture (`Gerardo 2`), transforming data into a standardized, Git-compatible format for manual version control tracking.

### Phase 2: ETL & Data Cleaning (Python / Pandas)
The data underwent a rigorous cleaning pipeline to isolate dimensions and enforce data integrity:
* **Record Cleansing & Validation:** Parsed and audited a raw input dataset of **32,885 records**, filtering out duplicates and structural anomalies to arrive at a verified core of **30,666 clean transaction rows**.
* **Feature Engineering (Time Isolation):** Extracted the raw timestamp values to isolate individual fields:
  * Extracted an integer `Hour` column (values from 0 to 23) to analyze hourly operational patterns.
  * Standardized the `InvoiceDate` column for uniform date formatting.
* **Normalization (Dimension Decoupling):** Split the wide flat file into separate entities to build a proper relational star schema:
  * **`Dim_Clientes`:** Isolated user IDs and customer acquisition metadata (`AcquisitionChannel`).
  * **`Dim_Productos`:** Grouped product stock keeping units (`ProductSKU`).
  * **`Fact_Sales`:** Maintained operational numerical metrics (`Quantity`, `Ingreso_Total`, `Hour`) tied back to dimension foreign keys.

### Phase 3: Data Modeling & Architecture (Power BI)
Once the `.csv` outputs were loaded into Power BI, a professional relational model was designed:
* **Star Schema Implementation:** Linked the tables in a 1-to-many (`1:N`) topology: `Dim_Clientes`, `Dim_Productos`, and `Dim_Calendario` filtering the central `Fact_Sales` table.
* **Time Intelligence Optimization:** Created a dedicated **`Dim_Calendario`** table using a continuous date column (`Date`), completely bypassing Power BI's automatic date hierarchies to allow smooth time-series analysis.
* **Chronological Sorting Logic:** Fixed a typical visualization bug where hours sorted by total volume instead of time. Configured the `Total_Transacciones by Hour` chart to explicitly sort by the `Hour` numerical column ascendingly, achieving a true 24-hour chronological timeline view.
* **Business KPI Metrics (DAX):** Built the core reporting metrics using explicit Data Analysis Expressions measures inside `Fact_Sales`:
  * `Ingreso_Total = SUM(Fact_Sales[Ingreso_Total])`
  * `Total_Transacciones = COUNT(Fact_Sales[InvoiceID])`
  * `Ticket_Promedio (Media) = DIVIDE([Ingreso_Total], [Total_Transacciones], 0)`

### Phase 4: UI/UX Dashboard Design & Polish
The front-end design was structured to balance executive readability with corporate UI styling:
* **Canvas Layout:** Applied a soft-grey background (`#F8F9FA`) paired with white floating visual cards using modern rounded corners (border-radius) and subtle drop shadows.
* **Symmetrical Distribution:** Structured the report into an upper KPI block (3 Cards aligned at the top) and a lower analytical block (3 Charts aligned horizontally).
* **Visual Breakdown:**
  1. **Total Incomes Trend Chart:** Line graph displaying cumulative historical income across years, quarters, and months (2025–2026).
  2. **Total Transactions by Hour Chart:** Chronological bar chart pinpointing server and traffic load distribution.
  3. **Total Incomes by Acquisition Channel Chart:** Funnel breakdown detailing revenue capture via **Web ($8.72M)**, **Mobile App ($4.53M)**, and **B2B Portal ($2.77M)**.
  4. **Product Slicer:** Added a horizontal `ProductSKU` segmentator allowing stakeholders to instantly filter all 6 visual elements on the fly.

---

## 🚀 Repository Structure

```text
├── data/                    # Processed dimension and fact tables (.csv)
├── notebooks/               # Google Colab Python ETL & cleaning scripts
└── pbix/                    # Production Power BI Dashboard file (.pbix)
