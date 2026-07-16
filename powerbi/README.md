# Power BI Data Preparation & Data Modelling

After completing data exploration and cleaning using Python, the cleaned datasets were imported into Power BI for further transformation, modelling and business intelligence development.

The objective of this stage was to create a scalable data model that could support accurate reporting and dashboard analysis.

---

# Power Query Transformation

Power Query was used to validate and prepare the cleaned datasets before building the analytical model.

Transformations performed included:

- Imported cleaned transaction and menu datasets into Power BI.
- Reviewed and validated column data types.
- Ensured date, time and numerical fields were correctly formatted.
- Prepared datasets for relationship modelling.
- Validated data quality before loading into the reporting layer.

---

# Data Model Design

A star schema approach was implemented to separate transactional data from descriptive information.

This structure improves:

- Data organisation
- Report performance
- Scalability
- Accuracy of business calculations

The final model consists of:

## Fact Table — Fact_Sales

Contains transactional-level sales data.

Fields include:

- `order_details_id`
- `order_id`
- `order_date`
- `order_time`
- `item_id`
- `order_month`
- `day_of_week`
- `order_hour`

This table represents individual menu item transactions.

---

## Dimension Table — Dim_Menu

Contains descriptive product information.

Fields include:

- `item_id`
- `item_name`
- `category`
- `price`

This table provides additional context for analysing product performance.

---

# Relationship Design

The tables were connected using a one-to-many relationship:

Dim_Menu
|
| 1
|
*
Fact_Sales


Relationship:

`Dim_Menu[item_id] → Fact_Sales[item_id]`

This allows transaction data to be analysed by:

- Menu item
- Category
- Product pricing

while maintaining a clean and efficient data structure.

---

# Business Intelligence Workflow

The completed workflow demonstrates an end-to-end analytics process:

Raw Data  
↓  
Data Exploration (Python)  
↓  
Data Cleaning & Validation (Python/Pandas)  
↓  
Power Query Transformation  
↓  
Star Schema Data Model  
↓  
DAX Measures & KPI Development  
↓  
Power BI Dashboard & Insights

---

# Tools Used

- Power BI Desktop
- Power Query
- Data Modelling
- Star Schema Design
- Python
- Pandas
- CSV Data Integration

# DAX Measures & KPI Development

To support business reporting, reusable DAX measures were created within Power BI.

Key metrics developed include:

## Revenue Analysis

- Total Revenue
- Monthly Revenue

## Order Performance

- Total Orders
- Total Items Sold
- Average Order Value
- Average Items Per Order

These measures were designed to provide consistent calculations across dashboards and enable interactive business analysis.

## Date Modelling

A dedicated date dimension was created to support accurate time-based analysis and reporting.

The date table enables analysis across:

- Monthly revenue trends
- Day-of-week performance
- Time-based business patterns
- Future time intelligence calculations

The model follows a star schema approach with:

Dim_Date → Fact_Sales
Dim_Menu → Fact_Sales

# 📊 Power BI

Following data validation and cleaning in Python, the prepared datasets were imported into Power BI to develop an interactive Business Intelligence report. The report was built using a structured star schema, DAX measures, and multiple dashboard pages to transform raw restaurant transaction data into actionable business insights.

## Data Preparation

Before visualisation, Power Query was used to prepare the data for analysis by:

* Importing the cleaned `orders_cleaned.csv` and `menu_cleaned.csv` datasets.
* Creating a merged **Fact_Sales** table containing transactional sales data.
* Building separate **Dim_Menu** and **Dim_Date** dimension tables.
* Creating relationships to form a **Star Schema** data model.
* Validating data types and ensuring the model was optimised for reporting.

## Data Model

A Star Schema was implemented to improve report performance and support scalable analysis.

**Fact Table**

* Fact_Sales

**Dimension Tables**

* Dim_Menu
* Dim_Date

This structure enables efficient filtering, cleaner relationships, and follows industry-standard Business Intelligence modelling practices.

## DAX Measures

Reusable measures were created to calculate key business metrics, including:

* Total Revenue
* Total Orders
* Total Items Sold
* Average Order Value
* Average Menu Price
* Total Menu Items
* Total Categories
* Peak Ordering Hour
* Busiest Ordering Day
* Active Ordering Hours

Using DAX measures ensured consistent calculations across all report pages while allowing dynamic filtering through slicers.

## Dashboard Development

Three interactive dashboard pages were developed, each designed to answer a different business question.

### 📈 Executive Overview

Provides a high-level summary of business performance through KPI cards and interactive visualisations.

**Features**

* Revenue KPIs
* Monthly revenue trend
* Revenue by menu category
* Top 10 revenue-generating menu items
* Interactive month filtering

---

### 🍽️ Menu Performance

Focuses on analysing product performance and identifying opportunities for menu optimisation.

**Features**

* Menu KPIs
* Revenue contribution by category
* Top-performing menu items
* Product performance matrix
* Sales volume vs revenue analysis

---

### ⏰ Operational Insights

Analyses customer ordering behaviour to support operational decision-making.

**Features**

* Peak ordering hour
* Busiest ordering day
* Orders by hour
* Orders by day
* Day vs hour heatmap

## Outcome

The final report transforms transactional restaurant data into a clear, interactive dashboard that enables stakeholders to monitor performance, identify revenue drivers, analyse customer ordering behaviour, and support data-driven business decisions.
