
# 📊 Customer Cohort Retention & Lifecycle Analysis (Power BI)

An end-to-end Business Intelligence dashboard built in **Power BI** to analyze customer retention, churn behavior, and monthly customer movement using real-world e-commerce transactional data.
## Over_View Page
<img width="1371" height="781" alt="image" src="https://github.com/user-attachments/assets/caa08371-2756-4d75-baf4-a0783d914b72" />
## cohort_details Page
<img width="1342" height="725" alt="WhatsA 04 PM" src="https://github.com/user-attachments/assets/edaedbb1-fee8-412f-b75a-9ae31739c75b" />

---

## 📌 Project Overview
Surface-level revenue metrics often hide underlying customer churn. This project shifts the focus from total sales to **customer lifecycle health** by answering three critical business questions:
1. **Retention & Churn:** How many first-time buyers return in subsequent months, and when does the sharpest drop-off occur?
2. **Customer Movement:** How does our active customer base evolve each month across **New**, **Returning**, **Recovered**, and **Lost** segments?
3. **Revenue & Geography:** Which countries generate the highest customer concentration and revenue?

---

## 📂 Dataset
* **Source:** [Online Retail II Dataset – UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/502/online+retail+ii)
* **Scope:** Real-world transactional data (2009–2011) for a UK-based online retail business, covering **5,878+ unique customers** and **$17.7M+ in total revenue**.
* **Data Cleaning (Power Query):** Removed cancelled invoices, handled missing `Customer ID` records, standardized date formats, and calculated transaction totals (`Quantity * Price`).

---

## 🏗️ Data Modeling (Star Schema)
To ensure optimal DAX performance and clean filter propagation, the data was structured into a **Star Schema**:
* **`FactSales` (Fact Table):** Transactional records including `Customer ID`, `InvoiceDate`, `Country`, `Quantity`, `Price`, `Total Sales`, and calculated lifecycle index `Month Since First Transaction`.
* **`DimCustomer` (Dimension Table):** Unique customer attributes including `Customer ID` and `First Transaction Month` (Cohort assignment).
* **`DimDate` (Dimension Table):** Dedicated calendar table supporting time-intelligence and month-over-month comparisons.

---

## 🧮 Key DAX Measures
Advanced set-theory functions (`INTERSECT`, `EXCEPT`, `CALCULATETABLE`, `SUMX`) were used to track dynamic customer states:
