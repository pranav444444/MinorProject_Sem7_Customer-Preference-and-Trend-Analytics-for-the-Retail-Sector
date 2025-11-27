## 🛍️ **Customer Preference and Trend Analytics for Retail Sector**

**A Retail Business Intelligence Project | Semester 7 Minor Project**

**Author:** Pranav Patel (22CS060)

**Department of Computer Science and Engineering, CSPIT-CSE**

**Internal Guide:** Prof. Akshita Kadam

**Industry Mentor:** Mr. Divyang Shah (Founder & CEO, Electrosoft)

---


## 🎯 **Objective**

To analyze customer preferences, purchasing behavior, and transaction trends using data-driven dashboards, enabling the retail business to make informed decisions that improve profitability, marketing strategy, and customer retention.

---

## 🧩 **Dataset Information**

**Source:** [Kaggle – Retail Transactional Dataset](https://www.kaggle.com/datasets/bhavikjikadara/retail-transactional-dataset)
**Records:** ~3,00,000 transaction and customer records
**Columns:** 28 (transactional, demographic & feedback attributes)
**Key Fields:**
`Customer_ID, Gender, Age, Income, Product_Category, Payment_Method, Ratings, Feedback, Date, Time, Total_Amount`
**Purpose:** To understand customer purchasing behavior, segment performance, and operational efficiency.

---

## ⚙️ **Project Workflow**

```
1️⃣ Data Collection → Kaggle Retail Dataset (~3 lakh records)
2️⃣ Data Cleaning & Preprocessing (Python)
      - Removed duplicates, handled missing values
      - Standardized date/time, created new features (Time_Slot, Customer_Segment)
3️⃣ Exploratory Data Analysis (EDA) in Python
      - 14 charts: revenue trends, demographics, product mix, and feedback
4️⃣ SQL Integration (SQLite3)
      - Built star schema (Fact_Transaction, Dim_Customer, Dim_Product, Dim_Date)
      - Extracted structured tables (output_*.csv)
5️⃣ Power BI Visualization
      - Developed 4 interactive dashboards with slicers, DAX KPIs & storytelling
6️⃣ Insights, RCA & Recommendations
      - Actionable business insights and performance improvement strategies
```

---

## 🧠 **Tools & Technologies Used**

| Tool                          | Purpose                                                 |
| ----------------------------- | ------------------------------------------------------- |
| **Python (Jupyter Notebook)** | Data cleaning, preprocessing, EDA                       |
| **SQLite3**                   | Data storage, relational modeling, SQL querying         |
| **Power BI**                  | Dashboard creation & storytelling                       |
| **Power Query**               | Data transformation & model integration                 |
| **DAX**                       | Calculated measures (e.g., Delivery Score, Repeat Rate) |
| **Excel**                     | Intermediate data validation                            |

---

## 🧩 **Entity Relationship Diagram (Power BI Data Model)**

<img width="1010" height="727" alt="image" src="https://github.com/user-attachments/assets/0f1e5a3d-d479-4477-97ce-400ed07f2151" />

-> This Power BI data model connects cleaned transactional data (df_time_cleaned) with multiple dimension tables (Customer, Product, Calendar, and supporting outputs) to enable efficient DAX calculations and interactive visualizations.

## 📊 **Dashboard Summaries**

---

### 🟣 **Dashboard 1 – Global Sales Overview**

**Purpose:** Track total revenue, orders, and customer performance by region, city, and month.

**Key KPIs:**

* Total Revenue: ₹242.61M
* Total Orders: 177K
* Unique Customers: 77K
* Avg Order Value (AOV): ₹1.37K

**Insights & RCA:**

* USA and UK lead in revenue; Chicago is top city.
* Spikes in March–April & October–November.
* Pending/Processing orders (~35%) slow deliveries.

**Recommendations:**

* Run campaigns in Feb & June (low months).
* Improve warehouse automation to reduce Pending orders.
* Expand marketing in Canada & Australia.

<img width="1340" height="751" alt="image" src="https://github.com/user-attachments/assets/843742e4-f1f8-4412-81cb-3089e938d096" />


---

### 🟡 **Dashboard 2 – Customer Insights**

**Purpose:** Understand demographics, repeat behavior, and income-based spending.

**Key KPIs:**

* Repeat Customers: 68%
* Avg Revenue/Customer: ₹3.14K
* Top Age Group: 18–25 years
* Top Income Group: Medium

**Insights & RCA:**

* High retention but low upselling potential.
* Medium-income & young customers dominate sales.
* AOV stable across groups → underused cross-selling.

**Recommendations:**

* Strengthen loyalty programs for repeat & premium customers.
* Promote bundles and personalized upsells.
* Focus digital ads on 18–25 demographic.

<img width="1338" height="747" alt="image" src="https://github.com/user-attachments/assets/7f002e7e-4d88-4ff9-a6ff-08a6158f4045" />


---

### 🟢 **Dashboard 3 – Product Performance & Preferences**

**Purpose:** Analyze category & brand performance, popularity vs quality, and gender-based spend.

**Key KPIs:**

* Total Products Sold: 177K
* Avg Rating: 3.17★
* Top Category: Electronics (₹57M)
* Top Brand: Pepsi (₹25M)

**RCA Summary:**

* Electronics & Grocery dominate revenue but moderate ratings.
* Brand concentration among top 5 brands.
* Male customers contribute 60–65% of revenue.
* Stable monthly trends with slight seasonal peaks.

**Recommendations:**

* Improve quality for Electronics via post-sale checks.
* Diversify supplier network; promote mid-tier brands.
* Gender-focused campaigns to grow female engagement.
* Plan inventory around March–April & Aug–Oct peaks.

<img width="1336" height="749" alt="image" src="https://github.com/user-attachments/assets/b043ba7f-0ce1-49d5-855c-cc034f447d5c" />


---

### 🔵 **Dashboard 4 – Operational & Feedback Insights**

**Purpose:** Evaluate delivery, payment, and customer feedback performance.

**Key KPIs:**

* Avg Rating: 3.17★
* Avg Delivery Score: 1.97
* Excellent Feedback: 33%
* Night Orders (9PM–5AM): 59K

**RCA Summary:**

* Bad feedback linked to Delivered orders → packaging/quality issues.
* Same-Day & Express shipments preferred (high demand).
* Peak orders at night → need for late-hour service support.

**Recommendations:**

* Conduct post-delivery satisfaction checks.
* Strengthen courier tie-ups for express deliveries.
* Introduce reward points for digital payments.
* Schedule promotions & support availability during night hours.

<img width="1337" height="750" alt="image" src="https://github.com/user-attachments/assets/b808c09a-8cf1-456f-bdb3-b37918429a65" />


---

## 📈 **Overall Business Impact**

* Unified view of sales, customer, product, and feedback data.
* Identified key revenue drivers and underperforming regions.
* Improved understanding of customer loyalty & feedback trends.
* Enabled data-driven marketing and logistics decisions.

---

## 🔍 **Key Learnings**

* Hands-on experience with complete analytics workflow (Python → SQL → Power BI).
* Improved understanding of data modeling, DAX calculations, and storytelling.
* Developed ability to translate data into actionable business strategies.

---

## ⚠️ **Project Limitations**

* Dataset limited to 5 countries (US, UK, Germany, Canada, Australia).
* No real-time data updates — historic snapshot only.
* Customer and product inconsistencies required manual cleaning.
* DAX delivery scoring is an estimate, not real courier tracking.
* Power BI performance tuned for 3L rows — not yet enterprise-scaled.

---

## 🚀 **Future Scope**

* Integrate ML models for demand & sales prediction (Python → Power BI).
* Automate dashboard refresh via Power Automate.
* Include live streaming data from e-commerce APIs.
* Build mobile-responsive Power BI reports.

---

## 📁 **Folder Structure**

```
📦 Retail_Analytics_Project
│
├── 📂 Extra notes for my reference        # Viva and explanation prep (personal use)
├── 📂 images                              # Dashboard backgrounds & visuals
├── 📂 PPT and final report                # Project PPT & final written report
│
├── 🧾 new_retail_data.csv                 # Raw Kaggle dataset (~3 lakh records)
├── 🧾 df_full_cleaned.csv                 # Cleaned dataset (Phase 1 output)
├── 🧾 df_time_cleaned.csv                 # Time-transformed dataset (Phase 2 output)
├── 🧾 output_*.csv                        # SQL query outputs used for Power BI modeling
│
├── 📊 retail_analysis_dashboard.pbix      # Final Power BI dashboard file
├── 🧠 sample_retail_sales.ipynb           # Python + SQL notebook
├── 🧰 retail.sqlite / retail_analytics.db # SQLite databases
│
└── 📄 README.md                           # Project documentation (this file)
```

---

## 🧾 **Citation**

Dataset Source:

> Kaggle – Retail Transactional Dataset by Bhavik Jikadara
> [https://www.kaggle.com/datasets/bhavikjikadara/retail-transactional-dataset](https://www.kaggle.com/datasets/bhavikjikadara/retail-transactional-dataset)

---

✅ **Final Note:**
This project demonstrates the **complete data analytics lifecycle** — from data cleaning and EDA in Python to SQL integration and advanced Power BI dashboards — resulting in a **360° retail analytics solution** that connects customer behavior, product performance, and operational efficiency in one interactive system.


