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
**Final Cleaned Records:** 292,439
**Columns:** 28 (transactional, demographic & feedback attributes)
**Key Fields:**
`Customer_ID, Gender, Age, Income, Product_Category, Payment_Method, Ratings, Feedback, Date, Time, Total_Amount`
**Purpose:** To understand customer purchasing behavior, segment performance, and operational efficiency.

---

## ⚙️ **Project Workflow**

```
1️⃣ Data Collection → Kaggle Retail Dataset (~3 lakh records)
2️⃣ Data Cleaning & Preprocessing (Python)
      - Removed duplicate records and duplicate Transaction_IDs
      - Handled missing values in critical fields
      - Standardized date/time and resolved mixed international date formats
      - Created new features (Time_Slot, Customer_Segment)
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

## 🧹 **Important Data Quality Fix – International Date Parsing**

During data preprocessing, an issue was identified with date parsing because the dataset contains records with different international date formats.

The original parsing logic caused valid international dates to be converted into `NaT`. Since these records were subsequently removed during missing-value handling, the dataset temporarily dropped from approximately **292K records to 177K records**.

### 🔧 **Fix**

The date parsing logic was updated to:

      ```python
      df['Date'] = pd.to_datetime(
          df['Date'],
          format='mixed',
          errors='coerce'
      )
---

## 🧹 **Important Data Quality Fix – International Date Parsing**

During data preprocessing, an issue was identified with date parsing because the dataset contains records with different international date formats.

The original parsing logic caused valid international dates to be converted into `NaT`. Since these records were subsequently removed during missing-value handling, the dataset temporarily dropped from approximately **292K records to 177K records**.

### 🔧 **Fix**

