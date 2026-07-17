# 🍽️ Restaurant Business Performance Analysis

## 📌 Project Overview

This project demonstrates an end-to-end **Business Intelligence and Data Analytics solution** designed to transform raw restaurant transaction data into actionable insights that support strategic decision-making.

The objective was to analyse restaurant performance by identifying key revenue drivers, evaluating menu performance, understanding customer ordering behaviour, and uncovering opportunities to improve operational efficiency and profitability.

The project follows a complete analytics workflow:

**Raw Data → Data Exploration → Data Cleaning → Feature Engineering → Data Modelling → DAX Development → Interactive Dashboard → Business Insights**

By combining **Python-based data preparation** with **Power BI Business Intelligence reporting**, this project demonstrates how raw transactional data can be converted into a scalable analytical solution that supports stakeholder reporting and data-driven decisions.

---

# 🎯 Business Objectives

The analysis was designed to answer key business questions and provide insights into restaurant performance.

## 📈 Analyse Business Performance

- Evaluate overall revenue and sales performance.
- Identify monthly sales trends and changes in demand.
- Understand the main contributors to revenue generation.
- Analyse factors influencing business growth.

## 🍽️ Evaluate Menu & Product Performance

- Identify the highest-performing menu items.
- Analyse revenue contribution by category.
- Compare product demand against revenue generation.
- Highlight opportunities for menu optimisation and promotional strategies.

## 📊 Develop Data-Driven Insights

- Clean, transform and validate raw business data.
- Apply Python, Pandas and analytical techniques to identify trends.
- Build interactive dashboards to communicate findings effectively.
- Translate technical analysis into meaningful business insights.

## 🚀 Support Strategic Decision-Making

- Provide stakeholders with visibility into business performance.
- Identify opportunities to improve profitability and operational efficiency.
- Demonstrate how data can support informed business decisions.

---

# 📊 Interactive Power BI Dashboard

The completed Power BI report provides an interactive view of restaurant performance, including:

- Revenue performance
- Order trends
- Menu item analysis
- Category performance
- Customer ordering behaviour
- Operational insights

