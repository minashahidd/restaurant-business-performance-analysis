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

# 📂 Dataset Overview

The analysis uses restaurant transaction data containing order-level purchasing information and menu details.

The dataset provides insight into:

- Customer purchasing activity
- Revenue generation
- Product demand
- Menu performance
- Ordering patterns

The dataset consisted of two primary tables:

## 🧾 Order Details Table

The order details table contains transaction-level information for every menu item purchased.

Each row represents an individual item within a customer order.

### Key Fields

| Column | Description |
|---|---|
| `order_details_id` | Unique identifier for each transaction record |
| `order_id` | Customer order identifier |
| `order_date` | Date the order was placed |
| `order_time` | Time the order was placed |
| `item_id` | Identifier linking transactions to menu items |


## 🍔 Menu Items Table

The menu table contains descriptive information required for product-level and revenue analysis.

### Key Fields

| Column | Description |
|---|---|
| `item_id` | Unique product identifier |
| `item_name` | Menu item name |
| `category` | Product category |
| `price` | Selling price |

---

# 🔍 Data Exploration & Quality Assessment

Before developing any reporting solutions, an initial data assessment was performed using **Python and Pandas**.

The purpose of this stage was to:

- Understand the structure of the datasets.
- Identify potential data quality issues.
- Validate the reliability of the information.
- Determine the preparation requirements before analysis.

This ensured that all reporting and calculations were built on accurate and consistent data.


## 📊 Dataset Structure Analysis

Initial exploration identified the following:

- **12,234 transaction-level records**
- **5,370 unique customer orders**
- **32 unique menu items**

The dataset contained individual item transactions rather than complete customer orders.

Therefore, order-based calculations were performed using unique values instead of transaction row counts to ensure accurate business reporting.

## 🧪 Data Quality Assessment
### Missing Value Analysis

A missing value assessment was performed across all columns.

The analysis identified:

137 missing values within the item_id field

Further investigation showed these records represented:

137 unique customer orders
Approximately 1.12% of the dataset

Since item_id was required to connect transactional data with menu information, these records could not accurately contribute towards product-level analysis.

### Cleaning Decision

The affected records were removed during the data cleaning stage to:

Maintain analytical accuracy.
Prevent incorrect product performance calculations.
Preserve the integrity of the data model.

### 🔁 Duplicate Record Validation

A duplicate record assessment was performed to ensure transaction accuracy.

Result:

✅ No duplicate transaction records identified.

This confirmed that each transaction detail represented a unique record within the dataset.

### 🛠️ Data Formatting Assessment

The initial analysis identified several formatting issues requiring transformation.

Column	Issue Identified	Required Transformation
order_date	Stored as text format	Converted into datetime format
order_time	Required formatting for time analysis	Converted into usable time format
item_id	Stored as float due to missing values	Converted into integer after missing records were removed

### 🐍 Data Cleaning & Transformation

Following the initial data assessment, Python and Pandas were used to clean, transform and validate the datasets.

The objective was to create reliable, analysis-ready datasets suitable for:

SQL analysis
Power BI reporting
Data modelling
Business intelligence development

The cleaning process focused on:

Data quality improvement
Data type standardisation
Missing value handling
Feature engineering
Analytical preparation
🧾 Order Details Cleaning

The order details dataset initially contained:

12,234 transaction records

Missing Data Handling

The following steps were performed:

Identified missing values within the item_id column.
Investigated the impact of incomplete records.
Confirmed that missing product identifiers affected:
137 transaction records
137 unique orders
Removed these records because product-level analysis required accurate links between transactions and menu items.
Result:

The dataset was reduced while maintaining analytical reliability.

The removal affected only:

1.12% of the original dataset

Data Type Standardisation

The following transformations were applied:

Date Conversion

Converted:

order_date

from text format into a datetime field.

This enabled:

Monthly trend analysis
Time-based filtering
Date calculations within Power BI
Time Conversion

Converted:

order_time

into a suitable time format.

This supported:

Peak ordering analysis
Hourly demand trends
Operational insights
Identifier Formatting

Converted:

item_id

from float format into integer format after removing incomplete records.

This ensured consistency when creating relationships between:

Transaction data
Menu reference data
⚙️ Feature Engineering

Additional analytical fields were created to support deeper business analysis.

Created Features
Feature	Purpose
order_month	Analyse monthly sales trends
day_of_week	Identify demand patterns by weekday
order_hour	Identify peak ordering periods

These additional fields enabled analysis of:

Customer purchasing behaviour
Revenue trends
Operational demand patterns
Staffing and resource planning opportunities
🍔 Menu Dataset Cleaning

The menu dataset contained:

32 menu items

Due to its smaller size, minimal transformation was required.

Validation checks included:

✅ No missing values identified
✅ Correct data types confirmed
✅ Pricing fields validated for numerical analysis
✅ Column names standardised for data modelling

The final menu table contained:

Menu item names
Product categories
Pricing information
Unique product identifiers
✅ Final Clean Dataset Structure

After cleaning and validation, the datasets were prepared for integration into the Business Intelligence workflow.

Orders Table

Contains:

Transaction identifiers
Customer order identifiers
Order date and time
Product identifiers
Analytical time-based fields
Menu Table

Contains:

Product identifiers
Menu item names
Categories
Pricing information

The cleaned datasets were now ready for:

SQL querying
Power BI modelling
DAX calculations
Dashboard development
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