The date parsing logic was updated to:

      ```python
      df['Date'] = pd.to_datetime(
          df['Date'],
          format='mixed',
          errors='coerce'
      )

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

* Total Revenue: ₹400.22M
* Total Orders: 292.439K
* Unique Customers: 86.488K
* Avg Order Value (AOV): ₹1.37K

**Insights & RCA:**

* USA leads in revenue at approximately ₹126M, followed by the UK at approximately ₹84M.
* Chicago is the top revenue-generating city at approximately ₹29M, followed by Portsmouth at approximately ₹27M.
* Monthly revenue remains relatively stable, ranging from approximately ₹32M to ₹34M.
* Delivered orders account for the largest order-status segment at approximately 43.45%.
* Pending and Processing orders together represent a significant share of orders and can be monitored for operational improvement.

**Recommendations:**

* Monitor lower-performing months and use targeted campaigns to improve demand.
* Investigate Pending and Processing orders to identify potential operational bottlenecks.
* Continue regional marketing analysis across the USA, UK, Germany, Canada, and Australia.
* Use city-level revenue trends to identify high-value markets for targeted campaigns.

<img width="1340" height="751" alt="image" src="https://github.com/user-attachments/assets/843742e4-f1f8-4412-81cb-3089e938d096" />


---

### 🟡 **Dashboard 2 – Customer Insights**

**Purpose:** Understand demographics, repeat behavior, and income-based spending.

**Key KPIs:**

* Repeat Customers: 75K
* Avg Revenue/Customer: ₹4.63K
* Repeat Purchase %: 86.79%
* Top Age Group: 18–25 years
* Top Income Group: Medium

**Insights & RCA:**

* Repeat customers represent approximately 86.79% of the customer base.
* Medium-income and younger customers form the largest customer groups.
* The 18–25 age group represents the largest age segment.
* Average spending is relatively similar across Premium, Regular, and New customer segments.
* Customer distribution can be further analyzed by segment, income level, age group, and country.

**Recommendations:**

* Strengthen loyalty programs for repeat customers.
* Promote bundles and personalized cross-selling opportunities.
* Focus digital campaigns on the largest age and income segments.
* Analyze Premium customers separately to identify opportunities for increasing customer value.

<img width="1338" height="747" alt="image" src="https://github.com/user-attachments/assets/7f002e7e-4d88-4ff9-a6ff-08a6158f4045" />


---

### 🟢 **Dashboard 3 – Product Performance & Preferences**

**Purpose:** Analyze category & brand performance, popularity vs quality, and gender-based spend.

**Key KPIs:**

* Total Products Sold: 292K
* Avg Rating: 3.16★
* Top Category: Electronics
* Top Brand: Pepsi

**RCA Summary:**

* Electronics is the highest-revenue product category at approximately ₹94M.
* Grocery follows Electronics at approximately ₹88M.
* Pepsi is the highest-revenue brand in the current dataset.
* The Top 5 Brands by Customer Rating include BlueStar, Mitsubishi, Whirlpool, Pepsi, and Unknown.
* Male customers contribute a larger share of revenue than female customers across the displayed product categories.
* Product popularity and quality can be compared using the Product Popularity vs. Quality visualization.

**Recommendations:**

* Monitor quality and customer ratings for high-revenue product categories.
* Diversify brand performance rather than relying heavily on a small number of high-revenue brands.
* Use category-level and gender-level analysis to develop targeted marketing campaigns.
* Align inventory planning with category demand and observed monthly trends.

<img width="1336" height="749" alt="image" src="https://github.com/user-attachments/assets/b043ba7f-0ce1-49d5-855c-cc034f447d5c" />


---

### 🔵 **Dashboard 4 – Operational & Feedback Insights**

**Purpose:** Evaluate delivery, payment, and customer feedback performance.

**Key KPIs:**

* Avg Rating: 3.16★
* Total Orders: 292.44K
* Total Payment Methods: 5
* Avg Delivery Score: 1.97

**RCA Summary:**

* Excellent feedback represents approximately 33.39% of feedback records.
* Good feedback represents approximately 31.53%.
* Bad feedback represents approximately 14.29%.
* The largest customer-rating group is 4-star ratings, with approximately 95K records.
* Night shopping (9PM–5AM) represents the largest displayed shopping-time segment at approximately 97K orders.
* Same-Day and Express shipping each account for approximately 0.10M orders, while Standard shipping accounts for approximately 0.09M.
* Among the displayed feedback/order-status combinations, Delivered orders contain the largest number of Bad feedback records.

**Recommendations:**

* Conduct post-delivery satisfaction checks to understand the causes of negative feedback.
* Strengthen courier tie-ups for Same-Day and Express deliveries.
* Introduce reward points or suitable incentives for digital payments.
* Schedule promotions and support availability during high-volume night hours.
* Track rating distributions to identify opportunities for product and service quality improvement.

<img width="1337" height="750" alt="image" src="https://github.com/user-attachments/assets/b808c09a-8cf1-456f-bdb3-b37918429a65" />


---

## 📈 **Overall Business Impact**

* Unified sales, customer, product, and operational feedback data into a single interactive Power BI solution.
* Recovered **115,104 valid records** by resolving the mixed-format international date parsing issue.
* Restored the final analytical dataset to **292,439 records**.
* Identified key revenue drivers across countries, cities, product categories, and brands.
* Improved visibility into customer loyalty, demographics, and purchasing behavior.
* Analyzed customer ratings, feedback sentiment, payment methods, and shipping patterns.
* Enabled data-driven marketing, customer retention, product, and logistics decisions.
* Applied Power BI Performance Analyzer to evaluate report and visual performance after model cleanup.

---

## 🔍 **Key Learnings**

## 🔍 **Key Learnings**

* Hands-on experience with a complete analytics workflow (**Python → SQL → Power BI**).
* Improved understanding of data cleaning, preprocessing, feature engineering, and international date handling.
* Learned how incorrect date parsing can cause significant downstream data loss.
* Improved understanding of data modeling, Power Query transformations, and DAX calculations.
* Developed practical experience in customer-level, product-level, and operational analysis.
* Learned to use Power BI Performance Analyzer for report and visual performance evaluation.
* Developed the ability to translate analytical findings into actionable business strategies.
* Improved understanding of root-cause analysis and data-quality validation.

---

## ⚠️ **Project Limitations**

* Dataset limited to 5 countries (USA, UK, Germany, Canada, Australia).
* No real-time data updates — historical snapshot only.
* Customer and product inconsistencies required manual cleaning and transformation.
* Mixed international date formats required explicit handling during preprocessing.
* DAX delivery scoring is an estimate based on shipping-method categories, not actual courier tracking.
* Power BI performance was evaluated using Performance Analyzer on the current report and dataset size; it has not been tested at enterprise scale.
* Business recommendations are based on historical transaction patterns and should be validated against current operational data before implementation.

---

## 🚀 **Future Scope**

* Integrate ML models for demand and sales prediction (Python → Power BI).
* Build customer churn and customer lifetime value prediction models.
* Automate dashboard refresh via Power Automate.
* Include live or near-real-time data from e-commerce APIs.
* Build advanced customer segmentation using machine learning.
* Develop product recommendation models based on customer purchasing behavior.
* Build mobile-responsive Power BI reports.
* Scale the solution to larger enterprise datasets and cloud-based data warehouses.

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