> Explore the full interactive dashboard here:  
> [Launch Restaurant Performance Dashboard →](https://app.powerbi.com/view?r=eyJrIjoiYjRkZWMzYzYtMzNjNS00NWY1LWFjMzYtMjE3MDkxMzZiYWQ5IiwidCI6IjNlYTdjMTI4LWM2MDEtNDQ3OS1hMDAzLWUxNGQwMGMwYjVjYiJ9)

## Dashboard Preview

![Executive Overview](Restaurant%20Performance%20-%20Executive%20Overview.png)

![Menu Overview](Restaurant%20Performance%20-%20Menu%20Overview.png)

![Operational Insight](Restaurant%20Performance%20-%20Operational%20Insights.png)

---

📂 Dataset Overview

This analysis uses restaurant transaction data containing order-level purchasing information and menu details, to provide insights into customer purchasing activity, revenue generation, product demand, menu performance, and ordering patterns.

The dataset consists of two linked core tables:

🧾 Order Details Table

Contains transaction-level information for every menu item purchased — each row represents an individual item within a customer order.

Key Fields
Column Description 
order_details_id Unique identifier for each transaction record 
order_id Customer order identifier 
order_date Date the order was placed 
order_time Time the order was placed 
item_id Identifier linking transactions to menu items 

🍔 Menu Items Table

Contains descriptive information required for product-level and revenue analysis.

Key Fields
Column Description 
item_id Unique product identifier 
item_name Menu item name 
category Product category 
price Selling price 

🔍 Data Exploration & Quality Assessment

All initial checks were completed using Python and Pandas, to understand dataset structure, identify quality issues, validate data reliability, and define preparation steps — ensuring all later analysis and reporting is built on accurate, consistent data.

📊 Initial Dataset Profile

• 12,234 total transaction-level records

• 5,370 unique customer orders

• 32 unique menu items
ℹ️ Note: The source data lists individual purchased items rather than full customer orders. All order-based calculations use unique values to avoid overcounting and ensure accurate reporting.
🧪 Quality & Validation Checks

Missing Value Analysis

• 137 missing values in the item_id field

• These correspond to 137 unique orders, equal to ~1.12% of the full dataset

• As item_id is required to link transactions to menu details, these records were removed to preserve analytical accuracy, prevent calculation errors, and maintain data integrity.

Duplicate Validation

✅ No duplicate transaction records found — every entry is unique.

Formatting & Data Type Fixes

All required transformations were applied in one pass:
Column Original Format Transformation Applied Business Purpose 
order_date Stored as text Converted to standard datetime Enable trend analysis, date filtering and time-based calculations 
order_time Unformatted text Converted to standard time format Support peak hour analysis and hourly demand reporting 
item_id Stored as float Converted to integer (after removing incomplete records) Ensure correct relationships between transaction and menu data 

🛠️ Additional Cleaning & Preparation

All work completed in Python and Pandas, producing datasets ready for SQL querying, Power BI modelling and end-to-end business intelligence development.

🧾 Order Details Table

After removing incomplete records, reliability is fully preserved with only 1.12% of the original dataset removed.

🧩 Feature Engineering

New fields added to enable deeper analysis:
New Field Business Use Case 
order_month Track monthly sales and revenue trends 
day_of_week Identify demand patterns across weekdays 
order_hour Pinpoint peak ordering periods 

These support analysis of customer behaviour, revenue trends, demand forecasting, and staffing/resource planning.

🍔 Menu Items Table

Minimal transformation required; full validation confirmed:
✅ No missing values
✅ Correct data types
✅ Valid numerical pricing data
✅ Consistent, standardised column names for modelling
✅ Final Clean Dataset

Ready for integration into your full workflow:
Table Contents 
Order Details Transaction IDs, order references, timestamps, product links, and engineered time/date fields 
Menu Items Product IDs, item names, categories, and pricing 

Fully optimised for Power BI data modelling, DAX calculation, and dashboard development.
# 📊 Power BI Business Intelligence Development

Following data exploration and cleaning in Python, the prepared datasets were imported into Power BI to develop an interactive Business Intelligence solution.

The objective of this stage was to build a scalable analytical model capable of supporting KPI reporting, revenue analysis, operational insights, and stakeholder decision-making.

The development process included:

- Power Query transformations
- Data modelling using a Star Schema
- Relationship design
- DAX measure development
- Interactive dashboard creation
- Business insight generation

---

# 🔄 Power Query Data Preparation

Although the datasets had already been cleaned in Python, Power Query was used to validate and prepare the data before loading it into the reporting layer.

The following transformations were performed:

- Imported the cleaned `orders_cleaned.csv` and `menu_cleaned.csv` datasets.
- Reviewed and validated column data types.
- Confirmed date, time and numerical fields were correctly formatted.
- Standardised datasets for reporting consistency.
- Validated data quality before loading into the Power BI model.

Power Query acted as the final quality assurance stage before analytical modelling.

---

# 🏗️ Data Modelling

A **Star Schema** data model was implemented to separate transactional data from descriptive information.

This modelling approach follows Business Intelligence best practices by improving:

- Report performance
- Data organisation
- Model scalability
- Calculation accuracy
- Ease of maintenance

The final model consisted of one fact table supported by descriptive dimension tables.

---

## 📄 Fact Table — Fact_Sales

The Fact_Sales table contains transaction-level sales data.

### Key Fields

| Column |
|---------|
| `order_details_id` |
| `order_id` |
| `order_date` |
| `order_time` |
| `item_id` |
| `order_month` |
| `day_of_week` |
| `order_hour` |

Each row represents an individual menu item purchased within a customer order.

---

## 📚 Dimension Tables

### Dim_Menu

Contains descriptive product information including:

- Product ID
- Item Name
- Category
- Price

### Dim_Date

Contains date attributes used to support time intelligence and trend analysis across the dashboard.

---

# 🔗 Relationship Design

Relationships were created using the unique product identifier.
Dim_Menu
│
│ 1
│
│
*
Fact_Sales


Relationship:


Dim_Menu[item_id] → Fact_Sales[item_id]


This allows transactional sales data to be analysed by:

- Menu item
- Product category
- Product pricing

while maintaining a clean and efficient reporting model.

The Star Schema design reduces redundancy and improves filtering performance throughout the report.

---

# 📐 DAX Measures & KPI Development

Reusable DAX measures were developed to provide consistent business calculations across every report page.

Creating measures rather than calculated columns improves model efficiency and ensures metrics update dynamically as filters and slicers are applied.

## Revenue Metrics

- Total Revenue
- Monthly Revenue

These measures provide visibility into overall sales performance and monthly trends.

---

## Order Performance

Measures created include:

- Total Orders
- Total Items Sold
- Average Order Value
- Average Items Per Order

These KPIs provide insight into customer purchasing behaviour and overall business performance.

---

## Menu Performance

Additional measures include:

- Average Menu Price
- Total Menu Items
- Total Categories

These measures support product-level analysis and menu optimisation.

---

## Operational Metrics

Operational DAX measures include:

- Peak Ordering Hour
- Busiest Ordering Day
- Active Ordering Hours

These measures provide visibility into customer demand patterns and operational workload.

---

# 📈 Dashboard Development

Three interactive dashboard pages were developed, each designed to answer a different business question and communicate findings through clear data visualisation.

---

# 📊 Executive Overview

The Executive Overview provides stakeholders with a high-level summary of overall business performance.

### Dashboard Features

- KPI Cards
  - Total Revenue
  - Total Orders
  - Average Order Value

- Monthly Revenue Trend

- Revenue by Menu Category

- Top 10 Revenue-Generating Menu Items

- Interactive Month Filtering

### Business Purpose

Provides management with a quick overview of business performance, allowing stakeholders to monitor revenue trends and identify high-performing products.

---

# 🍽️ Menu Performance

The Menu Performance dashboard focuses on evaluating individual products and category performance.

### Dashboard Features

- Menu KPI Cards

- Revenue Contribution by Category

- Top Performing Menu Items

- Product Performance Matrix

- Sales Volume vs Revenue Analysis

### Business Purpose

Supports menu optimisation by identifying products generating the greatest business value while highlighting opportunities for promotional strategies and pricing decisions.

---

# ⏰ Operational Insights

The Operational Insights dashboard focuses on customer ordering behaviour and operational performance.

### Dashboard Features

- Peak Ordering Hour

- Busiest Ordering Day

- Orders by Hour

- Orders by Day

- Day vs Hour Heatmap

### Business Purpose

Provides operational insight into customer demand patterns, helping management make informed staffing, scheduling and resource allocation decisions.

---

# 💡 Business Insights & Recommendations

The completed dashboard transforms transactional restaurant data into meaningful business intelligence by highlighting the key drivers behind business performance.

Key insights include:

- Identification of the highest-performing menu items contributing the greatest revenue.
- Analysis of category-level performance to support menu optimisation.
- Recognition of peak ordering periods to improve staffing and operational planning.
- Identification of customer purchasing trends across different days and times.
- Clear visibility of overall revenue performance through interactive KPI reporting.

### Recommendations

Based on the analysis, the business could:

- Promote high-performing menu items to maximise revenue.
- Review underperforming products for potential menu optimisation.
- Schedule staffing around peak ordering periods to improve operational efficiency.
- Use category performance insights to guide future pricing and promotional strategies.
- Monitor KPIs regularly to support data-driven decision-making.

---

# 🛠️ Tools & Technologies

## Programming & Data Preparation

- Python
- Pandas
- NumPy

## Data Processing

- Data Cleaning
- Data Validation
- Feature Engineering

## Business Intelligence

- Power BI Desktop
- Power Query
- DAX

## Data Modelling

- Star Schema Design
- Relationship Modelling
- Fact & Dimension Tables

## Analytical Techniques

- KPI Development
- Revenue Analysis
- Trend Analysis
- Time Series Analysis
- Business Intelligence Reporting
- Dashboard Design
- Data Visualisation

---

# 🔄 End-to-End Analytics Workflow

The completed project demonstrates a full Business Intelligence pipeline from raw data through to business insight.

Raw Restaurant Data
│
▼
Data Exploration (Python)
│
▼
Data Quality Assessment
│
▼
Data Cleaning & Validation (Python & Pandas)
│
▼
Feature Engineering
│
▼
Power Query Transformation
│
▼
Star Schema Data Model
│
▼
Relationship Design
│
▼
DAX Measure Development
│
▼
Interactive Power BI Dashboard
│
▼
Business Insights & Recommendations


---

# 📌 Project Outcome

This project demonstrates an end-to-end Business Intelligence workflow that transforms raw transactional restaurant data into an interactive reporting solution capable of supporting strategic business decisions.

Using Python for data preparation and Power BI for modelling and visualisation, the project showcases core data analytics competencies including:

- Data exploration
- Data cleaning and validation
- Feature engineering
- Data modelling
- DAX development
- Dashboard design
- KPI reporting
- Business storytelling
- Insight generation
- Stakeholder-focused reporting

The final solution provides an interactive dashboard that enables stakeholders to monitor performance, evaluate menu effectiveness, understand customer behaviour and make informed, data-driven business decisions.
