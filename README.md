Customer Preference and Trend Analytics for the Retail Sector
Project Summary
This end-to-end data analytics project analyzes a retail dataset of over 290,000 transactions to uncover key insights into customer behavior, product performance, and operational trends. The project encompasses the entire analytics lifecycle, from data cleaning and preprocessing in Python to the development of a suite of four interactive dashboards in Power BI. The final result is a powerful business intelligence tool for data-driven decision-making.

Phases of the Project
Phase 1: Data Cleaning & Preprocessing (Python)
Handled missing values, standardized data formats, and removed duplicate records to ensure data quality.

Engineered new features from raw data, such as Time_Slot, Year, and Month, to enable deeper time-based analysis.

Filtered an initial dataset of ~293,000 records down to a high-quality, analysis-ready dataset of ~177,000 records with valid temporal data.

Phase 2: Exploratory Data Analysis (EDA) (Python)
Conducted statistical summaries and developed 14 key visualizations using Matplotlib and Seaborn to uncover initial patterns in sales, customer demographics, and product preferences.

This phase was crucial for identifying significant data integrity issues, such as inconsistent customer attributes (Gender, Age, Income) for the same Customer_ID.

Phase 3: SQL Analysis & Data Modeling (Python/SQLite & Power BI)
Utilized SQL to perform advanced aggregations and diagnostic queries, confirming the data inconsistencies found in the EDA phase.

Designed and implemented a robust Star Schema data model in Power BI to create a reliable analytical framework.

Built clean Dimension Tables (Customer Table, Product Table, Calendar) in Power Query to establish a "single source of truth" for all customer, product, and date attributes, resolving all previously identified data quality issues.

Phase 4: Dashboard Development (Power BI)
Developed a suite of four interconnected, interactive dashboards:

Global Sales Overview: High-level view of revenue and geographic performance.

Customer Insights: Deep-dive into customer demographics, loyalty, and value.

Product Performance: Analysis of top-selling products and brands.

Operational Insights: Overview of shipping, payments, and customer feedback.

Authored over 15 DAX measures to create dynamic KPIs for real-time performance tracking.

Key Insights
Identified a strong customer repeat rate of 68.2%, indicating a loyal customer base that drives month-to-month activity.

Uncovered significant data integrity issues in the source data, correcting a 43% over-counting discrepancy in demographic analysis.

Revealed distinct purchasing patterns across regions and customer segments, such as "Grocery" being the top product category in the USA, while "Electronics" leads globally.

Technical Stack
Data Cleaning & Analysis: Python (Pandas, Matplotlib, Seaborn)

Database & Querying: SQLite

Business Intelligence & Visualization: Microsoft Power BI (Power Query, DAX)

Version Control: Git & GitHub
